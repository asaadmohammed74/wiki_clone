Conquer Online's screen system starts with a square. Despite whatever resolution you set on the client, it will always have the same, fixed square for determining what is and is not in the player's view. Objects in view must be less than or equal to 18 tiles away in both the x and y direction; in contrast, objects not in view are greater than 18 tiles away in either the x or y direction.

### Handling Actors
As an actor moves into the observer's screen, the movement is disregarded and the player is spawned into the screen. This is because TQ Digital's servers handles the player's movement and new position before updating the actor's screen. This flaw is expected by the client. After the actor enters the screen, all additional movements are thereafter sent to the observer. If the actor's new position is out of the screen, do not send the entity removal packet from [MsgAction](Packets/MsgAction); instead, send the movement of the player leaving the screen and they will be removed once their distance from the observer exceeds 18. To recap, entities coming into the screen send the spawn with their new location. Then after, each movement is sent to observers. When they leave the screen, simply send the movement of them leaving and they will disappear from the screen.

### Handling Movement
As the actor moves through their own screen, the client needs to update the chunk they reside in. For each movement verified by the server, send back the movement packet that was received. This will update the boundary location for the client's screen. Then, the new observers are sent to the actor at the updated location. During this process, a rare misstep can occur where an observer is not spawned into the actor's screen. This may be due to distance or additional movement by the observer. To correct this, the client queries the server for the spawn using [MsgAction](Packets/MsgAction).

### Sample Implementation
Below is a sample implementation of a simple screen system in Conquer Online. This screen system and its use can be found in Phoenix, an open-source private server for Conquer Online.

```cs
namespace Phoenix.Structures
{
    using System.Collections.Concurrent;
    using System.Threading.Tasks;
    using Phoenix.Infrastructure;
    using Phoenix.Networking.Packets;
 
    /// <summary>
    /// This class encapsulates the client's screen system. It handles screen objects that the player can currently
    /// see in the client window as they enter, move, and leave the screen. It controls the distribution of packets
    /// to the other players in the screen and adding new objects as the character (the actor) moves. 
    /// </summary>
    public sealed class Screen
    {
        // Ownership Variable Declarations:
        private Client _owner;
 
        // Global-Scope Variable Declarations:
        public ConcurrentDictionary<uint, IScreenObject> Objects;
        public ConcurrentDictionary<uint, IScreenObject> Players;
 
        /// <summary>
        /// This class encapsulates the client's screen system. It handles screen objects that the player can currently
        /// see in the client window as they enter, move, and leave the screen. It controls the distribution of packets
        /// to the other players in the screen and adding new objects as the character (the actor) moves. 
        /// </summary>
        /// <param name="owner">The owner of the screen.</param>
        public Screen(Client owner)
        {
            _owner = owner;
            Players = new ConcurrentDictionary<uint, IScreenObject>();
            Objects = new ConcurrentDictionary<uint, IScreenObject>();
        }
 
        /// <summary>
        /// This method adds the screen object specified in the parameter arguments to the owner's screen. If the 
        /// object already exists in the screen, it will not be added and this method will return false. If the
        /// screen object is being added, and the object is of type character, then the owner will be added to the
        /// observer's screen as well. 
        /// </summary>
        /// <param name="obj">The screen object being added to the owner's screen.</param>
        public bool Add(IScreenObject obj)
        {
            // If the object is a character, add the owner to the observer (if the owner is visible). 
            if (obj.GetType() == typeof(Character))
            {
                // Add observer to the owner's screen.
                return (Players.TryAdd(obj.Identity, obj) && (obj.Owner.Screen != null)
                    && obj.Owner.Screen.Players.TryAdd(_owner.Identity, _owner.Character));
            }
            return this.Objects.TryAdd(obj.Identity, obj);
        }
 
        /// <summary>
        /// This method clears the owner's screen trackers. It does not remove the objects from the screen. The 
        /// delete method is required to delete screen objects.
        /// </summary>
        public void Clear()
        {
            Players = new ConcurrentDictionary<uint, IScreenObject>();
            Objects = new ConcurrentDictionary<uint, IScreenObject>();
        }
 
        /// <summary>
        /// This method deletes a screen object from the owner's screen. It uses the entity removal subtype from
        /// the general action packet to forcefully remove the entity from the owner's screen. It returns false if
        /// the character was never in the owner's screen to begin with.
        /// </summary>
        /// <param name="identity">The identity of the screen object.</param>
        public bool Delete(uint identity)
        {
            IScreenObject observer = null;
            if (Players.TryRemove(identity, out observer) || Objects.TryRemove(identity, out observer))
            {
                _owner.Send(new GeneralAction(identity, 0, 0, 0, GeneralActionType.RemoveEntity));
                return true;
            }
            return false;
        }
 
        /// <summary>
        /// This method removes a screen object from the owner's screen without using force. It will not remove the
        /// spawn. This method is used for characters who are actively removing themselves out of the screen.
        /// </summary>
        /// <param name="identity">The identity of the actor.</param>
        public bool Remove(uint identity)
        {
            IScreenObject obj = null;
            if (Players.TryRemove(identity, out obj))
            {
                // The object is a player. Try to remove the owner from the player's screen as well.
                IScreenObject trash;
                obj.Owner.Screen.Players.TryRemove(_owner.Identity, out trash);
                return true;
            }
            return Objects.TryRemove(identity, out obj);
        }
 
        /// <summary>
        /// This method removes the owner from all observers. It makes use of the delete method (general action 
        /// subtype packet) to forcefully remove the owner from each screen within the owner's screen distance.
        /// </summary>
        public void RemoveFromObservers()
        {
            foreach (IScreenObject observer in Players.Values)
                observer.Owner.Screen.Delete(_owner.Identity);
        }
 
        /// <summary>
        /// This method removes the owner from all observers. It makes use of the delete method (general action 
        /// subtype packet) to forcefully remove the owner from each screen within the owner's screen distance.
        /// It then respawns the character in the observers' screens.
        /// </summary>
        public void RefreshSpawnForObservers()
        {
            foreach (IScreenObject observer in Players.Values)
            {
                observer.Owner.Screen.Delete(_owner.Identity);
                _owner.Character.SendSpawnTo(observer.Owner);
            }
        }
 
        /// <summary>
        /// This method loads the character's surroundings from the owner's current map after a teleportation. It 
        /// iterates through each map object and spawns it to the owner's screen (if the object is within the
        /// owner's screen distance).
        /// </summary>
        public void LoadSurroundings()
        {
            #region Spawn Players
            // Load Players from the Map:
            Parallel.ForEach(_owner.Map.Players.Values, observer =>
            {
                if (((observer.Identity != _owner.Identity) && Calculations.InScreen(
                    observer.Character.X, observer.Character.Y, _owner.Character.X, _owner.Character.Y)) &&
                    Add(observer.Character))
                    _owner.Character.ExchangeSpawnPackets(observer.Character);
            });
            #endregion
        }
 
        /// <summary>
        /// Similarly to the "send to all" method, this method sends a packet to each observing client in the owner's 
        /// screen; however, if the player is invisible, the message packet will be sent, regardless.
        /// </summary>
        /// <param name="packet">The packet for the message being sent.</param>
        public void SendMessage(byte[] packet)
        {
            foreach (IScreenObject observer in Players.Values)
                if (observer != null)
                    observer.Owner.Send(packet);
        }
 
        /// <summary>
        /// This method sends a movement packet to all observers that fall within the owner's new screen distance. It
        /// filters through each player on the map according to screen distance. If the character is within the 
        /// owner's new screen distance, the method will attempt to add the observer to the owner's screen. If the
        /// observer is already in the screen, the owner will send the movement packet to it. If the observer is not
        /// within the new screen distance, the method will attempt to remove it from the owner's screen.
        /// </summary>
        /// <param name="packet">The movement packet being sent.</param>
        public void SendMovement(byte[] packet)
        {
            #region Check Players
            // For each possible observer on the map:
            foreach (Client observer in _owner.Map.Players.Values)
            {
                if (observer.Identity != this._owner.Identity)
                    // If the character is in screen, make sure it's in the owner's screen:
                    if (Calculations.InScreen(observer.Character.X, observer.Character.Y,
                        _owner.Character.X, _owner.Character.Y))
                    {
                        if (Add(observer.Character))
                            _owner.Character.ExchangeSpawnPackets(observer.Character);
                        else observer.Send(packet);
                    }
                    // Else, remove the observer and send the last packet.
                    else if (observer.Screen.Remove(_owner.Identity) || _owner.Screen.Remove(observer.Identity))
                        observer.Send(packet);
            }
            #endregion
        }
 
        /// <summary> This method sends a packet to all observers in the owner's screen. </summary>
        /// <param name="packet">The packet being sent to observers.</param>
        public void SendToAll(byte[] packet)
        {
                foreach (IScreenObject observer in Players.Values)
                    if (observer != null)
                        observer.Owner.Send(packet);
        }
    }
 
    /// <summary> This interface defines a screen object that may or may not have an owner. </summary>
    public interface IScreenObject
    {
        uint Identity { get; set; }  // The unique identifier of the object.
        Client Owner { get; set; }  // The ownership of the object (a player on the server).
        ushort X { get; set; }      // The current X coordinate of the object from the spawn packet.
        ushort Y { get; set; }      // The current y-coordinate of the object from the spawn packet.
 
        /// <summary>
        /// This method defines the spawn method of the object. It may be set by a script or by the server; however,
        /// in the end, it is called to spawn an object to the observer's screen.
        /// </summary>
        /// <param name="observer">The observer the object is being spawned to.</param>
        void SendSpawnTo(Client observer);
    }
}
```
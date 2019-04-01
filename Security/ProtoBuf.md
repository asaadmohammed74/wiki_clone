Google Protocol Buffers are Google's language-neutral, platform-neutral, extensible mechanism for serializing structured data. “You define how you want your data to be structured once, then you can use special generated source code to easily write and read your structured data to and from a variety of data streams and using a variety of languages.” It was implemented in patch 6132. Additional documentation can be found [here](https://developers.google.com/protocol-buffers/).

### Conceptual Example
Using the walk packet structure defined as below and protobuf-net for C# development with Protocol Buffers. Reference to the library can be added through NuGet (right click references and select “Manage NuGet Packages”).

```cs
[ProtoContract]
class WalkPacket
{
    public ushort Length;
    public ushort Identifier;
    [ProtoMember(1, IsRequired=true)]
    public uint Direction;
    [ProtoMember(2, IsRequired=true)]
    public uint Identity;
    [ProtoMember(3, IsRequired=true)]
    public uint MovementType;
    [ProtoMember(4, IsRequired=true)]
    public uint Timestamp;
    [ProtoMember(5, IsRequired=true)]
    public uint MapID;
}
```

Below is an example of serializing and deserializing the message packet (described on this page here) using protobuf-net's serialize and deserialize functions. The buffer variable is assumed to be the byte array representation of the packet structure defined above.

```cs
// Serializing a message:
WalkPacket test = new WalkPacket() { Direction = 1, Identity = 1000000, MapID = 1002, MovementType = 1, Timestamp = (uint)DateTime.Now.Ticks };
using (Stream stream = new MemoryStream())
    Serializer.SerializeWithLengthPrefix(stream, test, PrefixStyle.Fixed32);
 
// Deserializing a message:
WalkPacket result;
using (Stream stream = new MemoryStream(buffer))
    result = Serializer.DeserializeWithLengthPrefix<WalkPacket>(stream, PrefixStyle.Fixed32);
```
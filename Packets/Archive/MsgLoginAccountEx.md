This packet was implemented in the base implementation of their game and server, but was removed before Conquer Online 1.0 Alpha. It can be assumed that this packet was originally drafted as an alternative to [MsgConnect](Packets/MsgConnect) for 91 Game Portal logins. The packet was sent from the client to the game server (containing a mixture of the [MsgAccount](Packets/MsgAccount) packet's content and [MsgConnect](Packets/MsgConnect) packet's content).

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt16 | Packet Length | 136 |
| 2 | UInt16 | Packet Identifier | 1090 |
| 4 | UInt32 | Login Type | 5 |
| 8 | Char[32] | Account | Spirited |
| 40 | Char[32] | Password | test |
| 72 | Char[32] | Server | Meteor |
| 104 | Char[32] | Info (Res.ini) | 0001 |
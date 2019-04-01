This internal packet is sent by TQ Digital Entertainment's NPC server to initialize synchronization between the NPC server and Game server. It is processed similarly to how accounts are processed using [MsgAccount](Packets/MsgAccount) (even processed in the same method but with preprocessor conditions for disabling RC5). The server uses this packet to send the version of the NPC server to the game server, along with an account and password in plain text. 

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt16 | Packet Length | 40 |
| 2 | UInt16 | Packet Identifier | 1002 |
| 4 | UInt32 | Version | 100 |
| 8 | Char[16] | Account | |
| 24 | Char[16] | Password | |
This packet is sent from the game server to the client, and then back again from the client to the game server in a round-trip for checking network congestion. The packet is responsible for the "Warning: the network is congested" message that appears in the top-left of the client screen. It's secondary purpose is for verifying that the user is not a bot (Conquer 1.0 and early Conquer 2.0).

### Patch 5615

| Offset | Type | Description | Example|
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 1012 |
| 4 | UInt32 | Character Identity | 1000000 |
| 8 | UInt32 | Timestamp | 1807831 |
| 12 | Byte[16] | Random Padding | random() |
| 28 | UInt32 | Character Name (2 Bytes) | 56925 |

Notes: The timestamp field requires to be XORed by the Character Identity field before server processing of this packet. The character name (the first two bytes of the character name) has a similar requirement: XORed by 0x9823.

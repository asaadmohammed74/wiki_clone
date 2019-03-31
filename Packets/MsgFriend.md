This packet is sent from the game client to the game server and vise versa to process friend actions. It allows the server to process friend requests, acceptances, and deletions, and allows the client to display friends and enemies in the friends/enemies window. The "Level" parameter in this packet was replaced by the use of the [[MsgFriendInfo]] packet. Facebook incorporation in some (if not all) clients relies on a now broken implementation, and will not function correctly.

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 68 |
| 2 | UInt16 | Type | 1019 |
| 4 | UInt32 | Character Identity | 1000000 |
| 8 | Byte | Action Type | 15 |
| 9 | Byte | Online | 1 |
| 10 | UInt16 | Level (Unreferenced) | 0 |
| 12 | UInt32 | Nobility Rank | 3 |
| 16 | UInt32 | Gender | 1 |
| 20 | Char[16] | Forename | Test |
| 36 | Char[31] | Facebook ID | 123456789012345 |
| 67 | Byte | Null Terminator (client forced) | 0 |

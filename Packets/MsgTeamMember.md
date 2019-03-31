Sent to the game client to add or drop a member on the team. All players on the team should be sent this packet every time a new member joins or leaves. Shows the member in the vertical team member list on the right side of the game window, and in the team members UI on add. 

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 36 |
| 2 | UInt16 | Packet Type | 1026 |
| 5 | Byte | Amount | 1 |
| **for i := 0; i < Amount; i++** |
| 8 + i  | Char[16] | Name | Spirited |
| 24 + i | UInt32 | Identity | 1000001 |
| 28 + i | UInt32 | Mesh | 501002 |
| 32 + i | UInt16 | Max HP | 1024 |
| 34 + i | UInt16 | Current HP | 1024 |

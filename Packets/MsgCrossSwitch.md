After sending this the server receives op 1015:60, reply with 1015:61. Switch guids can be below 4 billion but won't be correct.

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | |
| 2 | UInt16 | Type | 2501 |
| 4 | UInt32 | Switch | 0 = normal, 1 = switch |
| 8 | UInt32 | Original Character Id | 1000001 |
| 12 | UInt32 | Switch Character Id | 1000002 |
| 16 | UInt16 | Item Count | 1 |
| 18 | Foreach Item |
| | UInt32 | Original Item Id | 400 |
| | UInt32 | Switch Item Id | 450 |

**Notes:** sending this the server receives op 1015:60, reply with 1015:61.
Switch guids can be below 4 billion but won't be correct.

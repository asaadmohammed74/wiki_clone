This packet is used to control ground movement of the player. In recent versions there are many different subtypes used rather than the classic Walk-Run types.

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 10 |
| 2 | UInt16 | Type | 1005 |
| 4 | UInt32 | Character ID | 1000001 |
| 8 | Byte | [Directions](Enums/Directions) | 1 |
| 9 | Byte | [Movement Type](Enums/MsgWalk Type) | MovementType.Walk |

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 24 |
| 2 | UInt16 | Type | 10005 |
| 4 | UInt32 | [Directions](Enums/Directions) | 1 |
| 8 | UInt32 | Character ID | 1000001 |
| 12 | UInt32 | [Movement Type](Enums/MsgWalk Type) | MovementType.Walk |
| 16 | UInt32 | Timestamp | 123123 |
| 20 | UInt32 | Map ID | 1002 |

### Patch 6132

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 24 |
| 2 | UInt16 | Type | 10005 |
| Google Protocol Buffer (Offsets 4 - 20) |
| 4 | UInt32 | [Directions](Enums/Directions) | 1 |
| 8 | UInt32 | Character ID | 1000001 |
| 12 | UInt32 | [Movement Type](Enums/MsgWalk Type) | MovementType.Walk |
| 16 | UInt32 | Timestamp | 123123 |
| 20 | UInt32 | Map ID | 1002 |

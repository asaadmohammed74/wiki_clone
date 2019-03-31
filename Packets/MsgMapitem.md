This packet is sent from the game server to the game client to inform it of an item being added/removed from the map floor. it is also sent from the game client to the game server to request that an item be picked up.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Item Identity | 123 |
| 8 | UInt32 | Item Type | 500329 |
| 12 | UInt16 | X | 400 |
| 14 | UInt16 | Y | 400 |
| 16 | UInt16 | Color | 5 |
| 18 | UInt16 | Action | GroundItemAction.Pick |

### Patch 6719

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Timestamp |  |
| 8 | UInt32 | Item Identity | 123 |
| 12 | UInt32 | Item Type | 500329 |
| 16 | UInt16 | X | 400 |
| 18 | UInt16 | Y | 400 |
| 20 | UInt16 | Color | 5 |
| 22 | UInt16 | Action | GroundItemAction.Pick |

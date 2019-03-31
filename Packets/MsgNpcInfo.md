This packet is used to spawn NPCs to players.

### Patch 5065

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 20 |
| 2 | UInt16 | Type | 2030 |
| 4 | UInt32 | UniqueID | 123123 |
| 8 | UInt16 | X | 100 |
| 10 | UInt16 | Y | 100 |
| 12 | UInt16 | Lookface | 100 |
| 14 | UInt16 | NpcType | 2 |
| 16 | UInt16 | RoleType | 2 |
| 18 | String[] | Names | 0 |

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2030|
| 4 | UInt32 | UniqueID | 123123 |
| 8 | UInt32 | StaticID | 123123 |
| 12 | UInt16 | X | 100 |
| 14 | UInt16 | Y | 100 |
| 16 | UInt16 | Lookface | 100 |
| 18 | UInt16 | NpcType | 2 |
| 20 | UInt16 | RoleType | 2 |
| 22 | String[] | Names | 0 |

This packet is sent from the game server to the game client to set a character's proficiency with a specific weapon type.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Weapon Type | 480 |
| 8 | UInt32 | Level | 19 |
| 12 | UInt32 | Experience | 10000 |
| 16 | UInt32 | Experience Required | 2100000000 |

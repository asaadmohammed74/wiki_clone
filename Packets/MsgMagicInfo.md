This packet is sent from the game server to the game client to add a spell or set its level.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Experience | 100 |
| 8 | UInt16 | Spell Type | 1000 |
| 10 | UInt16 | Level | 1 |

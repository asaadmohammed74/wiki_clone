This packet is sent from the game client to the game server. It is used to add a gem to an empty socket, or remove a gem that is already embedded.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Sender Identity | 1000000 |
| 8 | UInt32 | Item Identity | 123 |
| 12 | UInt32 | Gem Identity | 321 |
| 16 | UInt16 | Location | 1 |
| 18 | UInt16 | Action | 0 or 1 |

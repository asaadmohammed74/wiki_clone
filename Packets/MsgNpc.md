This packet is used to interact with a NPC and contains multiple DialogAction types

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 16 |
| 2 | UInt16 | Type | 2031 |
| 4 | UInt32 | Id | 123123 |
| 8 | UInt32 | Data | 10 |
| 12 | NpcActionType | Action | NpcAction.Activate |
| 14 | UInt16 | Sort | 0 |

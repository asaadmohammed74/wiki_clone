This packet is used to list or change a player's title.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 20+TitleCount|
| 2 | UInt16 | Type | 1130 |
| 4 | UInt32 | TitleType | 11|
| 8 | UInt32 | Action | 3 |
| 12 | Byte | TitleCount | 1 |
| 13 | TitleType[] | Titles | 11 |

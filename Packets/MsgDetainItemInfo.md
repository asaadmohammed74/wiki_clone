This packet is sent to fill the detained items window.

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 112 |
| 2 | UInt16 | Type | 10014 |
| 4 | UInt32 | Detain Identity | 103 |
| 8 | UInt32 | Item Identity | 54646 |
| 12 | UInt32 | Item Type | 410339 |
| 16 | UInt16 | Durability | 7099 |
| 18 | UInt16 | Maximum Durability | 7099 |
| 20 | UInt16 | Detain Mode | 1 |
| 24 | UInt32 | Socket Progress | 1000 |
| 28 | Byte | Socket One | 13 |
| 29 | Byte | Socket Two | 13 |
| 30 | Byte | Item Effect | 200 |
| 32 | Byte | Plus | 12 |
| 33 | Byte | Blessing | 7 |
| 34 | Byte | Bound | 0 |
| 35 | Byte | Enchantment | 252 |
| 40 | Byte | Suspicious | 0 |
| 42 | Byte | Locked | 0 |
| 44 | Byte | Item Color | 3 |
| 48 | UInt32 | Character Identity | 1000002 |
| 52 | STRING | Character Name | Length16String12 |
| 68 | UInt32 | Target Identity | 1000003 |
| 72 | STRING | Target Name | szHunterOrTarget |
| 88 | UInt32 | Capture Date | 20161001 |
| 96 | UInt32 | CPs Cost | 1950 |
| 100 | Byte | Expired | 1 |
| 108 | UINT | Days Left | 6 |

**Note:** The character name is the player who is viewing the item and the target is the hunter or who lost the equip.

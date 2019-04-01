This packet is sent server>client to add or update the attributes of a specific item.

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 44|
| 2 | UInt16 | Type | 1008|
| 4 | UInt32 | UniqueID | 1 |
| 8 | UInt32 | [ItemType ID](Systems/Item Archetype) | 730001 |
| 12 | UInt16 | Durability | 10000 |
| 14 | UInt16 | MaxDurability | 10000 |
| 16 | UInt16 | [Action Type](Enums/MsgItemInfo Type) | 1 |
| 18 | Byte | Location| 0 |
| 19 | Byte | Unknown | 0 |
| 20 | UInt32 | Unknown | 0 |
| 24 | Byte | Gem1 | 13 |
| 25 | Byte | Gem2 | 13 |
| 26 | Byte | RebornEffect | 200 |
| 27 | Byte | Unknown | 0 |
| 28 | Byte | Plus | 9 |
| 29 | Byte | Bless | 7 |
| 30 | Byte | Enchant | 255 |
| 31 | Byte | Unknown | 0 |
| 32 | UInt32 | RestrainType | 0 |
| 36 | UInt32 | Unknown | 0 |
| 40 | UInt32 | Unknown | 0 |

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length |  |
| 2 | UInt16 | Type | 1008 |
| 4 | UInt32 | User ID | 1000001 |
| 8 | UInt32 | [ItemType ID](Systems/Item Archetype) | ‭132003‬ |
| 12 | UInt16 | Durability | ‭1095 |
| 14 | UInt16 | Max Durability | ‭1099 |
| 16 | UInt16 | [Action Type](Enums/MsgItemInfo Type) | 1 |
| 18 | UInt16 | Position | 3 |
| 20 | UInt32 | Socket Progress | 0 |
| 24 | Byte | Socket 1 | 0 |
| 25 | Byte | Socket 2 | 0 |
| 28 | UInt16 | RebornEffect | 0 |
| 33 | Byte | Plus | 0 |
| 34 | Byte | Blessed Dmg / Steed Red | 0 |
| 35 | BOOL | Bound | false |
| 36 | Byte | Enchanted HP / Steed Green | 0 |
| 40 | Byte | Refinery / Steed Blue | 0 |
| 44 | BOOL | Shadiness | false |
| 46 | BOOL | Locked | false |
| 48 | UInt32 | Color | 3 |
| 52 | UInt32 | LevExp Progress | 0 |
| 56 | UInt32 | Syndicate ID | 0 |
| 60 | UInt32 | Delete Time | 0 |
| 64 | UInt32 | Stack | 1 |

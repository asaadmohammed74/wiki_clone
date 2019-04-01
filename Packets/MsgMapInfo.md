This packet is sent from the game server to the game client to set game map rules and details. The packet may be used to set game map rules, such as no-pk and no-jump. It may also be used to create dynamic map copies of static maps, or static copies of static maps. The game identity comes from GameMap.dat. The unique map identity will be the same as the game map identity if the map is static (not a copy).

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 16 |
| 2 | UInt16 | Type | 1110 |
| 4 | UInt32 | Unique Map Id | 1002 |
| 8 | UInt32 | Game Map Id | 1002 |
| 12 | UInt32 | [Rule Flags](Enums/MsgMapInfo Rule) | 0 |

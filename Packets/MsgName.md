This packet is a variable length packet sent between the client and game server to request, set and modify certain strings (such as spouse name). It can also be used to display client assets in game (effects, sounds, etc)


### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 13 + totalStringLength |
| 2 | UInt16 | Type | 1015|
| 4 | UInt32 | Data | 1000001 |
| 8 | StringType| Action | StringType.Mate |
| 9 | NetStringPacker| Strings | 1 5 Booty |

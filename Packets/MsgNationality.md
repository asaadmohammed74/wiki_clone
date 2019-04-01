This packet is sent to the game client to update the player's country flag. The country flag appears near players' names after patch 5639. Strings must match a preset from a dictionary of countries names, found in Nationality.ini.

### Patch 6150

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 10 |
| 2 | UInt16 | Type | 2430 |
| 4 | UInt32 | Player ID | 11111111111 |
| 8 | Byte | [Country ID](Enums/MsgNationality Country) | 10 |

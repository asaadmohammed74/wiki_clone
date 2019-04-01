This packet is used to place an advertisement for your guild.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 338 |
| 2 | UInt16 | Type | 2225 |
| 4 | UInt32 | Id | 1000001 |
| 8 | Char[256] | Description | "Join us for cookies!" |
| 264 | UInt64 | Amount | 500000 |
| 272 | UInt16 | IsAutoRecruit | 1 |
| 274 | UInt16 | LevelRequirement | 120 |
| 276 | UInt16 | RebornRequirement | 1 |
| 278 | UInt16 | ClassForbid [Flag] | 0 |
| 280 | UInt16 | GenderForbid [Flag] | 0 |
| 282 | UInt16 | UnknownValue | 0 |

**Note:** the class/gender forbid is a bit flag and lists professions and genders >NOT< permitted to join through the advertisements.

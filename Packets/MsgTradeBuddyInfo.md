This packet is used to list information regarding trade partners. For actions related to adding/removing trade partners, reference [MsgTradeBuddy](Packets/MsgTradeBuddy).

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 34 |
| 2 | UInt16 | Type | 2046|
| 4 | UInt32 | Id | 123123 |
| 8 | UInt32 | Lookface | 1 |
| 12 | Byte| Level | 130 |
| 13 | Byte| Profession| 15 |
| 14 | UInt16 | PKPoints| 0 |
| 16 | UInt32  | GuildID| 0 |
| 20 | UInt32  | GuildRank| 0 |
| 24 | UInt16 | Unknown | 0 |
| 26 | Byte[16] | Name | “Pro4Never ” |
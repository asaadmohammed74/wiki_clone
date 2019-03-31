This packet is used to send requests relating to the trade partner system and contains multiple TradePartnerAction types

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2046|
| 4 | UInt32 | Id | 123123 |
| 8 | Byte | Action | 1|
| 9 | Bool | IsOnline| 1|
| 10 | UInt32 | HoursLeft | 0 |
| 14| UInt16 | Unknown | 0 |
| 16 | Byte[16] | Name| "Pro4Never       " |

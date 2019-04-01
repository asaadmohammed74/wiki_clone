This packet is used to interact with a NPC and contains multiple DialogAction types

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 12 + Strings.TotalLength |
| 2 | UInt16 | Type | 2032 |
| 4 | UInt32 | Id | 123123 |
| 8 | UInt16 | Avatar | 10 |
| 10 | Byte | OptionId | 0 |
| 11 | Byte | [Action](Enums/MsgTaskDialog Action) | DialogActionType.Text |
| 12 | NetStringPacker | Strings | 1 5 Hello |

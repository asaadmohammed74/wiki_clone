This packet is used to request and control player Broadcasts.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 12 + Strings.TotalLength |
| 2 | UInt16 | Type | 2050 |
| 4 | UInt32 | [Action](Enums/MsgPigeon Action) | BroadcastActionType.SendBroadcast |
| 8 | UInt32 | MessageId | 0 |
| 12 | NerStringPacker | Strings  | 1 5 Hello |

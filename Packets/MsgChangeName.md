This packet is used to handle the name change interface which TQ added in newer versions of conquer (around patch 5400)

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 26 |
| 2 | UInt16 | Type | 2080 |
| 4 | UInt16 | [Action](Enums/MsgChangeName Action) | NameChangeType.Request |
| 6 | UInt16 | EditsCount | 1 |
| 8 | UInt16 | EditsAllowed | 1 |
| 10 | Char[16] | Name | Pro4Never |

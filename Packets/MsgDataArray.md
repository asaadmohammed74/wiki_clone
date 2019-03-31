This packet is used to send a list of ItemIds to be used in systems such as composition or breeding.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 24 |
| 2 | UInt16 | Type | 2036 |
| 4 | DataArrayActionType | Action | DataArrayActionType.Compose |
| 5 | [INT32[]] | Items | 2 111 112  |

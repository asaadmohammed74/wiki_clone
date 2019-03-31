This packet is used to request and confirm many types of interactions such as attacking, casting spells or even proposing. It is worth noting that InteractType.Magic is hashed using the character ID/Timestamp values.

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 30 |
| 2 | UInt16 | Type | 1022 |
| 4 | UInt32 | Timestamp | 123123 |
| 8 | UInt32 | SenderId | 1000001 |
| 12 | UInt32 | TargetId | 1000002 |
| 16 | UInt16 | X | 400 |
| 18 | UInt16 | Y | 450 |
| 20 | InteractType | Action | InteractType.Shoot |
| 22 | UInt32 | Effect | 1 |
| 26 | UInt32 | ReturnedEffect | 0 |

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 38 |
| 2 | UInt16 | Type | 1022 |
| 4 | UInt32 | Timestamp | 123123 |
| 8 | UInt32 | SenderId | 1000001 |
| 12 | UInt32 | TargetId | 1000002 |
| 16 | UInt16 | X | 400 |
| 18 | UInt16 | Y | 450 |
| 20 | InteractType | Action | InteractType.Shoot |
| 22 | UInt32 | Effect | 1 |
| 26 | UInt32 | ReturnedEffect | 0 |
| 30 | ActivationFlag | Activation | Activation.CriticalStrike |
| 34 | UInt32 | ActivationEffect | 0 |

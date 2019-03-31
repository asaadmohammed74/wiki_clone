Updates the client screen with new status and data and also some character data to players on the screen.

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 40 |
| 2 | UInt16 | Type | 10017 |
| 4 | UInt32 | Identity | 1000002 |
| 8 | UInt32 | Update Count | 1 |
| 12 | UInt32 | Update Type | 1 |
| 16 | UInt64 | Value | 13500 |

**Note:** On some types you can send two UInt32 instead of one UInt64.

### Patch 5672

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 36 |
| 2 | UInt16 | Type | 10017 |
| 4 | UInt32 | User ID | 1000002 |
| 8 | UInt32 | Update Count | 1 |
| 12 | UInt32 | Update Type | 1 |
| 16 | UInt64 | Value 1 | 13500 |
| 24 | UInt64 | Value 2 | 0 |
| 32 | UInt32 | Value 3 | 0 |

**Note:** You may bundle updates together using "Update Count" and appending additional update data to the end of the packet structure. For double experience, Value 1 will be zero and Value 2 will be the exp value multiplied by 100.


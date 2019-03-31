Sent on login to display the last login time dialog box upon login. Shows an alert to the player if their account was previously logged into from another IP address. 

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 12 |
| 2 | UInt16 | Type | 2078 |
| 4 | UInt32 | UTC Timestamp | 0 |
| 9 | Bool | Different IP | 1 |

Timestamp = second + (60 * minute) + (3600 * (32 + hour)) + (86400 * daysdiff)
daysdiff = current total days - min total days (min: 1/1/1970 UTC)

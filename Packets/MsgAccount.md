This packet is sent during the client's authentication state. It's sent to the account server so that the password exchange can begin. It contains the account name and server from the client's input.

### Patch 4330

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 52 |
| 2 | UInt16 | Type | 1051 |
| 4 | Char[16] | Account Name | TestAccount |
| 20 | Char[16] | Account Password | RC5(MyPassword) |
| 36 | Char[16] | Server Name | Meteor |

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 276 |
| 2 | UInt16 | Type | 1086 |
| 4 | Char[16] | Account Name | TestAccount |
| 132 | Char[16] | Account Password | RC5(MyPassword) |
| 260 | Char[16] | Server Name | Meteor |

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 240 |
| 2 | UInt16 | Type | 1124 |
| 8 | Char[128] | Account Name | TestAccount |
| 136 | Char[16] | Server Name | Meteor |

**Notes:** Offsets 4, 152-224, and 232-239 are manually set to zero in the client. Offset 225 is never set, and could contain random data.

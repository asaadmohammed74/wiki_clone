This packet is created by the client after it processes the Res.dat.

**Security Warning**: The identity and additional data fields are passed from the account server; therefore, it is expected that the account server encrypts this information before sending it to the client. 

### Patch 4330

Account Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | File Contents | 10 |
| 12| Char[16] | File Name | Res.dat |

Game Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | Additional Data | 2 |
| 12 | Char[4] | Client Build Version | 117 |
| 16 | Char[12] | Language | English |

### Patch 5017

Account Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | File Contents | 10 |
| 12| Char[16] | File Name | Res.dat |

Game Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | Additional Data | 2 |
| 12 | UInt16 | Client Build Version | 123 |
| 14 | Char[10] | Language | En |
| 24 | UInt32 | File Contents | 10 |

### Patch 5615

Account Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | File Contents | 10 |
| 12| Char[16] | File Name | Res.dat |

Game Server:

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 |
| 2 | UInt16 | Type | 1052 |
| 4 | UInt32 | Client Identity | 1000000 |
| 8 | UInt32 | Additional Data | 2 |
| 12 | UInt16 | Client Build Version | 130 |
| 14 | Char[2] | Language | En |
| 16 | Byte[6] | Mac Address | 0A, 0B, 0C, 0D, 0E, 0F |
| 24 | UInt32 | Res.dat Contents | 10 |

Notes: The client does not write to offsets 22 and 23. It is possible that if the mac address cannot be retrieved that the Mac Address field will be zero or spell "LOOP" in ASCII for "loopback adapter".

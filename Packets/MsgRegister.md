This packet is sent from the game client to the game server. It contains initial character information from the character creation screen, such as the name, body type, profession, and mac address. This information needs to be verified with the server to ensure that the name is not taken and contains valid characters, and that the body and profession are valid.

### Patch 4330

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 60 |
| 2 | UInt16 | Type | 1001 |
| 4 | Char[16] | Account | Spirited |
| 20 | Char[16] | Name | Test |
| 36 | Char[16] | Password (yes, really) | test |
| 52 | UInt16 | Model | 1003 |
| 54 | UInt16 | Class | 10 |
| 56 | UInt32 | Identity | 1000000 |

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 60 |
| 2 | UInt16 | Type | 1001 |
| 4 | Char[16] | Account | Spirited |
| 20 | Char[16] | Name | Test |
| 36 | Char[16] | Masked Password | **** |
| 52 | UInt16 | Model | 1003 |
| 54 | UInt16 | Class | 10 |
| 56 | UInt32 | Identity | 1000000 |

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 104 |
| 2 | UInt16 | Type | 1001 |
| 20 | Char[16] | Character Name | TestPlayer |
| 52 | UInt16 | Character Body | 1003 |
| 54 | UInt16 | Character Class | 10 |
| 56 | UInt32 | Character Identity | 1000000 |
| 60 | UInt16[6] | Client MacAddress | 00,10,5A,44,12,B5 |

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 124 |
| 2 | UInt16 | Type | 1001 |
| 4 | UInt32 | Cancel | 0 |
| 8 | Char[16] | Account Name _(Unused)_ | |
| 24 | Char[16] | Forename | Test |
| 40 | Char[16] | Surname _(Unused)_ | |
| 56 | Char[16] | Password _(Unused)_ | |
| 72 | UInt16 | Character Body | 1003 |
| 74 | UInt16 | Character Class | 10 |
| 76 | UInt32 | Character Identity | 1000000 |
| 80 | Char[12] | Client MacAddress | 0A0027000000 |

The rest of this packet is confirmed empty space (32 bytes).

All "unused" fields are now not implemented in the client.

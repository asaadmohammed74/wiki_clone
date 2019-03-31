This packet is used to control and verify many different types of actions between the game client and game server. It contains the ID of an entity performing the action, a type of action being performed and a variable amount of information, often with various fields being used.

It is worth noting that it is very common for each 'Data' field to be broken into 2 UInt16 accessors to set 'high' and 'low' values.

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 24 |
| 2 | UInt16 | Type | 1010 |
| 4 | UInt32 | Client Timestamp | 123123 |
| 8 | UInt32 | Character ID | 1000001 |
| 12 | UInt32 | Data1 | 321 |
| 16 | UInt32 | Data2 | 123 |
| 20 | UInt16 | Direction | 1 |
| 22 | ActionType | Action | 137 |

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 10010 |
| 8 | UInt32 | Character ID | 1000001 |
| 12 | UInt32 | Data1 | 321 |
| 16 | UInt32 | Client Timestamp | 123123 |
| 20 | ActionType | Action | 137 |
| 22 | UInt16 | Direction | 1 |
| 24 | UInt32 | Data2 | 123 |
| 28 | UInt32 | Data3 | 123 |

### Patch 5212

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 42 |
| 2 | UInt16 | Type | 10010 |
| 8 | UInt32 | Character ID | 1000001 |
| 12 | UInt32 | Data1 | 321 |
| 16 | UInt32 | Data2 | 321 |
| 20 | UInt32 | Client Timestamp | 123123 |
| 24 | ActionType | Action | 137 |
| 26 | UInt16 | Direction | 1 |
| 30 | UInt32 | Data3 | 123 |
| 34 | UInt32 | Data4 | 123 |
| 38 | UInt32 | Data5 | 123 |

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 38 |
| 2 | UInt16 | Type | 10010 |
| 4 | UInt32 | Character Identity | 1000000 |
| 8 | UInt32 | Action Data | 321 |
| 12 | UInt32 | Action Details | 321 |
| 16 | UInt32 | Client Timestamp | 123123 |
| 20 | ActionType | Action Type | 137 |
| 22 | UInt16 | Direction | 0 |
| 24 | UInt16 | X | 400 |
| 26 | UInt16 | Y | 400 |
| 28 | UInt32 | Map | 1002 |
| 32 | UInt16 | Color | 0 |
| 36 | Bool | Mounted Flag | 0 |
| 37 | Bool | Action Response Flag | 0 |

This packet is used to record and teleport to previous locations using the MemoryAgate

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 28 + Count * 48 + 8 |
| 2 | UInt16 | Type | 2110|
| 4 | UInt32 | Action | 1 |
| 8 | UInt32 | ItemId | 100 |
| 12 | UInt32 | Unknown12 | 0 |
| 16 | UInt32 | Unknown16 | 0|
| 20 | UInt32 | Unknown20 | 0|
| 24 | UInt32 | Durability | 20|
| 28 | UInt32 | Locations Count | 1 |
| 32 | AgateLocation[] | Locations | 1 1002 440 400 etc|


Each Location consists of 48 bytes of data in the following format

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt32 | Id | 1 |
| 4 | UInt32 | Map | 1002 |
| 8 | UInt32 | X | 440 |
| 12 | UInt32 | Y | 400 |
| 16 | UInt32 | Unknown| 0 |
| 20 | UInt32 | Unknown | 0 |
| 24 | UInt32 | Unknown | 0 |
| 28 | UInt32 | Unknown | 0 |
| 32 | UInt32 | Unknown | 0 |
| 36 | UInt32 | Unknown | 0 |
| 40 | UInt32 | Unknown | 0 |
| 44 | UInt32 | Unknown | 0 |
| 48 | UInt32 | Unknown | 0 |

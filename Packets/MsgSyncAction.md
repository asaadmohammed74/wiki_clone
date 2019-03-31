This packet is used to send synchronized player actions with other players. This is used for the interactions system for sending synchronized walking and jumping animations to the clients.

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 24 |
| 2 | UInt16 | Type | 1114 |
| 4 | UInt16 | MsgSyncAction Type | 1 |
| 6 | UInt16 | X | 400 |
| 8 | UInt16 | Y | 400 |
| 12 | UInt32 | Amount | 2 |
| 16 | UInt32 | Actor Identity | 1000001 |
| 20 | UInt32 | Target Identity | 1000002 |

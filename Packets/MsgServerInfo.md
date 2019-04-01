This packet is sent between the game server and client to set client-side rules in regards to "Conquer Online 2.0" gameplay vs. "Conquer Online Classic" gameplay. The packet was first introduced with the classic servers to instruct the client on when and if to show the shopping mall and how player potency was calculated.

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 12 |
| 2 | UInt16 | Type | 2079 |
| 4 | UInt32 | Server Type | 0 |
| 8 | UInt32 | Potency Type | 0 |

**Notice:** For the server and potency types above, 

0 = Standard Conquer Online 2.0 Server

1 = Classic Conquer Online 2.0 Server

This packet is sent between the client and game server. It contains reward information for the player's contribution to helping apprentice players.

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 40 |
| 2 | UInt16 | Type | 2067 |
| 4 | UInt32 | Packet Type | 5 |
| 8 | UInt32 | User Identity | 1000000 |
| 24 | UInt64 | Prize Experience | 600 |
| 32 | UInt16 | Prize Heaven Blessing | 3 |
| 34 | UInt16 | Prize Composing | 200 |

**Notes:** 600 Experience is 1 ExpBall, Heaven Blessing is per hour and Composing 100 is 1.

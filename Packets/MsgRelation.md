This packet is sent from the game server to the game client in newer client versions when sending requests. It is used to display relation data as well as battle power and level to verify a target's identity.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Sender Identity | 1000000 |
| 8 | UInt32 | Target Identity | 1000001 |
| 12 | UInt32 | Level | 130 |
| 16 | UInt32 | BattlePower | 155 |
| 20 | UInt32 | IsSpouse | 0 |
| 24 | UInt32 | IsApprentice | 0 |
| 28 | UInt32 | IsTradePartner | 0 |

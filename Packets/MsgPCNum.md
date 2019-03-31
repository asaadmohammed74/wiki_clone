This packet is sent during the client's authentication state. It's sent to the account server after the [[MsgConnectEx]] packet has been processed by the client. The packet contains the player's mac address for successful login recording.

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 52 |
| 2 | UInt16 | Type | 1100 |
| 4 | UInt32 | Account Identity | 1000000 |
| 8 | Char[40] | Mac Address | 0A0B0C0D0E0F |
Notes: Client forces null terminator at offset 48 (byte). No other information is written to the packet past offset 48. If the mac address could not be retrieved, the mac address field will not be assigned.

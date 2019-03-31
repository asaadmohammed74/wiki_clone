This packet is sent from the game server to the client for invoking weather on a map. This packet must be sent when the player changes maps; otherwise, the weather will be cleared by the client. 

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 20 |
| 2 | UInt16 | Type | 1016 |
| 4 | UInt32 | Weather Type | 2 |
| 8 | UInt32 | Intensity (Range: 0 - 999) | 50 |
| 12 | UInt32 | Direction (Range: 0 - 359) | 14 |
| 16 | UInt32 | Color in ARGB (Default: 0x00FFFFFF) | 0xFFFFFF00 |
Notes: This example produces a light rain shower.

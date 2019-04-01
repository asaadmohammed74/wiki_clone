This packet is sent by the game server to the client to request a polite disconnect. Sending this packet to the client causes an error state for terminating the server connection, and spawns a message stating that the game server was shutdown. The packet has very little processing in the client; therefore, all offsets and uses for this packet are currently unknown.

### Patch 5615

Untested.

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (Assummed) | 12 |
| 2 | UInt16 | Type | 1350 |
| 4 | UInt32 | Action (client only accepts 0) | 0 |
| 8 | UInt32 | Message ID (client only accepts 10) | 10 |

Notes: The packet length is unchecked by the client.

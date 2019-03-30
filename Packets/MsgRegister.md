Sent to the game server from the client to request character creation. The character creation screen can be brought up via the [msgtalk](msgtalk) packet. More details available on that packet's page. Character information should be validated and other characteristics should be randomly generated before being saved to the database.

### Patch 4330
| Offset | Type     | Description | Example |
|--------|----------|-------------|---------|
| 0      | UInt16   | Length      | 60      |
| 2      | UInt16   | Type        | 1001    |
| 4      | UInt16   | Type        | 1001    |

... This is only a test
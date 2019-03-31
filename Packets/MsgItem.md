MsgItem is sent from the game client to the game server. Item actions, market interface actions, and some interface updates are handled through this packet. Ping response is handled through this packet.

### Patch 4330

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 20 |
| 2 | UInt16 | Type | 1009 |
| 4 | UInt32 | Identity | 1000001 |
| 8 | UInt32 | Argument| 0 |
| 12 | UInt32 | Action | 27 |
| 16 | UInt32 | Timestamp | 42351641 |

### Patch 5672

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 20 |
| 2 | UInt16 | Type | 1009 |
| 4 | UInt32 | Identity | 1000001 |
| 8 | UInt32 | Data Param1 | 0 |
| 12 | UInt32 | Action | 27 |
| 16 | UInt32 | Timestamp | 42351641 |
| 20 | UInt32 | Count | 0 |
| 24 | UInt32 | Data Param2 | 1 |
| 28 | UInt32 | Data Param3 | 0 |

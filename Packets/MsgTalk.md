This packet is sent between the game client and server to exchange messages. The messages are used to control the client during login to the game server, and to socialize with other players on the server. The packet includes player [meshes](Systems/Mesh) in patches 5017 and higher for private whisper windows. Suffix is used for offline messages, and usually contains the date in the format yyyyMMdd.

### Patch 4330

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (20 + Len(Sender, Recipient, Suffix, Message)) | 43 |
| 2 | UInt16 | Packet Type | 1004 |
| 4 | UInt32 | Color in ARGB | 00FF0000 |
| 8 | UInt16 | [Tone](Enums/MsgTalk Tone) | 2101 |
| 10 | UInt16 | [Style Flags](Enums/MsgTalk Style) | 0 |
| 12 | UInt32 | Identity | 1000000 |
| 16 | Byte | String List Count | 4 |
|  | Byte | Sender's Name Length | 6 |
|  | Char[] | Sender's Name | SYSTEM |
|  | Byte | Recipient's Name Length | 8 |
|  | Char[] | Recipient's Name | ALLUSERS |
|  | Byte | Suffix Length | 0 |
|  | Char[] | Suffix | |
|  | Byte | Message Length | 8 |
|  | Char[] | Message | NEW_ROLE |

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (28 + Length from Sender's Name, Recipient's Name, Suffix, and Message) | 61 |
| 2 | UInt16 | Packet Type | 1004 |
| 4 | UInt32 | Text Color in ARGB | 00FF0000 |
| 8 | UInt16 | [Tone](Enums/MsgTalk Tone) | 2000 |
| 10 | UInt16 | [Style Flags](Enums/MsgTalk Style) | 0 |
| 12 | UInt32 | Sender's Identity | 1000000 |
| 16 | UInt32 | Recipient's [Mesh](Systems/Mesh) | 501002 |
| 20 | UInt32 | Sender's [Mesh](Systems/Mesh) | 501002 |
| 24 | Byte | String List Count | 4 |
|  | Byte | Sender's Name Length | 7 |
|  | Char[] | Sender's Name | Player1 |
|  | Byte | Recipient's Name Length | 7 |
|  | Char[] | Recipient's Name | Player2 |
|  | Byte | Suffix Length | 8 |
|  | Char[] | Suffix | 20140518 |
|  | Byte | Message Length | 11 |
|  | Char[] | Message | Hello world |

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (31 + Length from Sender's Name, Recipient's Name, Suffix, and Message) | 63 |
| 2 | UInt16 | Packet Type | 1004 |
| 4 | UInt32 | Text Color in ARGB | 0xFFFFFF00 |
| 8 | UInt16 | [Tone](Enums/MsgTalk Tone) | 2000 |
| 10 | UInt16 | [Style Flags](Enums/MsgTalk Style) | 0 |
| 12 | UInt32 | Sender's Identity / Time | (hour * 100) + min |
| 16 | UInt32 | Recipient's [Mesh](Systems/Mesh) | 501002 |
| 20 | UInt32 | Sender's [Mesh](Systems/Mesh) | 501002 |
| 24 | Byte | String List Count | 6 |
|  | Byte | Sender's Name Length | 7 |
|  | Char[] | Sender's Name | Player1 |
|  | Byte | Recipient's Name Length | 7 |
|  | Char[] | Recipient's Name | Player2 |
|  | Byte | Suffix Length | 8 |
|  | Char[] | Suffix | 20140518 |
|  | Byte | Message Length | 11 |
|  | Char[] | Message | Hello world |
|  | Byte | Unreferenced String Length (empty string used in client) | 0 |
|  | Byte | Unreferenced String Length (empty string used in client) | 0 |

### Patch 5808

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (31 + Length from Sender's Name, Recipient's Name, Suffix, and Message) | 63 |
| 2 | UInt16 | Packet Type | 1004 |
| 4 | UInt32 | Timestamp | 1579535985 |
| 8 | UInt32 | Text Color in ARGB | 0xFFFFFF00 |
| 12 | UInt16 | [Tone](Enums/MsgTalk Tone) | 2000 |
| 14 | UInt16 | [Style Flags](Enums/MsgTalk Style) | 0 |
| 16 | UInt32 | Sender's Identity / Time | (hour * 100) + min |
| 20 | UInt32 | Recipient's [Mesh](Systems/Mesh) | 501002 |
| 24 | UInt32 | Sender's [Mesh](Systems/Mesh) | 501002 |
| 28 | Byte | String List Count | 6 |
|  | Byte | Sender's Name Length | 7 |
|  | Char[] | Sender's Name | Player1 |
|  | Byte | Recipient's Name Length | 7 |
|  | Char[] | Recipient's Name | Player2 |
|  | Byte | Suffix Length | 8 |
|  | Char[] | Suffix | 20140518 |
|  | Byte | Message Length | 11 |
|  | Char[] | Message | Hello world |
|  | Byte | Unreferenced String Length (empty string used in client) | 0 |
|  | Byte | Unreferenced String Length (empty string used in client) | 0 |
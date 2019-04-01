MsgDH defines TQ Digital Entertainment's transport wrapper for the DH key exchange and delivering the server's public key and initial DH parameter constants. This is the first step in the DH key exchange.

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | Char[11] | Header Pad | ... |
| 11 | UInt32 | Length | 352 |
| 15 | UInt32 | Random Pad Len | 42 |
| 19 | Char[42] | Random Pad | ... |
| 61 | UInt32 | Encryption IV Len | 8 |
| 65 | Char[8] | Encryption IV | ... |
| 73 | UInt32 | Decryption IV Len | 8 |
| 77 | Char[8] | Decryption IV | ... |
| 85 | UInt32 | Prime Modulo Len | 128 |
| 89 | Char[128] | Prime Modulo | ... |
| 217 | UInt32 | Generator Len | 2 |
| 221 | Char[2] | Generator | ... |
| 223 | UInt32 | Public Key Len | 128 |
| 227 | Char[128] | Public Key | ... |

**Notes:** The length offset value of the packet is 3 bytes less than the actual length. If the length offset is set to the actual length, the client will hang (expecting the remaining bytes). In addition, this packet requires the game server footer "TQServer".

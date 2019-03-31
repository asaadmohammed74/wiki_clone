Used in replacement of MsgAccountSRP6 for the start of Conquer Online 3.0. Implements a random buffer, used in SRP6 as a key derivation function (KDF). In addition, it combines [[MsgPCNum]] and [[MsgConnect]] which used to be sent after authentication, but is now sent before authentication. Used to initialize anti-bot routines in the client and server. 

### Patch 6630

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | ‭312‬ |
| 2 | UInt16 | Type | ‭1636‬ |
| 8 | Char[128] | Account ID | Spirited |
| 136 | Char[16] | Server Name | Snowfall |
| 152 | Char[16] | Mac Address | 0A0027000007 |
| 193 | Char[4] | Res.dat | 10 |
| 244 | Byte[64] | Random Buffer | |
| 308 | UInt32 | Encrypt Code | 10000 |

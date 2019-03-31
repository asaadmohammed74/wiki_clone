This packet is sent during the client's authentication state from the account server. The keys in this packet are from the password cipher, representing the salt and public ephemeral value. It's sent as a request for the password challenge response packet.

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 653 |
| 2 | UInt16 | Type | 1213 |
| 4 | Byte | Length of the Public Ephemeral |  |
| 5 | Byte[] | Public Ephemeral | |
| 391 | Byte | Length of the Salt |  |
| 392 | Byte[] | Salt | |

This packet is sent during the client's on-connect state with the Account Server. It's sent to the client from the Account Server to begin the packet exchange process. This random number acts as a seed for Rivest Cipher 5 in the client, used for encrypting the password to be sent over the network. This cipher was eventually replaced; however, this packet is still sent to start the packet exchange process.

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 8 |
| 2 | UInt16 | Type | 1059 |
| 4 | UInt32 | Seed | 10000 |

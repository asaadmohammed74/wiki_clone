This packet is sent during the client's authentication state from the account server. The keys in this packet are for the password cipher, representing the client's proof of K (the client key). It's sent to start the final challenge for verifying the player's inputted password.

### Patch 5635

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 262 |
| 2 | UInt16 | Type | 1214 |
| 4 | Byte | Length of the Response Session Key |  |
| 5 | Byte[] | Response Session Key | |
| 133 | Byte | Length of Proof of K |  |
| 134 | Byte[] | Proof of K | |

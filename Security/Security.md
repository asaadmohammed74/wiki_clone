This section contains security protocols and ciphers, which establish rules for data transfer and communication exchanges between the client and game server. 

### Communication Protocols
* [Google ProtoBuf](https://developers.google.com/protocol-buffers/) ([Example](Security/ProtoBuf))

### Security Ciphers
* [Blowfish](https://en.wikipedia.org/wiki/Blowfish_(cipher)) ([Example](https://gitlab.com/spirited/conquer/snippets/1840796))
* Password Scan Codes Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840792))
* RC5 ([Example](https://gitlab.com/spirited/conquer/snippets/1840791), [MsgEncryptCode](Packets/MsgEncryptCode))
* TQ Client Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840784))
* TQ Server Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840785))
* TQ File Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840786))

### Security Protocols
* [DH Key Exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) ([Example](https://gitlab.com/spirited/conquer/snippets/1840793), [MsgDH](Packets/MsgDH))
* [SRP6A](https://en.wikipedia.org/wiki/Secure_Remote_Password_protocol) ([MsgAccountSRP6Ex](Packets/MsgAccountSRP6Ex), [MsgLoginChallengeS](Packets/MsgLoginChallengeS), [MsgLoginProofC](Packets/MsgLoginProofC))

This section contains security protocols and ciphers, which establish rules for data transfer and communication exchanges between the client and game server. 

### Communication Protocols
* [Google ProtoBuf](https://developers.google.com/protocol-buffers/) ([Example](Security/ProtoBuf))

### Security Ciphers
* TQ Client Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840784))
* TQ Server Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840785))
* TQ File Asymmetric Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840786))
* RC5 ([Example](https://gitlab.com/spirited/conquer/snippets/1840791), [MsgEncryptCode](Packets/MsgEncryptCode))
* Password Scan Codes Cipher ([Example](https://gitlab.com/spirited/conquer/snippets/1840792))

### Security Protocols
* DH Key Exchange ([MsgDH](Packets/MsgDH))
* SRP6A ([MsgAccountSRP6Ex](Packets/MsgAccountSRP6Ex), [MsgLoginChallengeS](Packets/MsgLoginChallengeS), [MsgLoginProofC](Packets/MsgLoginProofC))

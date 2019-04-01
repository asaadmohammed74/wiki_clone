This packet was implemented in the base implementation of their game and server, but was removed before Conquer Online 1.0 Alpha. The message initializes a guild like system called "Hero School", which contains a list of members focused around rankings. From this system, students can be assigned teachers for "tutoring". It can be assumed that this system was later replaced by the Guide/Apprentice system (see the [MsgGuide](Packets/MsgGuide) packet). 

### Packet Definition

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt16 | Packet Length | 53 |
| 2 | UInt16 | Packet Identifier | 2037 |
| 4 | Byte | Action | 1 |
| 5 | Byte | Member Count | 1 |
| 6 | STMEMBER_INFO[] | "Set of Members" Info |  |

### STMEMBER_INFO Definition

| Type | Description | Example |
| ------ | ---- | ----------- |
| UInt32 | Member Identity | 1000000 |
| Char[16] | Member Name | TestAccount1 |
| Char[16] | Mate Name | TestAccount2 |
| Byte | Member Level | 90 |
| Byte | Member Profession | 13 |
| UInt16 | Member PK Points | 0 |
| Byte | Member Nobility Rank | 0 |
| Byte | Member Relation | 0 |
| Byte | Member Status (Offline/Online) | 1 |
| UInt32 | Member Syn Rank | 0 |
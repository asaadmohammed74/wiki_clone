This packet is sent from the game server to the game client. It contains character information from the game database, such as the name, body type, profession, and [character attributes](Systems/Attribute Points). In response to this packet, the client will send a character location request. Check the MsgAction packet for details.

### Patch 4330

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (61 + String List) | 83 |
| 2 | UInt16 | Type | 1006 |
| 4 | UInt32 | Identity | 1000000 |
| 8 | UInt32 | [Mesh](Systems/Mesh) | 1003 |
| 12 | UInt16 | [Hairstyle](Enums/Hairstyles) | 535 |
| 14 | UInt32 | Silver | 10000 |
| 18 | UInt32 | CPs | 0 |
| 22 | UInt64 | Experience | 0 |
| 40 | UInt16 | Strength | 7 |
| 42 | UInt16 | Agility | 2 |
| 44 | UInt16 | Vitality | 4 |
| 46 | UInt16 | Spirit | 0 |
| 48 | UInt16 | [Attributes](Systems/Attribute Points) | 0 |
| 50 | UInt16 | Health | 123 |
| 52 | UInt16 | Mana | 0 |
| 54 | UNIT16 | PkPoints | 0 |
| 56 | Byte | Level | 1 |
| 57 | Byte | Class | 10 |
| 58 | BOOL | Autoallot | 1 |
| 59 | Byte | Rebirths | 0 |
| 60 | BOOL | ShowName | 1 |
| 61 | Byte | String List Count | 2 |
|  | Byte | Character Name Length | 13 |
|  | Char[] | Character Name | CptMotorcycle |
|  | Byte | Spouse Name length | 4 |
|  | Char[] | Spouse | None |

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (66 + String List) | 83 |
| 2 | UInt16 | Type | 1006 |
| 4 | UInt32 | Identity | 1000000 |
| 8 | UInt32 | [Mesh](Systems/Mesh) | 1003 |
| 12 | UInt16 | [Hairstyle](Enums/Hairstyles) | 535 |
| 14 | UInt32 | Silver | 10000 |
| 18 | UInt32 | CPs | 0 |
| 22 | UInt64 | Experience | 0 |
| 46 | UInt16 | Strength | 7 |
| 48 | UInt16 | Agility | 2 |
| 50 | UInt16 | Vitality | 4 |
| 52 | UInt16 | Spirit | 0 |
| 54 | UInt16 | [Attributes](Systems/Attribute Points) | 0 |
| 56 | UInt16 | Health | 123 |
| 58 | UInt16 | Mana | 0 |
| 60 | UNIT16 | PkPoints | 0 |
| 62 | Byte | Level | 1 |
| 63 | Byte | Current Class | 10 |
| 64 | Byte | Previous Class | 0 |
| 65 | Byte | Rebirths | 0 |
| 66 | BOOL | ShowName | 1 |
| 67 | Byte | String List Count | 2 |
|  | Byte | Character Name Length | 13 |
|  | Char[] | Character Name | CptMotorcycle |
|  | Byte | Spouse Name length | 4 |
|  | Char[] | Spouse | None |

### Patch 5165

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (87 + String List) | 110 |
| 2 | UInt16 | Type | 1006 |
| 4 | UInt32 | Character Identity | 1000000 |
| 8 | UInt32 | [Mesh](Systems/Mesh) | 501003 |
| 12 | UInt16 | [Hairstyle](Enums/Hairstyles) | 418 |
| 14 | UInt32 | Silver | 10000 |
| 18 | UInt32 | Conquer Points | 10000 |
| 22 | UInt64 | Experience | 0 |
| 50 | UInt16 | Strength | 4 |
| 52 | UInt16 | Agility | 6 |
| 54 | UInt16 | Vitality | 12 |
| 56 | UInt16 | Spirit | 0 |
| 58 | UInt16 | [Attributes](Systems/Attribute Points) | 0 |
| 60 | UInt16 | Health Points | 12 |
| 62 | UInt16 | Spirit Points | 0 |
| 64 | UInt16 | Player Kill Points | 0 |
| 66 | Byte | Level | 1 |
| 67 | Byte | Class | 10 |
| 69 | Byte | Reborn Count | 0 |
| 71 | UInt32 | Quiz Points | 0 |
| 87 | Byte | String List Count | 2 |
|  | Byte | Character Name Length | 10 |
|  | Char[] | Character Name | PlayerTest |
|  | Byte | Wife Name length | 10 |
|  | Char[] | Wife Name | PlayerWife |

### Patch 5615

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length (122 + String List) | 130 |
| 2 | UInt16 | Type | 1006 |
| 4 | UInt32 | Character Identity | 1000000 |
| 8 | UInt16 | Appearance | 3 |
| 10 | UInt32 | [Mesh](Systems/Mesh) | 501003 |
| 14 | UInt16 | [Hairstyle](Enums/Hairstyles) | 418 |
| 16 | UInt32 | Silver | 10000 |
| 20 | UInt32 | Conquer Points | 10000 |
| 24 | UInt64 | Experience | 0 |
| 44 | UInt64 | Virtue | 0 |
| 52 | UInt16 | Strength | 4 |
| 54 | UInt16 | Agility | 6 |
| 56 | UInt16 | Vitality | 12 |
| 58 | UInt16 | Spirit | 0 |
| 60 | UInt16 | [Attributes](Systems/Attribute Points) | 0 |
| 62 | UInt16 | Health Points | 12 |
| 64 | UInt16 | Spirit Points | 0 |
| 66 | UInt16 | PK Points | 0 |
| 68 | Byte | Level | 1 |
| 69 | Byte | Current Class | 10 |
| 70 | Byte | Ancestor Class (2nd rb) | 10 |
| 71 | Byte | Previous Class (2nd rb, else offset 70) | 10 |
| 73 | Byte | Reborn Count | 2 |
| 77 | UInt16 | Coach Chance Value P | 0 |
| 83 | UInt16 | Coach Day Info | 0 |
| 85 | UInt32 | VIP Level | 0 |
| 91 | UInt16 | TitleId | 0 |
| 93 | UInt32 | Bound Conquer Points | 10000 |
| 97 | Byte | Subclass Id | 0 |
| 98 | UInt64 | Subclass Step-Level | 0 |
| 106 | UInt32 | Ride Points | 0 |
| 110 | Byte | String List Count | 2 |
| 111 | Byte | Character Name Length | 4 |
|  | Char[] | Character Name | Test |
|  | Byte | Spouse Name length | 10 |
|  | Char[] | Spouse Name | None |

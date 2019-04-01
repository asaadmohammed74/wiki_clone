This packet is sent to the observing clients on the map server when the actor enters their screen or an acting client observes the character as they enter its screen. The packet contains the player's character spawn information.

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 100 + CharacterName + CharacterMate |
| 2 | UInt16 | Type | 10014 |
| 4 | UInt32 | [Mesh](Systems/Mesh) | 1003 |
| 8 | UInt32 | User Identity | 1000000 |
| 12 | UInt16 | Syndicate Identity | 30 |
| 15 | Byte | Syndicate Rank | 100 |
| 16 | UInt64 | Status Flags | 8 |
| 24 | UInt32 | Helmet | 118109 |
| 28 | UInt32 | Garment | 0 |
| 32 | UInt32 | Armor | 130109 |
| 40 | UInt32 | Left Hand | 410339 |
| 44 | UInt32 | Right Hand | 480339 |
| 48 | UInt16 | Life | 15000 |
| 52 | UInt32 | [Hairstyle](Enums/Hairstyles) | 316 |
| 54 | UInt16 | Map X | 430 |
| 56 | UInt16 | Map Y | 378 |
| 58 | Byte | Direction | 7 |
| 59 | Byte | Entity Action | 0 |
| 61 | Byte | Reborn | 2 |
| 62 | Byte | Level | 130 |
| 66 | Byte | Window Spawn | 1 |
| 70 | UInt16 | Shared Battle Power | 13 |
| 77 | UInt32 | Flower Charm | 0 |
| 81 | Byte | Nobility Rank | 12 |
| 85 | UInt16 | Armor Color | 3 |
| 87 | UInt16 | Shield Color | 4 |
| 89 | UInt16 | Helmet Color | 3 |
| 91 | UInt32 | Quiz Points | 6546 |
| 95 | NetStringPacket | Strings | 2 4 Name 6 Spouse |

**Note:** Not sure if the client or something being sent wrongly, but it bugs the screen when wearing a shield jumping like a ninja.

### Patch 5672

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 232 + Name + Spouse + Clan |
| 2 | UInt16 | Type | 10014 |
| 4 | UInt32 | [Mesh](Systems/Mesh) | 1003 |
| 8 | UInt32 | User ID | 1000000 |
| 12 | UInt32 | Syndicate Identity | 30 |
| 16 | UInt32 | Syndicate Rank | 100 |
| 22 | UInt64 | Status Flags 1 | 8 |
| 30 | UInt64 | Status Flags 2 | 0 |
| 38 | UInt64 | Status Flags 3 | 0 |
| 42 | UInt16 | Appearance | 3 |
| 44 | UInt32 | Headgear ID | 0 |
| 48 | UInt32 | Garment ID | 0 |
| 52 | UInt32 | Armor ID | 0 |
| 56 | UInt32 | Weapon Left ID | 0 |
| 60 | UInt32 | Weapon Right ID | 0 |
| 64 | UInt32 | Accessory Left ID | 0 |
| 68 | UInt32 | Accessory Right ID | 0 |
| 72 | UInt32 | Mount ID | 0 |
| 76 | UInt32 | Mount Armor ID | 0 |
| 84 | UInt32 | Health | 15000 |
| 90 | UInt16 | Level | 130 |
| 92 | UInt16 | X | 430 |
| 94 | UInt16 | Y | 378 |
| 96 | UInt16 | [Hairstyle](Enums/Hairstyles) | 316 |
| 98 | Byte | Direction | 0 |
| 99 | UInt32 | Action | 0 |
| 103 | UInt16 | Continue Action | 0 |
| 106 | Byte | Reborn | 2 |
| 107 | UInt16 | Level | 130 |
| 109 | Bool | Lock Dummy | 0 |
| 110 | Bool | AFK Status | 0 |
| 111 | UInt32 | Tutor Battle Power | 0 |
| 115 | UInt32 | Fate Battle Power | 0 |
| 119 | UInt32 | Team Amount | 0 |
| 123 | UInt32 | Team Leader ID | 0 |
| 127 | UInt32 | Flower Charm | 0 |
| 131 | UInt32 | Nobility | 12 |
| 135 | UInt16 | Armor Color | 3 |
| 137 | UInt16 | Shield Color | 5 |
| 139 | UInt16 | Headgear Color | 3 |
| 141 | UInt32 | Quiz Points | 6546 |
| 145 | UInt16 | Mount Plus | 0 |
| 147 | UInt32 | Mount Exp | 0 |
| 151 | UInt32 | Mount Color | 0 |
| 155 | UInt16 | Enlighten Points | 0 |
| 157 | UInt16 | Study Points | 0 |
| 163 | UInt32 | VIP Level | 0 |
| 167 | UInt32 | Clan ID | 0 |
| 171 | UInt32 | Clan Rank | 0 |
| 175 | UInt32 | Clan Battle Power | 0 |
| 179 | UInt16 | Title ID | 0 |
| 185 | Bool | Is Poker Actor | 0 |
| 186 | UInt32 | Totem Battle Power | 0 |
| 190 | Bool | Is Arena Witness | 0 |
| 193 | Bool | Is Boss | 0 |
| 194 | UInt32 | Headgear Soul ID | 0 |
| 198 | UInt32 | Armor Soul ID | 0 |
| 202 | UInt32 | Left Weapon Soul ID | 0 |
| 206 | UInt32 | Right Weapon Soul ID | 0 |
| 210 | Byte | Sub Profession | 0 |
| 211 | UInt64 | Sub Profession Info | 0 |
| 219 | UInt16 | First Profession | 15 |
| 221 | UInt16 | Second Profession | 25 |
| 223 | UInt16 | Current Profession | 45 |
| 225 | UInt16 | Nationality ID | 0 |
| 232 | NetStringPacket | Strings | 3 4 Name 6 Spouse 0 Clan |

This packet is sent between the client and game server. It contains information about a mentor and apprentices for a player. The packet is sent on login if the player has a mentor or when required by the client.

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 80 |
| 2 | UInt16 | Type | 2066 |
| 4 | UInt32 | Action Type | 2 |
| 8 | UInt32 | User Identity | 1000000 |
| 12 | UInt32 | Target Identity | 1000001 |
| 16 | UInt32 | Lookface | 571003 |
| 20 | UInt32 | Shared Battle Power | 3 |
| 24 | UInt32 | Hours | 1 |
| 28 | UInt32 | Enroll Date | 20160429 |
| 32 | Byte | Target Level | 130 |
| 33 | Byte | Target Profession | 55 |
| 34 | UInt16 | Target Pk Points | 17 |
| 36 | UInt16 | Syndicate Identity | 3 |
| 39 | Byte | Syndicate Rank | 100 |
| 48 | Byte | Target Online | 1 |
| 52 | UInt32 | Action Type | 2 |
| 56 | UInt32 | Apprentice Experience | 4654698 |
| 64 | UInt16 | Apprentice Blessing | 12 |
| 66 | UInt16 | Apprentice Composing | 200 |
| 68 | Byte | String Count | 3 |
| 69 | NetStringPacker | Strings | 3 6 Mentor 10 Apprentice 10 MentorWife |

**Removing Mentorship:** Hours == 999999; Field is ignored.
Hours == 0; The apprentice record is dropped from the mentor list.
Hours > 0; Value is parsed as the number of waiting hours left before the mentor-ship is active.

To remove the apprentice from the mentor list you send 
packet 2065 with ActionType = (ExpelApprentice = 18) followed by
packet 2066 with ActionType = (ApprenticeList = 2), and the Hours field set to 0.

This packet is sent between the game server to the game client and is used to control actions and display results in the DiceKing mini game.

### Patch 5017

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 12 + Amount * 8 |
| 2 | UInt16 | Type | 1113 |
| 4 | Byte | [DiceActionType](Enums/MsgDice Action) | DiceActionType.ChipIn |
| 5 | Byte | Amount | 1 |
| 6 | UInt16 | Unknown | 0 |
| 8 | UInt32 | DiceNpc Id | 1005 |
| 12 | UInt32 | DiceType | 1 |
| 16 | UInt32 | DiceData | 10000 |

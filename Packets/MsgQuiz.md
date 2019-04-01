Displays the quiz show interface and handles questions and replies from players. 

### Patch 5103

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 18 + String Lengths |
| 2 | UInt16 | Type | 2068 |
| 4 | UInt16 | Action | 1 |
| 6 | UInt16 | Param1 (Countdown, Score, Question Num.) | |
| 8 | UInt16 | Param2 (Last Correct Answer, Time Taken, Prize) | |
| 10 | UInt16 | Param3 (Time Per Question, Exp. Awarded, Rank) | |
| 12 | UInt16 | Param4 (First Prize, Time Taken) | |
| 14 | UInt16 | Param5 (Second Prize, Current Score) | |
| 16 | UInt16 | Param6 (Third Prize) | |
| 18 | [NetStringPacker](Systems/String Packer) | Strings | 5 Question Answer1 Answer2 Answer3 Answer4 |

These enumeration type values are sent between the client and game server to request/set/modify various client strings including spouse and guild names through the [MsgName](Packets/MsgName) Packet. 

```
None = 0,
Fireworks,
CreateGuild,
Guild,
ChangeTitle,
DeleteRole = 5,
Mate,
QueryNpc,
Wanted,
MapEffect,
RoleEffect = 10,
MemberList,
KickoutGuildMember,
QueryWanted,
QueryPoliceWanted,
PoliceWanted = 15,
QueryMate,
AddDicePlayer,
DeleteDicePlayer,
DiceBonus,
PlayerWave = 20,
SetAlly,
SetEnemy,
WhisperWindowInfo = 26
```
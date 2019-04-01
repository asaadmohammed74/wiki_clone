These enumeration type values are used to request and confirm various client interactions using [MsgInteract](Packets/MsgInteract). It is worth noting that based on client version, some of these types change. Target version: 5517

```
None = 0,
Steal,
Attack,
Heal,
Poison,
Assassinate = 5,
Freeze,
Unfreeze,
Court,
Marry,
Divorce = 10,
PresentMoney,
PresentItem,
SendFlowers,
Kill = 14,
JoinGuild = 15,
AcceptGuildMember,
KickoutGuildMember,
PresentPower,
QueryInfo,
RushAttack = 20,
Unknown21,
AbortMagic,
ReflectWeapon,
MagicAttack,
Unknown = 25,
ReflectMagic,
Dash,
Shoot,
Quarry,
Chop = 30,
Hustle,
Soul,
AcceptMerchant,
CounterKill = 43,
CounterKillSwitch = 44,
FatalStrike = 45,
/// <summary>
/// [46] 
/// Used to request player-player interactions like hug, kiss, etc.
/// </summary>
InteractRequest = 46,
/// <summary>
/// [47] 
/// Used to confirm player-player interactions like hug, kiss, etc.
/// </summary>
InteractConfirm,
Interact,
InteractUnknown,
InteractStop,
IntoneSpell = 52,
ShiftPlayer = 53,
AzureAntiDamage = 55,
WeaponSkill = 1000 
```
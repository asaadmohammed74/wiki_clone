These enumeration type values determine many different types of ground movement through the [MsgWalk](Packets/MsgWalk) packet. Earlier versions (Patch 5017 for example) are treated as a single byte where newer versions occupy 4 bytes of data in the MsgWalk packet.

```cs
Walk = 0,
Run = 1,
Shift = 2,
Jump = 3,
Trans = 4,
ChangeMap = 5,
JumpMagicAttack = 6,
Collide = 7,
Synchro = 8,
Mount = 9
```


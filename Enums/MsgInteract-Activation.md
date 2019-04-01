These flags determine various bonus effects which can be triggered during various interactions. Because they are flags they can be combined together and more than one can be sent in a single packet ([MsgInteract](Packets/MsgInteract)).

```cs
None = 0,
Block = 1 << 0,
Crash = 1 << 1,
CriticalStrike = 1 << 2,
Metal = 1 << 4,
Wood = 1 << 5,
Water = 1 << 6,
Fire = 1 << 7,
Earth = 1 << 8,
StudyPoints = 1 << 9,
```
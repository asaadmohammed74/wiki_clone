These enumeration type values are hard-coded into the client for [MsgMapInfo](Packets/MsgMapInfo), and control the regulations for a game map. 

```c
MAPTYPE_NORMAL           = 0x0000,	
MAPTYPE_PKFIELD	         = 0x0001,	
MAPTYPE_CHGMAP_DISABLE   = 0x0002, 
MAPTYPE_RECORD_DISABLE   = 0x0004, 
MAPTYPE_PK_DISABLE       = 0x0008,	
MAPTYPE_BOOTH_ENABLE     = 0x0010, 
MAPTYPE_TEAM_DISABLE     = 0x0020, 
MAPTYPE_TELEPORT_DISABLE = 0x0040, 
MAPTYPE_SYN_MAP          = 0x0080,	
MAPTYPE_PRISON_MAP       = 0x0100,	
MAPTYPE_WING_DISABLE     = 0x0200, 
MAPTYPE_FAMILY	         = 0x0400, 
MAPTYPE_MINEFIELD        = 0x0800, 
MAPTYPE_PKGAME           = 0x1000, 
MAPTYPE_NEVERWOUND       = 0x2000, 
MAPTYPE_DEADISLAND       = 0x4000, 
```
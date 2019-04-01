This file structure encapsulates covers, effects, scenes, and sounds, used for world maps. The purpose of the data map (.DMap) file is to link all assets and data structures together for a world map to exist. This file structure is the backbone of Conquer Online's map system.

### Root Structure

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt64 | Version | 1003 |
| 8 | Char[260] | Puzzle Path | map\\puzzle\\babel.pul |
| 268 | UInt32 | Width | 368 |
| 268 | UInt32 | Height | 368 |
||| **for y := 0; y < height; y++** |
||| **for x := 0; x < width; x++** |
| | UInt16 | Accessible | 1 |
| | UInt16 | Surface | 0 |
| | Int16 | Elevation | 0 |
||| **end for** |
| | UInt32 | Checksum | 136160 |
||| **end for** |
| | UInt32 | Amount Passageways | 0 |
||| **for i := 0; i < amount; i++** |
| | UInt32 | Portal X | |
| | UInt32 | Portal Y | |
| | UInt32 | Portal Index | |
||| **end for** |
| | UInt32 | Amount Layers | 48 |
||| **for i := 0; i < amount; i++** |
| | UInt32 | Layer Type | 10 |
| | Layer | See layer type structures below | |
||| **end for** |

*Notes:* The version could be a string prefixed with "DMAP". 

Passageway indexes are not consistent. They're only used for client indexing of passageways. Checksum for a column of tiles is generated with the formula below (per cell):
```cs
checksum += (uint32)((tile.Accessible ? 0 : 1) * (tile.Surface + y + 1) + (tile.Elevation + 2) * (tile.Surface + x + 1));
```

### Layer Type Structures
Data map files contain more sections that can be read from. 
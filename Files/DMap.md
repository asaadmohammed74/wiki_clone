This file structure encapsulates covers, effects, scenes, and sounds, used for world maps. The purpose of the data map (.DMap) file is to link all assets and data structures together for a world map to exist. This file structure is the backbone of Conquer Online's map system.

### Root Structure

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt64 | Version | 1003 |
| 8 | Char[260] | [Puzzle](Files/Pul) Path | map\\puzzle\\babel.pul |
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

### Cover Layer Type
This data structure is encapsulated by the data map file structure. A cover object is a scenery object or animation which is layered on top of all other objects and the player. The purpose of covers is to add depth to the world (a foreground in front of the player). Unlike scenery files, the cover file structure is not its own separate file format, but instead uses an ANI file to map the cover to its frames and assets.

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | Char[260] | File Path | ani\MapScene-saya.ani |
| 260 | Char[128] | Key Name | altar00 |
| 388 | UInt32 | Origin X | 568 |
| 392 | UInt32 | Origin Y | 788 |
| 396 | UInt32 | Width | 3 |
| 400 | UInt32 | Height | 2 |
| 404 | UInt32 | Offset X | 89 |
| 408 | UInt32 | Offset Y | 221 |
| 412 | UInt32 | Frame Interval | 100 |

Ani Example:
```ini
[altar00]
FrameAmount=1
Frame0=data/map/mapobj/newplain/altar/altar00.dds
```

### Effect Layer Type
This data structure is encapsulated by the data map file structure. An effect acts as a floor effect on the map. Players may walk over and obstruct them, similarly to scene objects. This entry contains the name of the effect, which is used as a key in 3DEffect.ini. Coordinates for this entry are in [world coordinates](Systems/World Coordinates).

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | Char[64] | Name | zf2-e224 |
| 64 | UInt32 | Origin X | 11392 |
| 68 | UInt32 | Origin Y | 6465 |

### Scene Layer Type
This data structure is encapsulated by the data map file structure. A scene acts as a background cover on the map, composed by multiple assets arranged as a [puzzle](Files/Pul). Players may walk over and obstruct them, similarly to the map's [puzzle](Files/Pul). This entry contains the file path of the scene part, which defines the [puzzle](Files/Pul) pieces for the scene.

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | Char[260] | Path | |
| 260 | UInt32 | Origin X | |
| 264 | UInt32 | Origin Y | |

### Sound Layer Type
This data structure is encapsulated by the data map file structure. A sound object is not visible by players on the screen and does not overlap with any other screen objects in the interactive layer. It only plays a sound which varies in volume, range, and location according to the structure defined below. Coordinates for this entry are in [world coordinates](Systems/World Coordinates).

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | Char[260] | Path | sound/water.wav |
| 260 | UInt32 | Origin X | 25995 |
| 264 | UInt32 | Origin Y | 11673 |
| 268 | UInt32 | Range | 1200 |
| 272 | UInt32 | Volume | 100 |
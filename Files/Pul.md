This file type defines a collection of puzzle pieces for constructing the background for a map. Each map background is split up into a group of separate graphics, similar to how a puzzle splits one picture up into multiple smaller pieces. Putting the pieces together constructs the map. Some maps have two puzzle files, one for the primary background and one for overlay. For example, the clouds in the water which move in the Great Plains. This is an example of a rolling puzzle.

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | Char[8] | Version | PUZZLE2 |
| 8 | Char[256] | File Path | ani\skybg.ani |
| 264 | UInt32 | Width | 12 |
| 268 | UInt32 | Height | 40 |
||| **for y := 0; y < height; y++** ||
||| **for x := 0; x < width; x++** ||
| | UInt16 | Ani Index | 0 |
||| **If Version 2** ||
| | UInt32 | Roll Speed X | 20 |
| | UInt32 | Roll Speed Y | 20 |
||| **End of if Version 2** ||
||| **End of for** ||
||| **End of for** ||

Ani Example:
```ini
[Puzzle0]
FrameAmount=1
Frame0=data/map/puzzle/sky/skybg/skybg000.dds
[Puzzle1]
FrameAmount=1
Frame0=data/map/puzzle/sky/skybg/skybg001.dds
```

Client Calculation for Puzzle Roll Speed:
```cpp
// 100 = The default move rate on normal tiles.
posOffset.x = RollSpeedX * defaultMoveRate * (dwTimeCurrent - m_dwTimeBegin) / (1000 * 100);
posOffset.y = RollSpeedY * defaultMoveRate * (dwTimeCurrent - m_dwTimeBegin) / (1000 * 100);
```
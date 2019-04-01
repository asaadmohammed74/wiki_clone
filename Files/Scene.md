This file type defines a collection of puzzle pieces for constructing a scenery object on a map. Each large scenery object is split up into a group of separate graphics, similar to how a map background is split up into separate graphics or how a puzzle splits one picture up into multiple smaller pieces. Putting the pieces together constructs the scenery object. For example, the bridges on some maps are large scenery objects composed of multiple graphics.

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt32 | Amount of parts |  |
||| **for i := 0; i < parts; i++** |
| | Char[256] | Path | |
| | Char[64] | Title | |
| | UInt32 | Origin X | |
| | UInt32 | Origin Y | |
| | UInt32 | Frame Interval | |
| | UInt32 | Width | |
| | UInt32 | Height | |
| | UInt32 | Thickness | |
| | UInt32 | Offset X | |
| | UInt32 | Offset Y | |
| | Int32 | Offset Elevation | |
||| **for y := 0; y < height; y++** |
||| **for x := 0; x < width; x++** |
| | UInt32 | Accessible | |
| | UInt32 | Surface Type | |
| | Int32 | Elevation | |
||| **end for** |
||| **end for** |
||| **end for** |
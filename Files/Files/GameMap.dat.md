A file which links map IDs to dmap paths. Starts with an INT32 for the amount of records in the file. Then, repeats the following data structure below:

| Offset | Type | Description | Example |
| ------ | ---- | ----------- | ------- |
| 0 | UInt32 | MapID | 1000 |
| 4 | UInt32 | Length | 19 |
| 8 | Char[Length] | Path | map/map/newplain.7z |
| | UInt32 | Puzzle Size | 256 |
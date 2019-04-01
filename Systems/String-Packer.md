TQs NetStringPacker is essentially just a list of variable length strings.

| Offset | Type | Description | Example |
| --- | --- | --- | --- |
| 0 | Byte | Strings Count | 2 |
| 1 | Byte | String Length | 5 |
| 2 | String | String Content | Hello |
| 7 | Byte | String Length | 3 |
| 8 | String | String Content | You |
This file was introduced around the time of the transition from Conquer Online 1.0 to Conquer Online 2.0. The official name for this file is the "EPvE szVersion File". In Conquer Online 1.0, the file contains "0001"; while in the Conquer Online 2.0 client, this file contains "0010". This is likely binary for 1 and 2. The file is only used during account and game servers' [MsgConnect](Packets/MsgConnect) packets. It's likely that this is a flag for handling the client on the server end.

### Examples
Conquer 1.0 Patch 4274: `0001`

Conquer 2.0 Patch 4343: `0010`
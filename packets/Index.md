## Network Packets
This section contains links to packet structures used for server-client communication in Conquer Online. Packets are organized by TQ internal packet type name and sorted by the packet type ID. All packets contain the following header, and is present in all packet structures listed on this wiki:

```go
type Header struct {
    Length  uint16
    Type    uint16
}
```
### Known Packet Structures
* 1001 - [MsgRegister](MsgRegister)
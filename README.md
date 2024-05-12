# Torrent client using NodeJS


## Tracker protocol and message formats using UDP:

The BEP describes the connect request as follows:
```
Offset  Size            Name            Value
0       64-bit integer  connection_id   0x41727101980
8       32-bit integer  action          0 // connect
12      32-bit integer  transaction_id  ? // random
16
```


The BEP describes the response as follows:
```
Offset  Size            Name            Value
0       32-bit integer  action          0 // connect
4       32-bit integer  transaction_id
8       64-bit integer  connection_id
16
```


Announce request:
```
Offset  Size    Name    Value
0       64-bit integer  connection_id
8       32-bit integer  action          1 // announce
12      32-bit integer  transaction_id
16      20-byte string  info_hash
36      20-byte string  peer_id
56      64-bit integer  downloaded
64      64-bit integer  left
72      64-bit integer  uploaded
80      32-bit integer  event           0 // 0: none; 1: completed; 2: started; 3: stopped
84      32-bit integer  IP address      0 // default
88      32-bit integer  key             ? // random
92      32-bit integer  num_want        -1 // default
96      16-bit integer  port            ? // should be betwee
98
```

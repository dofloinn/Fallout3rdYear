![](https://i.imgur.com/SjO7uNu.png)

![](https://i.imgur.com/tXobSik.png)

![](https://i.imgur.com/ce1u57N.png)

![](https://i.imgur.com/7GwlDGT.png)

![](https://i.imgur.com/ioNk0JC.png)

![](https://i.imgur.com/qIpz774.png)

![](https://i.imgur.com/wEN7Nds.png)

![](https://i.imgur.com/3BWX0lr.png)

![](https://i.imgur.com/tOyjJ4H.png)

![](https://i.imgur.com/OSoLLOI.png)

![](https://i.imgur.com/XSBnqim.png)

![](https://i.imgur.com/FmeoIlu.png)

![](https://i.imgur.com/x8RWJSr.png)

![](https://i.imgur.com/pVxDG0h.png)

![](https://i.imgur.com/PaU7Nw1.png)

![](https://i.imgur.com/o41NwWS.png)

![](https://i.imgur.com/GeGNEnJ.png)

![](https://i.imgur.com/ehcq003.png)

![](https://i.imgur.com/sE8icOF.png)

![](https://i.imgur.com/oqk8QuL.png)

![](https://i.imgur.com/YqZBkZz.png)

![](https://i.imgur.com/Iwc2DQZ.png)

![](https://i.imgur.com/ipMIGkd.png)

![](https://i.imgur.com/rMCy3RV.png)

![](https://i.imgur.com/RWzF4Gc.png)

<mark style="background: #FF5582A6;">(RUAN'S ANSWERS)</mark>

![](https://i.imgur.com/BfqNfZx.png)

```
a)
The client application sends a SYN packet and starts the sequence number
The server replies with a SYN + ACK to acknowledge the request.
The client then replies with an ACK to acknowledge the server's acknowledgement and the connection is established.

You can tell the client started the connection as an ephemeral port is connecting to a well-known port (In this case the port for HTTP, port 80).
Port 52903 -> Port 80 in line 1
```

![](https://i.imgur.com/pYbnKaZ.png)

```
b)
SEQ is the sequence number. This is the sequence of messages from the transmitter. It starts from zero.
Line 1 has Sequence 0, as it is the client's first message
Line 2 has Sequence 0, as it's the server's first message
Line 3 is Sequence 1 as it's the client's second message.

This allows out-of-frame packets to be found and resolved.


ACK is the acknowledgement number. It indicates the next expected packet. It acknowledges correct receipt for data delivery.

The ACK value is the value the next packet should have as its SEQUENCE number.


WIN is the buffer size for incoming data. This is how much the transmitter will send before the receiver sends an acknowledgement.
```

![](https://i.imgur.com/ZpzsPkE.png)

```
c)
ACKs are a control packet and does not contain any data. It is used to acknowledge any other control message.
In Line 4, SEQ would be 1 as well, as it has not increased from the client sending the ACK.
```

![](https://i.imgur.com/DkkV41f.png)

```
d)
The next ACK value will be 101.
Each segment would be 1 byte, so the ACK which is currently 1 would have 100 added to it, acknowledging the arrival of the last 100 bytes of content.
```

# <mark style="background: #FF5582A6;">2022/23:</mark>

![](https://i.imgur.com/4RMhT9V.png)

![](https://i.imgur.com/QBgZJkl.png)

![](https://i.imgur.com/TCMol3w.png)

![](https://i.imgur.com/iQP1Rka.png)

![](https://i.imgur.com/DZKTbJ7.png)


skipped non-relevant q

![](https://i.imgur.com/J6OB5ut.png)

![](https://i.imgur.com/zxHDmoO.png)

![](https://i.imgur.com/exsZ0d2.png)

![](https://i.imgur.com/lF6ZA2C.png)

![](https://i.imgur.com/jaaA4Cr.png)

![](https://i.imgur.com/6YFmv9W.png)

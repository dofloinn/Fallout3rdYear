### <mark style="background: #FF5582A6;">TCP Connections:</mark>

Applications that need to exchange data interact with their local TCP entity through the local socket to handle the connection <mark style="background: #FF5582A6;">Establishment</mark> and <mark style="background: #FF5582A6;">Termination</mark> activities:

These activities relate to <mark style="background: #FF5582A6;">Phase 1 (Initialisation)</mark> &  <mark style="background: #FF5582A6;">Phase 3 (Termination)</mark> of the communications model and are commonly referred to as <mark style="background: #FF5582A6;">Opening</mark> and <mark style="background: #FF5582A6;">Closing</mark> connections.

To facilitate an exploration of TCP’s role in Opening and Closing connections it is important to explore the structure of a TCP PDU a.k.a. a <mark style="background: #FF5582A6;">Segment</mark>.

### <mark style="background: #FF5582A6;">TCP Segment Header Format:</mark>

![](https://i.imgur.com/eXpIoG6.png)

### <mark style="background: #FF5582A6;">Opening a TCP connection: The Three-Way Handshake:</mark>

<mark style="background: #FF5582A6;">Opening a TCP connection:</mark>
- A client calling ``connect`` is performing an <mark style="background: #FF5582A6;">active</mark> open,
- A server having previously called: ``socket``, ``bind``, ``listen`` and ``accept``, has resulted in the creation of a socket that is in passive mode i.e. awaiting connection requests.

The call to ``connect`` causes the client TCP entity to send a ``SYN`` (synchronise) segment. This segment contains the client's initial <mark style="background: #FF5582A6;">sequence</mark> number for its data

The server TCP entity must acknowledge receiving a ``SYN`` segment and it must send its own ``SYN`` segment

This contains the initial sequence number for its data (note: the full duplex operation)

In addition, the server’s ``SYN`` contains an ``ACK`` of the client's ``SYN`` message

### <mark style="background: #FF5582A6;">The Three-Way Handshake – Contd:</mark>

The client TCP entity must also acknowledge receipt of the server's ``SYN`` segment: As there are three segments used in the opening sequence this procedure is called a <mark style="background: #FF5582A6;">three-way handshake</mark>

<mark style="background: #FF5582A6;">Note on sequence numbers:</mark>
- Sequence numbers contained in a TCP acknowledgement segment (``ACK``) is the <mark style="background: #FF5582A6;">next expected</mark> sequence number
- ``SYN`` messages occupy 1 byte of the sequence number space
- ``ACKs`` on their own do not consume a sequence number
- Refer to the example connection start-up sequence on the next slide

### <mark style="background: #FF5582A6;">Example Opening Three Way Handshake:</mark>

![](https://i.imgur.com/5Q799ds.png)

### <mark style="background: #FF5582A6;">Closing a TCP connection:</mark>

<mark style="background: #FF5582A6;">Closing a TCP Connection:</mark>
- An application calling ``close`` is performing an active close
- The other end of connection is said to be performing a passive close

<mark style="background: #FF5582A6;">The call to close() causes the local TCP entity to sends a FIN segment:</mark>
- This implies that the application is finished sending data
- Either application, the client or the server, can call ``close()``

### <mark style="background: #FF5582A6;">Example Closing using a Three-way Handshake:</mark>

![](https://i.imgur.com/TcVmKeV.png)

### <mark style="background: #FF5582A6;">Closing a TCP connection:</mark>

<mark style="background: #FF5582A6;">The FIN segment is acknowledged by the receiving TCP entity:</mark>
- This FIN message is passed to the application as an <mark style="background: #FF5582A6;">end-of-file</mark> and is queued <mark style="background: #FF5582A6;">after</mark> any remaining data
- Receipt of a FIN means no more data will arrive on the connection

<mark style="background: #FF5582A6;">An application that receives an end-of-file can choose to:</mark>
- Leave the local socket open for longer in order to return data to the remote app. This is known as a <mark style="background: #FF5582A6;">half-close</mark>, OR,
- Close its local socket by calling ``close()`` resulting in its local TCP entity sending a FIN. This FIN segment must be acknowledged by the remote TCP entity

This choice results in either a <mark style="background: #FF5582A6;">three-way</mark> or <mark style="background: #FF5582A6;">four-way</mark> handshaking sequence for closing the connection

### <mark style="background: #FF5582A6;">Closing a TCP connection:</mark>

Closing a connection requires a ``FIN`` and an ``ACK`` in each direction i.e. four segments are <mark style="background: #FF5582A6;">normally</mark> required, however the <mark style="background: #FF5582A6;">active</mark> ``FIN`` is normally sent with data and the passive ``FIN`` can be combined with the ``ACK`` into a single segment i.e. a three-way handshake

<mark style="background: #FF5582A6;">Connections can also be closed by terminating the application:</mark> 
- i.e. terminating the associated Unix process:
- This causes all open socket descriptors to <mark style="background: #FF5582A6;">close</mark>
- This results in a ``FIN`` segment being sent on any open TCP connections

<mark style="background: #FF5582A6;">Note on sequence numbers:</mark>
- Just like SYN segments, FIN segment also occupy 1 byte of the sequence number space
- ACKs on their own do not consume a sequence number
- Refer to the example connection termination sequence on the next slide

### <mark style="background: #FF5582A6;">Example Closing using a Four-way Handshake (a Half Close):</mark>

![](https://i.imgur.com/DdQl787.png)

### <mark style="background: #FF5582A6;">Example of a complete connection sequence:</mark>

![](https://i.imgur.com/IEZst89.png)

### <mark style="background: #FF5582A6;">TCP State Transition Diagram - explained:</mark>

<mark style="background: #FF5582A6;">The TCP State Transition Diagram shows the operation of TCP’s connection establishment and termination phases:</mark>
- There are 11 different states defined for a connection
- Client and server transitions are shown as dark solid and dark dashed lines respectively
- The transition from one state to another depends on the segment received in that state
- e.g. an application performing an active open in the ``CLOSED`` state moves to the ``SYN_SENT`` state and then to the ``ESTABLISHED`` state upon receipt of a ``SYN`` with an ``ACK``

The ``ESTABLISHED`` state is where most data transfer occurs

![](https://i.imgur.com/qNX9QVz.png)

<mark style="background: #FF5582A6;">Termination of a connection:</mark>
- From the ``ESTABLISHED`` state there are two possible transitions:
- An application calling ``close`` i.e. an active close moves to the ``FIN_WAIT_1`` state
- An application receiving a ``FIN`` (i.e. a passive close) moves to the ``CLOSE_WAIT`` state

In rare circumstances it is possible for both ends to
send SYN/FINs simultaneously (known as simultaneous open/close). This scenario is not explored here

### <mark style="background: #FF5582A6;">TCP’s TIME_WAIT State - explained:</mark>

The end that performs the <mark style="background: #FF5582A6;">active close</mark> goes through the ``TIME_WAIT`` state for a period of twice the <mark style="background: #FF5582A6;">MSL (maximum segment lifetime)</mark> a.k.a. 2MSL
- MSL is the maximum amount of time that an IP <mark style="background: #FF5582A6;">datagram</mark> can live in an internet. This is linked to the TTL field (max value is 255)
- TCP chooses a value for MSL of between 1 min. and 4 minutes

There are two reasons for the TIME_WAIT state:

<mark style="background: #FF5582A6;">1. To implement TCP's full-duplex connection termination reliably:</mark>
- Recall two of TCP’s service offerings is <mark style="background: #FF5582A6;">full-duplex communication</mark> and <mark style="background: #FF5582A6;">reliable termination</mark>
- The end that performs an <mark style="background: #FF5582A6;">active close</mark> remains in the ``TIME_WAIT`` state as it might have to retransmit the final ``ACK``

<mark style="background: #FF5582A6;">2. To allow old duplicate segments to expire in the network:</mark>
- Datagrams containing TCP segments can get caught in <mark style="background: #FF5582A6;">routing loops</mark> within an internet due to routing errors. These are known as lost or <mark style="background: #FF5582A6;">wandering duplicates</mark>
- TCP must handle these duplicates for connections that have been <mark style="background: #FF5582A6;">reincarnated</mark>
- TCP will not initiate an <mark style="background: #FF5582A6;">incarnation</mark> of a connection that is currently in the ``TIME_WAIT`` state
- This guarantees that all old <mark style="background: #FF5582A6;">duplicates</mark> from previous incarnations have expired
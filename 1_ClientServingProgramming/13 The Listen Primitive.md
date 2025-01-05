### <mark style="background: #FF5582A6;">The listen function:</mark>

The listen function performs two actions.

It converts an <mark style="background: #FF5582A6;">unconnected</mark> socket into a <mark style="background: #FF5582A6;">passive socket</mark>. This informs the kernel to accept incoming connection requests to this socket

It limits the number of connections that will be queued for this server:

``int listen(int sockfd, int backlog);``

Returns: 0 if OK, -1 on error

For a listening socket, the kernel maintains two
queues:

<mark style="background: #FF5582A6;">Incomplete:</mark>
- An <mark style="background: #FF5582A6;">incomplete</mark> connection queue contains an entry for each ``SYN`` segment that has arrived from a client but is awaiting completion of the TCP 3WHS. These sockets are in the ``SYN_RCVD`` state.
- Entries remain on this queue until the third segment of the 3WHS arrives or until the entry times out.

<mark style="background: #FF5582A6;">Complete:</mark>
- A <mark style="background: #FF5582A6;">completed</mark> connection queue contains an entry for each client for which the TCP 3WHS has been completed. These sockets are in the ``ESTABLISHED`` state.
- Entries on this queue are returned to the process when accept is called

<mark style="background: #FF5582A6;">TCP ignores the arriving SYN when the queues are full:</mark>
- It does <mark style="background: #FF5582A6;">not</mark> send an ``RST`` (reset) preventing the client's <mark style="background: #FF5582A6;">connect</mark> returning an error
- Instead, the client TCP entity is allowed retransmit its ``SYN`` segment

Data that arrives after the 3WHS completes, but before the server calls accept, is queued by the TCP entity up to the size of the <mark style="background: #FF5582A6;">connected</mark> socket's receive buffer

### <mark style="background: #FF5582A6;">TCP Queues:</mark>

![](https://i.imgur.com/ay0sN7A.png)

### <mark style="background: #FF5582A6;">The backlog argument:</mark>

The backlog argument specifies the <mark style="background: #FF5582A6;">maximum</mark> value for the <mark style="background: #FF5582A6;">sum</mark> of <mark style="background: #FF5582A6;">both</mark> queues. 

Do not specify a backlog of 0, as different implementations interpret this differently.

If you do not want any clients connecting to your <mark style="background: #FF5582A6;">listening</mark> socket then close it

A backlog of 5 was often used in the 1980s when busy servers handled only a few hundred client connections per day

With the growth of the World Wide Web (WWW) HTTP servers can handle millions of connections per day, this small number is inadequate

Hence, we specify an <mark style="background: #FF5582A6;">environment variable</mark> ``LISTENQ`` which can be changed without a recompile of the code.
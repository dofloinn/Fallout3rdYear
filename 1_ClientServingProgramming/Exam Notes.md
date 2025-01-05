# <mark style="background: #FF5582A6;">01 Protocol Hierarchies</mark>

### <mark style="background: #FF5582A6;">Protocol Hierarchies:</mark>

Computer Networks are generally comprised of numerous pieces of hardware and software.

Recall the previous attempt to 'model' how these components interconnect and interact with each other

Source -> Transmitter -> Transmission System -> Receiver -> Destination

Whilst the horizontal model is useful when looking at hardware components, the reality is that it does not explain everything

From previous discussions on: <mark style="background: #FF5582A6;">Data Link Control</mark>, <mark style="background: #FF5582A6;">LANs technologies</mark>, <mark style="background: #FF5582A6;">Internetworking</mark> etc. much of the functionality required to provide communications between host machines is not necessarily provided on individual hardware components.

For instance the transmission/reception of MAC frames requires sending and receiving binary ones and zeroes on a variety of transmission media using a variety of access techniques. 

This mixture of functionality is provided on <mark style="background: #FF5582A6;">NICs</mark> (one per LAN technology) and in software elsewhere on the host.

 A better model is required to explain these concepts and techniques.

<mark style="background: #FF5582A6;">To simplify network design most networking technologies are organised as layers of protocol software:</mark>
- The purpose of each layer is to provide <mark style="background: #FF5582A6;">one</mark> component of the overall solution to the “Communications Problem” such as “frame reception/transmission” etc.
- These layers of software can exist on separate hardware components and/or hosts or is some instances multiple layers can exist on a single hardware platform and/or hosts.

<mark style="background: #FF5582A6;">This concept is not dissimilar to the approach used for software development:</mark>
- Objects or libraries are used to perform specific operations.
- Importantly the object/library function keeps details of its internal state and algorithms hidden from the main program.

<mark style="background: #FF5582A6;">The same approach is used for network protocol software:</mark>
- Each layer of software provides one part of the solution such as: frame transmission/reception or, transmitting one/zeros onto a wire/wireless transmission medium etc.

With networking software, the layers of protocol software are organised into a <mark style="background: #FF5582A6;">Stack</mark>.

Each layer is said to offer <mark style="background: #FF5582A6;">services</mark> to higher layers and to use the services offered by the lower layers.

<mark style="background: #FF5582A6;">Protocol/Protocol Entity:</mark> A software module that performs one sub-task such as: frame transmission/reception etc.

<mark style="background: #FF5582A6;">Protocol suites/stack:</mark> A number of such software modules that work together to perform all of the tasks required to enable two hosts to communicate.

<mark style="background: #FF5582A6;">Protocol Architectures/Model:</mark> A model by which we can categorise or view the different protocol layers.

The OSI model deals with connecting open systems, i.e. systems that are open for communication with other systems regardless of who built them or how they were manufactured.

<mark style="background: #FF5582A6;">The principles that were applied to arrive at the seven layers are as follows:</mark>
- Each layer was created when a different <mark style="background: #FF5582A6;">level of abstraction</mark> was required.
- Each layer performs one well-defined function with each function chosen carefully to facilitate the development of <mark style="background: #FF5582A6;">standardised protocols</mark>.
- The number of layers chosen was sufficient enough to ensure that distinct functions were not <mark style="background: #FF5582A6;">lumped</mark> together to become unwieldy,

The layers of software work together in unison to provide overall solutions to the problems of communicating between host computers across complex networks.

<mark style="background: #FF5582A6;">Information</mark> flows up-down the stack, across each of the interfaces (boundaries) between the layers:
- These boundaries were carefully defined to <mark style="background: #FF5582A6;">minimise</mark> information flow across the interfaces.
- The following slides discuss the functionality of each layer of protocol software. This functionality should be recognisable from previous discussions.

<mark style="background: #FF5582A6;">OSI model:</mark>
1. Application
2. Presentation
3. Session
4. Transport
5. Network
6. Data Link
7. Physical

The role of the <mark style="background: #FF5582A6;">Physical</mark> layer is to act as a medium and transmit pulses that represent 1s and 0s.

The Data Link layer interprets and deals with frames. Flow control, error control and error recovery.

Ethernet cables use Manchester encoding

Have to use an 802.11 protocol to communicate across a wireless mask

TCP/IP is a five layer model, more simplistic than OSI

Data works its way down from the model.

### <mark style="background: #FF5582A6;">The Physical Layer:</mark>

Concerned with transmitting <mark style="background: #FF5582A6;">raw</mark> bits over a <mark style="background: #FF5582A6;">communication channel</mark>:

Its purpose is to ensure that the transmission of binary 1s and 0s adheres to what is appropriate for the transmission medium and what is expected by the <mark style="background: #FF5582A6;">receiver</mark>.

<mark style="background: #FF5582A6;">Primarily it deals with matters such as:</mark> 
- What voltage levels are used? What frequencies are used? 
- How long does it take to transmit a bit (Bit Duration)? etc. 

There are certain design issues to address such as: the <mark style="background: #FF5582A6;">mechanical</mark> and <mark style="background: #FF5582A6;">electrical</mark> design of the plugs (RJ-45, BNC etc.) and sockets, timing interfaces, the physical <mark style="background: #FF5582A6;">transmission medium</mark> etc.

### <mark style="background: #FF5582A6;">The Data Link Layer:</mark>

Concerned with the successful transmission of data across an individual link.

Its purpose is to transform a <mark style="background: #FF5582A6;">raw</mark> transmission facility into a <mark style="background: #FF5582A6;">data communications channel</mark> that <mark style="background: #FF5582A6;">appears</mark> free of transmission errors.

Primarily it deals with matters such as the transmission/reception of <mark style="background: #FF5582A6;">data frames</mark>. 

<mark style="background: #FF5582A6;">There are certain design issues to address such as:</mark>
- the creation of localised unique addressing, 
- the creation of a unique framing structure, 
- flow control, 
- error control, 
- controlling access to a <mark style="background: #FF5582A6;">shared</mark> channel etc.

<mark style="background: #FF5582A6;">Example DL functionality:</mark> 
![](https://i.imgur.com/dIX7TeT.png)

### <mark style="background: #FF5582A6;">The Network Layer:</mark>

Concerned with the successful delivery of data between hosts across complex network infrastructures.

Its purpose is to control the operation of the <mark style="background: #FF5582A6;">sub-networks</mark> to achieve host-to-host delivery.

Primarily it deals with matters such as the routing of packets from the source station towards the <mark style="background: #FF5582A6;">destination</mark> station across sub-nets etc. 

<mark style="background: #FF5582A6;">There are certain design issues to address such as:</mark> 
- the creation a globally unique address space,
- the creation of a globally unique framing structure.

Essentially this layer is responsible for managing data communications across interconnected <mark style="background: #FF5582A6;">heterogeneous</mark> networks.

![](https://i.imgur.com/CDAKuAq.png)

### <mark style="background: #FF5582A6;">The Transport Layer:</mark>

This is a key layer. 

It is a true <mark style="background: #FF5582A6;">end-to-end</mark> layer responsible for the reliable delivery of data between <mark style="background: #FF5582A6;">processes</mark> on end-host machines i.e. process-to-process delivery.

Its purpose is to provide a reliable data transport service to applications.

Primarily, it deals with interfacing with applications for the purpose of exchanging data between applications across a network.

<mark style="background: #FF5582A6;">There are certain design issues to address, such as:</mark>
- multiplexing data streams from/to remote applications, 
- data loss,
- network latency, etc.

### <mark style="background: #FF5582A6;">Data Flows:</mark>

The layers work together to provide the complete functionality required to facilitate communications between two remotely connected host machines regardless of how they connect to the internet.

The following slide shows how data flows between the layers (up-and-down):

Note that sometimes it is necessary to break up the data to meet some size restrictions associated with some lower layer protocol software. Recall use of <mark style="background: #FF5582A6;">Fragmentation</mark> at the Network layer.

Encapsulation and Information flow between the layers on an end-host.

![](https://i.imgur.com/FU1KSte.png)

Some of the layers are also implemented on intermediary networking devices such as Routers. This is because the functionality associated with these layers is needed for a particular purpose such as frame reception/transmission or packet routing etc.

The following slide shows how the complete set of layers are implemented on the end-hosts as well as on the intermediary networking devices.

### <mark style="background: #FF5582A6;">Repeater Implementation:</mark>

<mark style="background: #FF5582A6;">Repeater:</mark>
![](https://i.imgur.com/F4nJIkE.png)

<mark style="background: #FF5582A6;">Bridge:</mark>
![](https://i.imgur.com/Wk7RgyN.png)

<mark style="background: #FF5582A6;">Router:</mark>
![](https://i.imgur.com/KmI9XwZ.png)

The <mark style="background: #FF5582A6;">repeater</mark> deals only with the physical layer.

The <mark style="background: #FF5582A6;">bridge</mark> deals with the data link and physical layer.

The <mark style="background: #FF5582A6;">router</mark> deals with the network, data link and physical layer.

# <mark style="background: #FF5582A6;">02 Revision - IP</mark>

### <mark style="background: #FF5582A6;">Format of Internet Packets:</mark>

The IP software defines its own internet packet format known as an <mark style="background: #FF5582A6;">IP datagram</mark>.

It is a <mark style="background: #FF5582A6;">universal</mark>, <mark style="background: #FF5582A6;">virtual</mark> packet which has a particular format/structure which is very different to that of a hardware frame.

It can carry a <mark style="background: #FF5582A6;">single</mark> octet of data or multiple octets up to a maximum of <mark style="background: #FF5582A6;">64K</mark> octets (including the header)

### <mark style="background: #FF5582A6;">IP datagram header format:</mark>

![](https://i.imgur.com/afycdXO.png)

### <mark style="background: #FF5582A6;">Forwarding an IP datagram:</mark>

Recall that a router makes its routing decision based on the <mark style="background: #FF5582A6;">destination IP address</mark>.

Routing information is stored in a <mark style="background: #FF5582A6;">routing table</mark>. This table must be <mark style="background: #FF5582A6;">initialised on boot-up</mark> and <mark style="background: #FF5582A6;">updated</mark> if the topology changes.

The next three slides show example <mark style="background: #FF5582A6;">Routing Tables</mark>:
- The first slide recalls a high-level <mark style="background: #FF5582A6;">Routing Table</mark> from previous discussions,
- The second and third slides shows a <mark style="background: #FF5582A6;">Routing Table</mark> from a real router.

![](https://i.imgur.com/FyJCz28.png)

![](https://i.imgur.com/hvE88uM.png)

Note the network numbers and the connections to the routers.

The Routing Table router 1 (R1) is shown on the next slide.

![](https://i.imgur.com/uNmEBdF.png)

The <mark style="background: #FF5582A6;">physical network</mark> does not understand the datagram format.

Instead the datagram is placed in the <mark style="background: #FF5582A6;">data area</mark> of a <mark style="background: #FF5582A6;">hardware frame</mark>.

This is known as <mark style="background: #FF5582A6;">encapsulation</mark>.

![](https://i.imgur.com/pB3xJZ3.png)

### <mark style="background: #FF5582A6;">IP Encapsulation:</mark>

This process is applied on each leg of the transmission path.

The datagram is stored in memory without the additional frame header information.

The size of the frame header may vary as it traverses different network technologies.

![](https://i.imgur.com/if8mwjQ.png)

### <mark style="background: #FF5582A6;">IP Datagram and the internet:</mark>

![](https://i.imgur.com/6ZrjhyF.png)

### <mark style="background: #FF5582A6;">Encapsulation and Information flow between the layers on an end-host</mark>

![](https://i.imgur.com/R0CrDL7.png)

# <mark style="background: #FF5582A6;">04 Five Layer Protocol Model</mark>

### <mark style="background: #FF5582A6;">The ISO OSI Model</mark>

![](https://i.imgur.com/t70Q8KL.png)

<mark style="background: #FF5582A6;">The Application Layer:</mark> 
- Contains a <mark style="background: #FF5582A6;">variety</mark> of protocols commonly used on the Internet
- E.g. HTTP (HyperText Transfer Protocol) is the underlying protocol for the World Wide Web
- Other protocols include FTP, E-mail etc.

<mark style="background: #FF5582A6;">The Presentation Layer:</mark> 
- Concerned with the <mark style="background: #FF5582A6;">syntax</mark> and <mark style="background: #FF5582A6;">semantics</mark> of the information transmitted
- Facilitates communication between <mark style="background: #FF5582A6;">big-endian</mark> computers e.g. Sun Sparcs and <mark style="background: #FF5582A6;">little-endian</mark> computers e.g. Windows machines

<mark style="background: #FF5582A6;"> The Session Layer:</mark>  
- Facilitates the use of sessions between end stations. During a session the user and the computer system engage in a <mark style="background: #FF5582A6;">dialogue</mark>
- The session layer establishes and maintains dialogues
- It also determines the type of control to be used i.e. two-way simultaneous communication, two-way alternate comm. or one-way comm.
- It facilitates <mark style="background: #FF5582A6;">re-synchronisation</mark> of the dialogue after a crash

<mark style="background: #FF5582A6;">The Transport Layer:</mark> 
- This is a key layer. It is a true <mark style="background: #FF5582A6;">end-to-end</mark> layer
- Its function is to isolate the applications from the underlying network hardware technology
- It splits the source data into manageable chunks and passes them to the network layer 
- It uses the network as a reliable ‘deliverer’ of data

<mark style="background: #FF5582A6;">The Network Layer:</mark> 
- Concerned with controlling the operation of the <mark style="background: #FF5582A6;">sub-network</mark> (subnet)
- Deals with the routing of <mark style="background: #FF5582A6;">packets</mark> from the <mark style="background: #FF5582A6;">source</mark> station towards the <mark style="background: #FF5582A6;">destination</mark> station across sub-nets 
- It handles the different sub-net addressing formats 
- Essentially this layer is responsible for interconnecting <mark style="background: #FF5582A6;">heterogeneous</mark> networks 

<mark style="background: #FF5582A6;">The Data Link Layer:</mark> 
- Concerned with getting data across an individual link 
- Essentially it transforms a <mark style="background: #FF5582A6;">raw</mark> transmission facility into a <mark style="background: #FF5582A6;">data communications channel</mark> that appears free of transmission errors
- Breaks up the data into <mark style="background: #FF5582A6;">data frames</mark>. Also deals with flow control, controlling access to a <mark style="background: #FF5582A6;">shared</mark> channel etc.

<mark style="background: #FF5582A6;">The Physical Layer:</mark> 
- Concerned with transmitting <mark style="background: #FF5582A6;">raw</mark> bits over a <mark style="background: #FF5582A6;">communication channel</mark>. Must ensure that when a binary 1 is sent it is received as such by the <mark style="background: #FF5582A6;">receiver</mark>
- Deals with voltage levels used, bit duration etc. 
- Design issues deal with <mark style="background: #FF5582A6;">mechanical</mark>, <mark style="background: #FF5582A6;">electrical</mark>, and <mark style="background: #FF5582A6;">timing interfaces</mark>, and the physical <mark style="background: #FF5582A6;">transmission medium</mark>

![](https://i.imgur.com/XBAKdJr.png)

### <mark style="background: #FF5582A6;">TCP/IP Reference Model:</mark>

![](https://i.imgur.com/VYOqIHX.png)

The protocols upon which this model is based (<mark style="background: #FF5582A6;">TCP and IP</mark>) fuelled the early growth of the <mark style="background: #FF5582A6;">Internet</mark>:
- TCP and IP were adapted because they were available 
- The ISO protocols on the other hand were still being developed

The <mark style="background: #FF5582A6;">TCP/IP Reference Model</mark> was developed <mark style="background: #FF5582A6;">after</mark> the protocols.

Specific design goals of this <mark style="background: #FF5582A6;">Reference Model</mark> included:
- Ability to survive the loss of subnet hardware
- Ability to handle multiple types of data including files and real-time speech

These requirements led to the adoption of a connectionless packet-switching network within the <mark style="background: #FF5582A6;">internet</mark> layer.

<mark style="background: #FF5582A6;">The Internet Layer:</mark> 
- This layer is key to the whole architecture.
- It facilitates hosts injecting packets into any network. 
- It ensures correct routing of packets to the Destination station. 

<mark style="background: #FF5582A6;">The Transport Layer:</mark> 
- Facilitates <mark style="background: #FF5582A6;">end-to-end</mark> communication between the Source and Destination hosts.

<mark style="background: #FF5582A6;">Two end-to-end transport protocols have been defined:</mark>
- <mark style="background: #FF5582A6;">TCP (Transmission Control Protocol):</mark> This is a <mark style="background: #FF5582A6;">reliable</mark>, <mark style="background: #FF5582A6;">connection-oriented</mark> protocol that allows a byte stream originating on one machine to be delivered <mark style="background: #FF5582A6;">without</mark> error to any other machine in the internet. 
- <mark style="background: #FF5582A6;">UDP (User Datagram Protocol):</mark> This is an <mark style="background: #FF5582A6;">unreliable</mark>, <mark style="background: #FF5582A6;">connectionless</mark> protocol for applications that provide their own <mark style="background: #FF5582A6;">sequencing</mark> and <mark style="background: #FF5582A6;">flow control</mark> functionality

<mark style="background: #FF5582A6;">The Application Layer:</mark> 
- This layer contains all of the higher-level protocols including FTP, E-mail, the Domain Name System (DNS) and HTTP.

<mark style="background: #FF5582A6;">The Host-to-Network or Network Interface Layer:</mark>
- This layer is meant to deal with hosts connecting to the network - similar to the ISO OSI Data Link layer.

<mark style="background: #FF5582A6;">The Physical Layer:</mark>
- Similar to the Physical layer of the ISO OSI model.

These lower two layers are not well defined within the TCP/IP reference model

### <mark style="background: #FF5582A6;">Relationship between TCP, UDP and IP</mark>

![](https://i.imgur.com/w1mpP9I.png)

### <mark style="background: #FF5582A6;">A comparison of OSI and TCP/IP Reference Models:</mark>

<mark style="background: #FF5582A6;">Both models are similar in many ways:</mark>
- Both use the concept of a stack of independent protocols
- Both transport layers provide an end-to-end, network-independent transport service to applications

However, there are some notable differences as follows:

<mark style="background: #FF5582A6;">Number of layers:</mark> 
- OSI model has 7 layers, 
- TCP/IP has 5 layers

<mark style="background: #FF5582A6;">Services versus Interfaces/Protocols:</mark>
- OSI clearly defines what each layer does using service definitions
- TCP/IP did not originally clearly distinguish between service, interface and protocol. This hindered switching-out protocols to facilitate technological change.

<mark style="background: #FF5582A6;">Timing:</mark>
- OSI model was developed before the protocols were created.
- With TCP/IP the protocols came first and then the model.

### <mark style="background: #FF5582A6;">Conceptual vs Realistic view of Protocol layering</mark>

![](https://i.imgur.com/CLCo2Cc.png)

### <mark style="background: #FF5582A6;">The Layers in Operation:</mark>

<mark style="background: #FF5582A6;">Application and presentation:</mark>
![](https://i.imgur.com/iRZbLBI.png)

![](https://i.imgur.com/sRQWR6h.png)

<mark style="background: #FF5582A6;">The session layer:</mark>
![](https://i.imgur.com/3kPSoAP.png)

<mark style="background: #FF5582A6;">Transport and Network:</mark>
![](https://i.imgur.com/qVEqlGQ.png)
![](https://i.imgur.com/ZuNppS9.png)

<mark style="background: #FF5582A6;">Data Link and Physical:</mark>
![](https://i.imgur.com/YFiiU0b.png)

![](https://i.imgur.com/bBVBrS3.png)

### <mark style="background: #FF5582A6;">Design Issues for Layered Software:</mark>

<mark style="background: #FF5582A6;">There are a number of key design issues common to several layers:</mark>
- <mark style="background: #FF5582A6;">Addressing:</mark> Each layer needs to be able to identify senders and receivers. Some form of addressing is required
- <mark style="background: #FF5582A6;">Error control:</mark> The receiver must be able to tell the sender which messages have been correctly received and which have not
- <mark style="background: #FF5582A6;">Sequencing:</mark> The protocol software on the the receiver must be able to re-sequence incoming messages
- <mark style="background: #FF5582A6;">Flow Control:</mark> The receiver must be able to control the flow of information from the sender

The following are two examples of network <mark style="background: #FF5582A6;">models</mark>, namely the <mark style="background: #FF5582A6;">OSI</mark> and <mark style="background: #FF5582A6;">TCP/IP</mark> reference models

These form the basis for many of today’s <mark style="background: #FF5582A6;">network architectures</mark>

<mark style="background: #FF5582A6;">Operation of TCP/IP - Sender:</mark>
![](https://i.imgur.com/VNiWUzl.png)


1. <mark style="background: #FF5582A6;">Preparing the data.</mark> The application protocol prepares a block of data for transmission. For example, an email message (SMTP), a file (FTP). a block of user input (TELNET).
2. <mark style="background: #FF5582A6;">Using a common syntax.</mark> If necessary, data is converted to a form expected by the destination. This may include a different character code, the use of encryption. and/or compression.
3. <mark style="background: #FF5582A6;">Segmenting the data.</mark> TCP may break data block into a number of segments, keeping track of their sequence. Each TCP segment includes a header containing a sequence number and a frame check sequence to detect errors.
4. <mark style="background: #FF5582A6;">Duplicating segments.</mark> A copy is made of each TCP segment, in case the loss or damage of a segment necessitates retransmission. When an acknowledgment is received from the other TCP entity, a segment is erased.
5. <mark style="background: #FF5582A6;">Fragmenting the segments.</mark> IP may break a TCP segment into a number of datagrams to meet size requirements of intervening networks. Each datagram includes a header containing a destination address, a frame check sequence, and other control information.
6. <mark style="background: #FF5582A6;">Framing.</mark> An ATM header is added to each IP datagram to form an ATM cell. The header contains a connection identifier and a header error control field.
7. <mark style="background: #FF5582A6;">Transmission.</mark> Each cell is transmitted over the medium as a sequence of bits.

 <mark style="background: #FF5582A6;">Peer-to-peer dialogue.</mark> 
 1. Before data is sent, the sending and receiving applications agree on format and encoding, then agree to exchange data
 2. The two TCP entities agree to a connection.
 3. Each IP datagram is forwarded through networks and routers to the destination system.
 4. Each cell is forwarded through the ATM network
 5. <mark style="background: #FF5582A6;">Peer-to-Peer dialogue:</mark> The router will pass this datagram onto another router or to destination system.

<mark style="background: #FF5582A6;">Operation of TCP/IP Router and Receiver:</mark>
![](https://i.imgur.com/21zWJiZ.png)
![](https://i.imgur.com/odytNcZ.png)

8. <mark style="background: #FF5582A6;">Arriving at router:</mark> The incoming signal is received over the transmission medium and interpreted as a cell of bits.
9. <mark style="background: #FF5582A6;">Processing the cell:</mark> the ATM layer removes the cell header and processes it. The header error control system is used for detection. The connection number identifies the source.
10. <mark style="background: #FF5582A6;">Routing the packet:</mark> IP examines the IP header and makes a routing decision. It determines which outgoing link is to be used and then passes datagram back to the link layer for transmission on that link.
11. <mark style="background: #FF5582A6;">Forming LLC PDU:</mark> An LLC (Logical Link Control) header is added to each IP datagram to form an LLC PDU. The header contains sequence number and address information. The trailer contains a frame sequence check.
12. <mark style="background: #FF5582A6;">Framing:</mark> A MAC header and trailer is added to each LLC PDU, forming a MAC frame. The header contains address information and the trailer contains a frame check sequence.
13. <mark style="background: #FF5582A6;">Transmission:</mark> Each frame is transmitted over the medium as a sequence of bits.
14. <mark style="background: #FF5582A6;">Arriving at destination:</mark> The incoming signal is received over the transmission medium and interpreted as a frame of bits.
15. <mark style="background: #FF5582A6;">Processing the frame:</mark> MAC layer removes the header and trailer and processes them. The frame check sequence is used for error detection.
16. <mark style="background: #FF5582A6;">Processing the LLC PDU:</mark> The LLC layer removes the header and processes it. The sequence number is used for flow and error control.
17. <mark style="background: #FF5582A6;">Processing the IP datagram:</mark> IP removes the header. The frame check sequence and other control information are processed.
18. <mark style="background: #FF5582A6;">Processing the TCP segment:</mark> TCP removes the header. It checks the frame check sequence and acknowledges if there is a match and discards for mismatch. Flow control is also performed.
19. <mark style="background: #FF5582A6;">Reassembling user data:</mark> If TCP has broken the user data into multiple segments, these are reassembled and the block is passed up to the application.
20. <mark style="background: #FF5582A6;">Delivering the data:</mark> The application performs any needed transformations, including decompression and decryption. and directs the data to the appropriate file or other destination.

# <mark style="background: #FF5582A6;">05 Client Server:</mark>

### <mark style="background: #FF5582A6;">Network Programming and Applications:</mark>

<mark style="background: #FF5582A6;">Previously</mark> we looked at some of the services that a network provides

A data network is a <mark style="background: #FF5582A6;">passive</mark> entity, it neither <mark style="background: #FF5582A6;">generates</mark> nor <mark style="background: #FF5582A6;">understands</mark> the data being sent.

<mark style="background: #FF5582A6;">Now, we look at computer networks from an application perspective:</mark>
- Applications that use computer networks operate in pairs; the <mark style="background: #FF5582A6;">client</mark> and the <mark style="background: #FF5582A6;">server</mark>.
- Typically these applications run on hosts that are remote from each other.
- Between the host machines there is a network across which the data must travel.

<mark style="background: #FF5582A6;">Server applications run on server-class machines</mark>:
- Sometimes these are mistakenly referred to as <mark style="background: #FF5582A6;">servers</mark>,
- <mark style="background: #FF5582A6;">Servers</mark> are applications and the machines on which they run are server-class machines.

Client applications can run on any machine.

Server applications play a vital role in modern networked applications. They are continuously running, waiting for contact from Client applications. 

Some texts use the analogy of two people communicating over the telephone network to represent client-server communications. However, the analogy falls short as there are some unique challenges when writing client and server  applications which we will explore in the lab.

### <mark style="background: #FF5582A6;">Making Contact - Client Server Interaction:</mark>

How does an application know when a message has arrived? 

<mark style="background: #FF5582A6;">It’s not so straight forward with applications:</mark>
- Before any inter-application communication can take place an application must interact with its local protocol software to notify it to expect <mark style="background: #FF5582A6;">messages</mark> of a specific <mark style="background: #FF5582A6;">type</mark>,
- The application then waits <mark style="background: #FF5582A6;">passively</mark> for contact from remote applications.

### <mark style="background: #FF5582A6;">Client-Server Interaction:</mark>

The protocol software examines incoming messages and passes <mark style="background: #FF5582A6;">matching</mark> messages to the application.

The application that is continuously running, passively waiting for contact from other applications is called a <mark style="background: #FF5582A6;">server</mark>.

The application that actively initiates contact with a server is called a <mark style="background: #FF5582A6;">client</mark>.

This is known as the <mark style="background: #FF5582A6;">client-server</mark> paradigm.

### <mark style="background: #FF5582A6;">Characteristics of Clients:</mark>

<mark style="background: #FF5582A6;">In general, client software has the following characteristics:</mark>
- It provides general purpose computational functionality to a user but on occasion it becomes a <mark style="background: #FF5582A6;">client application</mark>
- It is invoked directly by a user and executes for one session
- It runs locally on a user's personal computer
- It actively <mark style="background: #FF5582A6;">initiates</mark> contact with a server
- It can access multiple services but can only contact one <mark style="background: #FF5582A6;">server</mark> at a time
- It does not require specialised hardware or a sophisticated operating system

### <mark style="background: #FF5582A6;">Characteristics of Servers:</mark>

<mark style="background: #FF5582A6;">In general, server software has the following characteristics:</mark>
- It is a special-purpose, <mark style="background: #FF5582A6;">privileged</mark> program dedicated to providing one <mark style="background: #FF5582A6;">service</mark>
- It can handle multiple remote clients simultaneously 
- It is invoked automatically upon boot-up, and executes through many sessions
- It runs on a shared computer 
- It passively waits for and accepts contact from <mark style="background: #FF5582A6;">arbitrary</mark> remote clients
- It requires powerful hardware and a sophisticated operating system

### <mark style="background: #FF5582A6;">Multiple Services on one computer:</mark>

<mark style="background: #FF5582A6;">Some server-class machines run clients and servers simultaneously:</mark> 
- These computers have an operating system that allows multiple application programs to execute <mark style="background: #FF5582A6;">concurrently</mark> (e.g., UNIX or Windows). 
- For each service offered there must be an associated server program executing e.g. a single computer might run a <mark style="background: #FF5582A6;">file server</mark> and a <mark style="background: #FF5582A6;">World Wide Web server</mark>
- The following diagram illustrates this

![](https://i.imgur.com/DHHduvU.png)

With <mark style="background: #FF5582A6;">multiple</mark> servers running, how can a client identify a <mark style="background: #FF5582A6;">particular</mark> server <mark style="background: #FF5582A6;">unambiguously</mark>?

<mark style="background: #FF5582A6;">Some form of addressing is required:</mark>
- Each server is assigned a unique identifier
- <mark style="background: #FF5582A6;">Clients</mark> and <mark style="background: #FF5582A6;">servers</mark> use this identifier in <mark style="background: #FF5582A6;">all</mark> interactions 

The <mark style="background: #FF5582A6;">communications paradigm</mark> is as follows:
- The server application starts execution first
- It registers its identifier with the local protocol software
- It then waits for contact from clients
- <mark style="background: #FF5582A6;">Clients</mark> contact <mark style="background: #FF5582A6;">servers</mark> by specifying the server’s <mark style="background: #FF5582A6;">location</mark> and <mark style="background: #FF5582A6;">unique identifier</mark> 
- The client and server exchange messages and terminate communication

# <mark style="background: #FF5582A6;">06 The Transport Layer:</mark>

Having examined the TCP/IP Protocol Reference the focus now shifts to the TCP layer.

This layer is the heart of the whole protocol hierarchy.

It sits below the Application Layer providing a ‘Transport’ service to the applications that wish to communicate across a Network.

![](https://i.imgur.com/vzkY477.png)

TCP provides a reliable, cost-effective end-to-end data transport service <mark style="background: #FF5582A6;">independently</mark> of the physical network(s).

It is important to realise that a <mark style="background: #FF5582A6;">service</mark> is very different to a <mark style="background: #FF5582A6;">protocol</mark>, although they are frequently confused.

The next slide shows how the Transport Layer views the lower network interface layers.

### <mark style="background: #FF5582A6;">The Transport Layer's view of the Network:</mark>

![](https://i.imgur.com/id8kaxc.png)

### <mark style="background: #FF5582A6;">Services:</mark>

<mark style="background: #FF5582A6;">Each layer of the reference model provides a set of functionality to the layer immediately above:</mark>
- This set of functionalities is known as <mark style="background: #FF5582A6;">the Services</mark>.
- The layer below is known as the <mark style="background: #FF5582A6;">Service Provider</mark> and the layer above is known as the <mark style="background: #FF5582A6;">Service User</mark>

The Services are accessed through the interface between the layers.

### <mark style="background: #FF5582A6;">Protocols:</mark>

<mark style="background: #FF5582A6;">Protocols</mark>, on the other hand, are how the Services are implemented.

Typically a Protocol specifies a <mark style="background: #FF5582A6;">framing structure</mark> which will include a number of fields containing Control data:
- Generically this framing structure is known as a Protocol Data Unit (<mark style="background: #FF5582A6;">PDU</mark>)
- Examples include Data Link Frame, IP Datagram etc.

The <mark style="background: #FF5582A6;">Protocol</mark> will also typically specify a procedure for interpreting and responding to the Control data within the PDU:
- For instance, if a service provides for reliable transfer of data then there must be some means specified within the protocol for tracking and recovering from data loss.
- In this instance part of the PDU Control field will include numbering e.g. byte numbers, frame numbers etc.

The Protocol will also specify how data in the Control Fields are to be interpreted and responded to if necessary, e.g. for missing frame return a REJ message.

### <mark style="background: #FF5582A6;">The TCP Transport Service Offering:</mark>

<mark style="background: #FF5582A6;">The TCP Transport Service has the following characteristics:</mark>
- <mark style="background: #FF5582A6;">Connection Orientation:</mark> Before two applications' entities can communicate they must first establish a connection.
- <mark style="background: #FF5582A6;">Point-To-Point Communication:</mark> Each TCP connection has exactly two endpoints. 
- <mark style="background: #FF5582A6;">Complete Reliability:</mark> TCP guarantees that the data will be delivered exactly as sent i.e. no data missing or out of sequence 
- <mark style="background: #FF5582A6;">Full Duplex Communication:</mark> 
	- A TCP connection allows data to flow in either direction
	- TCP buffers outgoing and incoming data 
	- This allows applications to continue executing other code whilst the data is being transferred
- <mark style="background: #FF5582A6;">Stream Interface:</mark> 
	- The <mark style="background: #FF5582A6;">source</mark> application sends a continuous sequence of octets across a connection
	- The data is passed en-bloc to TCP for delivery
	- TCP does not guarantee to deliver the data in the same size pieces that it was transferred by the source application.
- <mark style="background: #FF5582A6;">Reliable Connection Startup:</mark> TCP both applications to <mark style="background: #FF5582A6;">agree</mark> to any new connection
- <mark style="background: #FF5582A6;">Graceful Connection Shutdown:</mark> Either can request a connection to be shut down. TCP guarantees to deliver all the data reliably before closing the connection.

### <mark style="background: #FF5582A6;">The Transport Service:</mark>

The TCP transport service is offered to a <mark style="background: #FF5582A6;">user process</mark> that exists within the application layer:
- This user process is considered a <mark style="background: #FF5582A6;">Transport Service User</mark>,
- The service is typically offered through a set of <mark style="background: #FF5582A6;">primitives</mark> across the interface between the layers,
- Calls to these primitives cause the transport service provider to perform some action. 

### <mark style="background: #FF5582A6;">The Transport Entity:</mark>

The TCP software within the transport layer that implements the service will be referred to as the <mark style="background: #FF5582A6;">Transport Entity</mark>: This is the “Transport Service Provider”.

The <mark style="background: #FF5582A6;">Transport Entity</mark> can be located in any number of places including:
- Within the operating system (OS) kernel,
- As a separate user process,
- Within a library package bound to the network application,
- On the network interface card.

If the <mark style="background: #FF5582A6;">protocol stack</mark> is located within the OS the <mark style="background: #FF5582A6;">primitives</mark> are implemented as <mark style="background: #FF5582A6;">system calls</mark>:
- These calls turn control of the machine over to the OS to send and receive the necessary PDUs.
- The next diagram shows the Transport Entity in context.
- As can be seen it shows the Transport Layer sitting between the Application and Network layers.

![](https://i.imgur.com/RigRyEM.png)

<mark style="background: #FF5582A6;">It has a connection to each of the layers above and below:</mark>
- It is the <mark style="background: #FF5582A6;">Service Provider</mark> to the Application Layer and,
- A <mark style="background: #FF5582A6;">Service User</mark> of the Network Layer.

The TPDU represents the framing structure that is exchanged between <mark style="background: #FF5582A6;">Peer Entities</mark>:
- The PDU does NOT move <mark style="background: #FF5582A6;">horizontally</mark> between the Transport layers as depicted,
- Instead it moves <mark style="background: #FF5582A6;">up-and-down</mark> through the Protocol Stack.

### <mark style="background: #FF5582A6;">Transport Service Primitives:</mark>

What do these primitives look like?

<mark style="background: #FF5582A6;">Consider a generic transport interface as shown in the next diagram:</mark> 
- Here can be seen a list of Primitives.
- These primitives allow application programs to establish, use and release connections.

Typically there is a very precise sequence of calls to these primitives. The exact sequence differs for clients and servers.

![](https://i.imgur.com/M0GOvvv.png)

![](https://i.imgur.com/OcYQYDU.png)

### <mark style="background: #FF5582A6;">Managing Connections:</mark>

Before explaining the sequence of primitive calls it is important to understand the Phases of Communication.

Recall from previous discussions on HDLC that there are generally three phases of communication associated with a connection-oriented service:
- <mark style="background: #FF5582A6;">Phase 1:</mark> Connection Establishment,
- <mark style="background: #FF5582A6;">Phase 2:</mark> Data Transfer,
- <mark style="background: #FF5582A6;">Phase 3:</mark> Connection Release.

During each phase a variety of PDUs are exchanged between the <mark style="background: #FF5582A6;">client</mark> and <mark style="background: #FF5582A6;">server</mark>:
- Each PDU contains a message destined for the peer entity on the remote end of the channel.
- The following slides explain the interaction for each phase.

### <mark style="background: #FF5582A6;">Connection interactions per phase:</mark>

<mark style="background: #FF5582A6;">Connection Establishment Phase:</mark>
1. The server application executes a ``LISTEN`` primitive (aka a <mark style="background: #FF5582A6;">call to Listen</mark>).
2. The server’s <mark style="background: #FF5582A6;">transport entity</mark> responds to this primitive call by: <mark style="background: #FF5582A6;">Blocking</mark> the server until a client request arrives.
3. The client application <mark style="background: #FF5582A6;">then</mark> executes a ``CONNECT`` primitive (aka <mark style="background: #FF5582A6;">call to Connect</mark>).
4. The client’s transport entity responds to this call by <mark style="background: #FF5582A6;">blocking</mark> the client <mark style="background: #FF5582A6;">and</mark> sending a ``CONNECTION REQUEST TPDU`` to the Server.
5. Upon receipt of the ``CONNECTION REQUEST TPDU`` the server’s <mark style="background: #FF5582A6;">transport entity</mark>: Unblocks the server <mark style="background: #FF5582A6;">and</mark> returns a ``CONNECTION ACCEPTED TPDU`` to the Client,
6. The client’s transport entity then unblocks the client.
7. The connection is now deemed <mark style="background: #FF5582A6;">established</mark>

<mark style="background: #FF5582A6;">Data Transfer Phase:</mark>
- With an <mark style="background: #FF5582A6;">active</mark> connection now established data can be exchanged between the client and server using the ``SEND`` and ``RECEIVE`` primitives,
- Each side must take turns using (blocking) <mark style="background: #FF5582A6;">RECEIVE</mark> and <mark style="background: #FF5582A6;">SEND</mark>.

<mark style="background: #FF5582A6;">Release Phase:</mark>
- Either the client or the server application can call a ``DISCONNECT`` primitive
- This causes a ``DISCONNECT TPDU`` to be sent to the remote transport entity.
- Once the ``DISCONNECT TPDU`` has been received and acknowledged the connection is deemed <mark style="background: #FF5582A6;">released</mark>.

### <mark style="background: #FF5582A6;">Berkeley Sockets:</mark>

The basic transport primitives discussed above are <mark style="background: #FF5582A6;">not</mark> standardised.

Instead most OS designers have adopted the <mark style="background: #FF5582A6;">socket 
primitives</mark>:
- These originated from the Berkeley University of California’s UNIX OS which contained the original <mark style="background: #FF5582A6;">TCP/IP</mark> suite of internetworking protocols.

Consequently the socket API has become the <mark style="background: #FF5582A6;">de facto</mark> standard for interfacing to TCP/IP

### <mark style="background: #FF5582A6;">Origins of the socket concept:</mark>

Coming from a UNIX background <mark style="background: #FF5582A6;">sockets</mark> use many concepts found in UNIX: An application communicates through a <mark style="background: #FF5582A6;">socket</mark> in the same way that it transfers data to or from a file 

For File I/O UNIX uses an <mark style="background: #FF5582A6;">open-read-write-close</mark> paradigm, an application makes the following calls in strict order:
- <mark style="background: #FF5582A6;">open</mark> to prepare a file for reading/writing,
- <mark style="background: #FF5582A6;">read</mark> or <mark style="background: #FF5582A6;">write</mark> to retrieve or send data to/from the file,
- <mark style="background: #FF5582A6;">close</mark> to release the file.

When ``open`` is first called a <mark style="background: #FF5582A6;">descriptor</mark> is returned:
- All calls to the file use this <mark style="background: #FF5582A6;">descriptor</mark>,
- Socket communication also uses this <mark style="background: #FF5582A6;">descriptor</mark> approach.

### <mark style="background: #FF5582A6;">Socket Communication in UNIX:</mark>

Applications that need to use the TCP/IP protocols to communicate must request the OS to create a <mark style="background: #FF5582A6;">socket</mark>: This is an abstract concept which will be explained in detail later.

Similar to File I/O, the OS returns a descriptor that uniquely identifies the socket. As with File I/O this descriptor must be used in all interactions with the socket.

The following slides lists the Socket API primitives and illustrates an example of how these primitives are used by a client and server application

![](https://i.imgur.com/20vSvhc.png)

### <mark style="background: #FF5582A6;">An Example Client-Server Interaction using sockets:</mark>

![](https://i.imgur.com/AZHFzWK.png)


### <mark style="background: #FF5582A6;">The Socket Primitives - Explained:</mark>

<mark style="background: #FF5582A6;">The following primitives are executed by servers:</mark>
- <mark style="background: #FF5582A6;">SOCKET:</mark> 
	- This primitive creates a new <mark style="background: #FF5582A6;">end point</mark> within the Transport Entity:
	- Table space is allocated within the transport entity,
	- A file descriptor is returned which is used in all future calls
- <mark style="background: #FF5582A6;">BIND:</mark> This primitive binds a socket to a network address. This allows remote clients to connect to it
- <mark style="background: #FF5582A6;">LISTEN:</mark> This primitive allocates a queuing space within the transport entity for incoming call requests.
- <mark style="background: #FF5582A6;">ACCEPT:</mark> 
	- This primitive blocks the server waiting for an incoming connection:
	- Upon receipt of a connection request the <mark style="background: #FF5582A6;">transport entity</mark> creates a <mark style="background: #FF5582A6;">new</mark> socket identical to the original one and returns a file descriptor to the server.
	- The server <mark style="background: #FF5582A6;">forks off</mark> a new process or service thread to handle the <mark style="background: #FF5582A6;">connection</mark> on the new socket
	- The server <mark style="background: #FF5582A6;">also</mark> continues to wait for more connections on the original socket.

<mark style="background: #FF5582A6;">The following primitives are executed by clients:</mark> 
- ``SOCKET``: As before 
- ``CONNECT``: This primitive blocks the client and actively starts the connection process

<mark style="background: #FF5582A6;">The following primitives are executed by clients and 
servers:</mark> 
- ``SEND`` and ``RECV``: These primitives are used to transmit and receive data over the full-duplex connection 
- ``CLOSE``: This primitive releases the transport connection

### <mark style="background: #FF5582A6;">Sockets and Socket Libraries:</mark>

In most systems the socket functions are part of the OS.

<mark style="background: #FF5582A6;">Some systems, however, require a socket library to provide the interface to the transport entity:</mark>
- These operate differently to a native socket API, 
- The code for the library socket procedures are linked into the application program and resides in its address space, 
- Calls to a socket library pass control to the library routine as opposed to the OS.

Both implementations provide the same semantics from a programmer's perspective 

Applications using either implementation can be ported to other computer systems.

### <mark style="background: #FF5582A6;">Example use of Sockets:</mark>

The next slide shows an example Client application using the Sockets API.

It is a simple Daytime Client which connects to a Daytime Server for the purpose of retrieving the current date and time from the Server Host.

This application is written in ‘C’.

Lines 24, 41, 44 and 57 show four of the socket primitives being called. 

This programme will be explained in class and you will have a chance to compile and run it against a pre-compiled server.

![](https://i.imgur.com/fdrIRNq.png)
![](https://i.imgur.com/nXFqp8T.png)

# <mark style="background: #FF5582A6;">07 Berkely Sockets Addressing:</mark>

### <mark style="background: #FF5582A6;">Daytime Server Code:</mark>

![](https://i.imgur.com/GHC3NQ3.png)

### <mark style="background: #FF5582A6;">Overview of the daytime server:</mark>

Refer to the Daytime server code presented in class. 

<mark style="background: #FF5582A6;">The operation of the Daytime application is as follows:</mark>
- Client calls ``CONNECT`` to connect to the server,
- Server calls ``ACCEPT`` to accept the connection request,
- Server returns a formatted string using the ``SEND`` primitive 
- Server application calls ``CLOSE`` to close the connection,
- Client calls ``RECV`` to retrieve the data from the connection,
- Client closes the connection using the ``CLOSE`` primitive,
- The Client application terminates using ``exit(0)``;

<mark style="background: #FF5582A6;">Key points to note in the Daytime server code:</mark>
- Server address structure,
- Calls to ``bind()``, ``listen()`` and ``accept()``.

### <mark style="background: #FF5582A6;">The echo client-server:</mark>

Having explored the <mark style="background: #FF5582A6;">Daytime</mark> application, the next application to examine is the <mark style="background: #FF5582A6;">Echo</mark> Client and Server.

<mark style="background: #FF5582A6;">The essence of this application is as follows:</mark>
- The Client application sends (``send()``) a string (from the command-line) to the server across an open connection,
- The Server application reads (``recv()``) the string and returns it to the Client application (``send()``)exactly as it came in,
- Both applications call for the connection to be closed (``close()``).

#### <mark style="background: #FF5582A6;">The recv() primitive:</mark>

To complete this task it is necessary to understand the operation of the ``recv()`` primitive.

```C
while ((numBytes = recv(sock, recvbuffer, BUFSIZE - 1, 0)) >0) 
{
	recvbuffer[numBytes] = '\0'; 
	fputs(recvbuffer, stdout); 
}
```

<mark style="background: #FF5582A6;">The while loop is necessary as the data may not arrive across the connection in a single transfer:</mark>
- Recall that data arriving from the remote socket is stored in the ``RECV-Q`` buffer within the local TCP entity,
- Repeated calls to ``recv()`` are needed to transfer this data from TCP (the Transport layer) into the application (the Application layer).

``numBytes`` is the return value from ``recv()``, it represents the <mark style="background: #FF5582A6;">number of bytes</mark> read from the socket,

<mark style="background: #FF5582A6;">numBytes returns one of three values:</mark> 
- ``<1`` represents an error condition,
- ``0`` represents a closed connection i.e. remote application has called ``close()``, 
- ``>1`` represents an open connection with potentially more data to be received.

### <mark style="background: #FF5582A6;">Breaking from recv():</mark>

If the ``recv()`` primitive is used as above in the <mark style="background: #FF5582A6;">Echo</mark> ``Client`` and ``Server`` applications it will cause problems:
- Either or both applications will remain inside the loop,
- Refer to the solution discussed in class.

### <mark style="background: #FF5582A6;">Addressing:</mark>

A key aspect of Networked Applications, such as Daytime and Echo, is <mark style="background: #FF5582A6;">Addressing</mark>.

In order for the Client and Server applications to communicate with each other, some form of explicit addressing is required.

The Destination Server application requires an <mark style="background: #FF5582A6;">unambiguous (unique)</mark> address in order for the Source Client application to initiate a connection request:

Uniqueness can only be achieved using <mark style="background: #FF5582A6;">both IP and TCP addressing</mark>.

Recall that the IP layer is responsible for delivering datagrams/packets to remote hosts across an internetwork: It uses IP addressing to achieve this host-to-host delivery.

However, the data encapsulated inside these datagrams/packets is typically destined for an <mark style="background: #FF5582A6;">application</mark> in the Application Layer.

With potentially many applications residing in the Application layer, how does the data get to the correct application?

<mark style="background: #FF5582A6;">Transport Layer</mark> addressing plays a vital role in this task

### <mark style="background: #FF5582A6;">Transport Addressing:</mark>

Recall that transport protocols such as TCP provide services to the application layer.

To ensure unambiguous (unique) addressing of individual applications, the Transport layer provides its own addressing schema separate to the IP layer:
- These are generally known as <mark style="background: #FF5582A6;">Transport Service Access Points (TSAPs)</mark>,
- These TSAPs uniquely identify entities in the Transport layer known as end points,
- In TCP parlance, these end points are known as <mark style="background: #FF5582A6;">port numbers</mark> or more simply <mark style="background: #FF5582A6;">ports</mark>.

<mark style="background: #FF5582A6;">Port numbers are used by:</mark>
- Server applications to advertise their services and, to listen for Connection Requests.
- Client applications to uniquely identify a Server application when making a Connection Request.
- The <mark style="background: #FF5582A6;">network layer</mark> also defines <mark style="background: #FF5582A6;">end points</mark>. These are known as Network Service Access Points (NSAPs). IP addresses are examples of NSAPs.

The following slide illustrates the relationship between the NSAPs, TSAPs and transport connections.

### <mark style="background: #FF5582A6;">TSAPs, NSAPs and transport connections:</mark>

![](https://i.imgur.com/UHKnTOj.png)

### <mark style="background: #FF5582A6;">The TCP Port Number Range:</mark>

TCP Port numbers are sixteen bits long.

This creates a port number address space comprising approx. 65K addresses (16 bits implies 2<sup>16</sup> addresses) as follows:

![](https://i.imgur.com/bkuGzrP.png)

<mark style="background: #FF5582A6;">Reserved</mark> addresses are for well known applications such as HTTP (port 80), FTP (ports 20 and 21), Telnet (port 23) etc. These can only be allocated by users with SU privileges.

<mark style="background: #FF5582A6;">Ephemeral</mark> addresses are allocated by TCP to <mark style="background: #FF5582A6;">Client</mark> applications:
- It is not immediately obvious that Client applications require a port number,
- However, there needs to be a return address for data from the Server application.

Non-privileged addresses are for any other applications: This is the range that will be used in the lab exercises. 

It is important to note that the Ephemeral and <mark style="background: #FF5582A6;">Non-privileged</mark> ranges differ on different OS’s:
- Your home host may use different ranges depending on the OS used.
- On the Virtual Machines used in the labs, use the following command to view the range:
- ``sudo sysctl net.ipv4.ip_local_port_range``

### <mark style="background: #FF5582A6;">Socket Identifiers:</mark>

The concept of a ``socket`` or, ``end-point`` is complicated by the manner with which it is referenced within each of the Application and Transport layers:

Recall that from an Application layer perspective, sockets are referenced using a <mark style="background: #FF5582A6;">file descriptor</mark>:
- This is an ``integer`` descriptor similar to a <mark style="background: #FF5582A6;">file descriptor</mark> or <mark style="background: #FF5582A6;">file handle</mark>,
- Recall the ``int`` variable names used in the applications developed in lab: ``sock``, ``servSock``, ``clntSock`` etc.

From a TCP layer perspective, a ``socket`` is identified by a combination of an NSAP and TSAP separated by a colon (:)

Even though both layers are referencing the same entity – the ``socket``, the descriptors used are very different.

<mark style="background: #FF5582A6;">This difference is further complicated by the fact that the call to accept() returns a new socket:</mark>
- The <mark style="background: #FF5582A6;">listening</mark> socket and,
- The <mark style="background: #FF5582A6;">connected</mark> socket.

<mark style="background: #FF5582A6;">Referencing the connected socket from within the application is straightforward:</mark>
- A separate and unique ``int`` descriptor is returned,
- All interactions with the listening and connected sockets are obvious.

<mark style="background: #FF5582A6;">Referencing the connected socket from within the TCP layer is complicated:</mark>
- Each of the sockets will use the same NSAP:TSAP combination.
- To differentiate between the sockets, the <mark style="background: #FF5582A6;">socket-pair</mark> needs to be considered.

### <mark style="background: #FF5582A6;">Examining Socket Details:</mark>

<mark style="background: #FF5582A6;">Socket-pairs</mark> are used to identify TCP connections:

<mark style="background: #FF5582A6;">TCP connections can be viewed using the netstat utility:</mark>
- From the command-line prompt type: ``netstat –ntap``
- This returns details of active TCP connections within the host OS.

<mark style="background: #FF5582A6;">An explanation of the flags:</mark>
- ``‘n’`` reveals IP addresses in dotted-decimal **n**otation, 
- ``‘t’`` filters on **T**CP addresses only, 
- ``‘a’`` shows **a**ll connections,
- ``‘p’`` reveals the **p**rocess id details for each connection.

The following slide shows a sample output when the  <mark style="background: #FF5582A6;">netstat</mark> command is used.

### <mark style="background: #FF5582A6;">Examining Addressing Details:</mark>

<mark style="background: #FF5582A6;">From the server end:</mark>
![](https://i.imgur.com/hWjM6La.png)

<mark style="background: #FF5582A6;">From the client end:</mark>
![](https://i.imgur.com/9E4LwEe.png)

<mark style="background: #FF5582A6;">This shows:</mark>
- A server with listening and connected sockets on port 1022, 
- A client on an ephemeral port 4136.

Note the columns <mark style="background: #FF5582A6;">Local Address</mark> and <mark style="background: #FF5582A6;">Remote Address</mark>: These contain details of the <mark style="background: #FF5582A6;">socket</mark> at <mark style="background: #FF5582A6;">each</mark> end of a connection.

Notice how TCP refers to a <mark style="background: #FF5582A6;">socket</mark> using a NSAP:TSAP combination.

### <mark style="background: #FF5582A6;">Socket Pairs:</mark>

<mark style="background: #FF5582A6;">Each row in the output from netstat relates to a connection:</mark>
- A TCP connection can be considered as a connection between two sockets; a <mark style="background: #FF5582A6;">local</mark> socket and a <mark style="background: #FF5582A6;">remote</mark> socket. 
- The columns labelled <mark style="background: #FF5582A6;">Local Address</mark> and <mark style="background: #FF5582A6;">Remote Address</mark> contain details of the socket at <mark style="background: #FF5582A6;">each</mark> end of a connection.
- Notice how TCP refers to a <mark style="background: #FF5582A6;">socket</mark> using a ``NSAP:TSAP`` combination.

The combination of <mark style="background: #FF5582A6;">Local Address</mark> and <mark style="background: #FF5582A6;">Remote Address</mark> is the <mark style="background: #FF5582A6;">identifier</mark> for a connection:
- It is known as a <mark style="background: #FF5582A6;">Socket Pair</mark>.
- An example socket pair: {``147.252.30.9:1022``, ``147.252.234.34:4136``}

<mark style="background: #FF5582A6;">Socket Pairs</mark> are how TCP views connections.

For each connection, the detail contained in each row is reversed depending on which end of the connection the ``netstat`` command is run.

Using socket-pair identifiers enables TCP to separately and unique identify a server’s <mark style="background: #FF5582A6;">listening</mark> and potentially multiple <mark style="background: #FF5582A6;">connected</mark> sockets.

This is important when incoming data (incoming to the TCP layer) needs to be passed to a local socket.

How connections are established from a Socket Pair perspective: It assumes the following primitive calls have been made within each of the client an server applications.

![](https://i.imgur.com/sVKDmN8.png)

### <mark style="background: #FF5582A6;">Socket Pairs before Connection Establishment:</mark>

Before Connection Establishment

![](https://i.imgur.com/kGI8o6v.png)

A Client Connection Request is now sent to : ``206.62.226.35``, Port 21

The following slide shows the socket pairs relating to the connection after Connection Establishment.

### <mark style="background: #FF5582A6;">Sockets pairs after Connection Establishment:</mark>

![](https://i.imgur.com/LDPmYOB.png)

{0.0.0.0:80,0.0.0.0:\*}
{``serverip``:``serverport``, ``clientip``:``clientport``}
{``localIP``:``localPort``,``remoteIP``:``remotePort``}

# <mark style="background: #FF5582A6;">08 Addressing Structures</mark>

### <mark style="background: #FF5582A6;">Addressing Infromation:</mark>

Very often there is a need to exchange addressing information between the Application layer and the TCP layer.

<mark style="background: #FF5582A6;">Both the client and server need to do this after the socket has been created.</mark>
- The client needs to pass the contact details for the server before the Connect Primitive is called.
- The server needs to inform the TCP of the address that it wants to listen on. This is used by the Bind Primitive.

Occasionally, there is a need to pass information in the reverse direction i.e. TCP to Application layer. This will be looked at another time.

<mark style="background: #FF5582A6;">All addressing information, regardless of direction, must be:</mark>
- Of the correct byte order (discussed shortly) and,
- Only be passed by <mark style="background: #FF5582A6;">reference</mark> through a standardised address structure.

This structure is specified by the Sockets API and is discussed in the next slide.

### <mark style="background: #FF5582A6;">Socket Address Structure:</mark>

```C
struct in_addr
{
	in_addr_t s_addr; // 32-bit IPv4 address network byte
	//ordered
} ;

struct sockaddr_in
{
	uint8_t sin_len; // length of structure (16)
	sa_family_t sin_family; // AF_INET
	in-port_t sin_port; // 16-bit TCP or UDP port number
	// network byte ordered
	struct in_addr sin_addr ; //32-bit IPv4 address
	//network byte ordered
	char sin_zero[8]; // unused
};
```

<mark style="background: #FF5582A6;">Only concerned with three members in the structure:</mark>
- ``sin_family``, ``sin_addr``, and ``sin-port``.
- The ``sin_zero`` member pads the structure to at least 16 bytes in size

### <mark style="background: #FF5582A6;">Socket Address Structures:</mark>

<mark style="background: #FF5582A6;">Key features of socket address structures are that:</mark>
- They are of local significance only i.e. they are <mark style="background: #FF5582A6;">not</mark> communicated between different hosts and,
- Socket address structures are always passed by <mark style="background: #FF5582A6;">reference</mark>.

When used with the <mark style="background: #FF5582A6;">socket primitives</mark>, the structures are adaptable as they can be used with many protocol families, not just TCP/IP:
- Ordinarily this adaptability would be provided for by the use of the <mark style="background: #FF5582A6;">generic pointer type</mark> (`void *`) in the socket primitive definitions.
- However, the socket primitives pre-date the <mark style="background: #FF5582A6;">generic</mark> pointer type.
- Consequently, a different approach was used

### <mark style="background: #FF5582A6;">The Generic Socket Address Structure:</mark>

The socket definitions use a generic socket address structure as follows:

```C
struct sockaddr
{
	uint8_t sa_len;
	sa_family_t sa_family; //address family: AF_xxx value
	char sa_data[14]; // protocol-specific address
};
```

The socket functions are defined to take a pointer to this generic socket address structure:

For example in the bind function:
``int bind(listenfd, (struct sockaddr *) &servaddr …….``

<mark style="background: #FF5582A6;">Notes:</mark>
- ``serveraddr`` was previously declared as struct ``sockaddr_in``.
- This is then typecast to a pointer of type: struct ``sockaddr``, which is the generic socket address structure.

### <mark style="background: #FF5582A6;">Address Structures and Byte-order:</mark>

Having examined the members of the socket address structure, it is important to understand how addressing information is stored in these members:

This requires an understanding of <mark style="background: #FF5582A6;">Byte-ordering</mark>.

<mark style="background: #FF5582A6;">Fundamentally hosts store 16-bit integers (2 bytes) in one of two ways:</mark>
- Store the <mark style="background: #FF5582A6;">low-order</mark> byte at the starting address, known as <mark style="background: #FF5582A6;">little-endian</mark> byte order,
- Store the <mark style="background: #FF5582A6;">high-order</mark> byte at the starting address, known as <mark style="background: #FF5582A6;">big-endian</mark> byte order.

There is no requirement for all hosts to use the same byte-order: The order used by a host is known as the <mark style="background: #FF5582A6;">host byte order</mark>.

### <mark style="background: #FF5582A6;">Byte-order:</mark>

It should be obvious that Client and Server applications will typically extend across host systems that use different formats.

Consequently programmers of networked applications must deal with the <mark style="background: #FF5582A6;">byte-ordering</mark> differences as follows:
- TCP uses 16-bit port number and a 32-bit IPv4 addresses,
- Both end-protocol stacks must agree on the order of these bytes to ensure any addressing information exchanged is in the correct order.

TCP/IP has defined its own byte order, known as <mark style="background: #FF5582A6;">network byte order</mark> (similar to <mark style="background: #FF5582A6;">big-endian</mark>)

### <mark style="background: #FF5582A6;">Byte Ordering and Manipulation Functions:</mark> 

The addressing information stored in members of a socket address structure must be converted from <mark style="background: #FF5582A6;">host byte order</mark> to <mark style="background: #FF5582A6;">network byte order</mark>.

<mark style="background: #FF5582A6;">Depending on the level of conversion, there are two sets of functions that can be used:</mark>
- <mark style="background: #FF5582A6;">Byte Ordering Functions</mark> are the simplest in that they deal with string-to-numeric-to-string conversion,
- <mark style="background: #FF5582A6;">Byte Manipulation Functions</mark> are more complex in that they deal with more complicated string manipulation i.e. from dotted-decimal notation-to-numeric-to-dotted-decimal notation.

### <mark style="background: #FF5582A6;">Byte Ordering Functions:</mark>

<mark style="background: #FF5582A6;">There are four byte ordering functions to consider:</mark>
- ``htons()`` – converts host 16-bit value to network byte order 
- ``htonl()`` – converts host 32-bit value to network byte order
- ``ntohs()`` – converts 16-bit network value to host byte order
- ``ntohl()`` – converts 32-bit network value to host byte order


`h` - host
`n` - network
``s`` - short (i.e. 16 bits)
`l` - long (i.e. 32 bits)

### <mark style="background: #FF5582A6;">Byte Manipulation Functions:</mark>

<mark style="background: #FF5582A6;">There are two byte manipulation functions to consider:</mark>
- ``inet_pton`` - This function takes an ASCII string (<mark style="background: #FF5582A6;">presentation</mark>) that represents the destination address (in dotted-decimal notation) and converts it to a binary value (<mark style="background: #FF5582A6;">numeric</mark>) for inputting to a socket address structure (i.e. <mark style="background: #FF5582A6;">network byte order</mark>)
- ``inet_ntop`` - This function does the reverse conversion, i.e. from a <mark style="background: #FF5582A6;">numeric</mark> binary value to an ASCII string representation (<mark style="background: #FF5582A6;">presentation</mark>) i.e. <mark style="background: #FF5582A6;">dotted-decimal notation</mark>

Both functions work with IPv4 and IPv6 addresses:
```C
#include <arpa/inet.h>

int inet_pton ( int family, const char *strptr, void *addrptr);
/*
- Returns: 1 if OK, 0 if input not a valid presentation format, -1 on error
– convert the string pointed to by strptr, storing the binary result through the pointer addrptr */
const char *inet_ntop(int family, const void *addrptr, char *strptr, size_t len) ;

/*– Returns: pointer to result if OK, NULL on error*/
```

### <mark style="background: #FF5582A6;">Byte Manipulation Functions:</mark>

The ``family`` argument for both functions is ``AF_INET``: We are only concerned with IPv4 addresses.

The ``len`` argument is the <mark style="background: #FF5582A6;">size</mark> of the destination buffer: It is passed to prevent the function from overflowing the buffer.

### <mark style="background: #FF5582A6;">When is Byte Ordering considered?</mark>

Some of these Byte Ordering and Manipulation functions were used in the daytime and echo applications:

Specifically they were used when addressing information was required to be passed from the Application layer to the TCP layer.

However, there is often a need for addressing information to be passed in the reverse direction, from the <mark style="background: #FF5582A6;">TCP</mark> layer to the <mark style="background: #FF5582A6;">Application</mark> layer,

One such requirement is when there is a need to capture addressing information relating to client applications contacting servers.

### <mark style="background: #FF5582A6;">Capturing Client addresses using accept():</mark>

Accept is called by a server to return the next connection from the connection queue:
```C
#include <sys/socket.h>
int accept ( int sockfd, struct sockaddr *cliaddr, socklen_t *addrlen ) ;
```

<mark style="background: #FF5582A6;">Returns:</mark> non-negative Descriptor if OK, -1 on error

If the queue is empty, the process is put to sleep.

Notice the second and third arguments to the accept primitive.

### <mark style="background: #FF5582A6;">The accept() Primitive – Client addresses:</mark>

<mark style="background: #FF5582A6;">accept returns up to three values:</mark>
- An integer returns code that is either a new socket descriptor or an error indication,
- The protocol address of the client process (through the ``cliaddr`` pointer)
- The size of this address (through the ``addrlen`` pointer)

The ``cliaddr`` and ``addrlen`` arguments are used to return the protocol address of the client process. Before the call to accept is made, ``*addrlen`` is set to the size of the client address structure (``cliaddr``),

On return this integer value contains the actual number of bytes stored by the kernel in the socket address structure.

If we are not interested in the address of the client the last two arguments are set to <mark style="background: #FF5582A6;">NULL</mark> pointers.

### <mark style="background: #FF5582A6;">The accept Function - an example:</mark>

```C
int main(int argc, char **argv)
{
//……Lines of code omitted
socklen_t clntAddrLen; // new variable to hold length of address structure
struct sockaddr_in servaddr, cliaddr ; //new address structure
char clntName [INET_ADDRSTRLEN]; //buffer to hold the client address
//…… Lines of code omitted
clntAddrLen = sizeof(cliaddr); //determines length of Client Address Structure
connfd = Accept(listenfd, (struct sockaddr *) &cliaddr, &clntAddrLen); // call to accept

printf("connection from %s, port %d\n", inet_ntop(AF_lNET, &cliaddr.sin_addr, clntName,
sizeof(clntName)), ntohs(cliaddr.sin_port)); //print out client address
//…… Lines of code omitted
```

# <mark style="background: #FF5582A6;">09 HTTP WebBrowser</mark>

### <mark style="background: #FF5582A6;">WWW - Hypertext and Hypermedia:</mark>

The Web is a <mark style="background: #FF5582A6;">distributed hypermedia</mark> system that supports interactive access to Hypermedia documents (aka <mark style="background: #FF5582A6;">Resources</mark>).

<mark style="background: #FF5582A6;">Hypermedia</mark> (as opposed to <mark style="background: #FF5582A6;">Hypertext</mark>) resources potentially contain:
- Different types of information including: text, pictures, graphics, audio etc. Examples include: HTML files, image files, query results etc.
- <mark style="background: #FF5582A6;">Hyperlinks</mark> to other Resources,

From a Network Programming perspective these Resources are treated as <mark style="background: #FF5582A6;">Data</mark>.

### <mark style="background: #FF5582A6;">WWW and the Client-server paradigm:</mark>

The distributed nature of the Web means that the Resources/Data are potentially spread across a number of computers across the Internet.

<mark style="background: #FF5582A6;">This lends itself well to the Client-server paradigm as follows:</mark>
- <mark style="background: #FF5582A6;">On the Client-side:</mark> Here sits the consumer of the Resources/Data i.e. the end-users. They typically interact with a client application known as a Browser.
- <mark style="background: #FF5582A6;">On the Server-side:</mark> Here is where the resource repositories are located i.e. on a remote server-class machine. Access to these Resources is typically controlled by a Web server.

### <mark style="background: #FF5582A6;">Problems to be addressed:</mark>

<mark style="background: #FF5582A6;">However, this distribution of Resources also introduces a number of potential problems:</mark>
- The resources may be updated, moved or removed without notification to the client applications,
- Accessing resources on remote host machines has implications for network bandwidth usage.
- These problems can affect the end-user experience and the network.

### <mark style="background: #FF5582A6;">Client-server interaction - HTTP:</mark>

Browsers and servers interact with each other using the <mark style="background: #FF5582A6;">HyperText Transfer Protocol</mark> (<mark style="background: #FF5582A6;">HTTP</mark>).

<mark style="background: #FF5582A6;">This is a network protocol used to deliver virtually all Resources on the Web:</mark>
- The Browser client sends <mark style="background: #FF5582A6;">HTTP Request</mark> messages to a Web Server. These messages typically (but not always) contain requests for a Resource,
- The Web server returns <mark style="background: #FF5582A6;">HTTP Response</mark> messages to the clients. These messages typically contain Resources/Data (but not always).

### <mark style="background: #FF5582A6;">Operation of Web Browsers and Servers:</mark>

In order to appreciate the potential problems to be addressed when developing Browsers and Web servers, it is important to understand their operation.

<mark style="background: #FF5582A6;">Web Servers perform a straightforward task over and over again:</mark>
- Accept connection requests from clients,
- Accept and parse incoming HTTP Requests,
- Retrieve and return HTTP Responses indicating success or failure.
- Close the connection.

### <mark style="background: #FF5582A6;">Browser Architecture:</mark>

Web browsers are much more complex in their operation. This can be best seen from their architecture (see next slide).

<mark style="background: #FF5582A6;">The functions of a Browser include:</mark>
- Rendering and displaying disparate (different types) resources to the user,
- User interaction the user,
- Initiating interaction with Web servers to retrieve resources or in some instances to upload resources.

The Browser provides these services seamlessly using a number of software components.

![](https://i.imgur.com/Pr4NDCf.png)

<mark style="background: #FF5582A6;">Specifically, a browser consists of the following components:</mark>
- A set of clients for uploading/retrieving Resources,
- A set of interpreters for displaying/rendering Resources,
- A Controller to manage them all. 

<mark style="background: #FF5582A6;">The Controller is responsible for:</mark> 
- Interpreting user input via the keyboard and mouse clicks
- Invoking interpreter and client components at the appropriate time.

All browsers minimally contain a basic HTTP client, a basic HTML interpreter and a Controller.

Modern Browsers contain much more.

### <mark style="background: #FF5582A6;">Interpreter and Client components:</mark>

An example interpreter is the <mark style="background: #FF5582A6;">HTML interpreter</mark>:
- It parses documents that contain standard HTML code and renders the content to the local screen,
- Other interpreters are needed for displaying pictures, video, audio etc.

An example client is the <mark style="background: #FF5582A6;">HTTP client</mark>:
- It is used to interact with HTTP servers for the purpose of retrieving/uploading Resources,
- Other clients are needed for sending/receiving e-mail messages, file transfer using FTP etc.
- The 1st field in the destination URL identifies the client component to invoke.

### <mark style="background: #FF5582A6;">Document Transfer and HTTP:</mark>

From a Network Programming perspective we are interested in the HTTP client and its interaction with HTTP servers.

<mark style="background: #FF5582A6;">This interaction consists of an exchange of HTTP Requests and Responses:</mark>
- These are typically sent as plain-text encoded in ASCII i.e. in English, 
- This means that when viewed with a protocol analyser such as Wireshark, the Application Data field can be easily read and understood.

### <mark style="background: #FF5582A6;">HTTP Requests:</mark>

HTTP Requests originate from the HTTP client.

<mark style="background: #FF5582A6;">They support a number of operations through a set of methods:</mark>
- ``GET``, ``HEAD``, ``POST``, ``OPTIONS``, ``PUT``, ``DELETE``, ``TRACE`` and ``CONNECT``.
- For the purposes of this module we shall restrict ourselves to the ``GET`` and ``HEAD`` methods,
- These two methods should adequately demonstrate the problems to be addressed.

### <mark style="background: #FF5582A6;">HTTP Responses:</mark>

HTTP Responses originate from the HTTP server.

<mark style="background: #FF5582A6;">Recall the problems previously outlined in relation to broken links, re-located Resources and Bandwidth limitations:</mark>
- HTTP includes a lot of functionality to address these problems,
- The server typically sends additional information with each transfer of data,
- This additional information allows the HTTP client to call an appropriate interpreter to display/render the Resource data, to infer an error condition etc.

### <mark style="background: #FF5582A6;">Structure of HTTP Messages:</mark>

Recall that each layer of the Protocol Hierarchy specifies a “framing-type” structure known as a <mark style="background: #FF5582A6;">Protocol Data Unit (PDU)</mark>:

<mark style="background: #FF5582A6;">Examples include:</mark> 
- a Data Link Frame, 
- an IP Datagram/Packet, 
- a TCP segment etc.

<mark style="background: #FF5582A6;">HTTP is also a protocol:</mark>
- It exists in the Application layer,
- There are many other protocols that exist in the Application layer.

When talking about Application layer protocols the term PDU has no real meaning.

<mark style="background: #FF5582A6;">This is because Application layer protocols typically follow a request-response or command-response model of interaction:</mark>
- <mark style="background: #FF5582A6;">Clients</mark> typically <mark style="background: #FF5582A6;">request</mark> something from the server or, issue a command to the server,
- <mark style="background: #FF5582A6;">Servers</mark> typically <mark style="background: #FF5582A6;">respond</mark> to the Client with an indication of success or failure,
- However, sometimes servers issue requests and commands, but more on that later.

Application layer protocols are more usefully described in terms of <mark style="background: #FF5582A6;">Syntax</mark> and <mark style="background: #FF5582A6;">Semantics</mark>.

### <mark style="background: #FF5582A6;">Syntax and Semantics:</mark>

<mark style="background: #FF5582A6;">Syntax</mark> describes the structure of the request-response messages.

<mark style="background: #FF5582A6;">Semantics</mark> describes the interaction between the client and the server:
- Essentially this relates to the <mark style="background: #FF5582A6;">sequence</mark> of request/response messages,
- More usefully this can be described as “who talks first” i.e. which side issues the first message.

### <mark style="background: #FF5582A6;">Syntax of HTTP Messages:</mark>

HTTP Messages have a particular structure or format.

<mark style="background: #FF5582A6;">The format of the Requests and Responses messages are similar. Both consist of:</mark>
- An initial line,
- Zero or more Header Lines,
- A blank line, and
- An optional Message Body typically containing Resource data from a file, or a query output etc.

Specifically, the format of an HTTP message is:
```HTTP
<initial line, different for request and response>
Header1: value1
Header2: value2
Header3: value3
<Blank line>
<optional message body goes here, like file contents or query
data>
```

Initial lines and headers should end in CRLF - Specifically CR and LF here mean ASCII values 13 and 10 respectively.

This structure can more usefully be described in terms of a Protocol Box Diagram:

![](https://i.imgur.com/vhY7K8g.png)

### <mark style="background: #FF5582A6;">Initial Request Line:</mark>

<mark style="background: #FF5582A6;">The initial line for a Request line has three parts, separated by spaces</mark>:
- a method name
- the local path of the requested resource
- the version of HTTP being used.

<mark style="background: #FF5582A6;">A typical request line is:</mark>
```HTTP
GET /path/to/file/index.html HTTP/1.0
```

<mark style="background: #FF5582A6;">Notes:</mark>
- GET is the most common HTTP method - it says “fetch me this resource"
- Method names are always uppercase.
- The path is the part of the URL after the host name.
- The HTTP version always takes the form "HTTP/x.x", uppercase.

### <mark style="background: #FF5582A6;">Initial Response Line:</mark>

<mark style="background: #FF5582A6;">The initial response line also has three parts separated by spaces:</mark>
- The HTTP version,
- A response status code that gives the result of the request,
- An English reason phrase describing the status code.

<mark style="background: #FF5582A6;">Typical status lines are:</mark>
- HTTP/1.0 200 OK
- HTTP/1.0 404 Not Found

<mark style="background: #FF5582A6;">Notes:</mark>
- The HTTP version is of format "HTTP/x.x".
- The status code is meant to be <mark style="background: #FF5582A6;">computer-readable</mark>. It comprises a three-digit integer, and the first digit identifies the general category of response
- The reason phrase is meant to be <mark style="background: #FF5582A6;">human-readable</mark>, and may vary.

### <mark style="background: #FF5582A6;">Header Lines:</mark>

Header lines provide information about the <mark style="background: #FF5582A6;">request</mark> or <mark style="background: #FF5582A6;">response</mark>, or about the Resource sent in the message body.

<mark style="background: #FF5582A6;">The header lines are in a particular format:</mark>
- One line per header, of the form "Header-Name: value", ending with CRLF.
- This is a similar format used for email and is defined in RFC 822.
- The header name is <mark style="background: #FF5582A6;">not</mark> case-sensitive (although the value may be).

<mark style="background: #FF5582A6;">There are different versions of HTTP:</mark>
-  HTTP 1.0 is older and defines 16 headers, although none are required.
- HTTP 1.1 is newer and defines 46 headers, and one (Host:) is required in requests.
- HTTP/2.0 is the latest version and addresses some of the inefficiencies of HTTP/1.1.
- For application development purposes, this module will focus on HTTP/1.0 and HTTP/1.1

### <mark style="background: #FF5582A6;">Example Request Header Lines:</mark>

![](https://i.imgur.com/FkXQhdQ.png)

![](https://i.imgur.com/tyLMme8.png)

### <mark style="background: #FF5582A6;">Header Lines - Net-politeness:</mark>

<mark style="background: #FF5582A6;">Consider including the following headers in client requests:</mark>
- A `From`: header gives the email address of the person making the request or running the program. (This must be user-configurable, for privacy concerns.)
- A `User-Agent`: header identifies the program that's making the request, in the form <mark style="background: #FF5582A6;">"Program-name/x.xx"</mark>, where x.xx is the (mostly) alphanumeric version of the program.
- e.g. Netscape 3.0 sends the header "User-agent: Mozilla/3.0Gold".

<mark style="background: #FF5582A6;">Consider including the following headers in server responses:</mark>
- A `Server`: header. Similar to the ``User-Agent:`` header, it identifies the server software in the form "<mark style="background: #FF5582A6;">Program-name/x.xx</mark>".
- e.g. An Apache server might return "Server: Apache/1.2b3-dev".
- The `Last-Modified`: header gives the modification date (in GMT) of the resource that's being returned. It is used in caching.
- e.g. `Last-Modified: Fri, 31 Dec 1999 23:59:59 GMT`

### <mark style="background: #FF5582A6;">The Message Body:</mark>

A HTTP <mark style="background: #FF5582A6;">message</mark> may have a <mark style="background: #FF5582A6;">body</mark> of data sent after the header lines.

<mark style="background: #FF5582A6;">In a response:</mark>
- This is where the requested resource is returned to the client (the most common use of the message body),
- Or some explanatory text for an error condition.

<mark style="background: #FF5582A6;">In a request:</mark>
- This is where form data or uploaded files are sent to the server.

<mark style="background: #FF5582A6;">If a HTTP message includes a body, there are usually header lines in the message that describe the body. In particular,</mark>
- The `Content-Type`: header gives the MIME-type of the data in the body, such as text/html or image/gif.
- The `Content-Length`: header gives the number of bytes in the body.

### <mark style="background: #FF5582A6;">Other HTTP Methods - HEAD and POST:</mark>

Two other commonly used methods are ``HEAD`` and ``POST``.

<mark style="background: #FF5582A6;">The HEAD Method</mark>
- Similar to a ``GET`` request, except it asks the server to return the response headers only, not the actual resource (i.e. no message body).
- Useful for checking characteristics of a resource without actually downloading it.
- The response to a ``HEAD`` request must never contain a <mark style="background: #FF5582A6;">message</mark> body.

<mark style="background: #FF5582A6;">The POST Method</mark> A ``POST`` request is used to send data to the server to be processed in some way, like by a CGI script.

<mark style="background: #FF5582A6;">It differs from a GET request in the following ways:</mark>
- There's a block of data sent with the request, in the message body. There are usually extra headers to describe this message body, like `Content-Type` and `Content-Length`:
- The request URI is not a resource to retrieve, it's usually a program to handle the data you're sending.

### <mark style="background: #FF5582A6;">Sample Document Transfer with HTTP:</mark>

```HTTP
GET http://www.comp.dit.ie/dbourke/ HTTP/1.1
Accept-Language: en-us,en;q=0.5
Accept:text/xml,application/xml,application/xhtml+x
ml,text/html;q=0.9,text/plain;q=0.8,image/png.
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Host: www.comp.dit.ie
Accept-Encoding: gzip,deflate
User-Agent: Mozilla/5.0 (Windows; U; Windows NT
5.1; en-US; rv:1.8.0.1) Gecko/20060111
Firefox/1.5.0.1
Cookie: PHPSESSID=13ceaac67329048c4
Keep-Alive: 300
Proxy-Connection: keep-alive
HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache
MicrosoftOfficeWebServer: 5.0_Pub
ETag: "e21ceefa6e28df"
Accept-Ranges: bytes
Content-Type: text/html
Connection: close
Date: Wed, 22 Oct 2008 14:20:12 GMT
Server: Microsoft-IIS/6.0
Content-Location:
http://www.comp.dit.ie/dbourke/index.htm
Last-Modified: Thu, 02 Oct 2008 09:12:23 GMT
Content-Length: 1837
X-Powered-By: ASP.NET
```

### <mark style="background: #FF5582A6;">HTTP Versions 1.0 and 1.1:</mark>

As mentioned there are two versions of HTTP: HTTP/1.0 and HTTP/1.1

<mark style="background: #FF5582A6;">There are some key differences between the two in the following areas (not all are listed):</mark>
- Persistent connections,
- Multi-hosting
- More efficient cache control.

### <mark style="background: #FF5582A6;">HTTP/1.0 Connections:</mark>

With HTTP 1.0 the connection between the server and the client is closed by the server immediately after the HTTP Response is transmitted.

<mark style="background: #FF5582A6;">Consider a simple HTML page containing five image tags:</mark>
- Downloading and rendering this page requires six connection establishments and cessations,
- One for the HTML page and one for each of the images. The images are downloaded separately on a separate connection.

<mark style="background: #FF5582A6;">This behaviour has implications for:</mark>
- <mark style="background: #FF5582A6;">Network bandwidth</mark> due to the amount of extra segments required to establish and terminate connections,
- <mark style="background: #FF5582A6;">Internal TCP resources</mark>. Each connection consumes resources within the TCP memory space.

### <mark style="background: #FF5582A6;">HTTP/1.1 Persistent Connections:</mark>

<mark style="background: #FF5582A6;">With HTTP 1.1, the connection between the server and the client remains open by default:</mark>
- This allows for multiple HTTP Requests to be submitted across a single connection,
- This default behaviour is not always required and it can be overridden using the ``Connection``: header as follows: ``Connection: close\r\n``
- This is an instruction to the server to close the connection after the Resource has been returned.

### <mark style="background: #FF5582A6;">Multi-hosting:</mark>

<mark style="background: #FF5582A6;">HTTP/1.1 facilitates Multi-hosting:</mark>
- Multiple webservers sharing a single IP address,
- The problem is that each server is listening on Port 80,
- This causes problems for TCP determining which server should receive an incoming HTTP Request,
- The problem is solved using the `Host`: header as follows: ``Host: www.tudublin.ie``
- Its inclusion is mandatory in all HTTP/1.1 Requests.

# <mark style="background: #FF5582A6;">10. Name Address and Hostnames</mark>

### <mark style="background: #FF5582A6;">IP Addresses and Hostnames:</mark>

<mark style="background: #FF5582A6;">The applications developed thus far have used explicit IP addresses:</mark>
- Typically an IP address is passed from the command line to be used by a client application to establish a connection to a remote server,
- Practically, however, end-users rarely know the IP address of the remote server applications,
- Instead, end-users use human-readable <mark style="background: #FF5582A6;">hostnames</mark>.

<mark style="background: #FF5582A6;">Advantages for using hostnames:</mark>
- Using <mark style="background: #FF5582A6;">hostnames</mark> instead of IP addresses is easier for end-users,
- A host’s IP address can change without affecting its <mark style="background: #FF5582A6;">hostname</mark>. For instance, www.example.com currently resides at ``93.184.216.34``. This IP address could easily be changed.

### <mark style="background: #FF5582A6;">Hostname-to-IP Address Mappings:</mark>

Whilst hostnames are preferable, the client applications connecting to remote server applications still require an IP address to initiate communications:

There is a service that stores mappings for hostnames and their IP addresses: the <mark style="background: #FF5582A6;">Name Service</mark>

The process of mapping a hostname to a numeric quantity such as, an IP address or, Port Number, is called <mark style="background: #FF5582A6;">resolution</mark>,

When an IP address for a particular hostname is obtained from a <mark style="background: #FF5582A6;">name service</mark>, the hostname is said to be <mark style="background: #FF5582A6;">resolved</mark>.

<mark style="background: #FF5582A6;">Two primary name service sources are:</mark>
- The <mark style="background: #FF5582A6;">Domain Name System (DNS)</mark>. This is a distributed name service requiring the use of the DNS protocol and
- Local configuration databases which are operating-system specific.

Fortunately from a programming perspective the details of the name service are hidden. We only need to know how to ask for a name to be <mark style="background: #FF5582A6;">resolved</mark>.

### <mark style="background: #FF5582A6;">Resolvers and Name Servers:</mark>

Organisations often run one or more name servers a.k.a. DNS (Domain Name System) servers.

Applications interact with DNS servers using functions imported from a library known as a <mark style="background: #FF5582A6;">resolver</mark>: The resolver code is contained in a system library and is link-edited into the application during the <mark style="background: #FF5582A6;">build</mark> process,

Calls to the resolver code are made using functions such as ``getaddrinfo()`` and ``getnameinfo()``

The former maps a hostname into its IP address, and the latter does the reverse mapping

### <mark style="background: #FF5582A6;">Operation of Resolvers:</mark>

Prior to contacting a name server, the resolver code refers to a local <mark style="background: #FF5582A6;">configuration</mark> file to determine the IP Address of the name server(s):

The file ``/etc/resolv.conf`` normally contains the IP address of the <mark style="background: #FF5582A6;">local</mark> name servers

<mark style="background: #FF5582A6;">The resolver then sends a query to a local name server for a resource record:</mark>
- Entries in the DNS are known as <mark style="background: #FF5582A6;">resource records</mark> (RRs)
- If necessary, the local name server may query another name server (starting at the Root DNS server) for the RR.

### <mark style="background: #FF5582A6;">Resolvers and Name Servers:</mark>

![](https://i.imgur.com/Fm9yhkU.png)

### <mark style="background: #FF5582A6;">Name and Address Conversions:</mark>

There are a number of different <mark style="background: #FF5582A6;">resource records</mark>:
- <mark style="background: #FF5582A6;">A</mark> records map hostnames to a 32-bit IPv4 address,
- <mark style="background: #FF5582A6;">AAAA</mark> records map hostnames to a 128-bit IPv6 address,
- <mark style="background: #FF5582A6;">PTR</mark> records map <mark style="background: #FF5582A6;">IP addresses into hostnames</mark>,
- <mark style="background: #FF5582A6;">MX</mark> records specifies a host to act as a <mark style="background: #FF5582A6;">mail exchanger</mark>,
- <mark style="background: #FF5582A6;">CNAME</mark> records map common services, such as <mark style="background: #FF5582A6;">ftp</mark> and <mark style="background: #FF5582A6;">www</mark> to the actual host providing the service
- e.g. www.tudublin.ie has the <mark style="background: #FF5582A6;">canonical</mark> name tudublin.ie.

The RRs that we are interested in is the <mark style="background: #FF5582A6;">A record</mark>.

### <mark style="background: #FF5582A6;">The getaddrinfo() function:</mark>

The ``getaddrinfo()`` function performs a query for an <mark style="background: #FF5582A6;">A</mark> record. It is defined as follows:

```C
int getaddrinfo (const char *hostStr, const char *serviceStr,
const struct addrinfo *hints, struct addrinfo **results);
```

e.g. ``getaddrinfo(“www.google.com”, 0, NULL, &addrList);``

<mark style="background: #FF5582A6;">Returns:</mark> ``NULL`` if ok and a non-null error code if unsuccessful.

The function returns one, or more, ``addrinfo`` structures, each of which contains an Internet address that can be specified in subsequent calls to ``bind()`` or ``connect()``.

### <mark style="background: #FF5582A6;">getaddrinfo() parameters:</mark>

<mark style="background: #FF5582A6;">hostStr:</mark> Points to a null-terminated character string representing a host <mark style="background: #FF5582A6;">name</mark> such as aisling, or, a fully qualified domain name (<mark style="background: #FF5582A6;">FQDN</mark>) such as: aisling.student.tudublin.ie

<mark style="background: #FF5582A6;">serviceStr</mark>: A service name which is translated to the corresponding port number. This is ignored for the moment

<mark style="background: #FF5582A6;">hints:</mark> filters to be used to restrict the information returned

<mark style="background: #FF5582A6;">results:</mark> the address of a pointer (``type struct addrinfo``) to hold the first address of a <mark style="background: #FF5582A6;">linked list</mark> of results i.e. the protocol addresses

### <mark style="background: #FF5582A6;">addrinfo structure:</mark>

Each entry in the linked list is an ``addrinfo`` structure which is defined as follows:

```C
struct addrinfo {
int ai_flags; // Flags to control information resolution
int ai_family; // Family: AF_INET, AF_UNSPEC etc.
int ai_socktype; // Socket type: SOCK_STREAM, SOCK_DGRAM
int ai_protocol; // Protocol: 0 (default) or IPPROTO_XXX
socklen_t ai_addrlen; // Length of socket address ai_addr
struct sockaddr *ai_addr; // Socket address for socket
char *ai_canonname; // Canonical name
struct addrinfo *ai_next; // Next addrinfo in linked list
} ;
```

### <mark style="background: #FF5582A6;">addrinfo members of interest:</mark>

<mark style="background: #FF5582A6;">here are five members of interest:</mark>
- <mark style="background: #FF5582A6;">ai_family:</mark> Specifies the address family supported by the hostname. Recall we are interested in ``AF_INET`` which is the TCP/IP stack.
- <mark style="background: #FF5582A6;">ai_socktype:</mark> Specifies the type of socket supported by the hostname. Recall we are interested in ``SOCK_STREAM`` i.e. a streaming socket.
- <mark style="background: #FF5582A6;">ai_protocol:</mark> Specifies the specific protocol supported by the hostname. Recall we are interested in ``IPPROTO_TCP`` i.e. TCP
- <mark style="background: #FF5582A6;">*ai_addr:</mark> Points to a structure that holds the full TCP/IP address for the hostname. The next slide refers to this structure.
- <mark style="background: #FF5582A6;">ai_addrlen:</mark> The length of the socket address.

### <mark style="background: #FF5582A6;">ai_addr and sockaddr_in:</mark>

``*ai_addr`` points to a socket address structure of type ``sockaddr``. Recall this is the <mark style="background: #FF5582A6;">generic</mark> address structure.

TCP applications use the <mark style="background: #FF5582A6;">family-specific</mark> address structure (``sockaddr_in`` – members shown below) which is then typecast to the generic address structure in any calls to the socket primitives.

```C
struct sockaddr_in {
	uint8_t sin_len; // length of structure (16)
	sa_family_t sin_family; // AF_INET
	in-port_t sin_port; // 16-bit TCP or UDP port number network byte ordered
	struct in_addr sin_addr; // 32-bit IPv4 address
	network byte ordered
	char sin_zero[8]; // unused
};
```

Fortunately, it is not necessary to access individual members of the <mark style="background: #FF5582A6;">generic</mark> socket address structure:
- Calls to socket primitives that need addressing information only require a pointer to the structure.
- For instance a typical call to ``connect()`` is as follows: ``connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr))``,
- Where ``servAddr`` is a struct of type ``sockaddr_in``

To use information returned by ``getaddrinfo()`` we can use:
``connect(sock, addr->ai_addr, addr->ai_addrlen)``

Where ``addr`` is a pointer to a structure of type ``addrinfo`` and, ``ai_addr`` (a member of ``addr``) is a pointer to a generic address structure

### <mark style="background: #FF5582A6;">getaddrinfo() and freeaddrinfo():</mark>

Eventually the <mark style="background: #FF5582A6;">linked list</mark> of results returned by ``getaddrinfo()`` must be deallocated:
- This requires the use of the auxiliary function, ``freeaddrinfo()``
- Given a pointer to the head of the linked list, ``freeaddrinfo()`` frees all the storage allocated for the list.
- Failure to call this function can result in a memory leak

The following example program (``GetAddrInfo.c``) illustrates the use of ``getaddrinfo()`` and ``freeaddrinfo()``:

The program takes two command-line parameters, a hostname and a service name (or port number), and prints the IP address(es)

``./GetAddrInfo www.tudublin.ie http``

### <mark style="background: #FF5582A6;">A sample program using getaddrinfo():</mark>

![](https://i.imgur.com/i7WaVIq.png)

### <mark style="background: #FF5582A6;">Code Explained:</mark>

Line 16 is a <mark style="background: #FF5582A6;">struct</mark> that is used to restrict the type of information to be returned:
- In this case we are only interested in TCP/IP addresses
- The address of this struct is passed as the third argument (<mark style="background: #FF5582A6;">hints</mark>) to ``getaddrinfo()``

Line 25 is the call to ``getaddrinfo()``

Lines 30 iterates over each node of the linked list

Line 31 prints the IP address and Port number from the ``ai_addr`` member of the current linked list node:
- ``ai_addr`` points to a struct of type ``sockaddr``, the generic address structure.
- The addresses are then taken from the ``sa_data`` member.
- Recall we used a structure of type ``sockkaddr_in`` which has members: ``sin_addr`` and ``sin_por``

# <mark style="background: #FF5582A6;">11. TCP Flow Error Control Operation</mark>

### <mark style="background: #FF5582A6;">Where TCP and IP Operate:</mark>

![](https://i.imgur.com/evfK3Lh.png)

### <mark style="background: #FF5582A6;">The complete TCP Transport Service offering:</mark>

<mark style="background: #FF5582A6;">Connection Orientation:</mark> This aspect has been examined through a variety of lab exercises.

<mark style="background: #FF5582A6;">Point-To-Point Communication:</mark> Each TCP connection has exactly two endpoints. Also examined through the lab exercises.

<mark style="background: #FF5582A6;">Complete Reliability:</mark> TCP guarantees that the data will be delivered exactly as sent i.e. no data missing or out of sequence. To be examined later.

<mark style="background: #FF5582A6;">Full Duplex Communication:</mark> A TCP connection allows data to flow in either direction

TCP buffers outgoing and incoming data (recall ``RECVQ`` and ``SENDQ`` buffers) allowing applications to continue executing other code whilst the data is being transferred.

<mark style="background: #FF5582A6;">Stream Interface:</mark> The <mark style="background: #FF5582A6;">source</mark> application sends a continuous sequence of octets across a connection
- The data is passed en-bloc to TCP for delivery. Recall use of ``send()`` primitive containing a pointer to the local App-buffer.
- TCP does not guarantee to deliver the data in the same size pieces that it was transferred by the source application. Recall use of ``recv()`` primitive which is always placed inside a ``while()`` structure.

<mark style="background: #FF5582A6;">Reliable Connection Startup:</mark> TCP both applications to agree to any new connection. To be examined.

<mark style="background: #FF5582A6;">Graceful Connection Shutdown:</mark> Either can request a connection to be shut down. To be examined.

### <mark style="background: #FF5582A6;">TCP’s Reliability service offering</mark>

The following slides explore TCP’s <mark style="background: #FF5582A6;">Complete Reliability</mark>, <mark style="background: #FF5582A6;">Full Duplex Communication</mark> and <mark style="background: #FF5582A6;">Stream Interface</mark> service offerings.

Central to the provision of these services are the concepts of Flow Control and Error Control, both of which were explored previously from the perspective of the Data Link layer:

### <mark style="background: #FF5582A6;">Recap of Flow Control in the Data Link layer:</mark>

<mark style="background: #FF5582A6;">Recall the use of the Sliding Windows Flow Control technique:</mark>
- This technique allows multiple <mark style="background: #FF5582A6;">Frames</mark> to be in transit in quick succession,
- This provides for more efficient <mark style="background: #FF5582A6;">Link Utilisation</mark>.

<mark style="background: #FF5582A6;">Characteristics of the technique are:</mark>
- Both stations use extended buffers to hold <mark style="background: #FF5582A6;">multiple</mark> frames.
- The Sending/Receiving stations maintain a list of frames already sent/received.
- The transmission link is effectively treated as a <mark style="background: #FF5582A6;">pipeline</mark> that can be <mark style="background: #FF5582A6;">filled</mark> with many frames in transit,
- Allows for Full Duplex communications (unlike Stop & Wait)

### <mark style="background: #FF5582A6;">Example Sliding Windows Flow Control:</mark>

Consider two Stations, A and B exchanging data. Assume Station A is sending data to Station B.

Station A is the <mark style="background: #FF5582A6;">Sender</mark> and Station B is the <mark style="background: #FF5582A6;">Receiver</mark>.

Before any data is exchanged, each station allocates buffer space for W frames (for example consider <mark style="background: #FF5582A6;">W=8</mark>)

This means that Station B can accept up to W (8) frames and, Station A can send up to W (8) frames, without individual frame acknowledgements (ACKs) being sent or received.

<mark style="background: #FF5582A6;">All frames contain a sequence number:</mark>
- All frames from Station A to Station B contain a sequence number for the <mark style="background: #FF5582A6;">current frame</mark>,
- All acknowledgements from Station B contain the sequence number of the <mark style="background: #FF5582A6;">next frame</mark> expected.
- Frames leaving Station A are stored in an <mark style="background: #FF5582A6;">outgoing</mark> buffer on Station A until an ACK is <mark style="background: #FF5582A6;">received</mark>.
- Frames arriving at Station B are stored in an <mark style="background: #FF5582A6;">incoming</mark> buffer on Station B until an ACK is <mark style="background: #FF5582A6;">sent</mark>

### <mark style="background: #FF5582A6;">Example Sliding Windows:</mark>

![](https://i.imgur.com/HTb4iFg.png)

### <mark style="background: #FF5582A6;">Sliding Windows Flow Control:</mark>

<mark style="background: #FF5582A6;">Multiple</mark> frames can be <mark style="background: #FF5582A6;">acknowledged</mark> using a single control message (<mark style="background: #FF5582A6;">implicit</mark> ACK):

e.g. Receipt of ACK for frame 2 (RR3) followed later by ACK for frame 6 (RR7) implies acknowledgement of frames 4 and 5.

Station A maintains a list of frame numbers it is allowed to send and, Station B maintains a list of frame numbers it is prepared to <mark style="background: #FF5582A6;">receive</mark>:
- Each list cannot extend beyond the window size.
- These lists can be considered as windows.

![](https://i.imgur.com/aaY2kIx.png)

### <mark style="background: #FF5582A6;">Error Control:</mark>

Recall the purpose of Error Control: Sender and Receiver stations co-ordinate activities to recover from <mark style="background: #FF5582A6;">Lost</mark> or <mark style="background: #FF5582A6;">Damaged</mark> Frames etc.

<mark style="background: #FF5582A6;">Error Control involves enhancing Flow Control techniques with additional functionality such as:</mark>
- <mark style="background: #FF5582A6;">Transmission Timers:</mark> Sender stations set a timer for each frame transmitted and takes action when a timer expires.
- <mark style="background: #FF5582A6;">Negative ACKs:</mark> A Receiver station can reject an out-of- sequence/damaged frame with a ``REJ(5)`` or ``SREJ(4)`` message.

Example Error Control techniques include: <mark style="background: #FF5582A6;">Go-Back-N</mark> and <mark style="background: #FF5582A6;">Selective Reject</mark>: Both techniques are based on the Sliding Windows Flow Control technique.

### <mark style="background: #FF5582A6;">TCP Error/Flow Control:</mark>

TCP also uses Flow Control and Error Control techniques.

Whilst similar to the <mark style="background: #FF5582A6;">Sliding Window Flow Control</mark> technique used in the Data Link layer, it differs in the following ways:
- Data is sent in <mark style="background: #FF5582A6;">Segments</mark> not <mark style="background: #FF5582A6;">Frames</mark>.
- Sequence numbers relate to <mark style="background: #FF5582A6;">Bytes</mark> not Segments. Each byte in a segment is numbered:
	- Each Segment identifies the <mark style="background: #FF5582A6;">first byte</mark> in the data field.
	- ACKs contain the number of the <mark style="background: #FF5582A6;">next byte</mark> expected.
- There are no <mark style="background: #FF5582A6;">Negative</mark> ACKs.

### <mark style="background: #FF5582A6;">TCP Flow Control:</mark>

<mark style="background: #FF5582A6;">For the effective operation of Flow Control:</mark>
- TCP Senders and Receivers maintain lists of bytes sent/received <mark style="background: #FF5582A6;">not</mark> segments.
- TCP Buffers used to hold incoming segments are measured in bytes <mark style="background: #FF5582A6;">not</mark> segments.

The next slide shows the operation of TCP’s Sliding Windows Flow Control technique.

### <mark style="background: #FF5582A6;">TCP Sliding Windows:</mark>

Here it can seen that the available buffer space decreases as data is stored in the buffer and increases as data leaves the buffer:

![](https://i.imgur.com/jamIxlK.png)

### <mark style="background: #FF5582A6;">TCP Segment Format:</mark>

![](https://i.imgur.com/nHZivQp.png)

### <mark style="background: #FF5582A6;">TCP Flow Control – Buffers and Windows:</mark>

Recall that TCP creates two buffers per socket:

<mark style="background: #FF5582A6;">These can be viewed with the netstat utility:</mark>
- One for incoming data (known as ``RECV-Q`` in netstat)
- One for outgoing data (known as ``SEND-Q`` in netstat)

Incoming buffers can easily overflow.

To prevent this, the <mark style="background: #FF5582A6;">receiving</mark> TCP entity uses a <mark style="background: #FF5582A6;">Window Mechanism</mark>.

<mark style="background: #FF5582A6;">TCP Internal Data Buffers:</mark>
![](https://i.imgur.com/R05mzTz.png)

<mark style="background: #FF5582A6;">Each end of the connection allocates a window (RECVQ buffer) to hold incoming data:</mark>
- The size of the initial window, in bytes, is set using the Window Size field during Phase 1 (Connection Initialisation) when both sides exchange ``SYN`` messages.
- This is known as a <mark style="background: #FF5582A6;">Window Advertisement</mark>.

<mark style="background: #FF5582A6;">Thereafter, throughout Phase 2 (Data Exchange), all ACKs messages include a Window Advertisement:</mark>
- Again using the <mark style="background: #FF5582A6;">Window Size field</mark>.
- The window advertisement can be <mark style="background: #FF5582A6;">positive</mark> or <mark style="background: #FF5582A6;">zero</mark> depending on the available space in <mark style="background: #FF5582A6;">RECV-Q</mark>.

### <mark style="background: #FF5582A6;">Operation of Window Advertisements:</mark>

![](https://i.imgur.com/LLDxwDx.png)

### <mark style="background: #FF5582A6;">Achieving Reliability -Error Control:</mark>

In addition to Flow Control, TCP must address the following reliability problems:
- Unreliable delivery by the underlying communication system: Segments can be <mark style="background: #FF5582A6;">lost</mark>, <mark style="background: #FF5582A6;">duplicated</mark>, <mark style="background: #FF5582A6;">delayed</mark>, or delivered <mark style="background: #FF5582A6;">out-of-order</mark> by the underlying communication system (IP Layer).
- <mark style="background: #FF5582A6;">Computer reboot:</mark> During an active connection, either side may re-boot unexpectedly. Segments arriving after re-boot need to be dealt with.

### <mark style="background: #FF5582A6;">TCP Error Control:</mark>

This requires the use of some form of error control.

Interestingly, to implement <mark style="background: #FF5582A6;">flow</mark> and <mark style="background: #FF5582A6;">error control</mark>, TCP is only equipped with two elements:
- Positive ACKs and Timers,
- Significantly, TCP does not have a <mark style="background: #FF5582A6;">Negative ACK</mark>.

The following slide shows the operation of TCP during normal <mark style="background: #FF5582A6;">Data Exchange</mark> without error.

### <mark style="background: #FF5582A6;">TCP Data Flow – Normal Operation:</mark>

![](https://i.imgur.com/rX1UbTD.png)
![](https://i.imgur.com/Pf7fm76.png)
![](https://i.imgur.com/86FNuWq.png)

### <mark style="background: #FF5582A6;">TCP Error Control - Segment Loss:</mark>

To deal with lost or out-of-sequence segments, TCP implements a <mark style="background: #FF5582A6;">Retransmission</mark> scheme: This involves the retransmission of ACKs and/or lost segments.

<mark style="background: #FF5582A6;">For the Sender, timers play a key role in error control:</mark>
- Upon expiry of a timer (relating to an unacknowledged segment) the Sender simply re-transmits the segment,
- A key question is “How long should TCP wait before retransmitting?”

For the Receiver, sequence numbers play a key role in detecting <mark style="background: #FF5582A6;">lost</mark> or <mark style="background: #FF5582A6;">out-of-sequence</mark> segments: A previous ACK is re-transmitted in response until the situation is rectified.

![](https://i.imgur.com/gzEfkz0.png)

### <mark style="background: #FF5582A6;">Factors affecting TCP’s Retransmission scheme:</mark>

How long should a Sending TCP entity wait before re-transmitting a segment?

<mark style="background: #FF5582A6;">The answer depends upon two factors:</mark>
- The underlying network architecture, and,
- Traffic levels across the network.

TCP takes a measure of the delay between sending a segment and receiving an ACK. This is known as Round-Trip Time (RTT).

TCP uses the value for RTT to determine an appropriate value for the re-transmission timer (RTO - Retransmission Timeout).

### <mark style="background: #FF5582A6;">Calculation of Retransmission Timeout (RTO):</mark>

For each active connection, the RTT is continuously monitored: It represents the <mark style="background: #FF5582A6;">network latency</mark>.

TCP <mark style="background: #FF5582A6;">adapts</mark> its RTO timer to match the varying RTT values across the network:
- It uses a <mark style="background: #FF5582A6;">weighted</mark> average of <mark style="background: #FF5582A6;">RTT</mark> and a variance factor,
- It continuously re-calculates a value for RTO.

### <mark style="background: #FF5582A6;">TCP’s Adaptive Retransmission Scheme:</mark>

This is known as an <mark style="background: #FF5582A6;">adaptive retransmission</mark> scheme and is the key to TCP’s success.

This adaptability helps TCP to react <mark style="background: #FF5582A6;">quickly</mark> to changes in traffic levels and to <mark style="background: #FF5582A6;">maximise</mark> throughput on each connection.

# <mark style="background: #FF5582A6;">12 TCP Operation OpenClose State Transition:</mark>

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

# <mark style="background: #FF5582A6;">13 The Listen Primitive</mark>

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

# <mark style="background: #FF5582A6;">Practice Test:</mark>

![](https://i.imgur.com/h12BsYT.png)

Test 1: Connected Socket

![](https://i.imgur.com/BJV1r6R.png)
![](https://i.imgur.com/Hv3jv9g.png)
![](https://i.imgur.com/DNZtYBE.png)

Test1: send(clntSock)

![](https://i.imgur.com/RxVyRAc.png)

Test1: initiate connection to a remote socket

![](https://i.imgur.com/R8Wkuiy.png)
![](https://i.imgur.com/8OjOeeQ.png)

Test1: clntSock = accept(servSock, (struct sockaddr * ) NULL, NULL);

![](https://i.imgur.com/A5meqiL.png)
![](https://i.imgur.com/1CdqOGy.png)

Test1: None of the above

![](https://i.imgur.com/x6HJD55.png)
![](https://i.imgur.com/BtIZexY.png)

Test1: close(clntSock)

The VMs are on Ubuntu Linux 14.04

<mark style="background: #FF5582A6;">Adapter 1 (both machines):</mark>
- Configured as a NAT adapter
- "Network Adapter" is enabled
- "Cable Connected" is enabled
- "Port forwarding" is enabled

<mark style="background: #FF5582A6;">Adapter 2 (both machines):</mark>
- Configured as internal network adapter
- "Network Adapter" is enabled
- "Cable Connected" is enabled

WinSCP is an application for doing file transfer.

To compile using gcc:
```CLI
gcc -c -std=gnu99 filename.c
gcc -o destinationExecutableName filename.o
```

The `".o"` file suffix means object file.

server files do not usually have suffixes

Use ``ls -l`` to view the files and their permissions in your current directory 

Use `chmod xxx filename` to change the permissions (using the numbers 0-7)

The ``netstat`` command displays various network related information such as network connections, routing tables, interface statistics, masquerade connections, multicast memberships etc.,

http is on port 80

sudo is used in linux to run commands safely

<mark style="background: #FF5582A6;">There are four byte ordering functions to consider:</mark>
- ``htons()`` – converts host 16-bit value to network byte order 
- ``htonl()`` – converts host 32-bit value to network byte order
- ``ntohs()`` – converts 16-bit network value to host byte order
- ``ntohl()`` – converts 32-bit network value to host byte order

`h` - host 
`n` - network
``s`` - short (i.e. 16 bits)
`l` - long (i.e. 32 bits)

<mark style="background: #FF5582A6;">Structure of daytimeServer:</mark>
1. Initialise num of connections
2. Main function
3. send buffer
4. check if argc has the correct amount of vars
5. convert port number from ascii to int
6. Initialise servSock and call SOCKET() on it to turn it into a connected socket
7. Initialise the server address structure, zero it out. Tell it to use IPv4. Accept connections on any available interface. Store port num in network byte order.
8. BIND the server socket
9. LISTEN on the server socket
10. begin infinite server loop
11. ACCEPT the client socket.
12. get time
13. print time to sendbuffer
14. Initialise numBytesSent with SEND on clntSock
14. close(clntSock)

<mark style="background: #FF5582A6;">echoServer.c structure:</mark>
1. Initialise num of connections
2. Main function
3. Initialise send buffer and receive buffer
4. Check if argc has correct number of parameters
5. Convert port number from ascii to int
6. initialise servSock
7. SOCKET servSock
8. Initialise the server address structure, zero it out. Tell it to use IPv4. Accept connections on any available interface. Store port num in netowrk byte order.
9. BIND servSock
10. LISTEN on servSock
11. Infinite loop
12. initialise clntSock by calling connect on servSock.
11. While the amount of bytes is in the buffer is smaller than the amount of bytes written, write the byte to screen. 
12. Break when ``"\r\n"`` found -> enter
13. Copy the received message into snedbuffer (snprintf)
14. SEND the sendbuffer to the clntSock
15. close(clntSock)

<mark style="background: #FF5582A6;">httpServer.c structure:</mark>
1. Initialise num of connections
2. Main function
3. Initialise numBytes, recvLoop and totalBytes
4. Check if argc has correct number of parameters
5. Convert port number from ascii to int
6. initialise servSock
7. SOCKET servSock
8. Initialise the server address structure, zero it out. Tell it to use IPv4. Accept connections on any available interface. Store port num in netowrk byte order.
9. BIND servSock
10. LISTEN on servSock
11. infinite server loop
12. Initialise clntSock by calling ACCEPT on servSock
13. Initialise client vars (recvLoop, totalBytes, uri, sendbuffer, recvbuffer)
14. While loop until recvLoop reaches 0
15. initialise numBytes by calling RECV on client sock
16. increment totalBytes by numBytes
17. end loop either if totalBytes >= Bufsize -2 or if it reads "\r\n\r\n"
18. Parse the http request using sscanf on the receive buffer and read the three strings into discard1, uri and discard2
19. compare uri and "/favicon.ico" using strcmp. If the same, print that you found it
20. null complete the recvbuffer and output recbuffer to stdout
21. compare uri and "/index.html" using strcmp. If the same, print the homepage. If different, print error page.
22. initialise numBytesSent by calling SEND on clntSock
23. close(clntSock)

![](https://i.imgur.com/20vSvhc.png)

``"\r\n\r\n"`` signals the end of a HTTP message

<mark style="background: #FF5582A6;">SOCKET:</mark>
```C
int servSock; 
if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
		DieWithSystemMessage("socket() failed");
```

<mark style="background: #FF5582A6;">BIND:</mark>
```C
if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
	DieWithSystemMessage("bind() failed");
```

<mark style="background: #FF5582A6;">LISTEN:</mark>
```C
if (listen(servSock, MAXPENDING) < 0)
	DieWithSystemMessage("listen() failed");
```

<mark style="background: #FF5582A6;">ACCEPT:</mark>
```C
int clntSock = accept(servSock, (struct sockaddr * ) NULL, NULL);
```

<mark style="background: #FF5582A6;">RECV:</mark>
```C
while ((numBytes = recv(clntSock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
	recvbuffer[numBytes] = '\0';  // Null-terminate the received string
	fputs(recvbuffer, stdout);
}
```

<mark style="background: #FF5582A6;">SEND:</mark>
```C
ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);
```

<mark style="background: #FF5582A6;">CLOSE:</mark>
```C
close(clntSock);
```

### <mark style="background: #FF5582A6;">daytimeServer.c</mark>
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"
#include <unistd.h>
#include	<time.h>

static const int MAXPENDING = 5;

int main(int argc, char *argv[]) {
	time_t	ticks;  
	char sendbuffer[BUFSIZE];  
	
	if (argc != 2) 
		DieWithUserMessage("Parameter(s)", "<Server Port>");
	
	in_port_t servPort = atoi(argv[1]); 

	int servSock; 
	if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
		DieWithSystemMessage("socket() failed");
	
	
	struct sockaddr_in servAddr;
	memset(&servAddr, 0, sizeof(servAddr));       
	servAddr.sin_family = AF_INET;                
	servAddr.sin_addr.s_addr = htonl(INADDR_ANY); 
	servAddr.sin_port = htons(servPort);          
	
	
	if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
		DieWithSystemMessage("bind() failed");
	
	
	if (listen(servSock, MAXPENDING) < 0)
		DieWithSystemMessage("listen() failed");
	
	for (;;) { 
    
    
    int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);
    if (clntSock < 0)
      DieWithSystemMessage("accept() failed");
	
    
    snprintf(sendbuffer, sizeof(sendbuffer), "%.24s\r\n", ctime(&ticks));
    ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);  
    if (numBytesSent < 0)
      DieWithSystemMessage("send() failed");
	
	close(clntSock);

  }   
  
}
```

### <mark style="background: #FF5582A6;">daytimeServer.c COMMENTED:</mark>

```C
#include <stdio.h>          // For standard I/O functions
#include <stdlib.h>         // For general-purpose functions like atoi
#include <string.h>         // For string handling functions like memset
#include <sys/types.h>      // For data types used in socket programming
#include <sys/socket.h>     // For socket API functions
#include <netinet/in.h>     // For Internet address structures
#include <arpa/inet.h>      // For functions like htonl and htons
#include "Practical.h"      // Custom utility functions for error handling
#include <unistd.h>         // For close() to terminate socket connections
#include <time.h>           // For time-related functions like ctime

// Maximum number of pending connections in the queue
static const int MAXPENDING = 5;

int main(int argc, char *argv[]) {
    time_t ticks;                          // Variable to hold the current time
    char sendbuffer[BUFSIZE];              // Buffer to store the formatted time string

    // Ensure the correct number of arguments are provided (1 parameter: the server port)
    if (argc != 2) 
        DieWithUserMessage("Parameter(s)", "<Server Port>");

    // Convert the port number from string to integer
    in_port_t servPort = atoi(argv[1]);

    // Create a socket for the server
    // Creates a TCP socket in the IPv4 domain
    int servSock; 
    if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
        DieWithSystemMessage("socket() failed");

    // Initialise the server address structure
    struct sockaddr_in servAddr;
    memset(&servAddr, 0, sizeof(servAddr));       // Zero out the structure
    servAddr.sin_family = AF_INET;                // Use IPv4 address family
    servAddr.sin_addr.s_addr = htonl(INADDR_ANY); // Accept connections on any available interface
    servAddr.sin_port = htons(servPort);          // Store port number in network byte order

    // Bind the socket to the specified address and port
    if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("bind() failed");

    // Set the socket to listen for incoming connections
    if (listen(servSock, MAXPENDING) < 0)
        DieWithSystemMessage("listen() failed");

    // Server loop to handle multiple client connections
    for (;;) {
        // Accept an incoming client connection
        int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);
        if (clntSock < 0)
            DieWithSystemMessage("accept() failed");

        // Get the current time and format it into a string
        ticks = time(NULL); // Get current time in seconds since the epoch
        snprintf(sendbuffer, sizeof(sendbuffer), "%.24s\r\n", ctime(&ticks)); // Format time into sendbuffer

        // Send the formatted time to the client
        ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);  
        if (numBytesSent < 0)
            DieWithSystemMessage("send() failed");

        // Close the connection to the client
        close(clntSock);
    }

    // The program should never reach here due to the infinite loop
    return 0; 
}

```

### <mark style="background: #FF5582A6;">daytimeClient.c</mark>
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"

int main(int argc, char *argv[]) {
	char recvbuffer[BUFSIZE]; 
	int numBytes = 0; 

	if (argc < 3) 
    DieWithUserMessage("Parameter(s)",
        "<Server Address> <Server Port>");

	char *servIP = argv[1];     
  
	in_port_t servPort = atoi(argv[2]);  

	
	int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);
	if (sock < 0)
		DieWithSystemMessage("socket() failed");

	
	struct sockaddr_in servAddr;
	memset(&servAddr, 0, sizeof(servAddr));
	servAddr.sin_family = AF_INET;
	
	int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
	if (rtnVal == 0)
		DieWithUserMessage("inet_pton() failed", "invalid address string");
	else if (rtnVal < 0)
		DieWithSystemMessage("inet_pton() failed");
	servAddr.sin_port = htons(servPort);    // Server port

  
	if (connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr)) < 0)
		DieWithSystemMessage("connect() failed");

	while ((numBytes = recv(sock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
		recvbuffer[numBytes] = '\0';
		fputs(recvbuffer, stdout);
	}
    if (numBytes < 0)
      DieWithSystemMessage("recv() failed");
	
	fputc('\n', stdout);
	
	close(sock);  
	exit(0);
}
```

#### <mark style="background: #FF5582A6;">daytimeClient.c COMMENTED:</mark>

```C
#include <stdio.h>          // For standard I/O functions (e.g., fputs, fputc)
#include <stdlib.h>         // For general-purpose functions like atoi and exit
#include <string.h>         // For string handling functions like memset
#include <unistd.h>         // For close() to terminate socket connections
#include <sys/types.h>      // For data types used in socket programming
#include <sys/socket.h>     // For socket API functions (e.g., socket, connect)
#include <netinet/in.h>     // For Internet address structures
#include <arpa/inet.h>      // For functions like inet_pton to parse IP addresses
#include "Practical.h"      // Custom utility functions for error handling

int main(int argc, char *argv[]) {
    char recvbuffer[BUFSIZE];    // Buffer to store data received from the server
    int numBytes = 0;            // Number of bytes received in a single `recv` call

    // Ensure the correct number of arguments are provided: server IP and port
    if (argc < 3) 
        DieWithUserMessage("Parameter(s)", "<Server Address> <Server Port>");

    // Extract the server IP address and port number from command-line arguments
    char *servIP = argv[1];        // Server IP address as a string
    in_port_t servPort = atoi(argv[2]);  // Convert the port string to an integer

    // Create a socket for the client
    int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP); // TCP socket
    if (sock < 0)
        DieWithSystemMessage("socket() failed");

    // Set up the server address structure
    struct sockaddr_in servAddr;
    memset(&servAddr, 0, sizeof(servAddr));       // Zero out the structure
    servAddr.sin_family = AF_INET;                // Use IPv4 address family

    // Convert the IP address from string to network byte order
    int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
    if (rtnVal == 0)
        DieWithUserMessage("inet_pton() failed", "invalid address string");
    else if (rtnVal < 0)
        DieWithSystemMessage("inet_pton() failed");

    // Convert the server port to network byte order and store it
    servAddr.sin_port = htons(servPort);

    // Establish a connection to the server
    if (connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("connect() failed");

    // Receive data from the server in a loop
    while ((numBytes = recv(sock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
        recvbuffer[numBytes] = '\0'; // Null-terminate the received data
        fputs(recvbuffer, stdout);  // Print the received data to the console
    }

    // Check for errors during the receive operation
    if (numBytes < 0)
        DieWithSystemMessage("recv() failed");

    // Print a newline after all data has been received
    fputc('\n', stdout);

    // Close the socket after communication is complete
    close(sock);

    // Exit the program successfully
    exit(0);
}
```

### <mark style="background: #FF5582A6;">echoServer.c</mark>
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"
#include <unistd.h>

static const int MAXPENDING = 5;

int main(int argc, char *argv[]) {

	char sendbuffer[BUFSIZE], recvbuffer[BUFSIZE];
	int numBytes = 0;

	if (argc != 2)
		DieWithUserMessage("Parameter(s)", "<Server Port>");

	in_port_t servPort = atoi(argv[1]);

	int servSock;
	if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
		DieWithSystemMessage("socket() failed");


	struct sockaddr_in servAddr;
	memset(&servAddr, 0, sizeof(servAddr));
	servAddr.sin_family = AF_INET;
	servAddr.sin_addr.s_addr = htonl(INADDR_ANY);
	servAddr.sin_port = htons(servPort);


	if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
		DieWithSystemMessage("bind() failed");


	if (listen(servSock, MAXPENDING) < 0)
		DieWithSystemMessage("listen() failed");

	for (;;) {

    	int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);
    	if (clntSock < 0)
      		DieWithSystemMessage("accept() failed");

	while ((numBytes = recv(clntSock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
		recvbuffer[numBytes] = '\0';
		fputs(recvbuffer, stdout);

		if (strstr(recvbuffer, "\r\n") > 0)
			break;
		}
    	if (numBytes < 0)
      		DieWithSystemMessage("recv() failed");

	snprintf(sendbuffer, sizeof(sendbuffer), "%s", recvbuffer);
    	
	ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);
	
	if (numBytesSent < 0)
		DieWithSystemMessage("send() failed");

	close(clntSock);

  }
}
```

### <mark style="background: #FF5582A6;">echoServer.c COMMENTED:</mark>
```C
#include <stdio.h>          // For standard I/O functions
#include <stdlib.h>         // For general-purpose functions like atoi
#include <string.h>         // For string handling functions like memset, strstr
#include <sys/types.h>      // For data types used in socket programming
#include <sys/socket.h>     // For socket API functions like socket, bind, accept
#include <netinet/in.h>     // For Internet address structures
#include <arpa/inet.h>      // For functions like htonl and htons
#include "Practical.h"      // Custom utility functions for error handling
#include <unistd.h>         // For close() to close sockets

// Maximum number of pending client connections allowed in the queue
static const int MAXPENDING = 5;

int main(int argc, char *argv[]) {
    char sendbuffer[BUFSIZE], recvbuffer[BUFSIZE]; // Buffers for sending and receiving data
    int numBytes = 0;                              // Tracks the number of bytes received

    // Check if the user provided the required server port as an argument
    if (argc != 2)
        DieWithUserMessage("Parameter(s)", "<Server Port>");

    // Convert the provided port number from a string to an integer
    in_port_t servPort = atoi(argv[1]);

    // Create a socket for the server
    int servSock;
    if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
        DieWithSystemMessage("socket() failed");

    // Initialize the server address structure
    struct sockaddr_in servAddr;
    memset(&servAddr, 0, sizeof(servAddr));       // Zero out the structure
    servAddr.sin_family = AF_INET;                // Use IPv4 address family
    servAddr.sin_addr.s_addr = htonl(INADDR_ANY); // Accept connections on any network interface
    servAddr.sin_port = htons(servPort);          // Convert port number to network byte order

    // Bind the server socket to the specified address and port
    if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("bind() failed");

    // Set the socket to listen for incoming client connections
    if (listen(servSock, MAXPENDING) < 0)
        DieWithSystemMessage("listen() failed");

    // Server loop to handle multiple clients
    for (;;) {
        // Accept an incoming client connection
        int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);
        if (clntSock < 0)
            DieWithSystemMessage("accept() failed");

        // Loop to receive data from the client
        while ((numBytes = recv(clntSock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
            recvbuffer[numBytes] = '\0';  // Null-terminate the received string
            fputs(recvbuffer, stdout);   // Print the received data to the console

            // Check for the end-of-message indicator (CRLF: "\r\n")
            if (strstr(recvbuffer, "\r\n") > 0)
                break;  // Exit the loop if end-of-message is detected
        }

        // If the `recv` function fails, handle the error
        if (numBytes < 0)
            DieWithSystemMessage("recv() failed");

        // Prepare the response by copying the received message into the send buffer
        snprintf(sendbuffer, sizeof(sendbuffer), "%s", recvbuffer);

        // Send the response back to the client
        ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);
        if (numBytesSent < 0)
            DieWithSystemMessage("send() failed");

        // Close the client connection after sending the response
        close(clntSock);
    }
}
```

### <mark style="background: #FF5582A6;">echoClient.c</mark>
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"

int main(int argc, char *argv[]) {
	char recvbuffer[BUFSIZE];
	char sendbuffer[BUFSIZE];
	int numBytes = 0;

	if (argc < 3 || argc > 4 )
    		DieWithUserMessage("Parameter(s)", "<Server Address> <Server Port> <String Message>");

	char *servIP = argv[1];
	char *echoString = argv[3];
	in_port_t servPort = atoi(argv[2]);

	int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);
	if (sock < 0)
		DieWithSystemMessage("socket() failed");


	struct sockaddr_in servAddr;
	memset(&servAddr, 0, sizeof(servAddr));
	servAddr.sin_family = AF_INET;

	int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
	if (rtnVal == 0)
		DieWithUserMessage("inet_pton() failed", "invalid address string");
	else if (rtnVal < 0)
		DieWithSystemMessage("inet_pton() failed");
	servAddr.sin_port = htons(servPort);


	if (connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr)) < 0)
		DieWithSystemMessage("connect() failed");

	size_t echoStringLen  = strlen(echoString);


    	snprintf(sendbuffer, sizeof(sendbuffer), "%s\r\n", echoString);
    	ssize_t numBytesSent = send(sock, sendbuffer, strlen(sendbuffer), 0);
    	if (numBytesSent < 0)
      		DieWithSystemMessage("send() failed");

	while ((numBytes = recv(sock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
		recvbuffer[numBytes] = '\0';
		fputs(recvbuffer, stdout);
		}
    	if (numBytes < 0)
      		DieWithSystemMessage("recv() failed");

	fputc('\n', stdout);

	close(sock);
	exit(0);
}
```

### <mark style="background: #FF5582A6;">echoClient.c COMMENTED:</mark>

```C
#include <stdio.h>          // For standard I/O functions like printf, fputs
#include <stdlib.h>         // For general-purpose functions like atoi and exit
#include <string.h>         // For string handling functions like memset and strlen
#include <unistd.h>         // For close() to close sockets
#include <sys/types.h>      // For data types used in socket programming
#include <sys/socket.h>     // For socket API functions like socket, connect, send, recv
#include <netinet/in.h>     // For Internet address structures
#include <arpa/inet.h>      // For functions like inet_pton to handle IP addresses
#include "Practical.h"      // Custom utility functions for error handling

int main(int argc, char *argv[]) {
    char recvbuffer[BUFSIZE];     // Buffer for receiving data from the server
    char sendbuffer[BUFSIZE];     // Buffer for sending data to the server
    int numBytes = 0;             // Tracks the number of bytes received

    // Validate the number of arguments provided by the user
    if (argc < 3 || argc > 4)     // Requires exactly 3 arguments: server IP, port, and message
        DieWithUserMessage("Parameter(s)", "<Server Address> <Server Port> <String Message>");

    char *servIP = argv[1];       // First argument: server IP address
    char *echoString = argv[3];   // Third argument: message to be sent to the server
    in_port_t servPort = atoi(argv[2]); // Second argument: server port, converted to an integer

    // Create a socket for connecting to the server
    int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);
    if (sock < 0)
        DieWithSystemMessage("socket() failed");

    // Initialize the server address structure
    struct sockaddr_in servAddr;
    memset(&servAddr, 0, sizeof(servAddr));  // Zero out the structure
    servAddr.sin_family = AF_INET;           // Use IPv4 address family

    // Convert the server IP address from text to binary format
    int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
    if (rtnVal == 0)
        DieWithUserMessage("inet_pton() failed", "invalid address string"); // Invalid IP format
    else if (rtnVal < 0)
        DieWithSystemMessage("inet_pton() failed"); // System error
    servAddr.sin_port = htons(servPort);      // Convert port number to network byte order

    // Connect to the server
    if (connect(sock, (struct sockaddr *)&servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("connect() failed");

    // Calculate the length of the message to be sent
    size_t echoStringLen = strlen(echoString);

    // Prepare the message with a newline character for proper transmission
    snprintf(sendbuffer, sizeof(sendbuffer), "%s\r\n", echoString);

    // Send the message to the server
    ssize_t numBytesSent = send(sock, sendbuffer, strlen(sendbuffer), 0);
    if (numBytesSent < 0)
        DieWithSystemMessage("send() failed");

    // Receive the echoed response from the server
    while ((numBytes = recv(sock, recvbuffer, BUFSIZE - 1, 0)) > 0) {
        recvbuffer[numBytes] = '\0'; // Null-terminate the received string
        fputs(recvbuffer, stdout);  // Print the received data to the console
    }

    // If `recv` fails, handle the error
    if (numBytes < 0)
        DieWithSystemMessage("recv() failed");

    // Print a newline for formatting purposes
    fputc('\n', stdout);

    // Close the socket and clean up
    close(sock);
    exit(0);  // Exit the program successfully
}
```

### <mark style="background: #FF5582A6;">httpServer.c</mark>
```C
//This application is a very simplistic server that simply returns requested file or error file contents using HTTP with simplistic HTTP Headers 
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"
#include <unistd.h>
#include <sys/stat.h>

static const int MAXPENDING = 5; 

int main(int argc, char *argv[]) {
	int numBytes = 0, char_in, count = 0, size = 0, recvLoop = 0, totalBytes =0;
	char recvbuffer[BUFSIZE], sendbuffer[BUFSIZE], path[200] ={'.'}, discard1[50], discard2[50]; 

	struct stat st;
	FILE * hFile; //declare file pointer
	
	 if (argc != 2) 
	    DieWithUserMessage("Parameter(s)", "<Server Port>");

	  in_port_t servPort = atoi(argv[1]); 

 
	  int servSock; 

	  if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
		DieWithSystemMessage("socket() failed");

  
	struct sockaddr_in servAddr;                  
	memset(&servAddr, 0, sizeof(servAddr));      
	  servAddr.sin_family = AF_INET;               
	  servAddr.sin_addr.s_addr = htonl(INADDR_ANY); 
	  servAddr.sin_port = htons(servPort);          
  
  if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
    	DieWithSystemMessage("bind() failed");

  if (listen(servSock, MAXPENDING) < 0)
	DieWithSystemMessage("listen() failed");

  for (;;) {
  
    int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);

    if (clntSock < 0)
	DieWithSystemMessage("accept() failed");

		recvLoop = 1;
		totalBytes = 0;
		memset (sendbuffer, '\0', sizeof(sendbuffer));
		memset (recvbuffer, '\0', sizeof(recvbuffer));
		
		while (recvLoop  > 0) 
		{  

			numBytes = recv(clntSock, (recvbuffer+totalBytes), 1, 0); //note the one byte limitation -  argument three	
			totalBytes += numBytes; //updating the off-set

			if((totalBytes >= (BUFSIZE-2)) || (strstr(recvbuffer,"\r\n\r\n")>0))
				recvLoop = 0;  //Testing to ensure recv() does not over-write the recvbuffer OR looking for \r\n\r\n
					
		}


    if (numBytes < 0)
	DieWithSystemMessage("recv() failed");

	sscanf(recvbuffer, "%s %s %s", discard1, (path+1), discard2);
	printf("\npath contains: %s\n", path);


	if(strcmp(path, "./favicon.ico") == 0)
	{
		printf("\n\nFound and ignored favicon.ico\n\n");		
	}
	else
	{
		if(strcmp(path, "./") == 0)
		{
			strcpy(path, "./index.html");		//reset the path1 buffer back to "."
		}

		hFile = fopen(path, "r");  	//open the requested file			

		if (hFile == NULL) 	 		//if requested file does not exist
		{
			strcpy(path, "./error.html");		//reset the path1 buffer back to "."

			hFile = fopen(path, "r");  	//open the error file

			stat(path, &st);
			size = st.st_size;

			printf("\nERROR.HTML File size is: %d\n", size);
			snprintf(sendbuffer, sizeof(sendbuffer), "HTTP/1.1 404 File Not Found\r\nContent-Length: %d\r\nCache-Control: no-cache\r\nConnection: close\r\n\r\n", size); 
		}
		else
		{

			stat(path, &st);
			size = st.st_size;

			printf("\nRequested file size is: %d\n", size);
			snprintf(sendbuffer, sizeof(sendbuffer), "HTTP/1.1 200 Okay\r\nContent-Length: %d\r\nCache-Control: no-cache\r\nConnection: close\r\n\r\n", size); 
		}
	 
		ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);
		if (numBytesSent < 0)
			DieWithSystemMessage("send() failed");

		strcpy(sendbuffer,"");  				//empty the outgoing buffer

		while((char_in = fgetc(hFile))!= EOF)   //reading one char at-a-time from the open file
		{
			sendbuffer[count] = char_in;	//storing the char in the outgoing buffer
			count++;				//increment the buffer index ready for next character
		}

		numBytesSent = send(clntSock, sendbuffer, count, 0);
		if (numBytesSent < 0)
			DieWithSystemMessage("send() failed");

		size = 0;
		count = 0;	
		fclose(hFile);			//close the file
		strcpy(path, ".");
	}//reset the path1 buffer back to "."
	close(clntSock); // Close client socket
  } //END FOR LOOP
  // NOT REACHED
}
```

### <mark style="background: #FF5582A6;">httpServer.c COMMENTED:</mark>

```C
#include <stdio.h>            // Standard I/O functions
#include <stdlib.h>           // General-purpose functions like atoi, exit
#include <string.h>           // String manipulation functions
#include <sys/types.h>        // Data types for sockets
#include <sys/socket.h>       // Socket API
#include <netinet/in.h>       // Internet address structures
#include <arpa/inet.h>        // Helper functions for IP addresses
#include <unistd.h>           // POSIX API (close, etc.)
#include <sys/stat.h>         // File statistics
#include "Practical.h"        // Custom error-handling utilities

// Define HTTP response templates for home and error pages
#define HOME_PAGE "HTTP/1.0 200 File Found\r\nContent-Length: 131\r\nConnection: close\r\nServer: httpserver\r\n\r\n<HTML><HEAD><TITLE>File  Found</TITLE></HEAD><BODY><h2>FILE Found</h2><hr><p>Your requested INDEX FILE was found.</p></BODY></HTML>"
#define ERROR_PAGE "HTTP/1.0 404 File Not Found\r\nContent-Length: 142\r\nConnection: close\r\n\r\n<HTML><HEAD><TITLE>File NOT Found</TITLE></HEAD><BODY><h2>FILE NOT Found</h2><hr><p>Your requested INDEX FILE was NOT found.</p></BODY></HTML>"

// Maximum number of pending connections
static const int MAXPENDING = 2;

int main(int argc, char *argv[]) {
    int recvLoop = 0, numBytes = 0, totalBytes = 0;
    char recvbuffer[BUFSIZE], sendbuffer[BUFSIZE], uri[200] = {""}, discard1[50], discard2[50];

    // Ensure exactly one argument is passed: the server port
    if (argc != 2) 
        DieWithUserMessage("Parameter(s)", "<Server Port>");

    in_port_t servPort = atoi(argv[1]); // Convert port to integer

    // Create the server socket
    int servSock; 
    if ((servSock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP)) < 0)
        DieWithSystemMessage("socket() failed");

    // Configure server address structure
    struct sockaddr_in servAddr;
    memset(&servAddr, 0, sizeof(servAddr));       
    servAddr.sin_family = AF_INET;                
    servAddr.sin_addr.s_addr = htonl(INADDR_ANY); // Accept connections from any address
    servAddr.sin_port = htons(servPort);          // Convert port to network byte order

    // Bind the socket to the specified port
    if (bind(servSock, (struct sockaddr*) &servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("bind() failed");

    // Listen for incoming connections
    if (listen(servSock, MAXPENDING) < 0)
        DieWithSystemMessage("listen() failed");

    // Server runs indefinitely
    for (;;) {
        // Accept a client connection
        int clntSock = accept(servSock, (struct sockaddr *) NULL, NULL);
        if (clntSock < 0)
            DieWithSystemMessage("accept() failed");

        // Initialize variables for each client
        recvLoop = 1;
        totalBytes = 0;
        memset(uri, '\0', sizeof(uri));
        memset(sendbuffer, '\0', sizeof(sendbuffer));
        memset(recvbuffer, '\0', sizeof(recvbuffer));

        // Receive the HTTP request
        while (recvLoop > 0) {
            numBytes = recv(clntSock, (recvbuffer + totalBytes), 1, 0); // Read 1 byte at a time
            totalBytes += numBytes; 

            // Stop receiving if buffer is full or HTTP header is complete
            if ((totalBytes >= (BUFSIZE - 2)) || (strstr(recvbuffer, "\r\n\r\n") > 0))
                recvLoop = 0;
        }
        if (numBytes < 0)
            DieWithSystemMessage("recv() failed");

        // Parse the HTTP request
        sscanf(recvbuffer, "%s %s %s\r\n", discard1, uri, discard2);  

        // Ignore requests for favicon.ico
        if (strcmp(uri, "/favicon.ico") == 0) {
            printf("\n\nFound and ignored favicon.ico\n\n");
            close(clntSock);
            continue;
        }

        // Log the received request
        recvbuffer[totalBytes] = '\0'; 
        fputs(recvbuffer, stdout);

        // Generate the appropriate HTTP response
        if (strcmp(uri, "/index.html") == 0) {
            snprintf(sendbuffer, sizeof(sendbuffer), HOME_PAGE);
        } else {
            snprintf(sendbuffer, sizeof(sendbuffer), ERROR_PAGE);
        }

        // Send the HTTP response
        ssize_t numBytesSent = send(clntSock, sendbuffer, strlen(sendbuffer), 0);
        if (numBytesSent < 0)
            DieWithSystemMessage("send() failed");

        // Close the client socket
        close(clntSock);
    }
}
```
### <mark style="background: #FF5582A6;">httpClient.c</mark>
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include "Practical.h"

int main(int argc, char *argv[]) {

	char sendbuffer[BUFSIZE], recvbuffer[BUFSIZE], discard[20];
	int numBytes = 0; 

	if (argc < 3 || argc > 4) 
		DieWithUserMessage("Parameter(s)", "<Server Address> <Server Port> <HTTP Request>");

	char *servIP = argv[1];     
	char *httpRequest = argv[3]; 

	in_port_t servPort = atoi(argv[2]);

	int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);
	if (sock < 0)
		DieWithSystemMessage("socket() failed");

	struct sockaddr_in servAddr;         

	memset(&servAddr, 0, sizeof(servAddr)); 

	servAddr.sin_family = AF_INET;

	int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
	if (rtnVal == 0)
		DieWithUserMessage("inet_pton() failed", "invalid address string");
	else if (rtnVal < 0)
		DieWithSystemMessage("inet_pton() failed");

	servAddr.sin_port = htons(servPort);    // Server port


	if (connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr)) < 0)
		DieWithSystemMessage("connect() failed");

	snprintf(sendbuffer, sizeof(sendbuffer), "%s", httpRequest); 
	  
	ssize_t numBytesSent = send(sock, sendbuffer, strlen(sendbuffer), 0);

	if (numBytesSent < 0)
		  DieWithSystemMessage("send() failed");


	while ((numBytes = recv(sock, recvbuffer, BUFSIZE, 0)) > 0) {
		recvbuffer[numBytes] = '\0';    
		fputs(recvbuffer, stdout);      

		if (strstr(recvbuffer,"</html>")>0) 
			break;
		}
	if (numBytes < 0)
		DieWithSystemMessage("recv() failed");
			
	fputc('\n', stdout); 

	close(sock);
	exit(0);
}
```

### <mark style="background: #FF5582A6;">httpClient.c COMMENTED:</mark>

```C
#include <stdio.h>           // Standard input/output functions like printf
#include <stdlib.h>          // General-purpose functions like atoi, exit
#include <string.h>          // String manipulation functions like memset, strcmp
#include <unistd.h>          // For system calls like close()
#include <sys/types.h>       // Data types used in socket programming
#include <sys/socket.h>      // Socket API functions like socket(), connect()
#include <netinet/in.h>      // Structures and constants for Internet domain addresses
#include <arpa/inet.h>       // Functions for manipulating IP addresses
#include "Practical.h"       // Custom error-handling utilities

int main(int argc, char *argv[]) {
    char sendbuffer[BUFSIZE], recvbuffer[BUFSIZE], discard[20]; // Buffers for sending and receiving data
    int numBytes = 0;  // Variable to store the number of bytes received

    // Validate command-line arguments
    if (argc < 3 || argc > 4) 
        DieWithUserMessage("Parameter(s)", "<Server Address> <Server Port> <HTTP Request>");

    char *servIP = argv[1];      // Server IP address
    char *httpRequest = argv[3]; // HTTP request string

    in_port_t servPort = atoi(argv[2]); // Server port number

    // Create a socket
    int sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);
    if (sock < 0)
        DieWithSystemMessage("socket() failed");

    // Set up the server address structure
    struct sockaddr_in servAddr;          
    memset(&servAddr, 0, sizeof(servAddr)); // Clear the structure
    servAddr.sin_family = AF_INET;         // IPv4 protocol

    // Convert IP address from text to binary form
    int rtnVal = inet_pton(AF_INET, servIP, &servAddr.sin_addr.s_addr);
    if (rtnVal == 0)
        DieWithUserMessage("inet_pton() failed", "invalid address string");
    else if (rtnVal < 0)
        DieWithSystemMessage("inet_pton() failed");

    servAddr.sin_port = htons(servPort); // Convert port number to network byte order

    // Establish a connection to the server
    if (connect(sock, (struct sockaddr *) &servAddr, sizeof(servAddr)) < 0)
        DieWithSystemMessage("connect() failed");

    // Prepare the HTTP request
    snprintf(sendbuffer, sizeof(sendbuffer), "%s", httpRequest); 
      
    // Send the HTTP request to the server
    ssize_t numBytesSent = send(sock, sendbuffer, strlen(sendbuffer), 0);
    if (numBytesSent < 0)
        DieWithSystemMessage("send() failed");

    // Receive the HTTP response from the server
    while ((numBytes = recv(sock, recvbuffer, BUFSIZE, 0)) > 0) {
        recvbuffer[numBytes] = '\0';   // Null-terminate the received data
        fputs(recvbuffer, stdout);    // Print the received data to standard output

        // Stop receiving if the closing HTML tag is detected
        if (strstr(recvbuffer, "</html>") > 0) 
            break;
    }

    // Check for errors during reception
    if (numBytes < 0)
        DieWithSystemMessage("recv() failed");

    fputc('\n', stdout); // Add a newline for clean output

    // Close the socket and exit
    close(sock);
    exit(0);
}
```
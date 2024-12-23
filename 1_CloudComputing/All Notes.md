# <mark style="background: #BABD00;">02 Intro to Cloud Computing</mark>


### <mark style="background: #BABD00;">What is Cloud Computing?</mark>

<mark style="background: #BABD00;">A customer-oriented definition:</mark>
- Anytime
- Anywhere
- Any device
- Any service

<mark style="background: #BABD00;">A business-oriented definition:</mark>
- Universal access
- Scalable services
- Collaborative
- New revenue models

<mark style="background: #BABD00;">A developer-oriented definition:</mark>
- Distributed Computing
- Scalable
- Access to 3rd party functionality
- Mobility

### <mark style="background: #BABD00;">SaaS (ready to use):</mark>

- Most basic form of cloud computing
- No dev necessary for user
- No resources required form the user
- Software managed from a central location
- Software delivered in a “one to many” model
- Users not required to handle software upgrades and patches  
- Application Programming Interfaces (APIs) allow for integration between different pieces of software  
- Offer powerful tools right at web browser  
- Requires no installation  
- Requires no specific knowledge of user

### <mark style="background: #BABD00;">SaaS examples:</mark>

<mark style="background: #BABD00;">Google Docs:</mark>  
- Productivity suite  
- Free to use (free Google Account required)  
- Share documents with others  
- Try it: docs.google.com

<mark style="background: #BABD00;">Dropbox:</mark>  
- Online file storage  
- Automatic synchronization across computers  
- Sharing of files with other users  
- Web access + mobile access  
- Backup of data + restore (30 days)

<mark style="background: #BABD00;">Salesforce (CRM):</mark>  
- Sales cloud – automation of workflow  
- Service cloud – customer service  
- Chatter – collaboration tools  
- Jigsaw – customer contact database  
- Force.com – Salesforce platform for third party apps (PaaS)  
- Heroku – third party ruby apps (PaaS)

### <mark style="background: #BABD00;">Platform as a Service (PaaS):</mark>

- "Provides developers with a proprietary APIs to make an application that will run in a specific environment"
- Can be any application you can think of  
- Is locked to the platform used for creation
- Examples: metaverse apps, PHP, Java, Python, C#

<mark style="background: #BABD00;">Benefits of PaaS?</mark>
- Many services free to use
- Pay per use - good for users, not the best for providers
- Vendor lock-in difficult due to lack of standards. Containers can combat vendor lock-in.
- Why are companies offering PaaS environments?
- Key Benefit: DATA. "We're (IT companies) not Google's customers; we're Google's product that they sell to their customers" - Bruce Schneier

<mark style="background: #BABD00;">Linking? Infrastructure as a Service:</mark>
- Real business innovation behind SaaS and PaaS is gathering data
- Most important asset cloud computing can provide is processing data
- Solution to processing vast amounts of data quickly can be found in IaaS

<mark style="background: #BABD00;">Infrastructure for:</mark>
- Developing
- Running
- Storing
. . . applications and data in cloud environments.

### <mark style="background: #BABD00;">IaaS:</mark>
- provides virtually limitless storage  
- provides virtually limitless computing power  
- potentially negates the need of having physical hardware at hand for doing so  
- provides numerous Linux, Unix and Windows environments to work in  
- provides variety of tools, services, SDKs and the like running on those OSs  
- Usually requires specific knowledge to use APIs for creating and managing the virtual OSs in the cloud infrastructure  
- therefore usually not user-friendly and simple to use

<mark style="background: #BABD00;">IaaS provider examples:</mark>
- AWS
- IBM Cloud
- DigitalOcean
- Microsoft Azure
- Linode
- Cloudera

### <mark style="background: #BABD00;">"Cloud Computing" Model Abstraction:</mark>

![](https://i.imgur.com/QMURBci.png)

<mark style="background: #BABD00;">Efficiency vs. Effectiveness:</mark> Efficient systems do not make wasteful use of system resources. Effectiveness is more focused on impact.

<mark style="background: #BABD00;">Cloud Repatriation:</mark> Moving from the cloud back to local data centre.

### <mark style="background: #BABD00;">How do we do cloud development?</mark>

The development process remains the same...

![](https://i.imgur.com/VAtSsxu.png)

But where we do these tasks may change..

![](https://i.imgur.com/73PMiUx.png)

<mark style="background: #BABD00;">Deployment</mark> happens in the cloud.

The major players are:
1. Amazon 
2. Microsoft Azure
3. Google

Each has their own set of tools on offer.

![](https://i.imgur.com/R7dJhAb.png)

<mark style="background: #BABD00;">Downsides:</mark>
- Security
- Lock-in
- Reliability
- Lack of control

<mark style="background: #BABD00;">Upsides:</mark>
- Scale and cost
- Encapsulated change management
- Next-generation architectures
- Choice and agility

# <mark style="background: #BABD00;">03 History of Distributed Computing</mark>

### <mark style="background: #BABD00;">Evolution of Distributed Systems:</mark>

![](https://i.imgur.com/pqVCEWy.png)

<mark style="background: #BABD00;">Monolithic Systems (Single Tier):</mark>
- Central processing (mainframe)  
- Multiple access supported by time sharing Operating Systems  
- Primitive User Interface

<mark style="background: #BABD00;">Client/Server Database Systems (Two-Tier):</mark>
- Centralised DBMS, often running on a Unix system
- Windows clients connect over a LAN.  
- Service Logic resides on a client, for example, calculation of pay after overtime rates etc..  
- Manual Installation of clients

<mark style="background: #BABD00;">Multi-Tier Systems:</mark>
- Database server on one host  
- Web server and Application server on another host  (connected by a LAN)  
- (Thin) Clients downloaded as applets. Communicates with the application server.  

![](https://i.imgur.com/oggBGaO.png)

![](https://i.imgur.com/6vQlM4C.png)

### <mark style="background: #BABD00;">Sample N-Tier (Twitter):</mark>

![](https://i.imgur.com/YuHX7i1.png)

### <mark style="background: #BABD00;">Centralised System Characteristics:</mark>

- One component with non-autonomous parts  
- Component shared by users all the time  
- All resources accessible  
- Software runs in a single process  
- Single Point of control  
- Single Point of failure

### <mark style="background: #BABD00;">Distributed System Characteristics:</mark>  

- Multiple autonomous components  
- Components are not shared by all users  
- Resources may not be accessible  
- Software runs in concurrent processes on different processors  
- Multiple Points of control  
- Multiple Points of failure

### <mark style="background: #BABD00;">Examples of Distributed Systems:</mark>

#### <mark style="background: #BABD00;">The Internet </mark> 

Heterogeneous network of computers and applications  

Implemented through the Internet Protocol Stack  

Typical configuration:
![](https://i.imgur.com/Set6LBr.png)

#### <mark style="background: #BABD00;">Distributed Multimedia- Systems</mark>  

Often use Internet infrastructure  

<mark style="background: #BABD00;">Characteristics:</mark>  
- Heterogeneous data sources that need to be synchronized in real time:  
	- Video  
	- Audio  
	- Text  
	
- Often: Distribution services  
	- Multicast  

<mark style="background: #BABD00;">Examples:</mark>  
- Tele-teaching tools  
- Video- conferencing  
- Video and audio on demand

#### <mark style="background: #BABD00;">Intranets:</mark>  
- Locally administered network  
- Usually proprietary (e. g., the University campus network)  
- Interfaces with the Internet  
- Firewalls  
- Provides services internally and externally

![](https://i.imgur.com/s5qlO5f.png)

### <mark style="background: #BABD00;">Mobile and Ubiquitous Computing Systems:</mark>

<mark style="background: #BABD00;">Cellular phone systems (e. g., GSM, UMTS):</mark>  
- Resources being shared  
	- Radio frequencies  
	- Transmission times on one frequency (UMTS: multiplexing)  
	- The mobile on the move  

<mark style="background: #BABD00;">Laptop computers:</mark>  
- Wireless LANs  
- Handheld devices (PDAs etc. – Bluetooth networks)

<mark style="background: #BABD00;">Wearable devices</mark>

![](https://i.imgur.com/v6XKXQg.png)

### <mark style="background: #BABD00;">Embedded systems:</mark>  

<mark style="background: #BABD00;">Avionics control systems</mark>  - Flight management systems in aircraft  

<mark style="background: #BABD00;">Automotive control systems</mark> - Mercedes S- Class cars are equipped with 50+ autonomous embedded processors  

<mark style="background: #BABD00;">Connected through proprietary bus</mark> - like LANs  

<mark style="background: #BABD00;">Consumer Electronics</mark> - Audio HiFi equipment  

<mark style="background: #BABD00;">Medical Devices</mark> - Pace Makers

<mark style="background: #BABD00;">Tele Surgery</mark> - "Lindbergh Operation"


### <mark style="background: #BABD00;">Additional Notes:</mark>

<mark style="background: #BABD00;">GSM</mark> - (Global System for Mobile Communications, originally Groupe SpécialMobile), is a standard developed by the European Telecommunications Standards Institute (ETSI) to describe the protocols  for second-generation (2G) digital cellular networks used by mobile phones, first deployed in Finland in July 1991.[2] As of 2014 it has become the de facto global standard for mobile communications - with over 90% market share, operating in over 219 countries and territories.[3]  

<mark style="background: #BABD00;">UMTS</mark> - The Universal Mobile Telecommunications System (UMTS) is a third generation mobile  
cellular system for networks based on the GSM standard.  

<mark style="background: #BABD00;">Multiplexing</mark> (sometimes contracted to muxing) is a method by which multiple analogue or digital signals are combined into one signal over a shared medium. The aim is to share an expensive resource.  

<mark style="background: #BABD00;">The Lindbergh Operation</mark> was a complete tele-surgical operation carried out by a team of French  
surgeons located in New York on a patient in Strasbourg, France (over a distance of several thousand miles) using telecommunications solutions based on high-speed services and sophisticated surgical robotics. The operation was performed successfully on September 7, 2001 by Professor Jacques Marescaux and his team from the IRCAD (Institute for Research into Cancer of the Digestive System). This was the first time in medical history that a technical solution proved capable of reducing the time delay inherent to long distance transmissions sufficiently to make this type of procedure possible. The name was derived from that of American aviator Charles Lindbergh, because he was the first person to fly solo across the Atlantic

# <mark style="background: #BABD00;">04 Requirements of Distributed Computing</mark>

### <mark style="background: #BABD00;">Design Challenges of non-functional requirements:</mark>

Our objective is to understand the non-functional requirements of a distributed system.  

These are concerned with the <mark style="background: #BABD00;">quality</mark> of the system  

<mark style="background: #BABD00;">Certain requirements are common to many distributed systems: </mark> 
- Resource Sharing  
- Openness  
- Concurrency  
- Scalability  
- Fault Tolerance  
- Transparency

### <mark style="background: #BABD00;">Resource Sharing:</mark>

Ability to use any hardware, software or data anywhere in the system  

Cost effective for sharing expensive resources  

<mark style="background: #BABD00;">Security implications due to many users accessing the common resources</mark>  
- How to control/restrict access? Resource manager components  
- Resource manager controls access, provides naming scheme and controls concurrency  
- Client-server v n-tier architecture (distributed objects)

### <mark style="background: #BABD00;">Openness:</mark>

Openness is concerned with extendibility and improvability of distributed systems  

Well defined and documented interfaces of components need to be published. 

Allows other components know what services are available  

System needs to adhere to recognized standards  

<mark style="background: #BABD00;">Components achieve openness by communicating using well-defined interfaces:</mark>  
- supports changing functional requirements as an organisation grows  
- Helps preserve the investment  
- Supports the integration of new components

<mark style="background: #BABD00;">Coupling</mark> refers to the degree of dependency between components in a system.

### <mark style="background: #BABD00;">Concurrency:</mark>

Components in distributed systems are executed in concurrent processes  

Components access and update shared resources (e.g. variables, databases, device drivers)  

<mark style="background: #BABD00;">Integrity of the system may be violated if concurrent updates are not coordinated:</mark>  
- Lost updates  
- Inconsistent analysis (Non-Repeatable Read)

<mark style="background: #BABD00;">Lost Update:</mark>
- Lost updates occur when two or more processes select the same data and then update the data based on the value originally selected.  
- Each process is unaware of the other processes.  
- The last update overwrites updates made by the other process, which results in lost data.  
	1. Session #1 reads Account A, gets 300.  
	2. Session #2 reads Account A, gets 300.  
	3. Session #2 updates Account A to 400 (+100) and commits.  
	4. Session #1 updates Account A to 350 (+50) and commits.  
- In this scenario, because Session #1 does not know that another session has already modified the account, the update by Session #2 is overwritten ("lost").

### <mark style="background: #BABD00;">Scalability:</mark>

Adoption of distributed systems to  
- accommodate a growing load (e.g. more users)  
- respond faster (this is the hard one)  

Usually done by adding more and/or faster hosts or processors  

Components should not need to be changed when scale of a system increases  

Design components to be scalable! They shouldn’t have to be revisited as things scale up.

### <mark style="background: #BABD00;">Fault Tolerance:</mark>

Hardware, software and networks fail for lots of reasons  

Distributed systems must maintain availability even at low levels of hardware/software/network reliability, which is a huge improvement over centralised systems  

Operations that continue even in the presence of faults are referred to as fault-tolerant  

Fault tolerance is achieved by redundancy (replication)

### <mark style="background: #BABD00;">Transparency:</mark>

Non-functional requirements can be satisfied through the various forms of transparency within distributed systems.  

Application developers and users should perceive distributed systems as  
- One system  
- A collection of co-operating components which should be hidden  
- Efficient and cost-effective to construct and maintain (only possible if the complexity of distribution is hidden from the users)

### <mark style="background: #BABD00;">Dimensions of Transparency:</mark>

Defined in the international standard on Open Distributed Processing (ODP):  
“Distribution transparency is the property of hiding the properties  of distribution from end users”.

Transparency in computing is discussed in terms of hiding complexity from the user.

![](https://i.imgur.com/kanUCML.png)

<mark style="background: #BABD00;">Access Transparency:</mark>
- Enables local and remote components to be accessed using identical operations.  
- Example: File system operations in NFS.  
- Example: Navigation in the Web.  
- Example: SQL Queries  

It is critical in building distributed systems using heterogeneous computer architecture and programming languages.

<mark style="background: #BABD00;">Migration Transparency:</mark>
A component can be relocated without users or clients noticing it (i.e. allows the movement of information objects within a system without affecting the operations of users or application programs)  
- Example: NFS  
- Example: Web Pages

<mark style="background: #BABD00;">Replication Transparency:</mark>
- A replica is a component copy that remains synchronised with its original.  
- Users or application programs have no knowledge of the replica.  
- Example: Distributed DBMS  
- Example: Mirroring Web Pages.

<mark style="background: #BABD00;">Concurrency Transparency:</mark>
- Users and programmers are unaware that components request services concurrently.  
- Enables several processes to operate concurrently using shared information objects without interference between them.  
- Example: NFS  
- Example: Automatic teller machine (ATM) network  
- Example: Database management system

<mark style="background: #BABD00;">Scalability Transparency:</mark>
- Allows the system and applications to expand in scale without change to the system structure or the application algorithms.  
- Example: World-Wide-Web  
- Example: Distributed Database

<mark style="background: #BABD00;">Performance Transparency:</mark>
- Allows the system to be reconfigured to improve performance as loads vary.  
- Example: Distributed make

<mark style="background: #BABD00;">Failure Transparency:</mark>
- Enables distributed system to conceal faults.  
- Allows users and applications to complete their tasks despite the failure of other components.  
- Depends on concurrency and replication transparency.  
- Example: Database Management System

### <mark style="background: #BABD00;">Transparency Summary:</mark>

<mark style="background: #BABD00;">Transparency</mark> - Perceive distributed systems as One system  

<mark style="background: #BABD00;">Access</mark> - Enables local and remote information objects to be accessed using identical operations  

<mark style="background: #BABD00;">Location</mark> - Enables information objects to be accessed without knowledge of their location  

<mark style="background: #BABD00;">Migration</mark> - A component can be relocated without users or clients noticing it  

<mark style="background: #BABD00;">Replication</mark> - A replica is a component copy that remains synchronised with its original.  

<mark style="background: #BABD00;">Concurrency</mark> - Enables several processes to operate concurrently using shared information objects without interference between them.  

<mark style="background: #BABD00;">Scalability</mark> - Allows the system and applications to expand in scale without change to the system structure or the application algorithms  

<mark style="background: #BABD00;">Performance</mark> - Allows the system to be reconfigured to improve performance as loads vary  

<mark style="background: #BABD00;">Failure</mark> - Enables distributed system to conceal faults.


# <mark style="background: #BABD00;">05 Load Balancing</mark>

### <mark style="background: #BABD00;">Load Balancing:</mark>

All inbound traffic to a web role passes through a stateless load balancer, which distributes client requests among the role instances.  

Individual role instances do not have public IP addresses, and are not directly addressable from the Internet. (This is why you can’t ‘Ping’ the IP addresses).  

Web roles are stateless, so that any client request can be routed to any role instance.  

A Status-check event is raised every 15 seconds. This can be used to indicate if the role is ready to receive traffic, or is busy and should be taken out of the load balancer rotation.

![](https://i.imgur.com/heN0psc.png)

### <mark style="background: #BABD00;">Elasticity:</mark>

<mark style="background: #BABD00;">Elasticity – What is it?</mark> 
The degree to which a system is able to adapt to workload changes by provisioning and deprovisioning resources in an automated manner, such that at each point in time the available resources match the current demand as closely as possible.  

<mark style="background: #BABD00;">Elasticity is automated scalability.</mark>  
Scalability provides the ability to increase (or decrease) the amount of resources in scaling up (more powerful instances) or out (additional instances), which is usually done through manual intervention.  

Elasticity does the same but in an automated manner, independent from human interaction.

### <mark style="background: #BABD00;">Types of Auto Scaling:</mark>

![](https://i.imgur.com/q4Kkywn.png)

### <mark style="background: #BABD00;">Vertical Auto Scaling:</mark>  

Often referred to as scaling-up or scaling down.  

Requires that you modify the hardware (expand or reduce its capacity and performance).  

Or redeploy the solution using alternative hardware that has the appropriate capacity and performance.  
Vertical scaling is often a disruptive process that requires making the system temporarily unavailable while it is being redeployed .  

<mark style="background: #BABD00;">Not a common approach in the Cloud Industry!</mark>

### <mark style="background: #BABD00;">Horizontal Auto Scaling:</mark>  

Often referred to as scaling-in or scaling-out.  

Requires deploying the solution on additional or fewer resources, which are typically commodity resources rather than high-powered systems.  

The solution can continue running without interruption while these resources are provisioned.  

When the provisioning process is complete, copies of the elements that comprise the solution can be deployed on these additional resources and made available.  

If demand drops, the additional resources can be reclaimed after the elements using them have been shut down cleanly.  

<mark style="background: #BABD00;">The most common approach to implementing Elasticity in the Cloud.</mark>

### <mark style="background: #BABD00;">AWS Auto Scaling:</mark>

![](https://i.imgur.com/FegnUtZ.png)

# <mark style="background: #BABD00;">06 Virtualisation:</mark>

<mark style="background: #BABD00;">Virtualisation:</mark> The separation of a resource or request for a service from the underlying physical delivery of that service.

### <mark style="background: #BABD00;">Buffering:</mark>

When the speed in which data is received and the speed in which data is processed are different, then we use a buffer.

Buffer is a memory space which stores the input data as it is received and passes it on to the system according to the speed it can process.

![](https://i.imgur.com/KpI5ScA.png)

<mark style="background: #BABD00;">Example:</mark>
- Video or audio streaming  
- When you download an audio or video file from the Internet, it may load the first 10% of it into a buffer and then begin to play. While the clip plays back, the computer continually downloads the  rest of the clip and stores it in the buffer. Because the clip is being played from the buffer, not  directly from the Internet, there is less of a chance that the audio or video will stall or skip when there is network congestion.  
- There are buffers for screens, printers, keyboards,  network connections, etc

### <mark style="background: #BABD00;">Caching:</mark>

Caching is a high-speed storage in a separate disk or in dedicated memory which stores a subset of data.  

Future requests for that data are served up much faster than is possible by accessing the data’s original storage location.  

Thus, a Cache is used in a system to speed up the access to frequently used data.  

Caching allows you to efficiently reuse previously retrieved or computed data.

<mark style="background: #BABD00;">Local Caching:</mark>
![](https://i.imgur.com/lZNtf1P.png)

<mark style="background: #BABD00;">Distributed Caching:</mark>
![](https://i.imgur.com/Ps32x8y.png)

<mark style="background: #BABD00;">Distributed Caching Examples:</mark>

<mark style="background: #BABD00;">Redis:</mark> an open source, in-memory data store used by millions of developers as a database, cache, streaming engine, and message broker  
- https://redis.io/ (source-available from March 2024)  
- https://valkey.io/ (open-source alternative to redis)  

<mark style="background: #BABD00;">Memcached:</mark> open source, high-performance, distributed memory object caching system, generic in nature, but intended for use in speeding up dynamic web applications by alleviating database load.  
https://memcached.org/

### <mark style="background: #BABD00;">Difference between buffering and caching:</mark>

![](https://i.imgur.com/rc5MA7S.png)

### <mark style="background: #BABD00;">Virtual Memory:</mark>

The computer software gains access to more memory than is physically installed, via the background swapping of data to disk storage.

![](https://i.imgur.com/EaMNdYo.png)

### <mark style="background: #BABD00;">Virtual Machine:</mark>

Typically a single Operating System runs on a computer at any one time  
- Single OS installed or  
- Dual Boot where you choose the OS to load  

A virtual machine (VM) is a "completely isolated guest operating system installation within a normal host operating system“.  

The underlying Operating System is unaware of the virtual environment and runs as though it is in control of the computer  

An underlying Operating System is required to manage Virtual Machines  

Virtual Machines allow Operating Systems run on wide range of hardware not originally supported  
- Windows running on Sun/Oracle hardware  
- Windows running on Apple Operating System  
- Linux running on Windows Operating System

In a Virtual Machine - each process "seems" to execute on its own processor with its own memory and devices.  
- The resources of the physical machine are shared. Virtual devices are sliced out of the physical ones. Virtual disks are subsets of physical ones.  
- Useful for running different OS simultaneously on the same machine.  
- Protection is paramount

![](https://i.imgur.com/158ainT.png)

![](https://i.imgur.com/vqfDyjV.png)


<mark style="background: #BABD00;">Example: Java Virtual Machine (JVM)</mark>  

The Java Virtual Machine allows Java code to be portable between various hardware and OS platforms.

![](https://i.imgur.com/ih1sTTz.png)

### <mark style="background: #BABD00;">Virtualisation Extended:</mark>

<mark style="background: #BABD00;">Desktop virtualisation</mark> is a technology which enables detachment of the user state, the Operating System (OS), and the applications from endpoint devices.

Enables organisations to host and centrally manage desktops. Desktops run as virtual machines within the data centre and accessed over a network  

<mark style="background: #BABD00;">Desktop virtualization benefits:</mark>  
- Flexibility of access due to enablement of thin clients  
- Improved data security  
- Simplified data backup and PC maintenance

![](https://i.imgur.com/wCCm6Ov.png)

### <mark style="background: #BABD00;">Virtualisation Extended:</mark>

Virtualisation techniques can be applied to other IT infrastructure layers - including networks, storage, laptop or server hardware, operating systems and applications.  

This blend of virtualisation technologies - or <mark style="background: #BABD00;">virtual infrastructure</mark> - provides a layer of abstraction between computing, storage and networking hardware, and the applications running on it

![](https://i.imgur.com/Vo4SqTc.png)

### <mark style="background: #BABD00;">VM Hardware Components:</mark>

![](https://i.imgur.com/yFpkZVS.png)

### <mark style="background: #BABD00;">Network visualisation:</mark>

![](https://i.imgur.com/v73HTjX.png)

Server virtualisation runs multiple virtual servers on a physical server

Network virtualisation runs multiple virtual networks on a physical network.

### <mark style="background: #BABD00;">Virtualised Infrastructure:</mark>

Using virtual infrastructure solutions enterprise IT managers can address challenges that include:  
- <mark style="background: #BABD00;">Server Consolidation and Containment</mark> – Eliminating ‘server sprawl’ via deployment of systems as virtual machines (VMs) that can run safely and move transparently across shared hardware, and increase server utilisation rates from 5-15% to 60-80%.  
- <mark style="background: #BABD00;">Test and Development Optimisation</mark> – Rapidly provisioning test and development servers by reusing pre-configured systems, enhancing developer collaboration and standardizing development environments.  
- <mark style="background: #BABD00;">Business Continuity</mark> – Reducing the cost and complexity of business continuity (high availability and disaster recovery solutions) by encapsulating entire systems into single files that can be replicated and restored on any target server, thus minimizing downtime.  
- <mark style="background: #BABD00;">Enterprise Desktop</mark> – Securing unmanaged PCs, workstations and laptops without compromising end user autonomy by layering a security policy in software around desktop virtual machines.

### <mark style="background: #BABD00;">What is a Hypervisor?</mark>

Virtualisation is the addition of a software layer (the <mark style="background: #BABD00;">virtual machine monitor</mark> VMM, also known as <mark style="background: #BABD00;">hypervisor</mark>) between the hardware and the existing software that exports an interface at the same level as the underlying hardware.

![](https://i.imgur.com/ZWIP5Uq.png)

Has two components:  
- Kernel  
- Virtual Machine Monitor (VMM)

![](https://i.imgur.com/K4EM52B.png)

### <mark style="background: #BABD00;">Types of Hypervisor (VMM):</mark>

![](https://i.imgur.com/J66toHT.png)

<mark style="background: #BABD00;">Type 1 (or native, bare metal)</mark>  
- Run directly on the host's hardware to control the hardware and to monitor guest operating systems. A guest operating system thus runs on another level above the hypervisor. (Hyper-V, VMWare ESXi Server , Xen etc)  
- Typically the preferred approach because they can achieve higher virtualisation efficiency by dealing directly with the hardware.  
- Type 1 hypervisors provide higher performance efficiency, availability, and security than type 2 hypervisors.  

<mark style="background: #BABD00;">Type 2:</mark>  
- hypervisors run on a host operating system that provides virtualisation services, such as I/O device support and memory management.  
- Used on client systems where efficiency is less critical & support for a broad range of I/O devices is important and can be provided by the host operating system.  
- e.g. Oracle VirtualBox, VMware Server and Microsoft Virtual PC

### <mark style="background: #BABD00;">The Hypervisor:</mark>

![](https://i.imgur.com/rEHtfCm.png)

### <mark style="background: #BABD00;">VM Players:</mark>
  
<mark style="background: #BABD00;">VMWare</mark> is perhaps one of the most well-known virtualisation software makers in the market. VMWare also offers virtual appliances, which are virtual machines for download, sometimes for free. VMWare products are generally compatible with the Windows and Linux platforms. There is also a version that runs on Mac OS X.  

Xen is a lightweight open-source hypervisor which runs on Intel (Nasdaq: INTC) or AMD (NYSE: AMD) x86 and 64-bit processors, with or without virtualisation technologies.  

Microsoft (Nasdaq: MSFT) Virtual Server and Virtual PC are relatively new entrants into this software space. If you run only Windows desktops and servers, you may not need to look any further for virtualisation software.  

Parallels is one of the most widely used options for Mac computers. It was among the first to create commercial virtualisation products that could run non-Apple OSes on Mac hosts. Parallels also runs on Windows and Linux hosts.  

Other free or open-source choices include Qemu.

### <mark style="background: #BABD00;">Virtualisation in the cloud:</mark>

Where everything can be provided as a service.

![](https://i.imgur.com/mspKkg4.png)

### <mark style="background: #BABD00;">Responsibility:</mark>

Local clouds give you the power of cloud computing in your own IT infrastructure.  

Get the benefits of cloud computing behind the security of your own firewall.  

Deploy workloads and have them running immediately.  

Grow or shrink computing capacity to meet your application's needs.  

Get the most out of your existing infrastructure.

![](https://i.imgur.com/w2JqNeV.png)

### <mark style="background: #BABD00;">The main players:</mark>

![](https://i.imgur.com/vk6fgNJ.png)

# <mark style="background: #BABD00;">07 The Virtualised Data Centre</mark>

Transforming a <mark style="background: #BABD00;">Classic Data Centre (CDC)</mark> into a <mark style="background: #BABD00;">Virtualised Data Centre (VDC)</mark> requires virtualising the core elements of the data centre.

Using a phased approach to a virtualised infrastructure enables smoother transition to virtualize core elements.

![](https://i.imgur.com/SWp1MUx.png)

### <mark style="background: #BABD00;">Compute Virtualisation:</mark>

<mark style="background: #BABD00;">Compute Virtualisation:</mark> It is a technique of masking or abstracting the physical compute hardware and enabling multiple operating systems (OSs) to run concurrently on a single or clustered physical machine(s).

Enables creation of multiple virtual machines (VMs), each running an OS and application  
- VM is a logical entity that looks and behaves like physical machine  
- Virtualisation layer resides between hardware and VMs -> Also known as hypervisor  
- VMs are provided with standardized hardware resources

![](https://i.imgur.com/lL4unw0.png)

<mark style="background: #BABD00;">Benefits of Compute Virtualisation:</mark>
- Server consolidation  
- Isolation  
- Encapsulation  
- Hardware independence  
- Reduced cost

### <mark style="background: #BABD00;">Resource Management:</mark>

<mark style="background: #BABD00;">Resource management:</mark> A process of allocating resources from physical machine or clustered physical machines to virtual machines (VMs) to optimise the utilisation of resources.

<mark style="background: #BABD00;">Goals of resource management:</mark>  
- Controls utilisation of resources  
- Prevents VMs from monopolising resources  
- Allocates resources based on relative priority of VMs  

Resources must be pooled to manage them centrally

### <mark style="background: #BABD00;">Resource Pool:</mark>

<mark style="background: #BABD00;">Resource Pool:</mark> It is a logical abstraction of aggregated physical resources that are managed centrally.

Created from a physical machine or cluster  

Administrators may create child resource pool or virtual machine (VM) from the parent resource pool  

Reservation, limit, and share are used to control the resources consumed by resource pools or VMs.

### <mark style="background: #BABD00;">Resource Pool Example:</mark>

![](https://i.imgur.com/8WZPkl5.png)

### <mark style="background: #BABD00;">Share, Limit and Reservation:</mark>

Parameters that control the resources consumed by a child resource pool or a virtual machine (VM) are as follows:  
- <mark style="background: #BABD00;">Reservation:</mark> Amount of CPU and memory reserved for a VM or a child resource pool 
- <mark style="background: #BABD00;">Limit:</mark> Maximum amount of CPU and memory a VM or a child resource pool can consume  
- <mark style="background: #BABD00;">Share:</mark> Amount of CPU or memory resources a VM or a child resource pool can have with respect to its parent’s total resources

### <mark style="background: #BABD00;">Optimising CPU Resources:</mark>

Modern CPUs are equipped with multiple cores and hyper-threading:
- Multi-core processors have multiple processing units (cores) in a single CPU  
- Hyper-threading makes a physical CPU appear as two or more logical CPUs  

Allocating a CPU resource efficiently and fairly is critical  

Hypervisor schedules virtual CPUs on the physical CPUs  

Hypervisors support multi-core, hyper-threading, and CPU load-balancing features to optimize CPU resources

### <mark style="background: #BABD00;">Multi-core Processors:</mark>

![](https://i.imgur.com/3Hw6zIw.png)

### <mark style="background: #BABD00;">Resource Management Tool:</mark>

Provides ability to manage physical machines running hypervisor  

Enables centralised management of resources from a management server  

Enables pooling of resources and allocates capacity to VMs: Communicates with hypervisors to perform management  

Provides operational automation

![](https://i.imgur.com/lTyR9Kk.png)

### <mark style="background: #BABD00;">Storage Virtualisation:</mark>

<mark style="background: #BABD00;">Storage virtualisation:</mark> It is the process of masking the underlying complexity of physical storage resources and presenting the logical view of these resources to compute systems.

Logical to physical storage mapping is performed by virtualisation layer.  

Virtualisation layer abstracts the identity of physical storage devices: Creates a storage pool from multiple, heterogeneous storage arrays.  

Virtual volumes are created from the storage pools and are assigned to the compute system.

<mark style="background: #BABD00;">Benefits of storage virtualisation:</mark>
- Adds or removes storage without any downtime  
- Increases storage utilisation thereby reducing TCO  
- Provides non-disruptive data migration between storage devices  
- Supports heterogeneous, multi-vendor storage platforms  
- Simplifies storage management

### <mark style="background: #BABD00;">Storage for virtual machines:</mark>

VMs are stored as set of files on storage space available to hypervisor  

‘Virtual disk file’ represents a virtual disk used by a VM to store its data  

Size of virtual disk file represents storage space allocated to virtual disk  

<mark style="background: #BABD00;">VMs remain unaware of:</mark>
- Total space available to the hypervisor  
- Underlying storage technologies

![](https://i.imgur.com/ESrjNhO.png)

### <mark style="background: #BABD00;">Virtual Provisioning at Compute:</mark>

Hypervisor performs virtual provisioning to create virtual disks for VMs: Virtual machine sees full logical disk size at all times  

Hypervisor allocates storage space to the virtual disk only when VM requires storage space: Eliminates the need to overprovision virtual disks

![](https://i.imgur.com/cFT9boD.png)

<mark style="background: #BABD00;">Virtual Provisioning Benefits:</mark>  
- Reduces administrative overhead  
- Improves capacity utilisation  
- Reduces cost  
- Reduces downtime

### <mark style="background: #BABD00;">Network Virtualisation:</mark> 

<mark style="background: #BABD00;">Network Virtualisation:</mark> It is a process of logically segmenting or grouping physical network(s) and making them operate as single or multiple independent network(s) called “Virtual Network(s)”.  
 
Enables virtual networks to share network resources  

Allows communication between nodes in a virtual network without routing of frames  

Enforces routing for communication between virtual networks  

Restricts management traffic, including ‘Network Broadcast’, from propagating to other virtual network  

Enables functional grouping of nodes in a virtual network

### <mark style="background: #BABD00;">Network Virtualisation in VDC:</mark>

Involves virtualising physical and VM networks.

#### <mark style="background: #BABD00;">Physical Network:</mark>

Consists of following physical components: Network adapters, switches, routers, bridges, repeaters, and hubs  

<mark style="background: #BABD00;">Provides connectivity:</mark>  
- Among physical servers running hypervisor  
- Between physical servers and clients
- Between physical servers and storage systems

![](https://i.imgur.com/kJY6wcy.png)

#### <mark style="background: #BABD00;">VM Network:</mark>
- Resides inside physical server  
- Consists of logical switches called “virtual switches”  
- Provides connectivity among VMs inside a physical server  
- Provides connectivity to Hypervisor kernel  
- Connects to physical network

![](https://i.imgur.com/1B78FqG.png)

### <mark style="background: #BABD00;">Network Connectivity and Traffic Flow: Example:</mark>

![](https://i.imgur.com/HJPqvRD.png)

### <mark style="background: #BABD00;">Benefits of Network Virtualisation</mark>

![](https://i.imgur.com/BqjNl27.png)

### <mark style="background: #BABD00;">Desktop Virtualisation</mark>

<mark style="background: #BABD00;">Desktop Virtualisation:</mark> Technology which enables detachment of the user state, the Operating System (OS), and the applications from endpoint devices.

Enables organisations to host and centrally manage desktops:
- Desktops run as virtual machines within the VDC, They may be accessed over LAN/WAN  
- Endpoint devices may be thin clients or PCs

![](https://i.imgur.com/w7zwbP4.png)

### <mark style="background: #BABD00;">Virtual Desktop Infrastructure (VDI): Components</mark>

- Endpoint devices  
- VM hosting/execution servers  
- Connection Broker

![](https://i.imgur.com/vJMn1zC.png)

<mark style="background: #BABD00;">Connection Broker:</mark> It is responsible for establishing and managing the connection between the endpoint device and the desktop VM

![](https://i.imgur.com/WxkCRcm.png)

### <mark style="background: #BABD00;">Application Virtualisation:</mark>

<mark style="background: #BABD00;">Application Virtualisation:</mark>  It is the technique of presenting an application to an end user without any installation, integration, or dependencies on the underlying computing platform

Allows application to be delivered in an isolated environment
- Aggregates Operating System (OS) resources and the application into a virtualised container  
- Ensures integrity of Operating System (OS) and applications  
- Avoids conflicts between different applications or different versions of the same application

### <mark style="background: #BABD00;">Cloud Computing: Essential Characteristics</mark>

![](https://i.imgur.com/fndT1WR.png)

### <mark style="background: #BABD00;">Cloud Offering Examples:</mark>

![](https://i.imgur.com/NUoid2H.png)

### <mark style="background: #BABD00;">Cloud Computing Benefits:</mark>

![](https://i.imgur.com/sQg0mcR.png)

### <mark style="background: #BABD00;">Cloud Deployment Model - Public Cloud:</mark>

![](https://i.imgur.com/qB9fvbj.png)

### <mark style="background: #BABD00;">Cloud Deployment Model - Private Cloud:</mark>

![](https://i.imgur.com/qVPWPaX.png)

### <mark style="background: #BABD00;">Cloud Deployment Model - Hybrid Cloud:</mark>

![](https://i.imgur.com/BpcmBVr.png)

### <mark style="background: #BABD00;">Economics of Cloud:</mark>

Cloud has changed the economics of IT  

Cloud enables to move from a CAPEX to an OPEX model  

There are a variety of costs and expenses that companies have to pay to continue running their businesses. The most common are capital expenditures (<mark style="background: #BABD00;">CapEx</mark>) and operating expenses (<mark style="background: #BABD00;">OpEx</mark>). Capital expenditures are major purchases that a company makes, which are used over the long term. Operating expenses, on the other hand, are the day-to-day expenses that a company incurs to keep its business running.

<mark style="background: #BABD00;">Cloud provides the following key cost savings:</mark>  
- Infrastructure cost  
- Management cost  
- Power and energy cost

![](https://i.imgur.com/orr2QjE.png)

### <mark style="background: #BABD00;">Cloud Challenges – Consumer’s Perspective</mark>

<mark style="background: #BABD00;">Security and Regulation:</mark>  
- Consumers are indecisive to transfer control of sensitive data  
- Regulation may prevent organisations using Cloud services  

<mark style="background: #BABD00;">Network latency:</mark> Real time applications may suffer due to network latency and limited bandwidth  

<mark style="background: #BABD00;">Supportability:</mark> Legacy or Custom applications may not be compatible with Cloud platform  

<mark style="background: #BABD00;">Interoperability:</mark> Lack of standardisation across Cloud-based platforms

### <mark style="background: #BABD00;">Cloud Challenges – Provider’s Perspective:</mark>

<mark style="background: #BABD00;">Service warranty and service cost:</mark>  
- Resources must be kept ready to meet unpredictable demand  
- Hefty penalty, if SLAs are not fulfilled  

<mark style="background: #BABD00;">Huge numbers of software to manage:</mark>  
- Huge number of applications and platform software to purchase  
- ROI is unpredictable  

<mark style="background: #BABD00;">No standard Cloud access interface:</mark>  
- Cloud customers want open APIs  
- Need agreement among Cloud providers for standardisation

# <mark style="background: #BABD00;">08 DAS-NAS-SAN Storage</mark>

### <mark style="background: #BABD00;">Storage Basics:</mark>  

Information (data) is constantly flowing in and out of computers.  

Data coming in is either stored in memory for quick access (non-permanent storage) or written to disk so that it can be retrieved later.  

<mark style="background: #BABD00;">How this information is stored depends on several issues:</mark>  
- How will it be stored (what will it be stored ON)?  
- What is the protocol by which this data will be transferred?  
- What devices will it pass through on the way to being stored?

### <mark style="background: #BABD00;">Data Storage Types:</mark> 

Single disk drive (self explanatory)  

<mark style="background: #BABD00;">Volume:</mark> a “logical” disk drive. A concatenation of drives. When one fills up, it goes to the next one. No RAID, no striping. To the OS, a logical volume looks like one disk drive.  

<mark style="background: #BABD00;">Storage Array:</mark> Also a group of more than one disk joined together – but can do striping and/or redundancy. Implies some type of RAID. 

<mark style="background: #BABD00;">SCSI:</mark> SCSI stands for Small Computer System Interface. It is a means of attaching additional storage to a computer. For example, a typical RAID Controller is a SCSI device that allows connection to an external storage enclosure with multiple drives.  

<mark style="background: #BABD00;">ISCSI:</mark> Internet/SCSI protocol. Another approach to offering storage on a network. Rather then using file protocols to communicate across a TCP/IP network, native SCSI commands are “encapsulated” in TCP/IP packets. 

<mark style="background: #BABD00;">NAS:</mark> Network Attached Storage. Rather than simply attaching storage to one machine, it is attached to the computer network. Multiple machines can now access the storage. A file protocol must be used to communicate across the network. 

<mark style="background: #BABD00;">DAS:</mark> Direct Attached Storage is a type of storage that is attached directly to a computer without going through a network. The storage might be connected internally or externally. Only the host computer can access the data directly.

<mark style="background: #BABD00;">SAN:</mark> Storage Area Network. Whereas a NAS is storage that is attached to a network, SAN is a storage network in and of itself that can be attached to multiple machines.  
- SAN is an industry-wide term for both the storage and the switching network. A SAN does not have the protocol conversion overhead of NAS or ISCSI, and tends to offer better performance. A SAN may require a higher initial investment in infrastructure.  
- Devices appear as locally attached to the operating system.

### <mark style="background: #BABD00;">Network Storage:</mark>

Many forms of storage networking - Why?  

New technologies emerge and evolve but legacy systems remain – investment, familiarity, training?  

No single storage networking approach solves all problems or optimises all variables.  

There are trade-offs in cost, ease-of management, performance, distance and maturity  

Multiple storage network alternatives will coexist (often within the same organisation!)

### <mark style="background: #BABD00;">Hard Drives:</mark>

The Hard Drive - basic storage element  

Made of complex devices composed of platters, heads, cylinders and tracks  

Logical Block Addressing (LBA) addresses the sector within the disk. Modern drives have 4 kilo-byte sectors  

File systems arrange files into sectors so that they can be stored and retrieved  

The File system usually deals with clusters of blocks and uses a File Allocation Table to map a file to the sectors.

### <mark style="background: #BABD00;">Direct Attached Storage (Internal):</mark>

![](https://i.imgur.com/QJiOFVY.png)

Traditional internal data storage

![](https://i.imgur.com/Em4RKzr.png)

### <mark style="background: #BABD00;">DAS w/ internal controller and external storage:</mark>

![](https://i.imgur.com/OhJimG2.png)

Direct Attached Storage -RAID controller is internal to the computer system, and the disk drives are attached to the controller via a single path

### <mark style="background: #BABD00;">DAS ext. controller & ext. storage:</mark>

![](https://i.imgur.com/yndLZVx.png)

![](https://i.imgur.com/JV0aDmz.png)

### <mark style="background: #BABD00;">I/O Transfer:</mark>

<mark style="background: #BABD00;">RAID Controller:</mark>  
-  Contains the "smarts"  
- Determines how the data will be written (striping, mirroring, RAID 10, RAID 5, etc.)  

<mark style="background: #BABD00;">Host Bus Adapter (HBA):</mark>  
- Simply transfers the data to the RAID controller.  
- Does not do any RAID or striping calculations. Speed!  
- Required for external storage.

### <mark style="background: #BABD00;">The Old Storage Environment:</mark>

Direct Attached Storage (DAS)  

Storage is captive ‘behind’ the server  

<mark style="background: #BABD00;">Server CPU must handle user I/O requests, but also:</mark>  
- User-database inquiries  
- User file/print serving  
- Data-integrity checking  
- Communication with other devices  

Data access is file system and platform dependent  

Costly to scale; complex to manage

![](https://i.imgur.com/Utvgob9.png)

### <mark style="background: #BABD00;">NAS: What is it?</mark>

<mark style="background: #BABD00;">NAS:</mark> Network Attached Storage  

Designed to provide shared access to storage across a standard TCP/IP network  

Sharing data across TCP/IP by converting block-level SCSI commands to file sharing protocols  

<mark style="background: #BABD00;">‘sharing protocols’ ? (Common file sharing protocols):</mark>  
- UNIX Network File System (NFS) was developed originally for sharing files between UNIX systems across a LAN.  
- Support expanded to include non-UNIX systems;  
- (but most NFS clients today are computers running some flavour of UNIX/Linux.)  

Windows Common Internet File System (CIFS) created by Microsoft, formerly known as Server Message Block (SMB), developed by IBM in DOS.

### <mark style="background: #BABD00;">NAS I/O Requests:</mark>
  
File I/O is a higher-level type of request that, in essence, specifies the file to be accessed, an offset into the file (as if the file was a set of contiguous bytes), and a number of bytes to read or write beginning at that offset.  

Unlike block I/O, there is no awareness of a disk volume or disk sectors in a file I/O request.  

Inside the NAS product (“appliance”), an operating system or OS kernel tracks where files are located on disk and issues a block I/O request to the disks to fulfil the file I/O read and write requests it receives.

### <mark style="background: #BABD00;">Network Storage Possibilities:</mark>

For small businesses, the solution for managing storage intelligently is consolidation.  

Rather than dispersing data across several PCs, laptops or small servers, consolidating storage into one or two locations makes it much easier to grow, manage and protect.  

When storage is freed from the constraints of individual PCs and file servers, it can be put on the network as a separate, single resource that can be allocated to applications as necessary.

### <mark style="background: #BABD00;">NAS:</mark>

Storage “Appliances” utilise a stripped-down OS that optimises file protocol performance  

Instead of starting with a general-purpose computer and configuring or removing features from that base, NAS designs begin with the bare-bones components necessary to support file transfers and add features “from the bottom up.”  

Clients generally access a NAS over an ethernet connection. The NAS appears on the network as a single "node" that is the IP address of the head device.

### <mark style="background: #BABD00;">SAN - Storage Area Network:</mark>

SANs are networked infrastructures designed to provide a flexible, high-performance, and highly scalable storage environment.  

High-performance Fibre Channel switches and Fibre Channel network protocols ensure that device connections are both reliable and efficient.

![](https://i.imgur.com/qLvCf9O.png)

![](https://i.imgur.com/pjgA2ZE.png)

A Storage Area Network (SAN) is a specialised, high-speed network that provides network access to storage devices.  

SANs are typically composed of hosts, switches, storage elements, and storage devices that are interconnected using a variety of technologies, topologies, and protocols.  

SANs may span multiple sites..

[SAN explanation](https://www.snia.org/education/storage_networking_primer/san/what_san "https://www.snia.org/education/storage_networking_primer/san/what_san")

### <mark style="background: #BABD00;">SAN - Benefits:</mark>

<mark style="background: #BABD00;">Access:</mark>  
- longer distance between processors and storage, higher availability, improved performance (because I/O traffic is offloaded from a LAN to a dedicated network, and because Fibre Channel is generally faster than most LAN media).  
- larger number of processors can be connected to the same storage device compared to typical built-in  device attachment facilities.

<mark style="background: #BABD00;">Consolidation:</mark> 
- Replacement of multiple independent storage devices by fewer devices that support capacity sharing - disk and tape pooling.  
- SANs provide the ultimate in scalability - software can allow multiple SAN devices to appear as a single pool of storage accessible to all processors on the SAN.  
- Storage on a SAN can be managed from a single point of control. Controls over which hosts can see which storage (called zoning and LUN masking) can be implemented.

<mark style="background: #BABD00;">Protection:</mark>  
- LAN-free backups occur over the SAN rather than the (slower) LAN, and server-free backups can let disk storage “write itself” directly to tape without processor overhead.  

<mark style="background: #BABD00;">Data Sharing:</mark>  
- sharing data, as noted earlier, offers benefits such as reducing the number of copies of files, increasing accessibility to current data and reducing the need to transfer copies of data between servers over the network.

### <mark style="background: #BABD00;">SAN - Different Technologies:</mark>

Multiple technologies can be used when building a SAN  

Traditionally the dominant technology is Fibre Channel, but IP based solutions are also quite popular for specific applications (due to costs!)  
  
<mark style="background: #BABD00;">The concept of SAN is also independent from the devices that are attached to it:</mark>
- Can be disks, tapes, RAIDs, file servers, or other!  
- Yes, Magnetic Tape storage is still used in 2024: Often cheaper than alternative, can last 30 years or more (if kept clean, dry and protected) which is excellent for compliance with industry-specific storage regulations.

### <mark style="background: #BABD00;">Storage Systems Architecture:</mark>

![](https://i.imgur.com/l70GUI3.png)

### <mark style="background: #BABD00;">NAS vs SAN Similarities and differences:</mark>

![](https://i.imgur.com/9QNOQ9O.png)

Note the relative position of the File system in each case.

![](https://i.imgur.com/PIiYH61.png)

### <mark style="background: #BABD00;">NAS with HTTPS:</mark>

Many NAS systems also support Hypertext Transfer Protocol (HTTPS).  

Clients can often download files in their Web browser from a NAS that supports HTTPS.  

NAS systems also commonly employ HTTPS as an access protocol for Web-based administrative user interfaces.

### <mark style="background: #BABD00;">NAS vs. SAN:</mark>

<mark style="background: #BABD00;">NAS</mark> is optimised for ease-of-management and file sharing using lower-cost Ethernet-based networks.  

Installation is relatively quick, and storage capacity is automatically assigned to users on demand.  

<mark style="background: #BABD00;">SAN</mark> is optimised for performance and scalability.  
- Major potential benefits include support for high-speed Fibre Channel media which is optimised for storage traffic, managing multiple disk and tape devices as a shared pool with a single point of control, specialised backup facilities that can reduce server and LAN utilisation and wide industry support.  
- Cost savings can be obtained over TCP/IP using iSCSI (later).

### <mark style="background: #BABD00;">NAS Costs?</mark>

NAS will generally cost more than DAS (because of its built-in file sharing intelligence), but has the following potential advantages:
- <mark style="background: #BABD00;">distance</mark> (because it is attached over a network), large number of users being able to access the same storage device  
- <mark style="background: #BABD00;">capacity pooling</mark> within the NAS appliance (sharing capacity among all hosts using the NAS)  
- <mark style="background: #BABD00;">file sharing</mark> (as opposed to data transfer or multiple copies on distributed hosts).

### <mark style="background: #BABD00;">Summary:</mark>

![](https://i.imgur.com/EMKCax4.png)

# <mark style="background: #BABD00;">09 Cloud Migration Considerations:</mark>


<mark style="background: #BABD00;">Upon completion of this lesson, you should be able to:</mark>  
- Discuss the considerations for migration to Cloud  
- Discuss the Cloud models suitable for different categories of users  
- List the considerations for choosing applications suitable for Cloud  
- Discuss different phases to adopt the Cloud

<mark style="background: #BABD00;">Topics covered in this lesson:</mark>  
- Considerations for Cloud model and suitable application for Cloud  
- Criteria for Cloud vendor selection  
- Service Level Agreements (SLAs) and performance issues  
- Cloud vendor lock-in  
- Cloud open standards

### <mark style="background: #BABD00;">Cloud Migration – Key Questions</mark>  

<mark style="background: #BABD00;">CIOs/IT Managers seeking to move to Cloud face several questions.</mark>
- How does Cloud fit into the organisation’s requirements? (Financial advantage, convenience, etc. )
- Which are the applications suitable for Cloud?  
- How do I choose the Cloud Vendor?  
- Is the Cloud infrastructure capable of providing the required Quality of Service (QoS)?(Performance, availability, and security)  
- How will I address Change Management concerns?  
- What can Cloud provide? (Application, platform and infrastructure)

### <mark style="background: #BABD00;">How does Cloud fit to your requirements?</mark>  

Current infrastructure and requirements: Consider from application, network, and security perspectives.  

‘Risk vs. Convenience’ profile: Based on this profile, choose ‘Cloud model’ for your organisation.

![](https://i.imgur.com/qq4VTWs.png)

### <mark style="background: #BABD00;">What Model Fits for You?</mark>

![](https://i.imgur.com/15IZYu6.png)

### <mark style="background: #BABD00;">Choosing Applications for Public Cloud:</mark>

<mark style="background: #BABD00;">Proprietary and mission-critical application:</mark>  
- Proprietary applications provide competitive advantage  
- Organisation perceives high risk to move this application to Cloud  
- These applications are typically maintained in-house  

<mark style="background: #BABD00;">Non-proprietary but mission-critical application:</mark>  
- Organisation perceives high risk to move this application to Cloud  
- It can be moved to Cloud if the organisation does not have adequate resources to maintain the application  

<mark style="background: #BABD00;">Non-proprietary and non-mission critical application:</mark>  
- Perceived as good candidate for Cloud, unless it is performance sensitive.

### <mark style="background: #BABD00;">Selecting a Cloud Service Provider:</mark>  

<mark style="background: #BABD00;">Some key questions to ask before selecting a Cloud Service provider:</mark>  
- How long has the provider been providing the services?  
- How well does the provider meet the organisation’s current and future requirements?  
- How easy is it to relinquish resources not in use and to reduce cost?  
- What tools does the provider offer (like virtual machine images) that would make it easy to move to another provider when required?  
- How easy is it to add/remove services?  
- Does the provider have good customer service support?  
- What happens when the provider upgrades their software? Is it forced on everyone? Can you upgrade on your own schedule?  
- Does the provider offer required security services?  
- Does the provider meet your legal and privacy requirements?

### <mark style="background: #BABD00;">Service Level Agreement (SLA):</mark>  

SLA is an agreement between the Cloud provider and the consumer that defines the quality and reliability of service  

SLA also defines the penalty for not meeting the agreement  

SLAs include factors such as network availability, performance, etc.

### <mark style="background: #BABD00;">Cloud Performance:</mark>  

<mark style="background: #BABD00;">Two key performance considerations:</mark>  
- <mark style="background: #BABD00;">Infrastructure performance:</mark> Saturation of Cloud infrastructure may impact performance. Right amount of resources should be allocated to the application to ensure performance  
- <mark style="background: #BABD00;">Network latency:</mark> Network latency typically arises due to large data sets being sent to and from the Cloud provider

### <mark style="background: #BABD00;">Cloud Vendor Lock-in:</mark>

Cloud vendor (service provider) may lack open standards or use proprietary software/APIs.  

Rigid agreements prevent the consumer from moving without penalties.  

Cloud vendors may prevent a consumer from moving one service model to another (i.e. application built on a PaaS moving to an IaaS model).  

Application may require significant rework/redesign before deploying in different Cloud.

### <mark style="background: #BABD00;">Cloud Open Standards:</mark>
- Use proven and widely accepted technologies  
- Prevent lock-in issues  
- Open Virtual Machine Format (OVF) - an example of open standard

### <mark style="background: #BABD00;">Cloud Adoption Phases:</mark>

![](https://i.imgur.com/52roJ3L.png)

### <mark style="background: #BABD00;">Phase 1 - Assessment:</mark>

The assessment phase involves consideration of various factors  

Besides Cloud migration considerations discussed earlier, other key assessments are:  
- Financial  
- Security and compliance  
- Technical  
- Issues with licensed products

### <mark style="background: #BABD00;">Financial Assessment:</mark>

Provides cost comparison of in-house vs. service provider (TCO and ROI)  

Requires cost consideration of the following elements:

![](https://i.imgur.com/HsN7crB.png)

### <mark style="background: #BABD00;">Security and Compliance Assessment:</mark>

Involves security advisor early in the process  

<mark style="background: #BABD00;">Enables organisations to:</mark>  
- Identify risk tolerance and security threats for an application  
- Understand regulatory/contractual obligations to store data in specific jurisdictions  
- Explore whether the Cloud vendor offers: Choice of selecting geographic location to store the data. Guarantee that data does not move unless organisation decides to move 
- Explore options to retrieve all data back from the Cloud when required  
- Identify the download or delete option of data, if required  
- Identify the choice of encryption of data when in transit and at rest

### <mark style="background: #BABD00;">Technical Assessment:</mark>

<mark style="background: #BABD00;">Enables organisations to identify:</mark>  
- Whether Cloud service provider offers the required infrastructure  
- Whether an application is compatible with Cloud infrastructure  
- The dependencies of an application on other components and services  
- The component that must be local (on-premise) and components that can move to the Cloud 
- The latency and bandwidth requirements  
- The effort required to migrate the application

### <mark style="background: #BABD00;">Assessment of License Issues:</mark>  

<mark style="background: #BABD00;">Use existing license:</mark>  
- Identify whether the organisation can move its existing licensed software into the Cloud  
- Cloud providers have partnered with software vendors to permit the use of existing software license in the Cloud  

<mark style="background: #BABD00;">Use SaaS based Cloud service:</mark>  
- Some software vendors offer their software as a service apart from installable option 
- If a software vendor does not offer its software as a service, explore an equivalent offering by different Cloud vendor

### <mark style="background: #BABD00;">Phase 2: Proof of Concept</mark>  

Goal of this phase is to verify that an application runs as expected in the Cloud  

<mark style="background: #BABD00;">Proof of Concept enables organisations to:</mark>  
- Explore the capabilities of the Cloud  
- Explore the different business continuity and disaster recovery options offered by the Cloud vendor  
- Estimate the effort required to roll out the application  
- Identify applications that can be immediately moved after proof of concept

### <mark style="background: #BABD00;">Phase 3: Migration</mark>

![](https://i.imgur.com/eyDmzju.png)

### <mark style="background: #BABD00;">Phase 4: Optimisation</mark>

Test the application after migration is complete  

Understand the usage pattern and optimise resource consumption  

Relinquish idle resources

### <mark style="background: #BABD00;">Summary:</mark>

<mark style="background: #BABD00;">Key points covered in this module:</mark>  
- Considerations for migration to Cloud  
- Cloud models suitable for different categories of users  
- Guidelines for selecting a suitable application for Cloud  
- Phases to adopt the Cloud

### <mark style="background: #BABD00;">Check Your Knowledge:</mark>  
1. What are the key concerns that organisations have while adopting the Cloud?  
2. Describe the guidelines for choosing the right application for the Cloud.  
3. What are the two options available for migrating licensed software to the Cloud?  
4. Describe the two migration strategies.  
5. What should be considered to avoid Cloud vendor lock-in?

# <mark style="background: #BABD00;">10 Data Protection RAID</mark>


<mark style="background: #BABD00;">Upon completion of this lesson, you should be able to:</mark>  
- Describe RAID implementation methods  
- Describe the three RAID techniques  
- Describe commonly used RAID levels  
- Describe the impact of RAID on performance  
- Compare RAID levels based on their cost, performance, and protection

<mark style="background: #BABD00;">During this lesson the following topics are covered:</mark>  
- RAID Implementation methods  
- RAID array components  
- RAID techniques

### <mark style="background: #BABD00;">RAID Techniques:</mark>

<mark style="background: #BABD00;">RAID:</mark> It is a technique that combines multiple disk drives into a logical unit (RAID set) and provides protection, performance, or both.

Due to mechanical components in a disk drive it offers limited performance  

An individual drive has a certain life expectancy and is measured in MTBF (Mean Time Between Failures):  
- For example: If the MTBF of a drive is 750,000 hours, and there are 1000 drives in the array, then the MTBF of the array is 750 hours (750,000/1000)  

RAID was introduced to mitigate these problems

### <mark style="background: #BABD00;">RAID Implementation Methods</mark>  

#### <mark style="background: #BABD00;">Software RAID implementation</mark>  

Uses host-based software to provide RAID functionality  

<mark style="background: #BABD00;">Limitations:</mark>  
- Use host CPU cycles to perform RAID calculations, hence impact overall system performance  
- Support limited RAID levels  
- RAID software and OS can be upgraded only if they are compatible  

#### <mark style="background: #BABD00;">Hardware RAID Implementation</mark>  

Uses a specialised hardware controller installed either on a host or on an array.

### <mark style="background: #BABD00;">RAID Array Components:</mark>

![](https://i.imgur.com/jppzt5M.png)

### <mark style="background: #BABD00;">RAID Techniques:</mark>

<mark style="background: #BABD00;">Striping:</mark>  Striping is a technique which offers the best performance of any RAID configuration. In a striped array, data is interleaved across all the drives in the array.  

<mark style="background: #BABD00;">Mirroring:</mark> whatever you write to one drive, gets written simultaneously to another. Thus, you always have an exact duplicate of your data on the second drive.  

<mark style="background: #BABD00;">Parity:</mark> RAID controller adds a parity (extra) byte of data tacked onto the actual data being written to the array. Added by the RAID controller to equal either an even or an odd number. By analysing this value, the controller can determine whether the information has been compromised in any way. If it has, it can replace the data automatically with data from the other drive.

### <mark style="background: #BABD00;">RAID Technique – Striping:</mark>

![](https://i.imgur.com/s1Ctt8x.png)

### <mark style="background: #BABD00;">RAID Technique – Mirroring:</mark>

![](https://i.imgur.com/J8yI01A.png)

### <mark style="background: #BABD00;">RAID Technique - Parity:</mark>

![](https://i.imgur.com/WVbET7q.png)

### <mark style="background: #BABD00;">Data Recovery in Parity Technique:</mark>

![](https://i.imgur.com/KylOBLE.png)

### <mark style="background: #BABD00;">Lesson 2 - RAID Levels:</mark>

<mark style="background: #BABD00;">During this lesson the following topics are covered:</mark>  
- Commonly used RAID levels  
- RAID impacts on performance  
- RAID comparison  
- Hot spare

<mark style="background: #BABD00;">Commonly used RAID levels are:</mark>  
- RAID 0 – Striped set with no fault tolerance  
- RAID 1 – Disk mirroring  
- RAID 1 + 0 – Nested RAID  
- RAID 3 – Striped set with parallel access and dedicated parity disk  
- RAID 5 – Striped set with independent disk access and a distributed parity  
- RAID 6 – Striped set with independent disk access and dual distributed parity

### <mark style="background: #BABD00;">RAID 0:</mark>

![](https://i.imgur.com/5L6OURW.png)

<mark style="background: #BABD00;">RAID 0:</mark> non-redundant array of disk drives  

Also called "stripe" mode.  

Operations on the array will be split across the devices e.g. a large write could be split up as 4 kB to disk 0, 4 kB to disk 1, 4 kB to disk 2, then 4 kB to disk 0 again, and so on.  

<mark style="background: #BABD00;">Pro:</mark> parallel writing increase speed nX where n = no. of partitions, x speed on single drive  

<mark style="background: #BABD00;">Con:</mark> No Redundancy, inefficient use of disk space: no savings!  

RAID 0 provides no redundancy, and as such, should never be used for applications where data is critical.

![](https://i.imgur.com/d6U6m0l.png)

### <mark style="background: #BABD00;">RAID 1:</mark>

![](https://i.imgur.com/1jD4yum.png)

<mark style="background: #BABD00;">RAID-1 (Mirroring):</mark>  
- used on two or more disks.  
- This mode maintains an exact mirror of the information on one disk on the other disk(s).  

<mark style="background: #BABD00;">Pros:</mark> if disk removed (or crashes), all data is still intact  

<mark style="background: #BABD00;">Cons:</mark> Increase of cost proportional to the amount of redundancy.  

Performance may be impacted if copy is done serially.

![](https://i.imgur.com/pRW1DlG.png)

### <mark style="background: #BABD00;">RAID 1 + 0 (RAID 2):</mark>

![](https://i.imgur.com/rDSkUV5.png)

Also called Nested RAID
### <mark style="background: #BABD00;">RAID 3 & 4:</mark>

<mark style="background: #BABD00;">RAID 3:</mark>  
- Similar to RAID 2 which uses byte level striping and a dedicated parity disk  
- BUT RAID 3 uses simple (&fast) XOR algorithm to generate parity.  
- Data is striped (at the byte level) across multiple disks. The parity information is sent to a dedicated parity disk, but the failure of any disk in the array can be tolerated.  
- <mark style="background: #BABD00;">Pros:</mark> delivers good performance and fault tolerance.  
- <mark style="background: #BABD00;">Cons:</mark> dedicated parity disk does slow down write speeds because the parity info has to be written to the parity drive whenever a write occurs  

![](https://i.imgur.com/JlJ8OEY.png)

![](https://i.imgur.com/RAsCHIW.png)

<mark style="background: #BABD00;">RAID 4:</mark>  
- very similar to RAID 3. RAID 4 uses block level striping with parity disk. (Block> Byte)  
- Pros? advantage of block level change the stripe size to suit your application needs.

![](https://i.imgur.com/FCq7YgC.png)

### <mark style="background: #BABD00;">RAID 5:</mark>

Most popular member of the RAID family - combines block level striping with distributed parity for:  
- good performance,  
- fault tolerance  
- storage efficiency.  

<mark style="background: #BABD00;">Distributing parity stripes over a series of hard drives:</mark> 
- Minimises write bottlenecks of RAID levels 3 and 4  
- Provides relief to the concentration of write activity on a single drive, which in turn enhances overall system performance.  

RAID 5 is often used as an all-purpose RAID solution, but it is also used for database and file server applications.  

RAID 5 requires a minimum of three hard drives, but often costs less to implement than RAID 3 or 4.  

RAID recovery may be necessary if more than one disk fails.

![](https://i.imgur.com/UijDLWM.png)

![](https://i.imgur.com/M9qfCk1.png)

### <mark style="background: #BABD00;">RAID 6:</mark>

![](https://i.imgur.com/bqT87M7.png)

### <mark style="background: #BABD00;">RAID Impacts on Performance:</mark>

![](https://i.imgur.com/EZWrYvI.png)

In RAID 5, every write (update) to a disk manifests as four I/O operations (2 disk reads and 2 disk writes)  

In RAID 6, every write (update) to a disk manifests as six I/O operations (3 disk reads and 3 disk writes)  

In RAID 1, every write manifests as two I/O operations (2 disk writes)

### <mark style="background: #BABD00;">RAID Comparison:</mark>

![](https://i.imgur.com/U2NwEv6.png)

### <mark style="background: #BABD00;">Suitable RAID Levels for Different Applications:</mark>

<mark style="background: #BABD00;">RAID 1+0:</mark>  
- Suitable for applications with small, random, and write intensive (writes typically greater than 30%) I/O profile  
- Example: OLTP, RDBMS – Temp space  

<mark style="background: #BABD00;">RAID 3:</mark>  
- Large, sequential read and write  
- Example: data backup and multimedia streaming  

<mark style="background: #BABD00;">RAID 5 and 6:</mark>  
- Small, random workload (writes typically less than 30%)  
- Example: email, RDBMS – Data entry

### <mark style="background: #BABD00;">Hot Spare:</mark>

![](https://i.imgur.com/8CAgpPA.png)

### <mark style="background: #BABD00;">Summary:</mark>  

<mark style="background: #BABD00;">Key points covered in this module:</mark>  
- RAID implementation methods and techniques  
- Common RAID levels  
- RAID write penalty  
- Compare RAID levels based on their cost and performance

# <mark style="background: #BABD00;">11 Snapshots</mark>

Snapshots (or Checkpoints) is like capturing an image of your virtual machine at a moment in time

Easier when machine is powered off, like downloading a file.

A transaction in a database is not complete until all components of the transaction have been completed.

Snapshots often need to be taken of production machines that cannot be brought down, this is complicated

Useful when you need to perform a complicated upgrade to an application in a VM and want a quick way to roll back the changes if something goes wrong.

PowerPoint and word docs compile down to XML. Microsoft chose XML because it is extensible, promoting forward and backward compatibility.

A mark-up language is a language with annotations.

<mark style="background: #BABD00;">Do not ever use snapshots in place of backups!</mark>

### <mark style="background: #BABD00;">Creating a Snapshot:</mark>

Two types of checkpoints:
- Production Checkpoints
- Standard Checkpoints

### <mark style="background: #BABD00;">Introduction:</mark>

<mark style="background: #BABD00;">Scenario:</mark>  
- Need to perform a complicated upgrade to an application in a VM and want a quick way to roll back the changes if something goes wrong.  
- The company is building a demo or class lab and a quick way is needed to reset the virtual machines to their starting point.  
- You are testing software and need to repeat a set of tests very quickly without re-deploying virtual machines.

### <mark style="background: #BABD00;">Why Snapshots?</mark>

Keep multiple captures of a single virtual machine over time  

Could snapshot a virtual machine with just the operating system, service pack, and patches.  

Then create a second snapshot with SQL Server, service pack, and update rollup.  

Then a third snapshot with an application installed in the virtual machine.  

Can roll back the virtual machine (by applying a snapshot) to any of these 3 points in time to redo an install for the purposes of demo, testing, documentation, or training.  

A hierarchy of snapshots will be created for you

### <mark style="background: #BABD00;">Creating a Snapshot:</mark>

Two types of checkpoints  

<mark style="background: #BABD00;">Production Checkpoints:</mark>  
- Use backup technology in the Guest OS to create data-consistent checkpoints that do not include information about running applications.  
- uses Volume Shadow Copy Service or File System Freeze on a Linux virtual machine to create a data-consistent backup of the virtual machine. No snapshot of the virtual machine memory state is taken. 

<mark style="background: #BABD00;">Standard Checkpoints:</mark>
- Creates application-consistent checkpoints that capture the current state of the applications.  
- Takes a snapshot of the virtual machine and virtual machine memory state at the time the checkpoint is initiated.  
- A snapshot is not a full backup and can cause data consistency issues with systems that replicate data between different nodes such as Active Directory.  
- Hyper-V only offered standard checkpoints (formerly called snapshots) prior to Windows 10.

### <mark style="background: #BABD00;">Volume Shadow Copy Service (VSS):</mark>

Backing up and restoring critical business data can be very complex  

The data usually needs to be backed up while the applications that produce the data are still running. This means that some of the data files might be open or they might be in an inconsistent state  

If the data set is large, it can be difficult to back up all of it at one time  

<mark style="background: #BABD00;">Correctly performing backup and restore operations requires close coordination between</mark>  
- the backup applications,  
- the line-of-business applications that are being backed up,  
- the storage management hardware and software.

Volume Shadow Copy Service (VSS) facilitates the conversation between these components to allow them to work better together.  

When all the components support VSS, you can use them to back up your application data without taking the applications offline.  

VSS coordinates the actions that are required to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up.

<mark style="background: #BABD00;">The shadow copy can be used as-is, or it can be used in scenarios such as the following:</mark>  
- You want to back up application data and system state information, including archiving data to another hard disk drive, to tape, or to other removable media.  
- You're data mining.  
- You're performing disk-to-disk backups.  
- You need a fast recovery from data loss by restoring data to the original Logical Unit Number (LUN) or to an entirely new LUN that replaces an original LUN that failed

### <mark style="background: #BABD00;">How are snapshots stored?</mark>

When you take a snapshot of a running VM, Hyper-V briefly pauses the VM to create a new automatic virtual hard disk (AVHD) which is <mark style="background: #BABD00;">essentially a differencing disk</mark>, attaches it to the VM to store changes to the VM data, saves the processor state into a file (.bin), then resumes the VM.  

Hyper-V also makes a copy of the VM configuration file, and saves the contents of the VM memory and processor state.  

Snapshots can also be created when a VM is turned-off, in which case Hyper-V does not need to capture VM memory or processor state data.

Snapshot data files are stored as .avhd files (with Hyper-V).  

Taking multiple snapshots can quickly consume storage space!  

Files usually are located in the same folder (or a sub folder) as the virtual hard disk.  

Do not delete .avhd files directly from the storage location. Instead, use Hyper-V Manager to select the virtual machine, and then delete the snapshots from the snapshot tree.

### <mark style="background: #BABD00;">Virtual Disk File Formats:</mark>

<mark style="background: #BABD00;">VMDK:</mark> An open format developed by VMWare.  Most common format (used by Oracle VirtualBox)

<mark style="background: #BABD00;">VHD:</mark> A native format from Microsoft (Hyper-V and Microsoft Virtual PC)

<mark style="background: #BABD00;">VHDX:</mark> Next Generation VHD:
- VHDX has 64TB disk limit; VHD has 2TB disk limit.  
- VHDX supports large block sizes (sometimes better performance)  
- VHDX protects against file corruption, VHD does not.  
- Two way conversion between VHD and VHDX is possible.  
- VHDX works in Windows Server 2012 and later (not earlier).  
- VHDX is supported in Microsoft Azure (as of 2021).

<mark style="background: #BABD00;">AVHD:</mark> A VHD differencing disk.  

<mark style="background: #BABD00;">AVHDX:</mark> A VHDX differencing disk.

<mark style="background: #BABD00;">OVF:</mark>  
- The OVF Specification provides a means of describing the properties of a virtual system.  
- It is an XML based format.  
- It supports extendibility.  
- An OVF file is used to describe a single virtual machine or single virtual appliance.  

<mark style="background: #BABD00;">OVA:</mark> An OVA file is an OVF file packaged together with all of its supporting files (disk images, metadata, etc).

![](https://i.imgur.com/VUWGvD2.png)

### <mark style="background: #BABD00;">Snapshot considerations:</mark>

Taking a snapshot (also known as checkpoint) reduces the performance of the virtual machine while the snapshot is created. You should not use these snapshots on virtual machines that provide  
services in a production environment.  
[Microsoft Learning Link](https://learn.microsoft.com/en-us/windows-server/virtualization/hyper-v/best-practices-analyzer/avoid-using-checkpoints-on-a-virtual-machine-server-workload-production)  

MS do not recommend using snapshots on virtual machines that are configured with fixed virtual hard disks because they reduce the performance benefits that are otherwise gained by using fixed virtual hard disks. (Why?)

[Link 1 - Winsows 2012](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn818483(v=ws.11) "https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn818483(v=ws.11)")

[Link2 - Fixed vs dynamic disks](https://learn.microsoft.com/en-us/answers/questions/560255/fixed-vs-dynamic-disks "https://learn.microsoft.com/en-us/answers/questions/560255/fixed-vs-dynamic-disks")

[Azure managed disks overview](https://learn.microsoft.com/en-us/azure/virtual-machines/managed-disks-overview "https://learn.microsoft.com/en-us/azure/virtual-machines/managed-disks-overview")

[hyper v guest design fixed vs dynamic vhd](https://www.altaro.com/hyper-v/hyper-v-guest-design-fixed-vs-dynamic-vhd/ "https://www.altaro.com/hyper-v/hyper-v-guest-design-fixed-vs-dynamic-vhd/")

Presence of a VM snapshot reduces the disk performance of the virtual machine. Creating more snapshots will increase that degradation. Hyper-V snapshots should not to be used as a VM backup.  

Taking multiple snapshots can quickly consume a large amount of storage space. When you use Hyper-V Manager to delete a snapshot, the snapshot is removed from the snapshot tree but the ``.avhd`` file is not deleted until you turn off the virtual machine.

### <mark style="background: #BABD00;">Automatic Virtual Hard Disk:</mark>

Each virtual hard disk of the virtual machine is also treated by the snapshot. This is done using a special kind of differential virtual hard disk called the <mark style="background: #BABD00;">Automatic Virtual Hard Disk (AVHD)</mark>:

![](https://i.imgur.com/bHrMMLM.png)

A differencing disk is the disk created the moment you begin a snapshot.

Each <mark style="background: #BABD00;">VHD</mark> file will become a parent to an AVHD file. The virtual machine will start using the AVHD file for reads and writes after the snapshot, and the VHD file for reads older than the snapshot.  

Each <mark style="background: #BABD00;">VHDX</mark> file will become a parent to an AVHDX file. The virtual machine will start using the AVHDX file for reads and writes after the snapshot, and the VHDX file for reads older than the snapshot.  

With each new snapshot that is taken, the active AVHD is detached from the VM, and becomes the parent of a new child AVHD that is attached to the VM and captures changes to the VM data until the next snapshot is  created. Note: Hierarchy!

### <mark style="background: #BABD00;">Reverting/Applying Snapshots:</mark>

Revert feature can be thought of as a single-level undo feature! Previous snapshot state.  

During the Revert process, the VM is stopped, the current AVHD is deleted, and a new AVHD is created. (new ‘fork’ for progress)  

When a Revert is performed, all configuration modifications made to the running VM since the snapshot was taken are discarded.  

Apply option may be used to return to a snapshot that is higher than one level up from the running VM. Fully flexible.

### <mark style="background: #BABD00;">Deleting Snapshots:</mark>

Deleting a single snapshot will not affect other snapshots (at the same level), but it will immediately delete the configuration file and save state files associated with the snapshot. 

<mark style="background: #BABD00;">NB:</mark> In a snapshot hierarchy, the snapshot AVHD may be related to other snapshot AVHDs through a parent-child relationship. A snapshot AVHD is only immediately deleted if it is not the parent of a child AVHD.  

If there is only one child AVHD, it is merged into the parent AVHD the next time that the VM is powered-off.

Deleting a snapshot subtree immediately deletes the configuration and save state files associated with all the snapshots in the subtree. If the running virtual machine AVHD is not a child of any snapshot in the subtree, then all of the AVHDs in the subtree will also be deleted.  

(If the running virtual machine AVHD depends on a chain of AVHDs in the subtree that is deleted, then the AVHD chain will be merged into the AVHD that is one level above the deleted subtree, the next time that the VM is powered-off.)

### <mark style="background: #BABD00;">Common snapshot mistakes:</mark>

There are several mistakes that one can make with snapshots:  

<mark style="background: #BABD00;">Swap the parent VHD/X files:</mark> There is a link between the AVHD/X and the VHD/X file. Do not attempt to break and recreate this link.  

<mark style="background: #BABD00;">Delete the VHD/X files:</mark> Data older than the snapshot, such as the guest operating system, are stored in the parent disks. Do not delete the virtual hard disks.  

<mark style="background: #BABD00;">Delete the AVHD/X files:</mark> Doing this will delete all the data of the virtual machine since the snapshot was created. Do not do this.  

<mark style="background: #BABD00;">Leave a snapshot in place for a long time:</mark> Differential disks, and therefore AVHD/X files, are intended for short-term usage. Performance will degrade as the files will continue to grow over time.

### <mark style="background: #BABD00;">Archival Backups?</mark>

Export the virtual machine.  

Takes some time, but you can make an importable copy of many virtual machines at once by using the Hyper-V Manager. What you end up with is a set of files that can be copied to a new location and easily imported.  

<mark style="background: #BABD00;">Use PowerShell and it’s support of WMI to administer Hyper-V. So, a script could automate:</mark>  
- Shutting down the virtual machine  
- Exporting the virtual machine and/or Copy the .VHD files  
- Starting the virtual machine  

Or treat it as if it were a physical server – complete with backup agents installed into it, and using some enterprise class backup and archiving solution. It all depends upon the purpose of the server, the business applications and/or data housed therein, the ease with which you want to be able to recreate the server, etc. Altaro, VEEAM, etc.

# <mark style="background: #BABD00;">12 Introduction to Docker</mark>

### <mark style="background: #BABD00;">What is Docker?</mark>

Docker is an open-source project that automates the deployment of applications inside software containers, by providing an additional layer of abstraction and automation of operating system–level virtualisation on Linux.  - [Source: en.wikipedia.org]  

Docker allows you to package an application with all of its dependencies into a standardised unit for software development.  - [www.docker.com]

### <mark style="background: #BABD00;">The challenge:</mark>

![](https://i.imgur.com/bQAjcRU.png)

<mark style="background: #BABD00;">Results in NXM compatibility nightmare:</mark>

![](https://i.imgur.com/XMT3k90.png)

### <mark style="background: #BABD00;">Docker is a shipping container for code:</mark>

![](https://i.imgur.com/Vx0INie.png)

<mark style="background: #BABD00;">Solves the NXM matrix problem:</mark>

![](https://i.imgur.com/ic5kEeb.png)

### <mark style="background: #BABD00;">Docker Containers:</mark>

Docker container wrap a piece of software in a complete file system that contains everything needed to run:  
- Code, runtime, system tools, system libraries  
- Anything that can be installed on a server  

This guarantees that the software will always run the same, regardless of the environment it is running in.

![](https://i.imgur.com/ByKnuRX.png)

### <mark style="background: #BABD00;">Why containers matter:</mark>

![](https://i.imgur.com/Bjkok23.png)

### <mark style="background: #BABD00;">Docker containers</mark>

<mark style="background: #BABD00;">Lightweight:</mark>
- Containers running on one machine all share the same OS kernel  
- They start instantly and make more efficient use of RAM  
- Images are constructed from layered file systems  
- They can share common files, making disk usage and image downloads much more efficient

<mark style="background: #BABD00;">Open:</mark>
- Based on open standards  
- Allowing containers to run on all major Linux distributions and Microsoft OS with support for every infrastructure

<mark style="background: #BABD00;">Secure:</mark>
- Containers isolate applications from each other and the underlying infrastructure while providing an added layer of protection for the application

### <mark style="background: #BABD00;">Containers vs VMs:</mark>

Containers have similar resource isolation and allocation benefits as VMs but a different architectural approach allows them to be much more portable and efficient

<mark style="background: #BABD00;">Docker Container:</mark>
- It includes the application and all of its dependencies, but share the kernel with other containers.  
- They run as an isolated process in userspace on the host operating system.  
- Docker containers run on any computer, on any infrastructure and in any cloud

![](https://i.imgur.com/Avz94PV.png)

<mark style="background: #BABD00;">VM:</mark>
- Each virtual machine includes the application, the necessary binaries and libraries and an entire guest operating system - all of which may be tens of GBs in size

![](https://i.imgur.com/3roZxCc.png)

### <mark style="background: #BABD00;">Why are docker containers lightweight?</mark>

<mark style="background: #BABD00;">VMs:</mark> Every app, every copy of an app, and every slight modification of the app requires a new virtual server
![](https://i.imgur.com/OW9QmZP.png)

<mark style="background: #BABD00;">Containers:</mark>
![](https://i.imgur.com/7ukDqSv.png)

### <mark style="background: #BABD00;">What are the basics of the Docker system?</mark>

![](https://i.imgur.com/nVGc81q.png)

### <mark style="background: #BABD00;">Changes and Updates:</mark>

![](https://i.imgur.com/YQ9LHL1.png)

### <mark style="background: #BABD00;">How does this help you build better software?</mark>

<mark style="background: #BABD00;">Accelerate Developer Onboarding:</mark>
- Stop wasting hours trying to setup developer environments  
- Spin up new instances and make copies of production code to run locally  
- With Docker, you can easily take copies of your live environment and run on any new endpoint running Docker.

<mark style="background: #BABD00;">Empower Developer Creativity:</mark>
- The isolation capabilities of Docker containers free developers from the worries of using “approved” language stacks and tooling  
- Developers can use the best language and tools for their application service without worrying about causing conflict issues

<mark style="background: #BABD00;">Eliminate Environment Inconsistencies:</mark>
- By packaging up the application with its configs and dependencies together and shipping as a container, the application will always work as designed locally, on another machine, in test or production  
- No more worries about having to install the same configs into a different environment

### <mark style="background: #BABD00;">Easily Share and Collaborate on Applications:</mark>

Docker creates a common framework for developers and sysadmins to work together on distributed applications.

<mark style="background: #BABD00;">Distribute and share content:</mark>
- Store, distribute and manage your Docker images in your Docker Hub with your team  
- Image updates, changes and history are automatically shared across your organisation.  

<mark style="background: #BABD00;">Simply share your application with others:</mark>  
- Ship your containers to others without worrying about different environment dependencies creating issues with your application.  
- Other teams can easily link to or test against your app without having to learn or worry about how it works

### <mark style="background: #BABD00;">Getting started with Docker:</mark>

- install Docker  
- run a software image in a container  
- browse for an image on Docker Hub  
- create your own image and run it in a container  
- create a Docker Hub account and an image repository  
- create an image of your own  
- push your image to Docker Hub for others to use

### <mark style="background: #BABD00;">Example: a health and fitness Mobile App:</mark>

You’ve been tasked with creating the REST API for a mobile app for tracking health and fitness  

You code the first endpoint using the development environment on your laptop  

After running all the unit tests and seeing that they passed, you check your code into the Git repository and let the QA engineer know that the build is ready for testing  

The QA engineer dutifully deploys the most recent build to the test environment, and within the first few minutes of testing discovers that your recently developed REST endpoint is broken  

After spending a few hours troubleshooting alongside the QA engineer, you discover that the test environment is using an outdated version of a third-party library, and this is what is causing your REST endpoints to break

<mark style="background: #BABD00;">Slight differences between development, test, stage, and production environments can wreak mayhem on an application</mark>

<mark style="background: #BABD00;">Solution:</mark>
- Traditional approaches for dealing with this problem, such as change management processes, are too cumbersome for today’s rapid build and deploy cycles  
- What is needed instead is a way to transfer an environment seamlessly from development to test, eliminating the need for manual and error prone resource provisioning and configuration.  
- You can create Docker images from a running container. For example, one could launch a container, install a bunch of software packages using a package manager like APT or yum, and then commit those changes to a new Docker image.

<mark style="background: #BABD00;">Solution in Example:</mark>
- First, define a Docker image for launching a container for running the REST endpoint  
- Use this to test our code on a laptop, and the QA engineer can use this to test the code in Google Compute Engine/AWS EC2/Azure VM.  
- The REST endpoints are going to be developed using Ruby and the Sinatra framework, so these will need to be installed in the image  
- The back end will use Google Firestore/Amazon DynamoDB/Azure CosmosDB

![](https://i.imgur.com/rjSx09H.png)

# <mark style="background: #BABD00;">13 Required Reading CA 1</mark>

# <mark style="background: #BABD00;">Week 2:</mark>

### <mark style="background: #BABD00;">NIST Definition of Cloud Computing:</mark>

<mark style="background: #BABD00;">NIST:</mark> National Institute of Standards and Technology (USA)

<mark style="background: #BABD00;">Cloud computing</mark> is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction.  

This cloud model is composed of five essential characteristics, three service models, and four deployment  models.  

#### <mark style="background: #BABD00;">Essential Characteristics:</mark>  

<mark style="background: #BABD00;">On-demand self-service.</mark> A consumer can unilaterally provision computing capabilities, such as server time and network storage, as needed automatically without requiring human interaction with each service provider.  

<mark style="background: #BABD00;">Broad network access.</mark> Capabilities are available over the network and accessed through standard  mechanisms that promote use by heterogeneous thin or thick client platforms (e.g., mobile phones, tablets, laptops, and workstations).  

<mark style="background: #BABD00;">Resource pooling.</mark> The provider’s computing resources are pooled to serve multiple consumers using a multi-tenant model, with different physical and virtual resources dynamically assigned and reassigned according to consumer demand. There is a sense of location independence in that the customer generally has no control or knowledge over the exact location of the provided resources but may be able to specify location at a higher level of abstraction (e.g., country, state, or datacenter). Examples of resources include storage, processing, memory, and network bandwidth.  

<mark style="background: #BABD00;">Rapid elasticity.</mark> Capabilities can be elastically provisioned and released, in some cases automatically, to scale rapidly outward and inward commensurate with demand. To the consumer, the capabilities available for provisioning often appear to be unlimited and can be appropriated in any quantity at any time.  

<mark style="background: #BABD00;">Measured service.</mark> Cloud systems automatically control and optimise resource use by leveraging a metering capability<sup>1</sup> at some level of abstraction appropriate to the type of service (e.g., storage, processing, bandwidth, and active user accounts). Resource usage can be monitored, controlled, and reported, providing transparency for both the provider and consumer of the utilized service.  

#### <mark style="background: #BABD00;">Service Models:</mark>  

<mark style="background: #BABD00;">Software as a Service (SaaS).</mark> The capability provided to the consumer is to use the provider’s applications running on a cloud infrastructure<sup>2</sup>. The applications are accessible from various client devices through either a thin client interface, such as a web browser (e.g., web-based email), or a program interface. The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, storage, or even individual application capabilities, with the possible exception of limited user-specific application configuration settings. 

<mark style="background: #BABD00;">Platform as a Service (PaaS).</mark> The capability provided to the consumer is to deploy onto the cloud infrastructure consumer-created or acquired applications created using programming languages, libraries, services, and tools supported by the provider<sup>3</sup>. The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, or storage, but has control over the deployed applications and possibly configuration settings for the application-hosting environment.  

<mark style="background: #BABD00;">Infrastructure as a Service (IaaS).</mark> The capability provided to the consumer is to provision processing, storage, networks, and other fundamental computing resources where the consumer is able to deploy and run arbitrary software, which can include operating systems and applications. The consumer does not manage or control the underlying cloud infrastructure but has control over operating systems, storage, and deployed applications; and possibly limited control of select networking components (e.g., host firewalls).

#### <mark style="background: #BABD00;">Deployment Models:</mark>  

<mark style="background: #BABD00;">Private cloud.</mark> The cloud infrastructure is provisioned for exclusive use by a single organisation comprising multiple consumers (e.g., business units). It may be owned, managed, and operated by the organisation, a third party, or some combination of them, and it may exist on or off premises.

<mark style="background: #BABD00;">Community cloud.</mark> The cloud infrastructure is provisioned for exclusive use by a specific community of consumers from organisations that have shared concerns (e.g., mission, security requirements, policy, and compliance considerations). It may be owned, managed, and operated by one or more of the organisations in the community, a third party, or some combination of them, and it may exist on or off premises.  

<mark style="background: #BABD00;">Public cloud.</mark> The cloud infrastructure is provisioned for open use by the general public. It may be owned, managed, and operated by a business, academic, or government organisation, or some combination of them. It exists on the premises of the cloud provider.  

<mark style="background: #BABD00;">Hybrid cloud.</mark> The cloud infrastructure is a composition of two or more distinct cloud infrastructures (private, community, or public) that remain unique entities, but are bound together by standardized or proprietary technology that enables data and application portability (e.g., cloud bursting for load balancing between clouds).

<mark style="background: #BABD00;">Footnotes:</mark>
1. Typically this is done on a pay-per-use or charge-per-use basis.  
2. A cloud infrastructure is the collection of hardware and software that enables the five essential characteristics of cloud computing. The cloud infrastructure can be viewed as containing both a physical layer and an abstraction layer. The physical layer consists of the hardware resources that are necessary to support the cloud services being provided, and typically includes server, storage and network components. The abstraction layer consists of the software deployed across the physical layer, which manifests the essential cloud characteristics. Conceptually the abstraction layer sits above the physical layer.
3. This capability does not necessarily preclude the use of compatible programming languages, libraries, services, and tools from other sources.

### <mark style="background: #BABD00;">CONTENT DELIVERY NETWORK:</mark>
#### <mark style="background: #BABD00;">What is a Content Delivery Network (CDN)?</mark>

[Source](https://www.cloudflare.com/en-gb/learning/cdn/what-is-a-cdn/)

A content delivery network (CDN) is a geographically distributed group of servers that caches content close to end users. A CDN allows for the quick transfer of assets needed for loading Internet content, including HTML pages, JavaScript files, stylesheets, images, and videos.

The popularity of CDN services continues to grow, and today the majority of web traffic is served through CDNs, including traffic from major sites like Facebook, Netflix, and Amazon.

A properly configured CDN may also help protect websites against some common malicious attacks, such as [Distributed Denial of Service (DDOS) attacks](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/).

#### <mark style="background: #BABD00;">Is a CDN the same as a web host?</mark>

While a CDN does not host content and can’t replace the need for proper web hosting, it does help [cache](https://www.cloudflare.com/learning/cdn/what-is-caching/) content at the [network edge](https://www.cloudflare.com/learning/serverless/glossary/what-is-edge-computing/), which improves website performance. Many websites struggle to have their [performance](https://www.cloudflare.com/learning/cdn/performance/) needs met by traditional hosting services, which is why they opt for CDNs.

By utilising caching to reduce hosting bandwidth, [helping to prevent interruptions in service](https://www.cloudflare.com/learning/cdn/cdn-load-balance-reliability/), and [improving security](https://www.cloudflare.com/learning/cdn/cdn-ssl-tls-security/), CDNs are a popular choice to relieve some of the major pain points that come with traditional web hosting.

#### <mark style="background: #BABD00;">What are the benefits of using a CDN?</mark>

Although the benefits of using a CDN vary depending on the size and needs of an Internet property, the primary benefits for most users can be broken down into four different components:

1. <mark style="background: #BABD00;">Improving website load times</mark> - By distributing content closer to website visitors by using a nearby CDN server (among other optimisations), visitors experience faster page loading times. As visitors are more inclined to click away from a slow-loading site, a CDN can reduce bounce rates and increase the amount of time that people spend on the site. In other words, a faster a website means more visitors will stay and stick around longer.

2. <mark style="background: #BABD00;">Reducing bandwidth costs</mark> - Bandwidth consumption costs for website hosting is a primary expense for websites. Through caching and other optimizations, CDNs are able to reduce the amount of data an origin server must provide, thus reducing hosting costs for website owners.

3. <mark style="background: #BABD00;">Increasing content availability and redundancy</mark> - Large amounts of traffic or hardware failures can interrupt normal website function. Thanks to their distributed nature, a CDN can handle more traffic and withstand hardware failure better than many origin servers.

4. <mark style="background: #BABD00;">Improving website security</mark> - A CDN may improve security by providing [DDoS mitigation](https://www.cloudflare.com/learning/ddos/ddos-mitigation/), improvements to security certificates, and other optimizations.

#### <mark style="background: #BABD00;">How does a CDN work?</mark>

At its core, a CDN is a network of servers linked together with the goal of delivering content as quickly, cheaply, reliably, and securely as possible. In order to improve speed and connectivity, a CDN will place servers at the exchange points between different networks.

These [Internet exchange points (IXPs)](https://www.cloudflare.com/learning/cdn/glossary/internet-exchange-point-ixp/) are the primary locations where different Internet providers connect in order to provide each other access to traffic originating on their different networks. By having a connection to these high speed and highly interconnected locations, a CDN provider is able to reduce costs and transit times in high speed data delivery.

![](https://i.imgur.com/p4FOzjp.png)

Beyond placement of servers in IXPs, a CDN makes a number of optimisations on standard client/server data transfers. CDNs place Data Centres at strategic locations across the globe, enhance security, and are designed to survive various types of failures and Internet congestion.

#### <mark style="background: #BABD00;">Latency - How does a CDN improve website load times?</mark>

When it comes to websites loading content, users drop off quickly as a site slows down. CDN services can help to reduce load times in the following ways:
- The globally distributed nature of a CDN means reduce distance between users and website resources. Instead of having to connect to wherever a website’s [origin server](https://www.cloudflare.com/learning/cdn/glossary/origin-server/) may live, a CDN lets users connect to a geographically closer [data centre](https://www.cloudflare.com/learning/cdn/glossary/internet-exchange-point-ixp/). Less travel time means faster service.
- Hardware and software optimisations such as efficient load balancing and solid-state hard drives can help data reach the user faster.
- CDNs can reduce the amount of data that’s transferred by reducing file sizes using tactics such as [minification](https://www.cloudflare.com/learning/performance/why-minify-javascript-code/) and file compression. Smaller file sizes mean quicker load times.
- CDNs can also speed up sites which use [TLS](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/)/[SSL](https://www.cloudflare.com/learning/ssl/what-is-ssl/) certificates by optimizing connection reuse and enabling TLS false start.

[Explore all the ways a CDN helps websites load faster](https://www.cloudflare.com/learning/cdn/performance/)

#### <mark style="background: #BABD00;">Reliability and redundancy - How does a CDN keep a website always online?</mark>

Uptime is a critical component for anyone with an Internet property. Hardware failures and spikes in traffic, as a result of either malicious attacks or just a boost in popularity, have the potential to bring down a web server and prevent users from accessing a site or service. A well-rounded CDN has several features that will minimise downtime:

- Load balancing distributes network traffic evenly across several servers, making it easier to scale rapid boosts in traffic.
- Intelligent failover provides uninterrupted service even if one or more of the CDN servers go offline due to hardware malfunction; the failover can redistribute the traffic to the other operational servers.
- In the event that an entire data centre is having technical issues, [Anycast](https://www.cloudflare.com/learning/cdn/glossary/anycast-network/) routing transfers the traffic to another available data centre, ensuring that no users lose access to the website.

[Learn more about how a CDN helps keep websites online](https://www.cloudflare.com/learning/cdn/cdn-load-balance-reliability/)

#### <mark style="background: #BABD00;">Data security - How does a CDN protect data?</mark>

Information security is an integral part of a CDN. a CDN can keep a site secured with fresh [TLS/SSL certificates](https://www.cloudflare.com/learning/ssl/what-is-an-ssl-certificate/) which will ensure a high standard of authentication, [encryption](https://www.cloudflare.com/learning/ssl/what-is-encryption/), and integrity. Investigate the security concerns surrounding CDNs, and explore what can be done to securely deliver content. [Learn about CDN SSL/TLS security](https://www.cloudflare.com/learning/cdn/cdn-ssl-tls-security/)

#### <mark style="background: #BABD00;">Bandwidth expense - How does a CDN reduce bandwidth costs?</mark>

Every time an origin server responds to a request, bandwidth is consumed. See how a CDN, like the [Cloudflare CDN](https://www.cloudflare.com/application-services/products/cdn/), cuts down on origin requests and [reduces bandwidth costs](https://www.cloudflare.com/learning/cdn/how-cdns-reduce-bandwidth-cost/).

### <mark style="background: #BABD00;">Serverless Computing:</mark>

#### <mark style="background: #BABD00;">What is serverless computing?</mark>

Serverless computing is a method of providing backend services on an as-used basis. A serverless provider allows users to write and deploy code without the hassle of worrying about the underlying infrastructure. A company that gets backend services from a serverless vendor is charged based on their computation and do not have to reserve and pay for a fixed amount of bandwidth or number of servers, as the service is auto-scaling. Note that despite the name serverless, physical servers are still used but developers do not need to be aware of them.

In the early days of the web, anyone who wanted to build a web application had to own the physical hardware required to run a server, which is a cumbersome and expensive undertaking.

Then came [cloud computing](https://www.cloudflare.com/learning/cloud/what-is-the-cloud/), where fixed numbers of servers or amounts of server space could be rented remotely. Developers and companies who rent these fixed units of server space generally over-purchase to ensure that a spike in traffic or activity will not exceed their monthly limits and break their applications. This means that much of the server space that gets paid for can go to waste. Cloud vendors have introduced auto-scaling models to address the issue, but even with auto-scaling an unwanted spike in activity, such as a [DDoS Attack](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/), could end up being very expensive.

![](https://i.imgur.com/Gtd4R3y.png)

Serverless computing allows developers to purchase backend services on a flexible ‘pay-as-you-go’ basis, meaning that developers only have to pay for the services they use. This is like switching from a cell phone data plan with a monthly fixed limit, to one that only charges for each byte of data that actually gets used.

The term ‘serverless’ is somewhat misleading, as there are still servers providing these backend services, but all of the server space and infrastructure concerns are handled by the vendor. Serverless means that the developers can do their work without having to worry about servers at all.

#### <mark style="background: #BABD00;">What are backend services? What’s the difference between frontend and backend?</mark>

[Source](https://www.cloudflare.com/en-gb/learning/serverless/what-is-serverless/)

Application development is generally split into two realms: the frontend and the backend. The frontend is the part of the application that users see and interact with, such as the visual layout. The backend is the part that the user doesn’t see; this includes the server where the application's files live and the database where user data and business logic is persisted.

![](https://i.imgur.com/yZlc8Zm.png)

For example, let’s imagine a website that sells concert tickets. When a user types a website address into the browser window, the browser sends a request to the backend server, which responds with the website data. The user will then see the frontend of the website, which can include content such as text, images, and form fields for the user to fill out. The user can then interact with one of the form fields on the frontend to search for their favourite musical act. When the user clicks on ‘submit’, this will trigger another request to the backend. The backend code checks its database to see if a performer with this name exists, and if so, when they will be playing next, and how many tickets are available. The backend will then pass that data back to the frontend, and the frontend will display the results in a way that makes sense to the user. Similarly, when the user creates an account and enters financial information to buy the tickets, another back-and-forth communication between the frontend and backend will occur.

#### <mark style="background: #BABD00;">What kind of backend services can serverless computing provide?</mark>

Most serverless providers offer database and storage services to their customers, and many also have [Function-as-a-Service (FaaS)](https://www.cloudflare.com/learning/serverless/glossary/function-as-a-service-faas/) platforms, like [Cloudflare Workers](https://www.cloudflare.com/developer-platform/workers/). FaaS allows developers to execute small pieces of code on the [network edge](https://www.cloudflare.com/learning/serverless/glossary/what-is-edge-computing/). With FaaS, developers can build a modular architecture, making a codebase that is more scalable without having to spend resources on maintaining the underlying backend. [Learn more about FaaS >>](https://www.cloudflare.com/learning/serverless/glossary/function-as-a-service-faas/)

#### <mark style="background: #BABD00;">What are the advantages of serverless computing?</mark>

- <mark style="background: #BABD00;">Lower costs</mark> - Serverless computing is generally very cost-effective, as traditional cloud providers of backend services (server allocation) often result in the user paying for unused space or idle CPU time.
- <mark style="background: #BABD00;">Simplified scalability</mark> - Developers using serverless architecture don’t have to worry about policies to scale up their code. The serverless vendor handles all of the scaling on demand.
- <mark style="background: #BABD00;">Simplified backend code</mark> - With FaaS, developers can create simple functions that independently perform a single purpose, like making an API call.
- <mark style="background: #BABD00;">Quicker turnaround</mark> - Serverless architecture can significantly cut time to market. Instead of needing a complicated deploy process to roll out bug fixes and new features, developers can add and modify code on a piecemeal basis.

Learn more about [the benefits of serverless computing.](https://www.cloudflare.com/learning/serverless/why-use-serverless/)

#### <mark style="background: #BABD00;">How does serverless compare to other cloud backend models?</mark>

A couple of technologies that are often conflated with serverless computing are Backend-as-a-Service and Platform-as-a-Service. Although they share similarities, these models do not necessarily meet the requirements of serverless.

<mark style="background: #BABD00;">Backend-as-a-service (BaaS)</mark> is a service model where a cloud provider offers backend services such as data storage, so that developers can focus on writing front-end code. But while serverless applications are event-driven and run on the edge, BaaS applications may not meet either of these requirements. [Learn more about BaaS >>](https://www.cloudflare.com/learning/serverless/glossary/backend-as-a-service-baas/)

<mark style="background: #BABD00;">Platform-as-a-service (PaaS)</mark> is a model where developers essentially rent all the necessary tools to develop and deploy applications from a cloud provider, including things like operating systems and middleware. However PaaS applications are not as easily scalable as serverless applications. PaaS also don’t necessarily run on the edge and often have a noticeable start-up delay that isn’t present in serverless applications. [Learn more about PaaS >>](https://www.cloudflare.com/learning/serverless/glossary/platform-as-a-service-paas/)

<mark style="background: #BABD00;">Infrastructure-as-a-service (IaaS)</mark> is a catchall term for cloud vendors hosting infrastructure on behalf of their customers. IaaS providers may offer serverless functionality, but the terms are not synonymous. [Learn more about IaaS >>](https://www.cloudflare.com/learning/cloud/what-is-iaas/)

#### <mark style="background: #BABD00;">What is next for serverless?</mark>

Serverless computing continues to evolve as serverless providers come up with solutions to overcome some of its drawbacks. One of these drawbacks is cold starts.

Typically when a particular serverless function has not been called in a while, the provider shuts down the function to save energy and avoid over-provisioning. The next time a user runs an application that calls that function, the serverless provider will have to spin it up fresh and start hosting that function again. This start-up time adds significant latency, which is known as a ‘cold start’.

Once the function is up and running it will be served much more rapidly on subsequent requests (warm starts), but if the function is not requested again for a while, the function will once again go dormant. This means the next user to request that function will experience a cold start. Up until fairly recently, cold starts were considered a necessary trade-off of using serverless functions.

Cloudflare Workers has addressed this problem by spinning up serverless functions in advance, during the [TLS handshake](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/). Since Workers functions spin up at the edge in a very short amount of time, even shorter than the time required to complete the handshake, the result is an [FaaS platform with zero cold starts](https://blog.cloudflare.com/eliminating-cold-starts-with-cloudflare-workers/).

As more and more of the drawbacks of using serverless get addressed and the popularity of edge computing grows, we can expect to see serverless architecture becoming more widespread.

# <mark style="background: #BABD00;">Week 3:</mark>

### <mark style="background: #BABD00;">Network Physical Components:</mark>

<mark style="background: #BABD00;">Network Adapter:</mark> A network adapter is the component of a computer’s internal hardware that is used for communicating over a network with another computer. It enables a computer to connect with another computer, server or any networking device over an LAN connection. A network adapter can be used over a wired or wireless network.  

<mark style="background: #BABD00;">Network Router:</mark> Resides at the Network Layer. Data Transmission Form is a Packet. Uses IP address. Used for connecting two or more networks. A router is a networking device that connects a local network to other local networks. Routers connect two or more logical subnets, which do not necessarily map one-to-one to the physical interfaces of the router.  

<mark style="background: #BABD00;">Network Bridge:</mark> A network bridge is a computer networking device that creates a single aggregate network from multiple communication networks or network segments. This function is called network bridging. Bridging is distinct from routing. Routing allows multiple networks to communicate independently and yet remain separate, whereas bridging connects two separate networks as if they were a single network. In the OSI model, bridging is performed in the data link layer (layer 2).  

<mark style="background: #BABD00;">Network Switch:</mark> Resides at the Data Link Layer. Data transmission form is a Frame. Uses MAC address. Used for connecting two or more nodes in the same network (L2) or different network (L3). A network switch is a computer networking device that is used to connect many devices together on a computer network. A switch is considered more advanced than a hub because a switch will send on a msg to device that needs or request it. Allow connections to multiple devices, manage ports, manage VLAN security settings.  

<mark style="background: #BABD00;">Network Hub (or Repeater):</mark> Also called repeaters — are even less advanced that switches; while a hub broadcasts the same data to all its ports, a network switch forwards data only to those devices that the data is intended for. Network hubs do not manage any traffic coming through them; they only broadcast — or repeat — packets from an incoming port to all other ports.

# <mark style="background: #BABD00;">How HTTPS works:</mark>

[Source for Comic](https://howdns.works/)

Computers and other devices communicate using IP addresses to identify each other on the internet.

Humans can't remember IP addresses, so they use words. e.g. google.com

The domain name system (DNS) brings the two together and gets you to your destination.

The resolver server is usually your <mark style="background: #BABD00;">ISP</mark> (Internet service provider). All resolvers must know where to locate the root server.

The root server knows where to locate the .COM TLD server. TLD stands for Top-Level Domain.

There are 13 root servers that exist today. Root servers sit at the top of the DNS hierarchy.

![](https://i.imgur.com/PNkgGG2.png)

The root servers are scattered around the globe and operated by 12 independent organisations. They are named [letter].root-servers.net where [letter] ranges from A to M.

```
a.root-servers.net 
b.root-servers.net 
.... 
m.root-servers.net
```

This doesn't mean that we have only 13 physical servers to support the whole internet! Each organisation provides multiple physical servers distributed around the globe.

The coordination of most top-level domains (TLDs) belong to the Internet Corporation for Assigned Names and Numbers (ICANN). It is the largest TLD on the internet.

The .COM TLD was one of the first created in 1985.

<mark style="background: #BABD00;">When a user types something into the browser:</mark>
1. The browser checks its cache
2. If the url is not there, it asks the OS
3. The OS checks its cache
4. If the OS does not have the url cached, it asks the resolver to search for the url
5. The resolver checks its cache
6. If the resolver does not have the url cached, it asks the root server
7. The root server does not cache urls but it does know where to find the TLD server and passes this to the resolver
8. The resolver asks the TLD server for the ip address of the server
9. The TLD server will return either the ip address or the nameservers of the url
10. The resolver asks the name server for the ip address it resolves to 

### <mark style="background: #BABD00;">How HTTPS works:</mark>

<mark style="background: #BABD00;">HTTPS:</mark> HyperText Transfer Protocol Secure
[Source for Comic](https://howhttps.works/why-do-we-need-https/)

<mark style="background: #BABD00;">We need HTTPs for 3 reasons:</mark>
- Privacy
- Integrity
- Innovation

When you browse to a website without HTTPS, anyone on your network can sniff your traffic

Integrity is needed so that your traffic cannot be changed by malicious actors. This is often called a man-in-the-middle attack. Integrity means that the message is not manipulated on the way to its destination.

Identification means it can be checked that a message is coming from the correct entity. A digital signature attached to a message can identify the sender.

And when you are browsing the web, identification means that the site that you are visiting is indeed the one you think it is.

HTTPS, via SSL certificates, ensures you are connected exactly with the receiver you would expect.

HTTPS needs a way to provide privacy, integrity, and identification on the web. That mechanism is called 'encryption'.

<mark style="background: #BABD00;">Symmetric encryption:</mark>
- One key used to encrypt data
- Anyone with the key can open the box
- the data is scrambled through a series of steps.
- It was transformed and spread out multiple times. Each time obfuscating the message further.
- To decrypt a message, we just need to apply the same steps, but in reverse order.
- The encryption key is mixed in with the message, so even if you know the encryption algorithm, without the key, the message is still nonsense.
- One main issue with symmetric keys is that they are hard to share safely.

![](https://i.imgur.com/0mXDfah.png)

![](https://i.imgur.com/owCsIMt.png)

<mark style="background: #BABD00;">Asymmetric keys:</mark>
- you have 2 keys.
- One key is public, the other one is private. They are paired and work together.
- Only the private key can open a box locked with the public key pair.
- This is great not only for privacy, but also for identification since we know for sure that only the owner of the 2 keys can open the message.

When you view a website with https, your browser will display a lock on the address bar.
- Your browser communicated with a server, where the website is hosted, and they both established a secure connection to transmit messages.
- They needed to agree on how to communicate securely. If the negotiation is not successful, your browser lets you know by showing an error or warning.
- If an agreement is reached, your browser is happy to display a padlock on the address bar.

This process, the negotiation between a browser and a server, is called 'the handshake'.

<mark style="background: #BABD00;">The handshake:</mark>
1. <mark style="background: #BABD00;">Client Hello:</mark> The client sends a list of SSL/TLS versions and encryption algorithms that it can work with to the server.
2. <mark style="background: #BABD00;">Server Hello:</mark> The server chooses the best SSL/TLS version and encryption algorithm among the ones the client sent it, and based on its preferences. The server replies with its certificate, which includes its public key, so the client can verify who the server is.
3. <mark style="background: #BABD00;">Client Key Exchange:</mark> The client checks the server's certificate to make sure they are legit. The client generates a 'pre-master key' so they can both use it later when they generate a unique key. The client encrypts that pre-master key with the server's public key and then sends it.
4. <mark style="background: #BABD00;">Change cipher spec.</mark> The server uses its private key to decrypt the pre-master key. Now they both generate the same 'shared secret' that they are going to use as a symmetric key. The client sends a test and the server responds.

When the exchange of data is encrypted with SSL/TLS, then we call it HTTPS. The 'S' stands for Secure.

<mark style="background: #BABD00;">SSL</mark> stands for 'Secure Sockets Layer'. A protocol created by Netscape in 1995.

Netscape gave control of SSL protocol to the IETF: Internet Engineering Task Force. Before 1999 ended, IETF released TLS version 1.0 (Which was really SSL 3.1).

SSL was renamed to <mark style="background: #BABD00;">TLS:</mark> Transport Layer Security.

<mark style="background: #BABD00;">A certificate authority (CA) is a third-party organisation with 3 main objectives:</mark>
1. Issuing certificates.
2. Confirming the identity of the certificate owner.
3. Providing proof that the certificate is valid.

Becoming a CA is an intense task of security requirements and audits. You need to be trusted to be accepted into a root store - a database of trusted CAs

Apple, Windows, and Mozilla run their own root stores that they pre-install in your computer or device.

<mark style="background: #BABD00;">Three types of CA:</mark>
- <mark style="background: #BABD00;">Domain validated:</mark> The certificate just verifies the domain name, and nothing else. 
- <mark style="background: #BABD00;">organisation validated:</mark> The certificate requires the validation and manual verification of the organisation behind the certificate.
- <mark style="background: #BABD00;">Extended validation.</mark> The certificate requires an exhaustive verification of the business.

All valid certificates result in the browser displaying a secure badge in the browser bar. EV certificates generally display the company name as well.

When a CA issues a certificate, they sign the certificate with their root certificate pre-installed in the root store. Most of the time it's an intermediate certificate signed with a root certificate.

![](https://i.imgur.com/2t8fp3E.png)

If the root certificate is compromised, it's easier to revoke the intermediate certificates, since the root certificates are installed on each device.

### <mark style="background: #BABD00;">SAN: What is LUN?</mark>

[Source](https://www.purestorage.com/knowledge/what-is-lun-storage.html)

It’s common for servers to have multiple storage devices. A logical unit number (LUN) assigns a unique value to each drive. A LUN can be assigned to a group of drives configured as a single volume, a partition on a drive, or the entire drive itself. A LUN value can be automatically assigned or manually assigned by an administrator. In this article, we take a look at how LUNs work and the benefits and downsides of using them.  

#### <mark style="background: #BABD00;">What Is a LUN in Storage?</mark>

A LUN (logical unit number) is a unique identifier that defines a storage partition in a [storage area network (SAN)](https://www.purestorage.com/knowledge/what-is-storage-area-network.html) environment for data organisation and access. It’s important to note that a LUN is a component in storage organisation and not a type of storage device itself. A LUN is a numeric value that points to a physical disk or a logical set of disks. Storage LUNs can also point to a logical set of partitions.

The purpose of a LUN is for clients to make requests from storage space and retrieve data. Usually, LUNs refer to SAN storage, so client computers can map network drives, request data from network storage, or store data on the SAN. Users do not address a LUN when mapping a drive, so only administrators manage LUN identifiers.

#### <mark style="background: #BABD00;">How Does a LUN Work?</mark>

When you build a new server or add a drive to a server, you must partition it. Partitioning forces you to choose a file system. You can choose to make the entire drive space a part of the partition, use only some of the drive space for a partition, or create a logical volume from a group of drives. A LUN can be assigned to the new partition or a set of partitions.

When a server has several disks configured as a RAID (redundant array of independent disks) on SCSI (Small Computer System Interface) ports, the server uses a LUN to communicate with the right storage unit. LUN assignment is common with SCSI disks, but a storage area network (SAN) with other storage ports (e.g., SATA or SAS) could be configured as a RAID and connected via a Fibre Channel where a LUN is assigned.

For a user, the LUN is seen as a single-mounted storage device even if several partitions or a RAID of disks represent a single LUN. A server accessing internal storage needs the LUN to identify the right disk to read to or write from. LUNs assigned to a SAN are necessary for client computers to mount the right disk and assign it a name (e.g., X or Z as a drive letter).

It’s possible for a single LUN to identify thousands of logical volumes, especially in a SAN environment. Administrators can assign a LUN to SAN volumes or the SAN unit can automatically assign a LUN to storage. LUNs can be reassigned by administrators later after bootup to customize configurations to meet certain setup requirements.

#### <mark style="background: #BABD00;">Alternatives and Implementations of LUN Storage</mark>

Every server or network storage device has a LUN so that operating systems can identify a volume to read or write to disks. For many enterprise environments, large network storage devices use RAID storage, which means that several disks could be represented by a single LUN. A large SAN with several disks configured as a single volume could also have a single LUN.

Unless you use older [SCSI technology](https://blog.purestorage.com/purely-technical/iscsi-setup-with-flasharray/) on your personal computer, you only find LUN storage in older SAN or server hardware. Newer SATA (Serial Advanced Technology Attachment) drives are used in servers and personal computers, but SCSI was replaced with SAS (Serial Attached SCSI) or [iSCSI](https://blog.purestorage.com/purely-informational/iscsi-vs-fc-vs-fcoe-choosing-the-right-storage-protocol-for-your-business/) (Internet Small Computer System Interface). Enterprise systems may use SATA or SAS depending on the type of storage and speeds necessary to support a large volume of read and write requests.

#### <mark style="background: #BABD00;">Benefits of Using LUN Storage</mark>

Although a LUN represents some or all of a disk’s storage capacity, it does not always represent a single disk. LUN management software lets administrators choose LUN values for specific disks or volumes, but counting the number of LUN storage values does not represent the total number of disks. The operating system on the remote computer using the LUN can mount it as a drive, so the storage can be given a user-friendly name, usually a letter (e.g., Z drive or X drive).

LUN management lets administrators better control SAN disks and capacity. Enterprise networks use several large-capacity drives to hold petabytes of data, and a LUN lets a workstation mount a single LUN as a user-friendly drive letter. These drive letters often have logical organisation (e.g., storage for accounting or sharing documents company-wide) with user-friendly volume letters that most employees know when they transfer documents to network drives.

Although a LUN enables mounting drives and resource sharing on a local device, it does not offer any security. Administrators are still responsible for creating user groups and assigning appropriate permissions to each user group for data access control. Most organisations assign a different drive letter to each user group so there’s no confusion for employees about the purpose of each mounted drive. For example, the X drive might be used for sharing files with anyone within the organisation, while the Z drive might represent a link to personal file spaces that only a single employee can access.

#### <mark style="background: #BABD00;">Potential Downsides of a LUN</mark>

A LUN is a numeric assignment for SCSI or a Fibre Channel, but a LUN is often associated with a SAN using a RAID system. A standard user will not run into LUN assignments, but administrators working with legacy hardware might find LUN management challenging. Remember that a LUN represents a slice of storage in a SAN, but it does not always represent a single disk or partition. LUN assignments can be manual or automatic, but most administrators use SAN software to manage LUN values.

Any downsides to LUN are management related. Initial setup might be somewhat convenient, but any new space added to the SAN must be given a LUN or added to existing volumes so that current storage capacity can be expanded. Some administrators might struggle to add new disks to a LUN depending on the operating system and SAN configuration. Most operating systems have an interface to make it somewhat convenient to add storage to current capacity, but administrators might find that they need to troubleshoot when new disks aren’t recognized by the system.

LUNs aren’t always assigned in a SAN or NAS environment. RAID volumes can also exist on a physical server where administrators can assign a LUN. An operating system running on a virtual machine can also use a LUN. Administrators should create a LUN strategy to ensure that reads and writes are optimized for performance. Too many applications and users writing to the same LUN can cause performance degradation, so ensure that LUNs are assigned with performance in mind.

#### <mark style="background: #BABD00;">Conclusion</mark>

Logical unit numbers (LUNs) play an indispensable role in the realm of block storage, serving as a pivotal link between physical storage resources and the data they hold. As we've explored, LUNs facilitate the efficient and flexible allocation of storage space, allowing for the dynamic management of data in various environments, from small-scale setups to large data centres. 

Administrators working with enterprise solutions might find themselves working with LUN management, typically in a large SAN environment. For systems that use SCSI RAID environments, LUN assignment is a component in mounting drives on servers and client workstations. 

Understanding LUNs is just one piece of knowledge crucial for anyone involved in storage administration or data management as it provides the foundational knowledge required for efficient storage utilisation and data retrieval. The management and support of your storage infrastructure can consume precious IT resources. Learn how [Pure Professional Services](https://www.purestorage.com/services.html) can help reduce the administrative overhead of managing your storage arrays.

# <mark style="background: #BABD00;">14 Cloud Security</mark>

### <mark style="background: #BABD00;">Information Security: Terminology:</mark>

<mark style="background: #BABD00;">Information Security Goals: CIA Triad</mark>  
- Confidentiality, Integrity, and Availability  
- A security framework for logical and physical resources  

<mark style="background: #BABD00;">Authentication, Authorisation, and Auditing (AAA):</mark> An Access security framework for distributed systems  

<mark style="background: #BABD00;">Defense-in-Depth:</mark> Provides multiple layers of defense  

<mark style="background: #BABD00;">Trusted Computing Base (TCB):</mark> Defines boundary between security-critical and non critical parts of an information system  

<mark style="background: #BABD00;">Encryption:</mark> Conversion of data into a form that cannot be used by unauthorised users

### <mark style="background: #BABD00;">Basic information security terminology, which will assist in understanding VDC and Cloud security include:</mark> 

<mark style="background: #BABD00;">CIA triad:</mark> A security framework for an information system has three primary goals: Confidentiality, Integrity, and Availability of physical and logical resources. This is commonly known as CIA triad.  

<mark style="background: #BABD00;">AAA:</mark> The security framework for an information system should provide authentication and authorisation capabilities. Auditing assesses the effectiveness of security mechanisms.  

<mark style="background: #BABD00;">Defense-in-Depth:</mark> It is a risk management strategy which provides multiple layers of defense against attacks.  

<mark style="background: #BABD00;">Trusted Computing Base (TCB):</mark> 
- TCB of an information system is the set of all components that are critical to its security.
- Vulnerabilities occurring inside the TCB might jeopardise the security of the entire system. 
- This way, TCB essentially defines a boundary for security-critical and non critical parts of an information system; for example, kernel services of an OS are more critical for its security than application level services. 
- Therefore, kernel services are part of a TCB for an OS, whereas application level services need not be a part of it.  

<mark style="background: #BABD00;">Encryption:</mark> It is the conversion of data into a form that cannot be easily understood by unauthorised users. Decryption is the process of converting encrypted data back into its original form. Encryption is used to enforce confidentiality, privacy, and integrity.  

The following slides provide details on some of the above mentioned concepts.

### <mark style="background: #BABD00;">CIA Triad:</mark>

<mark style="background: #BABD00;">Confidentiality:</mark>  
- Provides required secrecy of information  
- Ensures that only authorised users have access to data (information)  

<mark style="background: #BABD00;">Integrity:</mark> Ensures that unauthorised changes to data are not allowed  

<mark style="background: #BABD00;">Availability:</mark> Ensures that authorised users have reliable and timely access to data

### <mark style="background: #BABD00;">Authentication, Authorisation and Auditing</mark>

<mark style="background: #BABD00;">Authentication:</mark>
- Is a process to ensure that a user’s credentials (for example identity) are genuine  
- Ensures that no illegitimate access is allowed  
- A special method for authentication is Multi-factor authentication  

<mark style="background: #BABD00;">Authorisation:</mark>  
- Is a process to give specific access rights to a user to resources  
- Defines the scope of the access rights of a user on a resource; for example, read-only access or read-write access  

<mark style="background: #BABD00;">Auditing:</mark> Is a process to evaluate the effectiveness of security enforcement mechanisms

In an information system security framework, authentication and authorisation capabilities are required to ensure legitimate access to data.  

Authentication is a process to ensure that a user’s or asset’s credentials (for example identity) are genuine so that no illegitimate access to information is allowed. Multi-factor authentication is a special method for authentication, which considers multiple factors together for authenticating a  
user.  

Authorisation is a process to grant specific access rights to a user on resources. Authorisation defines the limits of the access rights of a user on a resource; for example, read-only access or read-write access on a file.  

Finally, auditing is a process to evaluate the effectiveness of security enforcement mechanisms.

<mark style="background: #BABD00;">Observability</mark> is the managing, monitoring and observing of your log to see if something malicious is happening.

### <mark style="background: #BABD00;">Multi-factor Authentication:</mark>

<mark style="background: #BABD00;">Considers multiple factors together for authentication</mark>  
- <mark style="background: #BABD00;">First factor:</mark> What does a user know? For example, a password 
- <mark style="background: #BABD00;">Second factor:</mark> What does a user have? For example, a secret key generated by a physical token, in possession of the user  
- <mark style="background: #BABD00;">Third factor:</mark> Who is the user? For example, a biometric signature  

Access is granted only when all the specified factors are validated

![](https://i.imgur.com/83gE9GQ.png)

Multi-factor authentication considers multiple factors before permission to access a resource is granted to the user. 

Additional factors can also be considered, for example, “key phrases” unique to the user’s past activity.  

A multi-factor authentication scheme may consider any combination of these factors for authentication. User access is granted only when all the required factors are validated. 

For example, a two-factor authentication could be based upon the first and second factors discussed above and depicted in the diagram on this slide.

### <mark style="background: #BABD00;">Defense-in-Depth:</mark>

<mark style="background: #BABD00;">Defense-in-Depth (DID):</mark>  An information assurance strategy, whereby multiple security measures  
are used to reduce the risk of security threats if one component of the protection gets compromised.

DID is also known as a "layered approach“ to security  

DID gives an organisation additional time to detect and respond to an attack. Reduces the scope of a security breach

![](https://i.imgur.com/o4s7aJZ.png)

1. <mark style="background: #BABD00;">Perimeter Security</mark> (Physical Security)  
2. <mark style="background: #BABD00;">Remote Access Controls</mark> (VPN, Authentication, etc.)  
3. <mark style="background: #BABD00;">Network Security</mark> (Firewall, DMZ, etc.)  
4. <mark style="background: #BABD00;">Compute Security</mark> (Hardening, Anti Virus, etc.)  
5. <mark style="background: #BABD00;">Storage Security</mark> (Encryption, Zoning, etc.)

Defense-in-depth represents the use of multiple security defenses to help mitigate the risk of security threats if one component of the defense is being compromised. 

An example could be an antivirus software installed on individual VM when there is already a virus protection on the firewalls within the same environment. 

Different security products from multiple vendors may be deployed to defend different potential vulnerable resources within the network.  

Defense-in-depth is an information assurance strategy in which multiple layers of defense are  placed throughout the system. For this reason, it is also known as a “layered approach to security”.  

Because there are multiple measures for security at different levels, defense-in-depth gives additional time to detect and respond to an attack. This reduces the scope of a security breach.  

However, the overall cost of deploying defense-in-depth is often higher, compared to single-layered security mechanisms.

### <mark style="background: #BABD00;">Trusted Computing Base (TCB):</mark>

<mark style="background: #BABD00;">Trusted Computing Base (TCB):</mark> It is the set of all those components that are critical to the security of the system.

Defines boundary for security-critical parts and non-critical parts of a system  

Vulnerabilities occurring inside the TCB might jeopardise the security of the entire system  

Is designed as a combination of hardware and software components  

Careful design and implementation of a system's TCB can significantly improve its overall security

An important design concept while designing a security framework for an information system is the concept of Trusted Computing Base (TCB). TCB of an information system is the set of all components that are critical to its security, in the sense that vulnerabilities occurring inside the TCB might jeopardise the security of the entire system.  

TCB is often the only part of the entire system which runs in a privileged mode, thus enhancing the inherent security of the system. 

TCB controls and authenticates access to the system resources and verifies system integrity. TCB is usually designed as a combination of hardware and software components. 

TCB essentially defines a boundary for security-critical and non critical parts of an information system. 

Careful design and implementation of a system's TCB is of great significance to its overall security.

### <mark style="background: #BABD00;">Encryption:</mark>

<mark style="background: #BABD00;">Encryption:</mark> It is the process of converting data to a form which cannot be used in any meaningful way without special knowledge.

Encryption is a key technique to provide confidentiality and integrity of data  

The unencrypted data is called cleartext (or plaintext) and encrypted data is called ciphertext  

<mark style="background: #BABD00;">The process of converting the encrypted data back to its original form is called decryption:</mark>  
- Both encryption and decryption require keys (special knowledge)  
- Keys for encryption and decryption can be the same or different

Encryption is the process of converting data (information) to a form that cannot be used in any meaningful manner without special knowledge. Encryption is a key technique to enable the confidentiality and integrity of data. The non encrypted data, which is given to the encryption process as an input, is called plaintext (cleartext) and the encrypted data, which is an outcome of the encryption process, is called ciphertext. The process of converting the encrypted data back into its original form is called decryption.  

Encryption (and decryption) requires key(s) (special knowledge) or process to apply on data. When the keys for encryption and decryption are the same, it is known as symmetric encryption. When these keys are different (but related), it is known as asymmetric encryption. For data encryption, most often, symmetric encryption is used. Asymmetric encryption is most commonly used to secure separate end points of a connection, for example, Web browser and Web server (using https), VPN client and server, or for transferring a symmetric key.

### <mark style="background: #BABD00;">Security Concerns and Threats:</mark>

This lesson covers security concerns and threats in a <mark style="background: #BABD00;">VDC</mark> (<mark style="background: #BABD00;">Virtual Data Centre</mark>) and Cloud environment from Cloud Service Provider’s (CSP’s) and user’s perspectives.

Virtualisation-specific security concerns are common for all Cloud models  

<mark style="background: #BABD00;">In public Clouds, there are additional security concerns, which demand specific counter measures:</mark>  
- Clients have less control to enforce security measures in public Clouds  
- Difficult for CSPs to meet the security needs of all the clients  
- Different clients may have different requirements

Security concerns, which arise specifically due to virtualisation, are common to all Cloud models.  

As compared to VDC or Private Clouds, in Public Clouds, there are additional security concerns which demand specific counter measures. This is because, in a VDC or a Private Cloud, a client has complete control over the resources and can enforce security policies.  

In Public (and hybrid) Clouds, however, clients usually do not have that much control over resources and therefore, enforcement of security mechanisms for a client is comparatively difficult.  

For Cloud Service Providers (CSPs) also, it is not easy to enforce all the security measures that meet the security needs of all the clients, because different clients may have different security demands based upon their objective of using the Cloud services. In public Clouds, there are additional security concerns, which demand special measures.  

From a security perspective, both Cloud users as well as service providers have several concerns and face multiple threats. Some of the concerns and threats are common to both of them. From a CSP perspective, majority of the concerns and threats are common to all Cloud-deployment models. Therefore, in cases where a security concern or threat is specific to a Cloud model (for example Public Cloud), it will be explicitly mentioned.

### <mark style="background: #BABD00;">Security Concerns and Threats:</mark>

<mark style="background: #BABD00;">EXAM NOTICE: THREATS AND CONCERNS ARE DIFFERENT. Also, know how to mitigate it. </mark>

<mark style="background: #BABD00;">Cloud Security Concerns:</mark>  
- Multitenancy  
- Velocity of attack  
- Information assurance
- Data privacy and ownership  

<mark style="background: #BABD00;">Cloud Security Threats:</mark>  
- VM Theft and VM Escape  
- HyperJacking  
- Data leakage  
- Denial of Service (DoS) attack

Security concerns and threats in a Cloud environment can be classified for CSPs and Cloud users based upon whom that concern or threat affects more.  

For a CSP, the <mark style="background: #BABD00;">key security concerns</mark> are <mark style="background: #BABD00;">multitenancy</mark> and ‘<mark style="background: #BABD00;">velocity-of-attack</mark>’. Though these are also concerns for Cloud users, it is the CSP who needs to adopt suitable counter measures to address these concerns.  

<mark style="background: #BABD00;">Multitenancy</mark> refers to the fact that the Cloud infrastructure, by virtue of virtualisation, enables multiple independent clients (tenants) to be serviced using same set of resources. This consequently increases the risks for data confidentiality and integrity.  

These risks are especially more severe in case of Public Cloud environment. This is because, in Public Cloud, services can be used by competing clients as compared to Private Clouds. Also, the number of Cloud users are much higher in Public Clouds.  

The <mark style="background: #BABD00;">Velocity-of-attack</mark> in the Cloud refers to a situation where any existing security threat in the Cloud spreads more rapidly and has larger impact than that in the Classic Data Centre (CDC) environments.  

Information assurance, data privacy, and ownership are among the key Cloud security concerns for its users.  

Information assurance covers many related aspects of ensuring that data in a Cloud is “safe”. Data privacy and ownership concerns specifically relate to the risk of an unauthorised data disclosure.  

<mark style="background: #BABD00;">The key security threats for VDC and Cloud infrastructure include:</mark>  
- <mark style="background: #BABD00;">VM theft:</mark> It involves unauthorised copying or movement of a VM.  
- <mark style="background: #BABD00;">VM escape:</mark> Guest OS or an application running on it breaks out and starts interacting directly with the hypervisor.  
- <mark style="background: #BABD00;">HyperJacking:</mark> An attacker installs a rogue hypervisor or <mark style="background: #BABD00;">Virtual Machine Monitor</mark> <mark style="background: #BABD00;">(VMM)</mark> that can take complete control of the underlying server.  
- <mark style="background: #BABD00;">Data leakage:</mark> Refers to the fact that confidential data of a client stored on a third party Cloud is potentially vulnerable to unauthorised loss or manipulation. It is primarily a threat for a Cloud user.  
- <mark style="background: #BABD00;">Denial of Service:</mark> Denial of Service attacks prevent legal users of a system from accessing its services. In Cloud, it could occur when a malicious VM is installed on the same server and consumes all the server resources, thus preventing the other VMs from functioning properly.  

These Cloud security concerns and vulnerabilities will be discussed next.

### <mark style="background: #BABD00;">Security Concern: Multitenancy</mark>

<mark style="background: #BABD00;">Multitenancy is a key security concern in Cloud:</mark>  
- <mark style="background: #BABD00;">For Cloud Clients:</mark> Co-location of multiple VMs in a single server and sharing the same resources increases the attack surface 
- <mark style="background: #BABD00;">For CSPs:</mark> Enforcing uniform security controls and measures is difficult  

<mark style="background: #BABD00;">Mutual client isolation is a key measure against multitenancy-related concerns:</mark>  
- Isolation of VMs  
- Isolation of Data  
- Isolation of network communication

In spite of the benefits offered by multitenancy to a CSP, it is a major security concern for the Cloud clients.  

This is because Cloud infrastructure and services are, by nature, shared among multiple business entities, for example, multiple business units in an organisation or different companies. Co-location of multiple VMs in a single server and sharing the same resources increase the attack surface of vulnerability. This gives rise to a potential security concern for the Cloud users because it makes private data of one client vulnerable to theft by other competing clients who run applications using the same resources.  

There also exists a danger that in the absence of adequate security controls, a tenant application might disrupt operations of other tenants, for example, by launching DoS attacks. An already compromised VM might enable an attacker to compromise the security of other VMs (running on the same server) or of the hypervisor. A compromised guest OS in a VM can also impact other guest OSs in other VMs.  

For CSPs also, multitenancy makes it harder to enforce uniform security controls and counter measures for all the clients.  

Isolation of VMs, data, and network communication related to different clients is a key measure against multitenancy-related concerns. These measures will be discussed later in the module.  

<mark style="background: #BABD00;">Note:</mark> An attack surface refers to various access points/interfaces that an attacker can use to launch an attack; for example, the code within a compute system, which can be executed without requiring any authorisation.

### <mark style="background: #BABD00;">Security Concern: Velocity of Attack</mark>

<mark style="background: #BABD00;">Security threats amplify and spread quickly in a Cloud – known as “Velocity-of-Attack” (VOA) factor</mark>  
- Cloud infrastructure is comparatively larger  
- Similarity in the platforms/components employed by a CSP increases the speed at which an attack can spread  

<mark style="background: #BABD00;">Effects of high VOA</mark>  
- Potential loss due to an attack is comparatively higher  
- It is comparatively more difficult to mitigate the spread of the attack  

To counter the challenge of VOA, CSPs need to adopt more robust security enforcement mechanisms; for example, defense-in-depth

Clouds harness the power of relatively large compute, storage, and network infrastructure, compared to individual data centres. A Public Cloud might consist of thousands of physical servers, network connectivity across large geographic boundaries, and very high capacity storage arrays.  

There also exists homogeneity (similarity) in the platforms and components (for example, the virtualisation software, guest OS) employed by the Cloud service providers.  

Owing to these factors, security threats are amplified more and spread quickly, which is considered as the “velocity of attack” factor in the Cloud. Owing to this factor, security threats can cause much higher levels of losses to the Cloud service providers and to its clients, compared to those in a CDC.  

Mitigating the spread of a threat in a Cloud is also comparatively more difficult than in a CDC environment.  

Because of the potentially high velocity-of-attack, CSPs need to adopt and deploy stronger and robust security enforcement and containment mechanisms, for example, defense-in-depth. Cloud users also need to carefully assess the security services deployed by a CSP before moving operations to the Cloud.

### <mark style="background: #BABD00;">Security Concern: Information Assurance and Data Ownership</mark>

<mark style="background: #BABD00;">Information assurance concerns for Cloud users involves</mark>  
- CIA Triad  
- User Authenticity  
- Authorised use (can operate only with legitimate rights and scope)  

<mark style="background: #BABD00;">Data ownership concerns for Cloud clients:</mark>  
- In Cloud, data belonging to a client is maintained by a CSP, who has access to the data, but is not the legitimate owner of it  
- This raises concern of potential unauthorised data access and misuse  
- Data should be protected using encryption and access control mechanisms

<mark style="background: #BABD00;">The core information assurance concerns for Cloud users include:</mark>  
- <mark style="background: #BABD00;">CIA:</mark> Ensuring confidentiality, integrity, and availability of data in the Cloud.  
- <mark style="background: #BABD00;">Authenticity:</mark> Ensuring that all the users operating on the Cloud are genuine (i.e., their identities have not been fabricated).  
- <mark style="background: #BABD00;">Authorised use:</mark> Ensuring that the Cloud users (clients and CSP administrators) can operate only with legitimate rights and scope.  

Ownership of data is yet another concern for Cloud clients. Ownership issues arise in public Clouds because data belonging to a client is maintained by a CSP who has access to the data but is not the legitimate owner of it. This raises concern of potential misuse of the data for the users because they do not have much control over the data handled by CSP. Data should be protected using encryption. The access control mechanisms for Clouds must be designed to ensure ownership based access rights.

### <mark style="background: #BABD00;">Security Concern: Data Privacy:</mark>

Potential for unauthorised disclosure of private data of a Cloud client  

<mark style="background: #BABD00;">Private data may include:</mark>  
- Individual identity of the client  
- Details of the services requested by the client  
- Proprietary data of the client  

A CSP needs to ensure that private data of its clients is protected from unauthorised disclosure  

Both collection and dissemination of the private data requires protection  

A CSP needs to deploy data privacy mechanisms, which are compliant with the regional legal regulations

<mark style="background: #BABD00;">Data Privacy</mark> is a major concern in Cloud. A CSP needs to ensure that <mark style="background: #BABD00;">Private and Personally Identifiable Information (PII)</mark> about its clients is legally protected from any unauthorised disclosure. 

<mark style="background: #BABD00;">Private data may include:</mark>  
- Individual identity of a Cloud user  
- Details of the services requested by a client  
- Proprietary data of the client  

A CSP needs to ensure that private data of its clients is protected from unauthorised disclosure. Both collection and dissemination of the private data needs protection from any possible unauthorised disclosure, in particular, as per the regional legal requirements.

### <mark style="background: #BABD00;">Security Threat: VM Vulnerabilities</mark>

<mark style="background: #BABD00;">VMs are vulnerable to attack when they are running and when they are powered-off:</mark>  
- A powered-off VM is still available as an image file, which is susceptible to malware infections 
- Unprotected VM migration is vulnerable to network attacks  
- Encryption of VM image files is required as a protection measure when it is powered-off or during its migration  

<mark style="background: #BABD00;">VM templates are also vulnerable to attacks</mark>  
- When new unauthorised VMs are created from a template  
- When a template is modified to infect the VMs  
- To protect, VM templates must be kept encrypted and access should be restricted to privileged users (administrators)

VM templates are vulnerable when they are running and when they are powered-off.  

A powered-off VM is still available as a VM image file that is susceptible to malware infections and patching. If adequate security measures are not deployed, VM migration could expose the migrating VM to various network attacks, for example, eavesdropping and modification.  

VM templates are also vulnerable to attacks; for example, by creating new unauthorised VMs from a template or modifying the templates to infect the VMs that will be provisioned using those templates.  

Protecting VMs from these vulnerabilities require encryption of the VM image files when they are powered off, or while they are migrated. This is beyond the well-defined isolation of VMs, which is generally performed at the hypervisor level. Also, access to the VM templates should be restricted to a limited group of privileged users.

### <mark style="background: #BABD00;">Security Threat: VM Theft:</mark>

<mark style="background: #BABD00;">VM Theft:</mark> A vulnerability that enables an attacker to copy or move a VM in an unauthorised manner.

Is a result of inadequate controls on VM files allowing unauthorised copies or move operations  

<mark style="background: #BABD00;">Copy and Move restrictions are essential to safeguard against VM theft:</mark>  
- These restrictions bind a VM to a specific physical machine  
- A VM with copy and move restriction cannot run on a hypervisor installed on any other server 
- These restrictions use a combination of virtualisation management and storage management services for effective enforcement  
- Limit applying such restrictions to critical/sensitive VMs only

VM theft enables an attacker to copy and/or move a VM in an unauthorised manner. VM theft is a result of inadequate controls on VM files allowing their unauthorised copy or movement. VM theft can cause a very high degree of loss to a Cloud client if its files and data are sensitive in nature.  

Copy and Move restrictions are essential to safeguard against VM theft. Such restrictions effectively bind a VM to a specific (secure) physical machine so that even if there is a forceful copy of the VM, it will not operate on any other machine. A VM with copy and move restrictions cannot run on a hypervisor installed on any other machine. These restrictions use a combination of virtualisation management and storage management services for their effective enforcement.  

Even though these restrictions are essential to safeguard against VM theft, they, on the other hand, might limit the benefit of load balancing of VMs across physical servers. Therefore, it is advisable that copy and move restrictions be applied in a limited way, especially only on those VMs, which are considered security critical/sensitive or are relatively more vulnerable for theft.  

Apart from VM theft, another threat on the VM level is known as <mark style="background: #BABD00;">‘VM escape’</mark>. Normally, virtual machines are encapsulated and isolated from each other. There is no straightforward way for a guest OS and the applications running on it to break out of the virtual machine boundary and directly interact with the parent hypervisor.  

The process of breaking out and interacting with the hypervisor is called a VM escape. Since the hypervisor controls the execution of all VMs, due to VM escape, an attacker can gain control over every other VM running on it by bypassing security controls that are placed on those VMs.

### <mark style="background: #BABD00;">Security Threat: HyperJacking:</mark>

<mark style="background: #BABD00;">Hyperjacking:</mark> It enables an attacker to install a rogue hypervisor or Virtual Machine Monitor (VMM) that can take control of the underlying server resources

An attacker can run unauthorised applications on a guest OS without the OS realising it  

An attacker could control the interaction between the VMs and the underlying server  

Regular security measures are ineffective against hyperjacking  

<mark style="background: #BABD00;">Measures against hyperjacking include:</mark>  
- Hardware-assisted secure launching of the hypervisor  
- Scanning hardware-level details to assess the integrity of the hypervisor and locating the presence of the rogue hypervisor

HyperJacking is a rootkit level vulnerability that enables an attacker to install a rogue hypervisor or virtual machine monitor that can take complete control of the underlying physical server.  

A rootkit is a malicious program which is installed before an hypervisor or VMM is fully booted on a physical server. This way, a rootkit runs with privileged access and remains invisible to the administrators. After a rootkit is installed, it allows an attacker to mask the ongoing intrusion and maintain privileged access to the physical server by circumventing normal authentication and authorisation mechanisms employed by an OS.  

Using such a rogue hypervisor, an attacker can run unauthorised applications on a guest OS without that OS realising the presence of such an application. With hyperjacking, an attacker can control the interaction between the VMs and the underlying physical machine.  

<mark style="background: #BABD00;">Regular security measures are ineffective against this rough hypervisor because:</mark>  
- Guest OS would remain unaware of the fact that the underlying server has been attacked and  
- The antivirus and firewall applications cannot detect such rogue hypervisor because they are installed over the server itself  

<mark style="background: #BABD00;">Measures against hyperjacking include:</mark>  
- Hardware-assisted secure launching of the hypervisor so that rootkit level malicious programs cannot launch. This involves designing and using a TCB so that the hypervisor gets support at the hardware level itself  
- Scanning the hardware-level details to assess the integrity of the hypervisor and locating the presence of rogue hypervisor. This scanning may include checking the state of the memory and registers in the CPU.

### <mark style="background: #BABD00;">Security Threat: Data Leakage:</mark>

Confidential data stored on a third party Cloud is potentially vulnerable to unauthorised access or manipulation  

Attacks on service provider’s control systems (for example passwords lists) could make all the clients’ data vulnerable  

Cloud users must evaluate end-to-end data protection measures by all the concerned parties who have any level of access on the data  

<mark style="background: #BABD00;">Side Channel Attacks (SCA) can be used for data leakage in Cloud:</mark> An SCA extracts information by monitoring indirect activities; for example cache data, keystroke activity, etc.  

<mark style="background: #BABD00;">Cross-VM SCA:</mark>  
- Could reveal information of a client to another malicious client that runs its VMs on the same server  
- Protection against cross VM SCA requires placing only those clients that have no conflicts with one another on the same server

A cross VM SCA involves one VM being used to launch an SCA on another VM running on the same server. A cross VM SCA could reveal information on a client’s critical business activity to a malicious client that runs its VMs on the same server. Protection against such cross VM SCA requires a placement policy that permits clients to install only non-conflicting VMS on the same server. This will, however, reduce resource optimisation that virtualisation technology offers. It could also add extra service cost to the Cloud clients who demand such privileged services.

### <mark style="background: #BABD00;">Security Threat: Denial of Service Attacks:</mark>

<mark style="background: #BABD00;">Denial of Service (DoS):</mark> It is an attempt to prevent legitimate users from accessing a resource or service.

DoS attacks might affect software applications and network components  

<mark style="background: #BABD00;">A DoS attack involves:</mark>  
- Exhausting resources, for example, network bandwidth or CPU cycles  
- Exploiting weaknesses in communication protocols, for example, resetting of TCP sessions, corrupting domain name server’s cache  

A malicious client VM might be used to launch a DoS attack against the hypervisor or other VMs running on the same hypervisor  

As a protective measure, resource consumption of a VM needs to be restricted

A Denial of Service (DoS) attack is an attempt to make resources or services of an information system unavailable to its authorised users.  

A DoS attack prevents legitimate users from accessing a resource or service. DoS attacks could be targeted against software applications (example OS) and network components including routers or servers.  

<mark style="background: #BABD00;">Often a DoS attack involves either one or a combination of the following:</mark>  
- Attack aims to exhaust computing resources, for example, network bandwidth and CPU cycles. An attack may involve massive quantities of data sent to the target with the intention of consuming bandwidth/processing resources.  
- Attack involves exploiting weaknesses in a protocol to target network resources; for example, resetting of TCP sessions, IP address spoofing, or corrupting DNS server cache.  

A Distributed DoS (DDoS) attack is a special type of DoS attack in which several systems launch coordinated DoS attack on their target(s), thereby causing denial of service to the users of the targeted system(s). In a DDoS attack, the main attacker is able to multiply the effectiveness of the DoS attack by harnessing the resources of multiple collaborating systems. These collaborating systems serve as attack platforms. Typically a DDoS master program is installed on one compute system using a stolen account. Then, at a designated time, the master program communicates to any number of "agent" programs installed on computers anywhere on the network. When the agents receive the command, they initiate the attack.  

In a virtualised environment, a rough VM could be used to launch DoS attack against the hypervisor or other VMs running on the same hypervisor. Such a rough VM could use the internal virtual network for launching the DoS attacks. To protect against such VM based DoS attacks, the resource consumption of a VM should be restricted to specific limits.

### <mark style="background: #BABD00;">Security Mechanisms:</mark>

<mark style="background: #BABD00;">Topics covered in this lesson:</mark>  
- Security at compute level, including securing server, hypervisor, VM, guest OS, and applications  
- Security at network and storage levels, including virtual  firewall, demilitarized zone, and data shredding  
- Intrusion detection in VDC and Cloud  
- Physical Security of the premises  
- Access Control and Identity management services in Cloud

### <mark style="background: #BABD00;">Security at Compute Level:</mark>

<mark style="background: #BABD00;">Securing a compute system includes:</mark>  
- Securing physical server  
- Securing hypervisor  
- Securing VMs  
- VM Isolation  
- VM Hardening 
- Security at guest OS level  
- Guest OS Hardening  
- Security at application level  
- Application Hardening

Securing a compute infrastructure includes enforcing security of the physical server, hypervisor, VM, and guest OS.  

Security at the hypervisor level primarily aims at securing hypervisor from the rootkits and malware based attacks and protection of the hypervisor management system. 

VM isolation and hardening are two key techniques for securing VMs. Security at the guest OS level uses sandboxing and hardening as two key methods. Application hardening is used to reduce vulnerability of the applications from getting exploited by malicious attackers. All these security methods are explained in the following slides.

### <mark style="background: #BABD00;">Physical Server Security: Considerations:</mark>

<mark style="background: #BABD00;">Identifying physical server application details including:</mark>  
- Whether server will be used for specific applications or for general purpose  
- The network services provided on the server  
- Users and/or user groups who can operate the server and their access privileges  

<mark style="background: #BABD00;">Deciding protection measures:</mark>  
- Determining authentication and authorisation mechanisms  
- Disabling unused hardware such as NICs, USB ports, or drives 
- Physical security

<mark style="background: #BABD00;">Server security considerations include identifying server application details such as:</mark>  
- Deciding whether the server will be used for specific applications (for example backup applications) or for general purpose.  
- Identifying the network services to be provided on server; for example, LAN connection, wireless connection, etc.  
- Identifying users and/or user groups who will be given access rights on the server. This also includes determining their specific access privileges.  

<mark style="background: #BABD00;">Based upon these details, suitable protection measures need to be decided including the following:</mark>  
- Determine user authentication and authorisation mechanisms.  
- If the server has unused hardware components such as NICs, USB ports, or drives, they should be removed or disabled. This should also be done in the VM (template).  
- Adequate physical security protection including safety of the premises where the server will be housed.

### <mark style="background: #BABD00;">Hypervisor Security:</mark>

Attacks on the hypervisor impact all the VMs running on it - a single point of security failure  

<mark style="background: #BABD00;">Security measures:</mark>  
- Install hypervisor updates  
- Harden VMs to prevent attacks  

<mark style="background: #BABD00;">Protection of the hypervisor management system is critical because an insecure management system can:</mark>  
- Make existing VMs vulnerable for attacks  
- Enable creation of new malicious VMs  

<mark style="background: #BABD00;">Can be achieved by:</mark>  
- Configuring strong security on the firewall between the management system and the network  
- Providing direct access only to administrators to management server  
- Disable access to management console to prevent unauthorised access

A Hypervisor in a virtualised environment presents a single point of security failure for all the VMs running on it. A single breach of the hypervisor places all the guest OSs on these VMs at high risk.  

Rootkits and malware installed below the OS make detection difficult for the antivirus software installed on the guest OS.  

To protect against attacks, security-critical hypervisor updates should be installed at the earliest possible and the VMs hosted on it should be hardened (VM hardening measures are discussed next). Hypervisor services like clipboard, if not used, should be disabled.  

The hypervisor management system must be protected. Malicious attacks and infiltration to the management system can impact all the existing VMs and allow attackers to create new VMs.  

Access to the management system should be restricted only to authorised administrators. Levels of access should be restricted to selected administrators. Furthermore, there must be a separate firewall with strong security installed between the management system and the rest of the network. Yet another measure is to disable access to the management console to prevent unauthorised access.

### <mark style="background: #BABD00;">VM Security Isolation and Hardening:</mark>

<mark style="background: #BABD00;">VM isolation</mark> helps prevent a compromised guest OS and applications running on it from impacting other VMs  

<mark style="background: #BABD00;">VM Hardening:</mark> Hardening is a process of changing the default configuration in order to achieve greater security  

<mark style="background: #BABD00;">Considerations:</mark>  
- Use VM templates to provision new VMs  
- Limit the resources that VM can consume to  prevent DoS attacks  
- Disable unused functions and devices on VM  
- Use a directory service for authentication  
- Perform vulnerability scanning and penetration testing of the guest OS

VM isolation is a key measure that helps in preventing a compromised guest OS from impacting other guest OSs. VM isolation is implemented at the hypervisor level.  

Apart from isolation, VMs should be hardened against security threats. Hardening is a process of changing the default configuration in order to achieve greater security. 

<mark style="background: #BABD00;">Some of the key measures for hardening a VM (especially for a VDC or private Cloud environment) include the following:</mark>  
- <mark style="background: #BABD00;">Use VM templates to deploy VMs:</mark> When using templates, harden the VM image so that all the deployed VMs have a known security baseline. VM templates should be created with up-to-date VM patches and security updates.  
- In order to avoid DoS attacks, the VM management software should limit the VM’s resources so that a single VM is not allowed to consume all of the server’s resources. 
- Increase in the number of services, ports, and applications running on the VM also increases the area of attack surface. Therefore, unneeded functions and unused devices should be disabled.  
- Configure access permissions for the selected group of administrators. Avoid account sharing by groups of users and strictly control root privileges. Employ directory based authentication to ensure the genuineness of credentials.  
- Take VM backups on a regular basis and schedule point-in-time snapshots to restore a VM to a safe state, in case of an attack.  
- Perform vulnerability scanning of the guest OS regularly to identify existing vulnerabilities. Perform a penetration test to determine the feasibility of an attack and the extent of business impact of the attack. Note that in Public Clouds, usually, penetration tests originating from outside the CSP network are forbidden by the CSP. Therefore, a Cloud user should rely upon the CSP to perform these tests.

![](https://i.imgur.com/ObANoSi.png)

### <mark style="background: #BABD00;">Guest OS and Application Security:</mark>

<mark style="background: #BABD00;">Guest OS hardening measures include:</mark>  
- Deleting unused files and applying the latest patches  
- Applying hardening checklists available for specific OSs 
- Installing the guest OS in TCB mode if the VM is to be used for critical applications  
- Need support from hypervisor in configuring (trusted) virtual hardware component for TCB  

<mark style="background: #BABD00;">Application hardening measures include disallowing a vulnerable application from:</mark>  
- Launching any (untrusted) executable file  
- Creating or modifying executable files  
- Modifying sensitive areas of the guest OS, for example, MS Windows registry  

Sandboxing is another important measure for guest OS and application security

Apart from the measures to secure a hypervisor and VMs, VDC and Cloud environment also require further measures on the guest OS and application levels. Hardening is one such important measure which can effectively safeguard guest OS and the applications running on it.  

OS hardening, for example, may involve actions such as configuring system and network components, deleting unused files, and applying the latest patches. There are hardening checklists available for major OSs which administrators should follow to harden the guest OSs deployed in VDC or Cloud. In cases where a VM is to be used for business critical applications, the guest OS should be installed in the TCB mode – an option available with many OSs. Such TCB mode installation, however, requires hypervisor support for configuring trusted virtual hardware components (for example virtual CPU).  

Application hardening helps to prevent exploitation of vulnerabilities in software applications that have not been patched so far:

<mark style="background: #BABD00;">The key steps for hardening a vulnerable application include:</mark>  
- <mark style="background: #BABD00;">Disallowing the application from spawning executable files:</mark> One of the methods used by attackers is to make a vulnerable application into spawning executable files of their choice. Therefore, an important action for hardening the application is to disallow it from launching other executables, except those that are trusted.  
- <mark style="background: #BABD00;">Disallowing the application from creating or modifying executable files:</mark> Another technique, which is used by attackers, is to convert the vulnerable application into modifying or creating executable files of their choice in order to insert the malicious code into the system. The malicious code may eventually be executed and activated. Therefore, it is critical that applications are not allowed to modify or create any executable file when they are running.  
- <mark style="background: #BABD00;">Disallowing the application from modifying sensitive areas:</mark> It involves disallowing the application from modifying sensitive areas of the guest OS, for example, registry keys in the Windows OS.

### <mark style="background: #BABD00;">Security at Network Level: Virtual Firewall:</mark>

<mark style="background: #BABD00;">Securing VM-to-VM traffic running on a server is difficult in a VDC environment:</mark>  
- Virtual switches could be invisible to administrators (network and system)  
- Traffic may never leave the server, so it cannot be detected and intercepted  

Virtual Firewall (VF) is a firewall service running on the hypervisor

![](https://i.imgur.com/ja57Gus.png)

A <mark style="background: #BABD00;">firewall</mark> is a security technology designed to permit or deny network transmissions based upon a set of rules.

A firewall is implemented on a compute level and limits access between networks and/or systems in accordance with a specific security policy. A firewall is used to protect networks from unauthorised access while permitting only legitimate communications.

In a VDC and Cloud infrastructure, a firewall can also be used to protect hypervisors and VMs; for example, if remote administration is enabled on a hypervisor, access to all the remote administration interfaces should be restricted by a firewall.  

Securing the VM-to-VM traffic running on a server is a key security problem in a VDC environment. Securing this virtual network is a considerable challenge because virtual switches could be invisible to network and/or system administrators, who usually enforce security at the network level.  

Because the virtual network traffic may never leave the server, security administrators cannot observe VM-to-VM traffic, cannot intercept it, and so, cannot know what that traffic is for. Thus, logging of the VM-to-VM network activity within a single server and verification of virtual machine access for regulatory compliance purposes is relatively difficult. 

Inappropriate use of virtual network resources and bandwidth consumption in VM-to-VM are difficult to monitor or rectify. Therefore, a firewall service, which can be used to monitor and control VM-to-VM traffic, is critically required. It is provided by a Virtual Firewall (VF), which is a firewall service running entirely on the hypervisor. VF provides the usual packet filtering and monitoring of the VM-to-VM traffic. VF gives visibility and control over VM traffic and enforces policies at the VM level.

### <mark style="background: #BABD00;">Security at Network Level: Demilitarised Zone:</mark>

<mark style="background: #BABD00;">Demilitarised Zone (DMZ):</mark> It is a physical or logical (sub)network that limits the exposure of the nodes in the internal network from external networks.

<mark style="background: #BABD00;">Adds additional layer of security against external attacks:</mark>  
- An attacker has access only to the DMZ, rather than any other part of the network  
- For practical purposes ,services provided to users on the external networks can be placed in the DMZ  

A virtualised DMZ is a DMZ established in a virtualised environment using virtual network components.

![](https://i.imgur.com/eqA54tN.png)


<mark style="background: #BABD00;">PORT KNOCKING:</mark> Instead of allowing an external user to access an application on a specific port, have a number of ports they must request in a specific order in order to be authenticated. This is also audited.

### <mark style="background: #BABD00;">Securing at Network level:</mark>

<mark style="background: #BABD00;">Data-in-flight:</mark>  Data which is being transferred over a network i.e., “moving”  

<mark style="background: #BABD00;">Encryption of Data-in-flight:</mark>  
- Provides confidentiality and integrity  
- Is a key measure against “sniffing” attacks

![](https://i.imgur.com/Kv4f5mZ.png)

Encryption of data-in-flight is the key method for providing confidentiality and integrity services. Encryption makes the data indecipherable to an unauthorised user who otherwise may have access to the (encrypted) data. Encryption is indeed a key security measure against “sniffing” attacks. In a sniffing attack, a non recipient malicious device/user accesses the data transmitted over the network.  

<mark style="background: #BABD00;">Methods used for encrypting data-in-flight include:</mark>  
- <mark style="background: #BABD00;">Application-level encryption:</mark> Encryption is applied at the application level where the data is generated. Encrypting at the application level protects data against unauthorised access; for example, Transport Layer Security (TLS) protocol allows client/server applications to enforce encryption service.  
- <mark style="background: #BABD00;">Network-level encryption:</mark> Encryption is applied at the network layer; for example, IPSec, which can be used to encrypt and authenticate each IP packet transmitted over an IP network. The benefit of a network level encryption is that it is independent of the underlying guest OS.

### <mark style="background: #BABD00;">Storage Security in Cloud:</mark>

Major threats to storage system in a VDC and Cloud arise due to compromises at compute, network, and/or physical security levels  

Adequate security at compute and network levels is essential for storage security  

Storage Area Networks(SAN) have their unique vulnerabilities, for example, fabric access to an unauthorised device, WWN spoofing, DoS attack, zoning bypass, etc.  

<mark style="background: #BABD00;">WWN Spoofing:</mark>  
- World Wide Name Spoofing  
- It is the way of bypassing authorisation methods in a SAN
- Enables a device to masquerade as a different entity

Major threats to storage system in a VDC and Cloud environment arise due to compromises at compute, network, and/or physical security levels. This is because an access to storage systems needs to be made by using compute and network infrastructure. 

Therefore, adequate security measures need to be in place at compute and network levels to ensure storage security. 

<mark style="background: #BABD00;">Security mechanisms that might help to protect storage includes:</mark>  
- Access control methods to regulate which users and processes access the data on the storage systems.  
- Zoning and LUN masking  
- Encryption of data-at-rest (on the storage system) and data-in-transit. Data encryption should also include encrypting backups and storing encryption keys separately from the data.  
- WWPN and WWNN LUN masking for restricting access to the storage arrays in a SAN.  
- Data shredding, which removes the traces of the deleted data. It may be performed by both CSP and also by the client.  
- Backup and recovery in case of loss of data.  

Apart from these mechanisms, physical isolation of storage devices from the other hardware and also an isolation of storage traffic from other types of traffic using VLANs and FC zoning would help in protecting storage.  

Moreover, security protection is required for the storage utilised by the hypervisor for VMs, for example, a CFS supporting multiple VMs within a cluster. 

This may include using separate LUNs for VM components and for VM data and segregating VM traffic from hypervisor storage and management traffic.

### <mark style="background: #BABD00;">Securing Data-at-Rest:</mark>

<mark style="background: #BABD00;">Data-at-rest:</mark> Data which is not being transferred over a network. It includes data that resides in databases, file systems, flash drives, memory, networked storage, etc.  

<mark style="background: #BABD00;">Encryption of Data-at-rest:</mark> 
- Provides confidentiality and integrity services  
- Reduces legal liabilities of a CSP due to an unauthorised disclosure of data on its Cloud because even if the encrypted data becomes accessible to an unauthorised user, it cannot be used in any meaningful way.  

<mark style="background: #BABD00;">Full disk encryption is the key method used for encrypting data-at-rest residing on a disk:</mark> 
- Full disk encryption employs software application or built-in hardware capability to encrypt every bit of data that goes on a disk or disk volume. 
- Disk encryption thus prevents unauthorised access to data storage. For additional security, it can be used in conjunction with file system encryption. 
- Full disk encryption may use either a single key for encrypting the complete disk or different keys for encrypting different partitions.

### <mark style="background: #BABD00;">Data Shredding:</mark>

Data which is deleted by a Cloud client or a process, but which leaves traces on the system, can be a potential source of attacks  

Traces of deleted VMs can provide vital information to an attacker  

Partially recoverable “deleted data” may reveal client details  

Data shredding permanently removes all the traces of the deleted data and is a critical feature for data security in a Cloud infrastructure. 

Data that has been shredded can no longer be recovered

<mark style="background: #BABD00;">Traces of the deleted data include:</mark>  
- Logs of VM or application executions  
- Logs of old files, folders, and other resources  
- Logs of data communication

Unlike data stored in a privately controlled storage or in a CDC, data and information in a Cloud remain vulnerable even if deleted by the client or a process.   

### <mark style="background: #BABD00;">Physical Security in VDC and Cloud:</mark>

<mark style="background: #BABD00;">Restricted Port Access:</mark>  
- Leave unused ports in disabled state  
- Bind specific devices to designated ports  

<mark style="background: #BABD00;">Other types:</mark>
- CCTV based video surveillance  
- 24/7/365 onsite guarded security  
- Biometric authentication based physical access

Cloud customers essentially lose control over physical security when they move to the Cloud, because the actual servers can be anywhere the provider decides to put them. 

Since physical Cloud infrastructure supports many Cloud clients together, its security is very critical both for the CSP as well as its clients. 

Policies, processes, and procedures are critical elements of successful physical security that can protect the equipment and data housed in the hosting centre.  

<mark style="background: #BABD00;">Typical security measures that must be in place for securing physical Cloud infrastructure include:</mark>  
- Leaving a port in unconfigured or disabled state so that unknown devices or components cannot connect to the infrastructure. Additionally, bind specific devices to designated ports.  
- Apply MAC/WWPN binding and VLAN restrictions to physical Ethernet switches.  
- 24/7/365 onsite security for the premise where the Cloud physical infrastructure is hosted  
- Biometric authentication based access to the premises  
- Closed circuit TV cameras to monitor activity throughout the facility

### <mark style="background: #BABD00;">Role Based Access Control:</mark>

<mark style="background: #BABD00;">Resource access (permissions) is given to subjects (users and processes) based upon their roles:</mark>  
- Role may represent a job function  
- Permissions are associated with the roles  
- Subjects acquire permissions to perform operations on resources based upon the roles assigned to them  

Role Based Access Control (<mark style="background: #BABD00;">RBAC</mark>) can be enabled for Cloud clients by importing user groups using directory services of the client organisation  

CSP may use RBAC to control an administrative access to the hypervisor management system (console)

In a Role Based Access Control (RBAC) model, resource access rights (permissions) are given to subjects (users and processes) based upon their roles. A role may represent a job function, for example, an administrator. 

Permissions are associated with the roles and subjects are not given any direct permissions. Subjects acquire permissions to perform operations on resources based upon the roles assigned to them.  

For RBAC, users need to be grouped together into roles. As an example, a set of IT administrators can be given permissions to start, stop, and delete VMs that are running in the Cloud. However, there could be a specific subset of production servers that even the IT administrators are not allowed to control.  

To handle sensitive data and compliance requirements, a Cloud needs RBAC capabilities. To achieve this, user groups can be imported using LDAP based Directory Services of the client organisation for client installations in Cloud. CSPs may also use RBAC to control administrative access to the hypervisor management system (console).

### <mark style="background: #BABD00;">Identity Management (IM) in Cloud:</mark>

<mark style="background: #BABD00;">One-time passwords:</mark>  
- Every new access request requires new password  
- A measure against “password compromises”  

<mark style="background: #BABD00;">Federated Identity Management is provided as a service on Cloud:</mark>  
- Enables organisations to authenticate their users of Cloud services using the chosen identity provider  
- User identities across different organisations can be managed together to enable collaboration on Cloud  

<mark style="background: #BABD00;">OpenID:</mark>  
- Is an open standard for decentralised authentication and access control  
- Can be used while allowing users to log onto many services using the same digital identity

Identity management is an administrative process that deals with identifying users of an information system. Additionally, identity management also controls access to system resources by placing restrictions using user identities . The key identity management-related aspects in Cloud are as follows:  

<mark style="background: #BABD00;">One-time password:</mark> Because passwords can be compromised, they must be protected. The One-Time Password (OTP) concept demands that a new password be used for each new log on and thus provides necessary security against password compromises. Time-dependent password generated by hardware security tokens (for example, RSA SecureID) is an example of OTP. OTP is specifically useful in situations where likelihood of password compromises are high, for example, remote login based network access.  

<mark style="background: #BABD00;">Federated Identity Management:</mark> Federation is the process of managing the trust relationships among distinct organisations beyond the internal network or administrative boundaries. A federation is an association of organisations that come together to exchange information about their users and resources to enable collaborations and transactions. In a Cloud, Federated Identity Management (FIM) can play a vital role in enabling organisations authenticate their users of Cloud services using the organisations’ chosen identity provider. This would involve exchanging identity attributes between the CSP and the identity provider in a secure way.  

<mark style="background: #BABD00;">OpenID:</mark> It is an open standard that describes how users can be authenticated in a decentralised manner, obviating the need for services to provide their own ad hoc systems and allowing users to consolidate their digital identities. OpenID enables maintaining single-user credentials for access control and can be used while allowing users to log onto many services using the same digital identity. It allows users to log in once and gain access to resources across participating systems. For example, Google Apps provides cloud identity services to its enterprise customers using OpenID.

### <mark style="background: #BABD00;">Governance, Risks and Compliance:</mark>

This lesson covers governance, risk, and compliance aspects in Cloud. Governance aspects include SLAs and information flow regulations. Risk assessment includes identification of critical assets, potential risks, and the classification of critical assets into risk categories. Compliance includes internal and external policy compliance

<mark style="background: #BABD00;">Governance</mark> refers to the policies, processes, laws, and institutions that define the structure by which companies are directed and managed.  

<mark style="background: #BABD00;">Risk</mark> refers to the effect of uncertainty on business objectives; risk management is a coordinated activity to direct and control an organisation, and to realise business potential while managing negative events.  

<mark style="background: #BABD00;">Risk has two separate parts:</mark> 
- Identification
- Mitigation

<mark style="background: #BABD00;">Compliance</mark> refers to the act of adhering to and demonstrating adherence to external laws and regulations as well as corporate policies and procedures.

An <mark style="background: #BABD00;">Enterprise GRC (eGRC)</mark> solution allow a business to build an efficient, collaborative enterprise governance, risk and compliance (eGRC) program across IT, finance, operations, and legal domains. 

Such a program enables a business to manage risks, demonstrate compliance, automate business processes, and gain visibility into corporate risk and security controls.

A backup is only as good as your demonstrable ability to restore from that backup

### <mark style="background: #BABD00;">Cloud Governance: Information Flow Regulations</mark>

<mark style="background: #BABD00;">National and international regulations could constrain the flow of information in Cloud:</mark>  
- Various legislations specify that sensitive information cannot travel across regional boundaries; for example, European data protection laws impose obligations on handling and processing of data transferred to the U.S.  
- Existing Security standards also apply to Cloud  
- Specific regulations control certain types of information  

Information (data) flow regulations may limit adoption of public Clouds for applications handling sensitive data  

Among various Cloud deployment models, private Clouds offer the maximum information flow regulation

National and international regulations could constrain the flow of information in Cloud. For example, Cloud offers location independence to its clients in terms of where the actual data resides. This might also lead to difficult legal issues; for example, a governmental data on a Cloud, handled abroad by private parties, fall under the foreign jurisdiction. There are various regulations, which specify that sensitive information cannot travel across regional boundaries; for example, European data protection laws impose additional obligations on the handling and processing of data transferred to the U.S.  

Another aspect is that existing security standards may also apply to Cloud; for example, it is recommended that CSPs follow ISO 27001, which is an Information Security Management System standard and formally specifies requirements to bring information security under explicit management control.  

Furthermore, there are regulations that control certain specific types of information. For example, the Administrative Simplification provisions of Health Insurance Portability and Accountability Act (HIPAA) specify security and privacy aspects dealing with medical data in the USA.  

Such information flow regulations may limit adoption of Public Clouds for applications handling sensitive data. For example, governmental agencies might find it difficult to use public Clouds, which could potentially host their data in some other country due to cost advantages.  

Among various Cloud deployment models, private Clouds offer the maximum information flow regulation because the control over data remains fully with the organisation

### <mark style="background: #BABD00;">Cloud Governance: Contract Termination:</mark>

Cloud users need to assess implications of situations when services with a CSP should be terminated  

Termination agreement specifies the closure process  

<mark style="background: #BABD00;">Situations may include:</mark>  
- CSP going out of business  
- CSP cancelling the contract  
- Natural closure of a contract  

<mark style="background: #BABD00;">Key Considerations for a Cloud user:</mark>  
- Developing a contingency plan for handling data  
- Migrating the data, including time to migrate the data  
- Shredding the data on the Cloud after its migration

A client needs to assess implications when the existing business with a CSP needs to be terminated.  

<mark style="background: #BABD00;">There might exist many situations where such a contract termination is required:</mark>  
- The CSP goes out of business and winds up its services  
- The CSP cancels the contract  
- There is a natural closure for the contracted services  

In order to avoid the negative impact of such a closure, there needs to be a formal agreement between a Cloud client and the CSP, which is referred as termination agreement. 

<mark style="background: #BABD00;">In situations which involve the closure of the Cloud services for a client, the following points should be  
considered:</mark>  
- A contingency plan for handling data in the Cloud  
- A process for migrating the data back into the organisation or to another Cloud  
- A prior assessment as to whether the data can be moved over the network in a reasonable amount of time or whether it is necessary to make special arrangements for a physical transfer  

The plan for data destruction (storage, clones, backups) using shredding after the data has successfully moved from the Cloud

### <mark style="background: #BABD00;">Risk Assessment:</mark>

<mark style="background: #BABD00;">Aims to identify potential risks while operating in a Cloud environment:</mark>  
- Should be performed before moving to a Cloud  
- Used to determine the actual scope for Cloud adoption

<mark style="background: #BABD00;">Steps to perform Risk Assessment:</mark>  
1. Identifying critical and sensitive assets (data, applications, and processes). <mark style="background: #BABD00;">Critical assets</mark> are necessary for the operation of the business. <mark style="background: #BABD00;">Sensitive assets</mark> are those having high business value  
2. Identifying potential risks  
3. Classifying risks into severity levels  
4. Associating potential risks with critical assets

A risk assessment process aims to identify potential sources of risk while operating in a Cloud environment. This critical process is required before deciding to move operations to Cloud, especially if the decision is related to the Public Clouds.  

<mark style="background: #BABD00;">Various steps involved in this process are:</mark>  
1. <mark style="background: #BABD00;">Identifying critical and sensitive assets:</mark> All the assets (data, applications, and processes) must be carefully evaluated to assess as to how critical or sensitive an asset is for the organisation. Critical assets are necessary for the operation of the business. Sensitive assets are those having high business value for the organisation, for example, Intellectual Property (IP), project plans, and Personally Identifiable Information (PII).  
2. <mark style="background: #BABD00;">Identifying potential risks:</mark> It is important to analyse and identify all the potential risks while operating in a Cloud environment. An example could be the legal situations under which a CSP might have to disclose data belonging to its clients.  
3. <mark style="background: #BABD00;">Classifying risks into severity levels:</mark> After comprehensive classification of the risks associated with operating in Cloud, these risks need to be classified into various severity levels i.e., very high risk, moderately high risk, high risk, low risk, and no risk. These severity levels could alternately be numbered in a certain range, for example, 0 to 5.  
4. <mark style="background: #BABD00;">Associating potential risks with critical assets:</mark> This step involves associating the critical assets with potential risks; for example, employee’s banking records can be identified as critical assets (in step 1), data disclosure could be a risk (identified in step 2) of very high severity level (in step 3). Based upon these, data disclosure risk may be associated with  employee records.  

Based upon the risk assessment for the assets, a client could consider formulating terms and conditions of the contractual agreement with CSP; for example, a client might insist on having its data placed within certain geographical regions by the CSP.

### <mark style="background: #BABD00;">Compliance:</mark>

Cloud adoption and operation for enterprise businesses need to abide by compliance policies    

<mark style="background: #BABD00;">Internal policy compliance:</mark>  
- Controls the nature of IT operations within an organisation  
- Needs to maintain same compliance even when operating in Cloud  

<mark style="background: #BABD00;">External regulatory compliance:</mark>  
- Includes legal legislations and industry regulations  
- Controls the nature of IT operations related to flow of data out of an organisation  
- May differ based upon the type of information, business, etc.  

Meeting all varied client compliance requirements is difficult for a CSP  

Compared to Private Clouds, the Public Cloud environment makes compliance more challenging

Cloud service adoption and operation for enterprise businesses should abide by compliance policies. There are primarily two types of policies controlling IT operations in an enterprise that requires compliance even after moving operations to Cloud.  

<mark style="background: #BABD00;">Internal Policy Compliance:</mark> Controls the nature of IT operations within an organisation. A Cloud client organisation needs to maintain same compliance even when operating in Cloud. This would require clear assessment of the potential difficulties in maintaining the compliance in Cloud and a process to ensure that this is effectively achieved.  

<mark style="background: #BABD00;">External Policy Compliance:</mark> Includes legal legislations and industry regulations. These external compliance policies control the nature of IT operations related to the flow of data out of an organisation. However, they may differ based upon the type of information (for example, source code versus employee records), business (for example medical services versus financial services), etc.  

Meeting all the varied client compliance requirements is generally difficult for a CSP. Compared to Private Clouds, the Public Cloud environment makes compliance more challenging. Therefore, many enterprises may prefer to adopt the hybrid Cloud deployment model so that they can ensure all the necessary policy compliances.

### <mark style="background: #BABD00;">Summary:</mark>

- VDC and Cloud security concerns and threats  
- Cloud infrastructure security mechanisms at compute, storage, and network levels  
- Access control and identity management mechanisms in Cloud  
- Governance, Risk, and Compliance (GRC) aspects in Cloud including information flow regulations and risk assessment  
- Cloud security best practices including reference architecture for Cloud security

This module covered VDC and Cloud security concerns and threats including multitenancy, data privacy and ownership, and velocity of attack factor.  

Cloud infrastructure security mechanisms at compute, storage, and network levels include securing data using encryption, intrusion detection techniques, and methods to provide physical security.  

Access control mechanism included RBAC. Identity management included one-time password, federated identity management, and OpenID.  

The Governance, Risk, and Compliance (GRC) discussion focused upon various aspects, including information flow regulations and risk assessment process. Finally, the module discussed Cloud security best practices including recommendation of Cloud security Alliance.

# <mark style="background: #BABD00;">15 Business Continuity in VDC</mark>

### <mark style="background: #BABD00;">Overview:</mark>

BC planning should include end-to-end protection of both physical and virtual resources at Compute, storage, and network layers

Ensuring BC mainly involves redundancy of components at each layer

BC technology for data protection includes Backup and replication of data (similar to CDC environment)

Besides traditional approaches, VDC environment has additional BC solutions typically implemented at the compute layer.

In a VDC environment, technology solutions that enable the Business Continuity (BC) process need to protect both physical and virtualised resources. This protection should include resources at all the layers including compute, storage, and network. Ensuring BC in a VDC environment involves consistent copies of data and redundant infrastructure components.  

BC solutions for physical network and storage are the same as those for the Classic Data Centre (CDC) environment. This module focuses on the BC solutions for virtual resources built upon compute infrastructure including VMs and their data.

Whole point is to provide robustness no matter what disaster occurs.

<mark style="background: #BABD00;">Advantages of Compute Virtualisation in BC:</mark>
- Hardware independence
- Cross platform compatibility
- Mutual isolation. Different BC policies may be applied to different VMs, even if they are running on the same physical server
- Encapsulation of complete computing environment
- Relatively robust BC processes. Comparatively easier to maintain VM copies in diverse geographic locations
- Higher data availability

Virtualisation considerably simplifies the implementation of a BC solution in a VDC environment. 

<mark style="background: #BABD00;">VMs have inherent properties that facilitate the planning and implementation of a BC strategy:</mark>  
- VMs are compatible with standard x86 architectures and run independent of the underlying x86 hardware configurations. Therefore, BC solutions for VMs need not consider the details of the x86 hardware available at the failover site. In this module, the term compute hardware term is used to represent x86 hardware.  
- VMs are isolated from each other, as if physically separated, even if they run on a single physical server. This isolation prevents failure of one VM from spreading over to other VMs. Different DR policies may be applied to different VMs, even if they are running on the same physical server.  
- VMs encapsulate a complete computing environment. Therefore, they can be moved and restarted easily, compared to recovery of physical servers in a CDC.  

It is also comparatively easier to maintain VM copies in diverse geographic locations, which makes the BC process robust. Similarly, data maintained within a VDC has higher availability.  

Restoring of data after an outage in a VDC is faster and more reliable, compared to CDC.

### <mark style="background: #BABD00;">Single point of failure in a VDC:</mark>

Most important thing is to eliminate all single points of failure.

<mark style="background: #BABD00;">SPOF in Compute Infrastructure:</mark>
- Physical server and hypervisor
- VM and guest OS

<mark style="background: #BABD00;">SPOF in Storage Infrastructure:</mark>
- Storage Array and its components
- Virtual disks

<mark style="background: #BABD00;">SPOF in Network Infrastructure:</mark>
- Network Components
- Virtual network

<mark style="background: #BABD00;">Site:</mark>

To plan for an effective BC solution in a VDC, administrators need to identify potential single point of failure (SPOF). In a VDC, the SPOF includes the following:  

<mark style="background: #BABD00;">SPOF in Compute Infrastructure:</mark>  
- <mark style="background: #BABD00;">Physical Server:</mark> Failure of a physical server would result in the failure of complete virtualised infrastructure running on it. Similarly, failure of a hypervisor can cause all the running VMs and virtual network, which are hosted on it, to halt.  
- <mark style="background: #BABD00;">VM:</mark> Failure of a VM might result in the failure of the critical applications running on it. If there are (distributed) applications running across multiple VMs (for example an electronic banking application), failure of a VM might cause disruptions in the execution of distributed or dependent applications on other VMs. Similarly, the failure of a Guest OS might cause critical applications to stop executing, which would consequently cause disruptions in the client services.  

<mark style="background: #BABD00;">SPOF in Storage Infrastructure:</mark> 
- Failure of a storage array and its components might cause disruptions in the operations of hypervisor, VMs, and applications accessing data from that array.  
- Apart from physical storage, virtual disks are also subject to potential failure. However failures in virtual disks are often due to errors in VMFS, which would be either due to incorrect operation of an hypervisor or a security attack on the file system itself. Failure in VMFS or virtual disk would impact all the applications in the associated VMs.  

<mark style="background: #BABD00;">SPOF in Network Infrastructure:</mark> 
- Based upon the underlying network infrastructure – SAN, NAS, or converged network type (for example, FCoE, IP SAN, etc.) – the supporting components (NICs, communication paths, interconnect device, etc.) might fail and thus disrupt communication between the devices. Apart from physical network component, virtual network is also subject to potential failures. These failures in a virtual network could be due to incorrect design, the configuration of the applications realising these virtual components, or due to security attacks on these applications.  
- Failure in a virtual network component results in the disruption of communication between the VMs using that component for their communication.  

<mark style="background: #BABD00;">Site:</mark> 
- Failure of a VDC site due to a disaster could have significant impact on business operations and thus need special consideration in terms of detailed disaster recovery planning and testing.

### <mark style="background: #BABD00;">Eliminating Single Point of Failure:</mark>

![](https://i.imgur.com/CpWNb8a.png)

To mitigate SPOFs identified before, VDC components are often designed with redundancy so that the system fails only if all the components, including the redundant components, fail simultaneously. Such a failure is very unlikely to happen except during catastrophic disasters.  

Redundancy ensures that the failure of a single component does not affect the availability of the corresponding operations.  

Because of the large number of components involved in the overall operation of a VDC and their underlying complexity and interactions with each other, a careful analysis need to be performed to eliminate every SPOF. In the diagram, critical enhancements in the infrastructure of a VDC to mitigate SPOF is illustrated. 

<mark style="background: #BABD00;">Note that many of the employed mechanisms are similar to a CDC environment:</mark>  
- Configuration of multiple HBAs to mitigate single HBA failure.  
- Configuration of multiple fabrics to account for a switch failure.  
- Configuration of multiple storage array ports to enhance the storage array’s accessibility.  
- RAID configuration to ensure continuous operation in the event of disk failure.  
- Implementation of a storage array at a remote site to replicate data for mitigating the effect of local site failure.  
- Configuration of multiple copies of virtual disks and VM configuration files.  
- Implementation of server clustering.  
- A fault-tolerance mechanism whereby two VMs in a cluster access the same set of storage volumes. If one of the VMs fails, the other takes up the complete workload.

### <mark style="background: #BABD00;">Protecting Compute: Clustering:</mark>

![](https://i.imgur.com/eU8bROe.png)

<mark style="background: #BABD00;">Clustered Servers:</mark>
- Groups of physical servers are combined and managed as an aggregated compute resource pool
- Provides protection from server and hypervisor failures

One of the important techniques to protect compute infrastructure, for providing high availability of VMs and their data in a VDC environment, is clustering.  

<mark style="background: #BABD00;">Clustered Servers:</mark> Virtual Infrastructure provides the technology to combine groups of physical servers and manage them as an aggregated compute resource pool. These resource pools are an ideal way to abstract the underlying physical servers and present only the logical capacity to the user. 

Additionally, clustered servers provide an effective way to ensure compute resource availability in the event of a physical server or hypervisor failure. For example, as depicted in the diagram on this slide, if a server fails, all the VMs running on it are failed over (moved) to other servers, which are operational (active) at that time.  

Clustered servers use a clustered file system, such as VMFS (Virtual Machine File System), to enable failover.  

VMFS provides multiple VMs with shared access to a consolidated pool of clustered storage. A VM sees the (virtual) disks in a VMFS as local targets, where as are actually just files on the VMFS volume. 

Additionally, a VMFS encapsulates the entire VM state in a single directory, making the tasks of backup, replication, and migration of VMs easy. VMFS is implemented over CS and allows each hypervisor in the cluster to store its VM files in a specific subdirectory on the VMFS. When a VM is operating, VMFS locks those files so that other hypervisors cannot update them. VMFS, thus ensures that a VM cannot be opened by more than one hypervisor at the same time. VMFS also provides each VM a separate isolated directory structure for storing its files so that files belonging to one VM cannot be accessed by other VMs.

### <mark style="background: #BABD00;">Proctecting Compute: VM Fault Tolerance:</mark>

Uses a secondary VM running on another physical machine as a live copy of the primary VM

<mark style="background: #BABD00;">The two VMS remain in synchronisation:</mark>
- Event logs of the primary are transmitted to the secondary
- Received event logs are replayed by the secondary

![](https://i.imgur.com/YztHP1J.png)

The <mark style="background: #BABD00;">VM Fault Tolerance (VMFT)</mark> technique ensures that in the event of a VM failure, there is no disruption in business operations. The VMFT technique ensures that individual VMs are functioning well and are responding to failures without interruption in service. VMFT creates hidden duplicate copies of each VM so that when it detects that a VM has failed due to hardware failure, the duplicate VM can be used for failover.  

VMFT creates a live instance of the primary VM that runs on another physical machine. The two VMs are kept in synchronisation with each other. The logs of the event executions by the primary VM are transmitted over a high speed network to the secondary VM. 

Secondary VM replays them to bring its own state same as of the primary VM. The hypervisor running on the primary server captures the sequence of events for the primary VM, including instructions from the virtual I/O devices, virtual NICs, user inputs, etc. And transfers them to the secondary server. 

The hypervisor running on the secondary server receives these event sequences and sends them to the secondary VM for execution. The primary and the secondary VMs share the same virtual disk using VMFS, but all output (for example, write) operations are performed only by the primary VM. 

A special locking mechanism ensures that the secondary VM does not perform write operations on the shared virtual disks. Any other output instructions from the secondary VM are also not allowed. 

The hypervisor posts all events to the secondary VM at the same execution point as they occurred on the primary VM. This way, the two VMs play exactly the same set of events and their states are synchronised with each other.

### <mark style="background: #BABD00;">Protecting Storage:</mark>

<mark style="background: #BABD00;">RAID:</mark> Provides data protection against drive failures

<mark style="background: #BABD00;">Hot spare:</mark> 
- Is a standby disk drive in a RAID array
- Temporarily replaces a failed disk drive without disrupting the compute access

<mark style="background: #BABD00;">Redundant components:</mark>
- Array controllers
- Ports in a storage array
- Storage arrays

<mark style="background: #BABD00;">The key techniques for protecting storage in a VDC are similar to the ones used in CDC, including:</mark>  
- <mark style="background: #BABD00;">RAID:</mark> As explained earlier, RAID is an enabling technology that leverages multiple drives as part of a set to provide data protection against drive failures. For example, RAID uses mirroring and parity techniques to rebuild the data after a disk drive fails.  
- <mark style="background: #BABD00;">Hot spare:</mark> A hot spare refers to a spare disk drive in a RAID array that temporarily replaces a failed disk drive of a RAID set. A hot spare takes the identity of the failed disk drive in the array. When the failed disk drive is replaced with a new disk drive, either the hot spare replaces the new disk drive permanently, or the data from the hot spare is copied to it. The hot spare returns to its idle state and is used to replace the next failed drive. Multiple hot spares can be used to provide higher data availability.  

<mark style="background: #BABD00;">In addition to RAID architecture and hot spares, high availability design for storage infrastructure is achieved by using: </mark> 
- Redundant array controllers to address primary array controller failures  
- Redundant ports in a storage array if one of the currently active port fails  
- Redundant storage array when the whole array goes down

### <mark style="background: #BABD00;">Protect Network - Protecting physical network by using redundancy:</mark>

- Interconnect devices with redundant hot swappable components
- Redundant links and multipathing
- Redundant NICs and NIC teaming

### <mark style="background: #BABD00;">Protecting virtual network: Failure in a virtual network on a hypervisor may be the result of:</mark>

- Software error or security attack
- Physical server failures

Virtual network failure is not common

<mark style="background: #BABD00;">The following are the techniques to protect external physical network:</mark>  
- <mark style="background: #BABD00;">Interconnect devices with redundant hot swappable components:</mark> Allows the user to add or remove components while the interconnect device is operational.  
- <mark style="background: #BABD00;">Redundant links and multipathing:</mark> A technique to enable multiple paths for accessing the same storage device for I/O operations so that in case of a failure of one path, dynamic failover to an alternate path is possible.  
- <mark style="background: #BABD00;">NIC teaming:</mark> Grouping of two or more physical NICs into a single logical device.  

Apart from the protection of external physical network, another important aspect is to protect the virtual network (running on a single server or hypervisor) from failure. A virtual network failure may be caused either by an incorrect operation of the software components (for example, virtual NIC, virtual Switch) or because of the failures in the compute infrastructure, for example, physical server going down, or hypervisor, or VM crashes. 

In general, failures due to software errors or security attacks require software patches from hypervisor vendors. The second reason is more often a cause for the failure in a virtual network. 

Therefore, the methods to protect compute infrastructure, as discussed earlier, equally apply for protecting such virtual network as well.  

The discussion in this lesson will focus on protecting physical network infrastructure using the techniques mentioned above.

### <mark style="background: #BABD00;">Protecting Network: NIC Teaming:</mark>

Enables failover in case of physical NIC failures/link outages. Supports the IEEE 802.1AX-2008 link aggregation standard

<mark style="background: #BABD00;">VMS unaware of the underlying physical NICs:</mark>
- Packets sent to the logical NIC team are dispatched to one of the physical NICs
- Packets arriving at any of the physical NICs are automatically directed to the appropriate virtual NIC

![](https://i.imgur.com/GzGMp0Z.png)

NIC teaming allows grouping of two or more physical NICs - which may be of different types—into a single logical device called the NIC team. After an NIC team is configured, the VM will not be aware of the underlying physical NICs. 

Packets sent to the NIC team are dispatched to one of the physical NICs in the group. Packets arriving at any of the physical NICs are automatically directed to the NIC team, which consequently redirects them to the designated virtual NIC.  

Apart from load balancing, which was discussed earlier, NIC teaming enables fault tolerance such that if one of the underlying physical NICs fails or its cable is unplugged, the traffic is redirected to another physical NIC in the team. 

Thus, NIC teaming eliminates the SPOF associated with a single physical NIC. Such failover remains totally transparent to the VMs and applications may experience performance degradation during this process.  

In a VDC environment, with the hypervisor’s support for NIC teaming, a guest OS or a VM need not install separate drivers for NICs or configure NIC teaming. NIC teaming implementations in most of the hypervisors support the IEEE 802.1AX-2008 link aggregation standard.

### <mark style="background: #BABD00;">Protection from Site Failure:</mark>

In case of a regional disaster, the whole VDC site requires recovery

<mark style="background: #BABD00;">Automatic site failover capability is highly desirable:</mark>
- Manual steps are often error prone
- Reduces RTO (Recovery Time Objective)

"Bare-metal" (Type l) hypervisor running directly on the physical compute is the preferred choice of configuration

Offers greater levels of performance, reliability, and security during site failover

<mark style="background: #BABD00;">Site failover depends upon:</mark>
- VM migration capability, 
- reliable network infrastructure,
- data backup
- replication functionality

In case of a regional disaster, the whole VDC site requires recovery. To ensure error-free execution of BC solutions during a disaster, a non disruptive testing of <mark style="background: #BABD00;">Disaster Recovery (DR)</mark> plan is often required to be carried out beforehand.  

To ensure a robust and consistent failover in case of a site failure or during testing, automatic site failover capabilities are highly desirable. This is because manual steps are often error prone. RTO <mark style="background: #BABD00;">(Recovery Time Objective)</mark> with automated failover is significantly less compared to the manual process. However, the DR product that automates setup, failover, and testing of DR plans must be compatible with the guest OS.  

A hypervisor provides robust, reliable, and secure virtualisation platform that isolates applications and OSs from their underlying hardware. This considerably reduces the complexity of implementing and testing DR strategies. 

Among the different types of hypervisors for BC, the “bare-metal” (Type 1) hypervisor provides a robust DR. During the DR process, the bare-metal approach offers greater levels of performance, reliability, and security; and is better equipped to leverage the power of x86 server architectures found in the datacentres.  

A VDC site failover process also depends upon other capabilities, including VM replication and migration capabilities, reliable network infrastructure between primary (production) site and the secondary (recovery or DR) site, and data backup capabilities

### <mark style="background: #BABD00;">Backup in a VDC: An overview:</mark>

<mark style="background: #BABD00;">VM backup includes:</mark>
- Virtual disks containing system and application data
- Configuration data including network and power state

<mark style="background: #BABD00;">Backup options:</mark>
- File based
- Image based

<mark style="background: #BABD00;">Backup optimisation:</mark>
- Deduplication

<mark style="background: #BABD00;">De-duplication</mark> is when a backup software identifies duplicate files and stores only one copy of it in order to minimise storage use.

A backup operation in a VDC environment often requires backing up the VM state. The VM state includes the state of its virtual disks, memory (i.e. RAM), network configuration, as well as the power state (on, off, or suspended). A virtual disk includes all the information typically backed up (OS, applications, and data). As with physical machines, a VM backup needs to be periodically updated with respect to its source, in order to recover from human or technical errors.  

A VM backup may be performed either as a “set of files” retaining the directory structure or as a complete image. File-level backup provides a way to access individual files, whereas image level backup does not. 

Another important difference between file based and image based backup is that an image based backup is independent of the guest OS running on the VM, whereas file based backup may have guest OS dependency, owing to file system structure. In the case of an image based backup, recovery of individual files requires additional operations to be performed.  

Owing to the increased capacity requirements in a VDC environment, backup optimisation methods are necessary. 

<mark style="background: #BABD00;">Deduplication</mark>, which aims to reduce duplication of backup data, is one of the important techniques towards achieving optimum backup.

### <mark style="background: #BABD00;">Backup in a VDC:</mark>

<mark style="background: #BABD00;">Compute based - Backup VM as a physical server:</mark>
- Requires installing a backup agent on a VM
- Can only backup virtual disk data

<mark style="background: #BABD00;">Backup VM files:</mark>
- Requires installing backup agent on hypervisor
- Cannot backup LUNS directly attached to a VM

<mark style="background: #BABD00;">Array based:</mark> Uses snapshot and cloning techniques

![](https://i.imgur.com/CyMzrRm.png)

Traditional approaches for backup in a VDC environment use the same technologies as are used in a CDC, with minor modifications. These approaches often treat a VM as a set of files while creating its backup. 

<mark style="background: #BABD00;">The approaches are as following:</mark>  
- <mark style="background: #BABD00;">First approach:</mark> A VM is treated as if it were a physical server. A backup agent is installed on the VM that streams the VM data to the backup server. Management of the backup operation is similar to that of CDC, and hence, creating application consistent backups is easy. It is also possible to restore specific files to the guest OS. However, this solution requires the management of agents on all VMs. Note that the solution does not capture the VM files (i.e., Virtual BIOS file, VM swap file, Virtual disk file, Log file, and Configuration file). So, in the event of a restore, a user should manually recreate the VM and then restore data into it.  
- <mark style="background: #BABD00;">Second approach:</mark> Since a VM’s virtual disks are nothing but a collection of files, it is possible to simply back them up by performing a file system backup from a hypervisor.  This is a relatively simple method because it requires only an agent on the hypervisor, and that backs up all the VM files. However, LUNs assigned directly to a VM (using RDM) cannot be backed up using this approach.  
- <mark style="background: #BABD00;">Third approach:</mark> It uses array based technologies to backup a VM and utilises the storage subsystem for backup operations. These technologies often use snapshot and cloning techniques to capture and backup a VM. Snapshot and cloning of a VM will be discussed in the next lesson.

### <mark style="background: #BABD00;">Backup Considerations in a VDC:</mark>

<mark style="background: #BABD00;">Reduced computing resources:</mark> Existence Of multiple VMS running on the same physical machine leaves fewer resources available for backup process

<mark style="background: #BABD00;">Complex VM configurations:</mark>
- A backup agent running on VM has no access to VM configuration files
- Not possible for a backup agent running on hypervisor level to access storage directly attached to a VM using RDM

In a VDC environment, a single physical machine can run multiple VMs, that increases server utilisation. This results in reduced compute resources available for backup and recovery tasks.  

Apart from the increased capacity requirements and reduced computing resources, backing up a VM is more complex than backing up a physical machine. 

With a physical machine, the OS manages all the files on the machine. In a virtual environment, the guest OS is encapsulated in a VM that is managed by the hypervisor. 

Because of this architecture, there are files related to a VM; however, the VM does not have any direct access to these files; for example, the VM configuration files. 

In the case of RDM <mark style="background: #BABD00;">(Raw Device Mapping)</mark>, where storage is directly attached to a VM, an application running on the hypervisor level will have difficulty while accessing that LUN.  

These factors render backup processing more challenging in a VDC as compared to CDC (Classic Data Centre).

### <mark style="background: #BABD00;">Restoring a VM:</mark>

Restore VM to a required state using the backup Selection of the restore point depends upon RPObjective

<mark style="background: #BABD00;">Steps for restore process:</mark>
- Selection of VM and virtual disks to restore from backup
- Selection Of the destination
- Configuration settings

Restoring a VM may take significantly fewer steps, compared to recovering a physical machine.

![](https://i.imgur.com/mu3dvbL.png)

A restore process returns a VM to a selected previous state using the backup copies.  

Selection of the restore point actually depends upon the choice of the RPO.  

<mark style="background: #BABD00;">The key steps involved in the restore process include:</mark>  
1. Selection of the VM and virtual disks to be restored from the backup.  
2. Selection of the destination location for the restoration: In case of an actual VM failure, the original physical machine itself is selected as a destination, whereas for restore rehearsal purposes, some alternate physical machine is selected.  
3. Configuration settings: This includes deciding VM configuration settings either by using the existing backup or by applying new settings.  

Restoring a VM may take significantly fewer steps, compared to the recovery of physical machines. Therefore, recovery time requirements for a VM and consequently for the whole VDC are relatively shorter, compared to the CDC environment.

### <mark style="background: #BABD00;">VM Replication in VDC:</mark>

VM replication is a critical requirement for successful BC

VM replication is performed at the hypervisor level Relies upon replication software to propagate changes made to a VM's virtual disk

<mark style="background: #BABD00;">To ensure data integrity, quiescing of VM is necessary before replication process starts:</mark>
- Quiescing pauses currently running applications within a VM and forcibly flushes all data in the memory to the disk
- To achieve application-level consistency, is performed at the application level
- Applications complete any pending transactions and write the pending data to the disk

<mark style="background: #BABD00;">VM replication</mark> is a critical requirement for successful BC and DR processes in a VDC. This is because, in a VDC environment, to restart operations, a user needs to primarily restart VMs on the secondary (backup) site. VM replication makes this possible by making the copies of these VMs available at the backup site. VM replication is performed at the hypervisor level and relies on replication software that can copy all the changes made to a VM disk to another server. VM replication requires a secondary site which is up and a network connectivity linking these sites.  

A virtual disk snapshot taken at the hypervisor level temporarily redirects incoming writes to a separate delta file. The delta file maintains these I/Os to be written to the virtual disk after the snapshot is taken. The virtual disk is then mounted by the replication software and any updates since the last replication cycle are copied to another identical virtual disk on a VM at the secondary site.  

To ensure data integrity, quiescing of VM is necessary before the replication process starts. 

<mark style="background: #BABD00;">Quiescing</mark> pauses currently running applications within a VM and forcibly flushes all data in the memory to the disk. To ensure application-level consistency, applications (for example, Microsoft Exchange or SQL Server) are instructed to complete any pending transactions and write the pending data to the disk.

### <mark style="background: #BABD00;">VM Replication Methods:</mark>

<mark style="background: #BABD00;">Compute based replication:</mark>
- Enables replicating VMS between dissimilar storage; for example, from a local disk drive to a storage array in a different location
- Creates VM snapshot, or VM Template.

There are two main methods to replicate VMs. The first approach uses compute based replication. In this method, replication happens between similar/dissimilar storage devices.  

For example, using compute based replication, a VM is replicated from a local disk drive to a storage array in a different location. Compute based replication creates either a VM snapshot, or a VM clone, or a VM template – these will be discussed next.  

Another method is to use a storage array to replicate the VM either to an array at the primary site itself or to a remote array (for example, iSCSI, or Fibre channel, or NAS storage array) at the secondary site. This method is similar to the traditional array based replication method used in a CDC. It works by copying LUNs of the source VM to the target array. Replication to a remote array may be either synchronous or asynchronous.

### <mark style="background: #BABD00;">VM Snapshot:</mark>

Preserves the state and data of a VM at a specific point-in-time State includes VM configuration files as well as its power state (on, Off, suspended)

Data includes all the files that makeup the VM including memory, and other devices, such as virtual NIC

A log file captures the changes to the virtual disk after snapshot is taken

![](https://i.imgur.com/MAyLCcF.png)

A snapshot preserves both the state and data of a VM at a specific point in time. State includes VM files such as BIOS, network configuration, and its power state (powered-on, powered-off, or suspended). 

Data includes all the files that makeup the VM, including virtual disks, memory, and other devices. In this method, instead of making a copy of the entire virtual disk of the VM, which may be very large in size, a snapshot is created. A snapshot includes a separate log file which captures the changes to the virtual disk of the VM since the snapshot was taken.  

Referring to the diagram on this slide, the first snapshot of the VM is taken at time-point  13:00 (on date dd/mm/yyyy) and the second snapshot is taken after two hours at time-point 15:00. These snapshots are saved with unique names and details of the points-in-time, when they are created.

### <mark style="background: #BABD00;">VM Template:</mark>

A master copy to create and provision new VMs

A reusable image created from a VM Includes virtual hardware components, an installed guest OS, and software applications

<mark style="background: #BABD00;">Created in two ways:</mark>
- Convert a powered-off VM into a template
- Clone a VM into a template

<mark style="background: #BABD00;">Increase efficiency, consistency, and standardisation:</mark>
- Repetitive installation and configuration tasks can be avoided
- Deploying VMS from VM templates helps to enforce standards

A VM template is a reusable image created from a VM. The VM template works like a master copy of a VM to be used for creating and provisioning new copies of the VM. The template typically includes virtual hardware components, an installed guest OS (with any applicable patches), and software applications.  

Templates can be created in two ways, either by converting a powered-off VM into a template or by cloning a VM to a template. The advantage of converting a VM to a template is that the conversion is instantaneous. However, the template will not be used immediately.  

Cloning a VM to a template leaves the original VM intact, but will require waiting for the entire capacity of the VM to be duplicated into the template’s files.  

A template differs from a clone because new VMs are deployed from templates. From a clone, only additional cloning can be done to create new VMs. However the new VMs which are created out of a Clone will reflect the changed state of the clone as compared to a VM template which preserves the original state.  

<mark style="background: #BABD00;">Key advantages of the VM template include the following:</mark>
- VM templates increase efficiency; for example, with templates, many repetitive installation and configuration tasks can be avoided.  
- VM templates are also used to enforce consistency and standards. 
- Deploying from templates helps to enforce standards such as including antivirus and management software in any machine connected to the network.

### <mark style="background: #BABD00;">VM Migration:</mark>

Moving a VM from one hypervisor to another hypervisor

For example: hypervisor failure or scheduled hypervisor or storage array maintenance

<mark style="background: #BABD00;">Migration process:</mark>
- Involves movement of entire active state of a VM
- In case of server-to-server migration, virtual disks are not moved within clustered servers
- VM in the source hypervisor needs to be deleted after migration is complete

There are many situations where moving a VM from one hypervisor to another is necessary.  

The primary purpose is to achieve BC in case of hypervisor failure. Another situation might involve load balancing when one hypervisor is running many VMs but another hypervisor is relatively less occupied. Yet another reason might involve facilitating scheduled hypervisor or storage array maintenance.  

The process of moving VMs from one (source) hypervisor to another (target) is known as VM Migration. 

<mark style="background: #BABD00;">There are primarily two different types of VM migrations:</mark>  
- <mark style="background: #BABD00;">Server-to-server migration:</mark> This type of VM migration involves moving a VM from one hypervisor to another using a client (migration agent software) running on these hypervisors. The receiving hypervisor may be remotely located in a different data centre.  
- <mark style="background: #BABD00;">Array-to-array migration:</mark> This type of VM migration involves moving VMs or virtual disks across multiple physical servers using storage array based methods. 

VM migration involves moving the entire active state of a VM from the source hypervisor to the target. The state information includes memory contents and all other information which identifies the VM. VM identification information includes data, which maps the VM hardware elements such as BIOS, Devices, CPU, and MAC address for Ethernet cards. 

When a VM is migrated to another hypervisor on a clustered server, virtual disks of the VM are not migrated because these can be accessed from another hypervisor as well. However, in situations where a VM needs to be migrated to a hypervisor on a remote server, virtual disks are also moved. 

In case of array-to-array migration, virtual disks are always moved from the source array to the target array. After migration, VM in the source hypervisor is deleted.  

Virtual disks are also deleted if they were actually moved. For example, in the case of server-to-server remote migration and array-to-array based migration, virtual disks are deleted after their copies are saved at the target.

### <mark style="background: #BABD00;">VM Migration: Server-to-Server:</mark>

- <mark style="background: #BABD00;">Hot-On:</mark> Migrate a VM that is powered on. VM needs to be quiesced before migration.
- <mark style="background: #BABD00;">Cold:</mark> Migrate a VM that is powered off
- <mark style="background: #BABD00;">Hot-Suspended:</mark> Migrate a VM that is suspended
- <mark style="background: #BABD00;">Concurrent:</mark> Migrate multiple VMS simultaneously

<mark style="background: #BABD00;">There are primarily four major modes of VM migration between servers:</mark>  
- <mark style="background: #BABD00;">Hot-On migration:</mark> VM remains in a powered-on state (currently running). Shared storage and CPU compatibility might be necessary between the source and destination servers. VM also needs to be quiesced during migration so that the state of the VM after migration remains consistent. After migration, client accesses are directed to the VM on the target hypervisor. Hot on migration is useful in scenarios where a server or hypervisor is overloaded or requires maintenance and/or repair soon because it might be underperforming.  
- <mark style="background: #BABD00;">Cold migration:</mark> VM is in a power off state. Cold migration is typically used when a VM needs to be moved to another remote location or VDC.  
- <mark style="background: #BABD00;">Hot-Suspended migration:</mark> VM is in a suspended state. In a suspended state, all virtual machine activities are paused until the resume command is issued. This kind of migration could be useful when a VM needs to be migrated from a failing server to another operational server.  
- <mark style="background: #BABD00;">Concurrent migration:</mark> Multiple VMs are migrated simultaneously to one or more hypervisors. The maximum number of concurrent sessions is generally dependent upon the available network bandwidth. Concurrent migration can be performed when VM is on a power on/off/suspended state. Concurrent migrations are useful for continuously optimising VM placement across the entire IT environment.

# <mark style="background: #BABD00;">16 The Twelve-Factor App:</mark>

### <mark style="background: #BABD00;">TFA - Why should we care?</mark>

<mark style="background: #BABD00;">The Twelve-Factor App provides a methodology of established best practices that:</mark>  
- provides invaluable guidance that should inform and influence every decision when designing the architecture of a modern IT Environment and Infrastructure.  
- facilitates a highly scalable, highly available, performant, secure, resilient, robust, reliable, recoverable, responsive, flexible, transparent, interoperable, modular and composable IT Environment.

### <mark style="background: #BABD00;">TFA - What is it?</mark>

In the Cloud Era, software is delivered as a service software-as-a-service (SaaS).  

<mark style="background: #BABD00;">The Twelve-Factor App is a methodology (developed at Heroku) for building SaaS such that:</mark>  
- Use <mark style="background: #BABD00;">declarative</mark> formats for setup automation.  
- Have a <mark style="background: #BABD00;">clean contract</mark> with the underlying operating system (Portability).  
- Are suitable for <mark style="background: #BABD00;">deployment</mark> on modern <mark style="background: #BABD00;">cloud platforms</mark>.  
- <mark style="background: #BABD00;">Minimise divergence</mark> between development and production.  
- Designed for Scalability.

<mark style="background: #BABD00;">Imperative Language:</mark> evaluated left to right and top to bottom, specifies the how. e.g. C.

<mark style="background: #BABD00;">Object Oriented:</mark> encapsulation e.g. Java

<mark style="background: #BABD00;">Functional:</mark> Global values do not exist. There are no side effects, useful for concurrent programs. e.g. Go, Haskell.

<mark style="background: #BABD00;">Declarative:</mark> You tell the language what you want, not how to do it. e.g. SQL, Prolog

### <mark style="background: #BABD00;">Background:</mark>

TFA is a distillation of best practices and experiences of many contributors involved in the development, deployment and scaling of 100’s of apps.  

<mark style="background: #BABD00;">TFA seeks to integrate:</mark>  
- Ideal practices for App development.  
- The dynamic of collaboration between developers.  
- Avoid the cost of software deterioration/erosion.

TFA can be applied to any app written in any language.  

<mark style="background: #BABD00;">TFA can use any combination of services:</mark>
- Database.  
- Queue.  
- Memory Cache.

### <mark style="background: #BABD00;">Twelve Factors:</mark>

1. <mark style="background: #BABD00;">Codebase:</mark> One codebase tracked in revision control, many deploys.  
2. <mark style="background: #BABD00;">Dependencies:</mark> Explicitly declare and isolate dependencies.  
3. <mark style="background: #BABD00;">Config:</mark> Store config in the environment.  
4. <mark style="background: #BABD00;">Backing Services:</mark> Treat backing services as attached resources.  
5. <mark style="background: #BABD00;">Build, release, run:</mark> Strictly separate build and run stages.  
6. <mark style="background: #BABD00;">Processes:</mark> Execute the app as one or more stateless processes
7. <mark style="background: #BABD00;">Port Binding:</mark> Export services via port binding.  
8. <mark style="background: #BABD00;">Concurrency:</mark> Scale out via the process model.  
9. <mark style="background: #BABD00;">Disposability:</mark> Maximise robustness with fast start-up and graceful shutdown.  
10. <mark style="background: #BABD00;">Dev/prod parity:</mark> Keep development, staging, and production as similar as possible.  
11. <mark style="background: #BABD00;">Logs:</mark> Treat logs as event streams.  
12. <mark style="background: #BABD00;">Admin processes:</mark> Run admin/management tasks as one-off processes.

### <mark style="background: #BABD00;">Codebase:</mark>

<mark style="background: #BABD00;">One codebase tracked in revision control, many deploys</mark>  
- Put all your code in a source control system, such as Git, Mercurial or Subversion.  
- There is always a one-to-one correlation between the codebase and the app.  
- If there are multiple codebases, it’s not an app – it’s a distributed system.  
- Each component in a distributed system is an app, and each can individually comply with twelve-factor.

All shared code should be imported in as libraries.

![](https://i.imgur.com/1jeumRk.png)

<mark style="background: #BABD00;">Dependency Manager:</mark>
- Dependency management is a technique for declaring, resolving and using dependencies required by the project in an automated fashion.  
- Question: Is a dependency manager the same as a package manager?
- No. A package manager operates at the system level and most often deals with binaries. Its role is to install libraries, tools, and other applications. It affects the entire system and not just one project.
- A dependency manager operates at source code level. Its role is to setup the right dependencies for a particular application. It is used by developers, not users or system admins. Thus, a dependency manager is project specific.

Developers use dependency managers, SysAdmins use package managers.

### <mark style="background: #BABD00;">Dependencies:</mark>

<mark style="background: #BABD00;">Explicitly declare and isolate dependencies</mark>  

Many programming languages offer a packaging system for distributing support libraries.  

<mark style="background: #BABD00;">For example:</mark>
- Python has pip.  
- Perl has CPAN.  
- Ruby has Rubygems.  
- NodeJS has npm.  
- Rust has cargo, etc.  
- Libraries installed through a packaging system can be installed system-wide (known as “site packages”).  

Libraries also can be scoped into the directory containing the app (known as “vendoring” or “bundling”).

All the environments your code runs in need to have some dependencies, like a database, or an image processing library, or a command-line tool.  

<mark style="background: #BABD00;">Tips:</mark>
- Never let your application assume those things will be in place on a given machine.  
- Ensure they are present by baking those dependencies into your software system.  
- This philosophy extends to your devs or DevSecOps team managing entire machine configurations using management tools like Chef and Puppet.

A twelve-factor app never relies on implicit existence of system-wide packages or libraries.  

It declares all dependencies, completely and exactly, via a dependency declaration manifest.  

Furthermore, it uses a dependency isolation tool during execution to ensure that no implicit dependencies “leak in” from the surrounding system.  

The full and explicit dependency specification is applied uniformly to both production and development.

### <mark style="background: #BABD00;">Config:</mark>

<mark style="background: #BABD00;">Store config in the environment.</mark>  

Configuration is anything that may vary between different environments and deploys. Code is all the stuff that doesn’t. 

<mark style="background: #BABD00;">Examples include:</mark>  
- Resource handles to the database, Memcached, and any other backing services.  
- Credentials to external services such as Amazon S3 or Twitter.  
- Per-deploy values such as the canonical hostname for the deploy.

<mark style="background: #BABD00;">Apps sometimes store config as constants in the code:</mark>
- This is a violation of twelve-factor, which requires strict  separation of config from code. Config varies substantially across deploys, code does not.  
- A litmus test for whether an app has all config correctly factored out of the code is whether the codebase could be made open source at any moment, without compromising any credentials.  
- Note that this definition of “config” does not include internal application config (does not vary between deploys).

The twelve-factor app stores config in environment variables.  

Environment variables are easy to change between deploys without changing any code.  

Unlike config files, there is little chance of them being checked into the code repo accidentally.  

All configuration data should be stored in a separate place from the code, and read in by the code at runtime.  

So, when you deploy code to an environment, you copy the correct configuration files into the codebase at that time.

### <mark style="background: #BABD00;">Backing Services:</mark>

<mark style="background: #BABD00;">Treat backing services as attached resources.</mark>  

A backing service is any service the app consumes over the network as part of its normal operation. 

<mark style="background: #BABD00;">Examples include:</mark>  
- datastores (such as MySQL or CouchDB).  
- messaging/queueing systems (such as RabbitMQ or Beanstalkd).  
- SMTP services for outbound email (such as Postfix).  
- caching systems (such as Memcached). 

The code for a twelve-factor app makes no distinction between local and third party services. Your code shouldn’t know the difference.  

To the app, both are attached resources, accessed via a URL or other locator/credentials stored in the config.  

A deploy of the twelve-factor app should be able to swap out a local MySQL database with one managed by a third party (such as Amazon RDS) without any changes to the app’s code.  

Likewise, a local SMTP server could be swapped with a third-party SMTP service (such as Postmark) without code changes. In both cases, only the resource handle in the config needs to change.

![](https://i.imgur.com/cT33qN9.png)

### <mark style="background: #BABD00;">Build, Release, Run:</mark>

<mark style="background: #BABD00;">Strictly separate build and run stages.</mark> 

The process of turning the code into a bundle of scripts, assets and binaries that run the code is the <mark style="background: #BABD00;">build</mark>.  

The <mark style="background: #BABD00;">release</mark> sends that code to a server in a fresh package together with the nicely-separate config files for that environment.  

Then the code is <mark style="background: #BABD00;">run</mark> so the application is available on those servers.  

The twelve-factor app uses strict separation between the build, release, and run stages.

![](https://i.imgur.com/dyXe35y.png)

The idea here is that the build stage does a lot of heavy lifting, and developers manage it.  

The run stage should be simple and bullet-proof, kept to as few moving parts as possible, since problems that prevent an app from running can cause it to break in the middle of the night when no developers are on hand.  

The build stage can be more complex, since errors are always in the foreground for a developer who is driving the deploy.

### <mark style="background: #BABD00;">Processes:</mark>

<mark style="background: #BABD00;">Execute the app as one or more stateless processes.</mark>  

It’s likely you will have your application running on many servers, because that makes it more fault tolerant, and because you can support more traffic.  

As a rule, you want each of those instances of running code to be stateless.  

In other words, the state of your system is completely defined by your databases and shared storage, and not by each individual running application instance.  

Twelve-factor processes are stateless and share-nothing. Any data that needs to persist must be stored in a stateful backing service, typically a database.

Some web systems rely on “sticky sessions”.  That is, caching user session data in memory of the app’s process and expecting future requests from the same visitor to be routed to the same process.  

Sticky sessions are a violation of twelve-factor and should never be used or relied upon.  

Session state data is a good candidate for a datastore that offers time-expiration, such as Memcached or Redis.

Example: signup workflow, where a user has to enter 3 screens of information to create their profile.  

Wrong approach would be to store each intermediate state in the running code, and direct the user back to the same server until the signup process is complete.  

The right approach is to store intermediate data in a database or persistent key-value store.  

So, if the web server goes down in the middle of the user’s signup, another web server can handle the traffic, and the system is none-the-wiser.

<mark style="background: #BABD00;">Generic benefits of Stateless Apps:</mark>  
- More robust.  
- Easier to manage.  
- Less error prone.  
- Scalable (horizontally).

### <mark style="background: #BABD00;">Software Erosion:</mark>

![](https://i.imgur.com/e3fmAkq.png)

The “bathtub curve” for <mark style="background: #BABD00;">hardware</mark> failure.

![](https://i.imgur.com/TQ1BA7U.png)

Software doesn’t wear out.

### <mark style="background: #BABD00;">The Software Product:</mark>

<mark style="background: #BABD00;">What are some of the attributes of good software?</mark>
- <mark style="background: #BABD00;">Reliability:</mark> Software must be trustworthy.
- <mark style="background: #BABD00;">Usability:</mark> Software must be usable by the users for which it was designed.  
- <mark style="background: #BABD00;">Efficiency:</mark> Software should not make wasteful use of system resources.  
- <mark style="background: #BABD00;">Maintainability:</mark> Software must evolve to meet changing needs.  
- <mark style="background: #BABD00;">Portability:</mark> We should be able to move software from machine to machine as we require.
- <mark style="background: #BABD00;">Others:</mark> Functional suitability, Compatibility, Security (ISO/IEC 25010:2011

<mark style="background: #BABD00;">The cost of change:</mark>
![](https://i.imgur.com/JCoSRyn.png)

### <mark style="background: #BABD00;">Three Ways Software wears out:</mark>

<mark style="background: #BABD00;">1. Bugs</mark>

"Computer" was originally a job, mostly done by women. Seen as a secondary, secretarial role. 

First computer was made in 1942 by the British. "The Colossus".

The origin of the word "Bug" is from when a moth flew into a vacuum tube and had to be removed - "debugging".

Bugfixes are the second most common source of bugs.

<mark style="background: #BABD00;">2. New Feature requests</mark>

Users request more features as time goes on. 

<mark style="background: #BABD00;">3. Environment in which the software runs changes</mark>

SQLite is the most used DB in the world. Switching their build process to TCL

Dr. Richard Hipp created SQLite.

### <mark style="background: #BABD00;">The Twelve Factors:</mark>

1. <mark style="background: #BABD00;">Codebase:</mark> One codebase tracked in revision control, many deploys.  
2. <mark style="background: #BABD00;">Dependencies:</mark> Explicitly declare and isolate dependencies.  
3. <mark style="background: #BABD00;">Config:</mark> Store config in the environment.  
4. <mark style="background: #BABD00;">Backing Services:</mark> Treat backing services as attached resources.  
5. <mark style="background: #BABD00;">Build, release, run:</mark> Strictly separate build and run stages.  
6. <mark style="background: #BABD00;">Processes:</mark> Execute the app as one or more stateless processes.
7. <mark style="background: #BABD00;">Port Binding:</mark> Export services via port binding.  
8. <mark style="background: #BABD00;">Concurrency:</mark> Scale out via the process model.  
9. <mark style="background: #BABD00;">Disposability:</mark> Maximise robustness with fast start-up and graceful shutdown.  
10. <mark style="background: #BABD00;">Dev/prod parity:</mark> Keep development, staging, and production as similar as possible.  
11. <mark style="background: #BABD00;">Logs:</mark> Treat logs as event streams.  
12. <mark style="background: #BABD00;">Admin processes:</mark> Run admin/management tasks as one-off processes.

The role of any project manager is to manage time, resources, money and people in order to deliver a project on time, within budget and meeting the requirements

### <mark style="background: #BABD00;">Load Balancing:</mark>

All inbound traffic to a web role passes through a stateless load balancer, which distributes client requests among the role instances.  

Individual role instances do not have public IP addresses, and are not directly addressable from the Internet. (This is why you can’t ‘Ping’ the IP addresses).  

Web roles are stateless, so that any client request can be routed to any role instance.  

A Status-check event is raised every 15 seconds. This can be used to indicate if the role is ready to receive traffic, or is busy and should be taken out of the load balancer rotation.

![](https://i.imgur.com/1k4ZMNx.png)

### <mark style="background: #BABD00;">Elasticity:</mark>

<mark style="background: #BABD00;">Elasticity – What is it?</mark>  

The degree to which a system is able to adapt to workload changes by provisioning and deprovisioning resources in an automated manner, such that at each point in time the available resources match the current demand as closely as possible.  

<mark style="background: #BABD00;">Elasticity is automated scalability.</mark>  

Scalability provides the ability to increase (or decrease) the amount of resources in scaling up (more powerful instances) or out (additional instances), which is usually done through manual intervention.  

Elasticity does the same but in an automated manner, independent from human interaction.

### <mark style="background: #BABD00;">7. Port Binding:</mark>

<mark style="background: #BABD00;">Export services via port binding.</mark>  

In essence, your application must interface to the outside world using a simple URL.  

Web apps are sometimes executed inside a webserver container.  

For example, PHP apps might run as a module inside Apache HTTPD, or Java apps might run inside Tomcat.  

The twelve-factor app is completely self-contained and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service.

The web app exports HTTP (and any other server software) as a service by binding to a port, and listening to requests coming in on that port.  

This means that one app can become the backing service for another app, by providing the URL to the backing app as a resource handle in the config for the consuming app.  

<mark style="background: #BABD00;">Software Composable Intrastructure ???</mark>

![](https://i.imgur.com/5MmGUgs.png)

### <mark style="background: #BABD00;">8. Concurrency</mark>

<mark style="background: #BABD00;">Scale out via the process model.</mark>  

In the twelve-factor app, processes are a first class citizen.  

Processes in the twelve-factor app take strong cues from the unix process model for running service daemons.  

The unix philosophy states that an app should do one thing, only one thing and do it well.

A daemon is a program that runs in the background.

The developer can architect their app to handle diverse workloads by assigning each type of work to a process type.  

For example, HTTP requests may be handled by a web process, and long-running background tasks handled by a worker process.

![](https://i.imgur.com/6EImxu6.png)

![](https://i.imgur.com/viAPH3q.png)

The idea is that lots of little processes are handling specific needs.  

So you might have dozens of handlers at the ready to process web requests, and another dozen to handle API calls for your enterprise users. And still another half-dozen processing background welcome-emails going to new users.  

By keeping all these small parts working independently, and running them as separate processes, your application will scale better. In particular, you’ll be able to do more stuff concurrently.  

By scaling horizontally (or vertically).

### <mark style="background: #BABD00;">9. Disposability</mark>

<mark style="background: #BABD00;">Maximise robustness with fast start-up and graceful shutdown.</mark>  

The twelve-factor app’s processes are disposable, meaning they can be started or stopped at a moment’s notice.  

This facilitates fast elastic scaling, rapid deployment of code or config changes, and robustness of production deploys.  

Consequently, processes should strive to minimise start-up time.  

Processes shut down gracefully.  

For a web process, a graceful shutdown is achieved by ceasing to listen on the service port (thereby refusing any new requests), allowing any current requests to finish, and then exiting.

Further, your application should be robust against sudden death (crashing) in the case of a failure in the underlying hardware.  

Meaning, if it does crash, it should always be able to start back up cleanly.  

You should never do any mandatory “clean-up” tasks when the app shuts down, because that might cause problems if they failed to run in a crash scenario.  

A recommended approach is use of a robust queueing backend, such as Beanstalkd, that returns jobs to the queue when clients disconnect or time out.

You should never require any manual intervention or manual clean-up tasks unless you have a good and compelling reason to do so.

### <mark style="background: #BABD00;">10. Dev/Prod Parity</mark>

<mark style="background: #BABD00;">Keep development, staging, and production as similar as possible.</mark>
![](https://i.imgur.com/fSfO4mc.png)

<mark style="background: #BABD00;">Historically, there have been substantial gaps between development and production:</mark>  
- <mark style="background: #BABD00;">The time gap:</mark> A developer may work on code that takes days, weeks, or even months to go into production.  
- <mark style="background: #BABD00;">The personnel gap:</mark> developers write code, ops engineers deploy it.  
- <mark style="background: #BABD00;">The tools gap:</mark> Developers may be using a stack like Nginx, SQLite, and OS X, while the production deploy uses Apache, MySQL, and Linux.

The twelve-factor app is designed for continuous deployment by keeping the gap between development and production small.  

<mark style="background: #BABD00;">This involves:</mark>
- <mark style="background: #BABD00;">Make the time gap small:</mark> a developer may write code and have it deployed hours or even just minutes later.  
- <mark style="background: #BABD00;">Make the personnel gap small:</mark> developers who wrote code are closely involved in deploying it and watching its behaviour in production.  
- <mark style="background: #BABD00;">Make the tools gap small:</mark> keep development and production as similar as possible.

![](https://i.imgur.com/9YM79wZ.png)

### <mark style="background: #BABD00;">Continuous Delivery Vs Continuous Deployment:</mark>

Subtle but important different between Continuous Delivery and Continuous Deployment.  

Continuous deployment is the next step of continuous delivery

![](https://i.imgur.com/Jtd1zB8.png)

### <mark style="background: #BABD00;">Logs:</mark>

<mark style="background: #BABD00;">Treat logs as event streams.</mark>  

Logs provide visibility into the behaviour of a running app.  

Logs are the stream of aggregated, time-ordered events collected from the output streams of all running processes and backing services.  

Logs have no fixed beginning or end, but flow continuously as long as the app is operating.  

Logs in their raw form are typically a text format with one event per line (though backtraces from exceptions may span multiple lines).

<mark style="background: #BABD00;">A twelve-factor app never concerns itself with routing or storage of its output stream.</mark>  
- It should not attempt to write to or manage logfiles. Instead, each running process writes its event stream, unbuffered, to stdout.  
- During local development, the developer will view this stream in the foreground of their terminal to observe the app’s behaviour.

<mark style="background: #BABD00;">In staging or production deploys, each process’ stream will be captured by the execution environment:</mark>  
- collated together with all other streams from the app.  
- routed to one or more final destinations for viewing and long-term archival.  

These archival destinations are not visible to or configurable by the app, and instead are completely managed by the execution environment.

### <mark style="background: #BABD00;">12. Admin Processes</mark>

<mark style="background: #BABD00;">Run admin/management tasks as one-off processes.</mark>  

<mark style="background: #BABD00;">Developers will often wish to do one-off administrative or maintenance tasks for the app, such as:</mark>  
- Running database migrations.  
- Running a console (also known as a REPL shell) to run arbitrary code or inspect the app’s models against the live database (e.g.: python, perl, irb for ruby, etc).  
- Running one-time scripts committed into the app’s repo (e.g. php scripts/fix_bad_records.php).

One-off admin processes should be run in an identical environment as the regular long-running processes of the app.  

Admin code must ship with application code to avoid synchronisation issues.  

Twelve-factor strongly favours languages which provide a REPL shell out of the box, and which make it easy to run one-off scripts.  

In a local deploy, developers invoke one-off admin processes by a direct shell command.  

In a production deploy, developers can use ssh or other remote command execution mechanism to run a one-off process.

[Source](https://12factor.net)

# <mark style="background: #BABD00;">17 DevOps Intro:</mark>

<mark style="background: #BABD00;">What is DevOps?</mark>
- Infrastructure As Code 
- Desired State Configuration

### <mark style="background: #BABD00;">Traditional Development and Operations:</mark>

![](https://i.imgur.com/y4sfU1v.png)

![](https://i.imgur.com/0kbQbAj.png)

![](https://i.imgur.com/fe8NI1R.png)

### <mark style="background: #BABD00;">Continuous Integration:</mark>

![](https://i.imgur.com/dGboCXj.png)

![](https://i.imgur.com/xAnMxcl.png)

### <mark style="background: #BABD00;">Testing:</mark>

<mark style="background: #BABD00;">Unit testing:</mark> Comes from mathematics where the unit circle has a circle of 1. A unit test should test one thing and one thing only. If expected behaviour = accepted behaviour, it passes. Can be fully automated as it is completely binary in terms of passing/failing.

<mark style="background: #BABD00;">Integration Testing:</mark> Tests multiple units integrated together. All the way up.

<mark style="background: #BABD00;">System Testing:</mark> Testing the system at every level beyond core functionality. e.g. performance testing, fuzzy testing.

<mark style="background: #BABD00;">UAT:</mark> See how user reacts.

### <mark style="background: #BABD00;">DevOps: the three stage conversation:</mark>

![](https://i.imgur.com/gpwcdiI.png)

- Collaboration of People.
- Convergence of Processes.
- Creation/Exploitation of Tools.

### <mark style="background: #BABD00;">DevOps: from individual stand-alone silos to an integrated automated pipeline.</mark>

<mark style="background: #BABD00;">Integration - People and Processes:</mark>

![](https://i.imgur.com/VR6o5lj.png)

The goal is to create a single, integrated seamless automated pipeline of activities.
### <mark style="background: #BABD00;">The consequences of Inefficiency:</mark>

![](https://i.imgur.com/cnDS0NA.png)

### <mark style="background: #BABD00;">DevOps Benefits:</mark>

- Reduces 'Tribal Knowledge'
- Consistency and Repeatability (Automation).
- Speed and Productivity (deploy faster). 
- Reliability.
- Excellence - codify best practices.
- Communication and Fast/frequent feedback.

### <mark style="background: #BABD00;">What does DevOps look like?</mark>

![](https://i.imgur.com/ugmctd7.png)

### <mark style="background: #BABD00;">Fundamental DevOps Principles:</mark>

![](https://i.imgur.com/ByEEok8.png)

### <mark style="background: #BABD00;">DevOps Best Practices:</mark>

- Infrastructure as Code (IaC)
- Continuous Integration
- Automated Testing
- Continuous Deployment
- Release Management
- App Performance Monitoring
- Load Testing & Auto-Scale
- Fast Feedback Loops
- Availability Monitoring
- Change/Configuration Management
- Feature Flags
- Automated Environment De-Provisioning
- Self Service Environments
- Automated Recovery (Rollback & Roll-Forward)
- Hypothesis Driven Development
- Testing in Production
- Fault Injection
- Usage Monitoring/User Telemetry

### <mark style="background: #BABD00;">Infrastructure as Code (IaC):</mark>

<mark style="background: #BABD00;">Many IT teams still rely on:</mark>
- manual configurations
- custom scripts
- outdated tools to manage infrastructure
- resulting in errors and slow deployments

<mark style="background: #BABD00;">By treating your Infrastructure as software:</mark>
- Code can be managed with the same tools and processes as software
- Such as version control, continuous integration, code reviews, automated testing, etc.
- Thus Infrastructure can be changed more easily, rapidly, safely and reliably.

![](https://i.imgur.com/GEDw7w4.png)

<mark style="background: #BABD00;">Programmable Infrastructure (laC):</mark>
- Writing in a high-level descriptive or declarative language.
- To manage configurations and to automate provisioning of resources and the deployment of infrastructure.
- Involves using tried and tested software development practices (including design patterns).
- To not only provision Infrastructure but all the processes governing the management of said Infrastructure.

Differs from <mark style="background: #BABD00;">infrastructure automation</mark>, which just involves replicating steps multiple times and reproducing them on several servers. It

<mark style="background: #BABD00;">Programmable Infrastructure (IaC):</mark>
- The knowledge of server provisioning, configuration management and deployment is no longer only with the systems admins.
- Developers can easily engage in the activities, because they can easily write infrastructure code in the languages that they are familiar with.

<mark style="background: #BABD00;">A whole host of tools have sprung up to make the whole process easier:</mark>
- Vagrant, ansible, puppet, Chef, Salt, Terraform, Consul, Bcfg2, CFEngine, etc.
- Many of these tools provide RESTFul APIs that leverage to support any desired degree of interoperability.
- Terraform used for creation and provisioning broad infra
- Ansible very good at provsioning SPECIFIC instances. Often used with Terraform.

![](https://i.imgur.com/vGuVViZ.png)

The infrastructure is provisioned, created and managed by specifications in configuration files.

This is declarative - you specify WHAT, not HOW.
### <mark style="background: #BABD00;">Idempotent:</mark>

Comes from maths, a mathematical op is idempotent if and only if you perform an operation one or more times then the result is the exact same as if you performed it only once. e.g. adding by 1 is not idempotent (0+1 =1, 1+1=2) but multiplying by 0 is (1 x 0 = 0, 2 x 0 =0)

<mark style="background: #BABD00;">The dictionary definition:</mark> denoting an element of a set that is unchanged in value when multiplied or otherwise operated on by itself.

Idempotence is simply a word that describes an operation that will have the same effect whether you run it once or 1001 times.

Adding one is not idempotent because the result keeps incrementing, but multiplying by one is idempotent because the answer is the same no matter how many times you multiply it!

In the context of Infrastructure as Code, if a virtualised resource or software component is already installed or configured, an idempotent tool will not try to reinstall or reconfigure the component, even if it is given the command to do so.

You can go from any arbitrary state to any specific desired state.

### <mark style="background: #BABD00;">Advantages:</mark>

Both development and testing become much easier.

The same configuration can be applied to local physical servers or virtualised Cloud based servers.

The ability to use version control on your infrastructure code implies that you can easily track all the changes in your infrastructure environment. Therefore, you have an easier option of rolling back configuration changes to a previous working configuration in case of a problem.

<mark style="background: #BABD00;">Idempotent:</mark> you can go from any arbitrary state to a specific desired state.

### <mark style="background: #BABD00;">Disadvantages:</mark>

Significant planning required upfront before the configuration - such as choosing the right tools.

Bad configurations could get duplicated on all the servers

<mark style="background: #BABD00;">Configuration drift</mark>, in which the server configurations are modified on the machines (for example, through hot-fixes without modifying the original templates), makes configurations on the server and in the template to differ.

This is especially true if strict discipline is not followed.

Recent IaC tools are getting smarter. Some can now detect config drift.

### <mark style="background: #BABD00;">Desired State Configuration:</mark>

Configurations are documents that describe an environment. Environments typically consist of "nodes", which are commonly virtual or physical machines.

The management and maintenance of servers quickly becomes complex without standardisation.

The danger is that we end up with a plethora of scripts in order to manage a server, all more complicated than the other, and this works.

DSC gives us a declarative model for system configuration management. What that really means is that we can specify how we want a workstation or server (a 'node') to be configured and we leave it to the tool to make it happen on those target 'nodes'. We don't have to specify how we want it to happen.

### <mark style="background: #BABD00;">Benefits of DSC:</mark>

To simplify your sysadmin tasks by configuring one or more devices automatically

To be able to configure machines identically with the aim to standardise them.

To ensure, at a given time, that the configuration of a machine always be identical to its initial configuration, so as to avoid drift.

Deployment on demand as a Cloud strategy, or 'en masse', is largely automated and simplified.

### <mark style="background: #BABD00;">Two Types of architecture with DSC:</mark>

<mark style="background: #BABD00;">Push mode:</mark> the configurations are sent ("pushed") manually towards one or more units that we call "node". This action is done by an administrator.

<mark style="background: #BABD00;">Pull mode:</mark> a "pull server" is created and the nodes contact this server at regular intervals so as to obtain their configuration.

### <mark style="background: #BABD00;">DSC Push Mode:</mark>

![](https://i.imgur.com/OBqEvsC.png)

### <mark style="background: #BABD00;">DSC Pull Mode:</mark>

![](https://i.imgur.com/axdcfNS.png)

# <mark style="background: #BABD00;">18 DevOps - Continuous Integration</mark>

### <mark style="background: #BABD00;">Continuous Integration:</mark>  
  
<mark style="background: #BABD00;">Continuous Integration (CI)</mark> is a development practice that requires different developers in a team to integrate code into a shared repository several times a day.  

Each check-in is then verified by an automated build, allowing teams to detect problems early.  

While automated testing is not strictly part of CI it is typically implied.  

By integrating regularly, you can detect errors quickly, and locate them more easily.

Every developer is expected to do a "smoke test" on the work they've done. They commit it to a private repo and integrate it to the main repo.

![](https://i.imgur.com/vTeG43e.png)

Build process should be no more than 10 mins. If it is longer, introduce a multi-stage build process.

### <mark style="background: #BABD00;">Productivity:</mark>

Because you’re integrating so frequently, there is significantly less back-tracking to discover where things went wrong, so you can spend more time building features.  

Continuous Integration is cheap relative to not integrating continuously is expensive.  

If you don’t follow a continuous approach, you’ll have longer periods between integrations. This makes it exponentially more difficult to find and fix problems.  

Such integration problems can easily knock a project off-schedule, or cause it to fail altogether.

### <mark style="background: #BABD00;">Benefits:</mark>  

Say goodbye to long and tense integrations.  

Increase visibility enabling greater communication.  

Catch issues early and nip them in the bud. CI doesn't get rid of bugs, but it does make them dramatically easier to find and remove.  

Spend less time debugging and more time adding features.  

Stop waiting to find out if your code’s going to work  

Reduce integration problems allowing you to deliver software more rapidly

![](https://i.imgur.com/IVXsSLO.png)

### <mark style="background: #BABD00;">Practices:</mark>  
- Maintain a single source repository  
- Automate the build.  
- Make your build self-testing.  
- Every commit should build on an integration machine.  
- Keep the build fast. (10 mins or less).
- Test in a clone of the production environment.  
- Make it easy for anyone to get the latest executable version.

### <mark style="background: #BABD00;">How to do it:</mark>  
- Developers check out code into their private workspaces.  
- When done, commit the changes to the repository.  
- The CI server monitors the repository and checks out changes when they occur.  
- The CI server builds the system and runs unit and integration tests.  
- The CI server releases deployable artefacts for testing.  
- The CI server assigns a build label to the version of the code it just built.  
- The CI server informs the team of the successful build.  
- If the build or tests fail, the CI server alerts the team. The team fixes the issue at the earliest opportunity.  
- Continue to continually integrate and test throughout the project

<mark style="background: #BABD00;">Semantic Versioning:</mark> Three numbers. Major (1st number) when you make incompatible API changes. Minor (2) version when you add functionality in a backward compatible manner. Patch (3rd number) is for bugfixes. e.g. 1.7.2

### <mark style="background: #BABD00;">Team Responsibilities:</mark>  
- Check in frequently.  
- Don’t check in broken code  
- Don’t check in untested code.  
- Don’t check in when the build is broken.  
- Don’t go home after checking in until the system builds.  
- Always maintain a correct consistent state.

![](https://i.imgur.com/jL7Vagp.png)

### <mark style="background: #BABD00;">Automate the Build:</mark>

What exactly do we mean by ‘Automate the build’?  

Getting the sources turned into a running system can often be a complicated process involving compilation, moving files around, loading schemas into the databases, and so on.  

However like most tasks in this part of software development it can be automated - and as a result should be automated. Asking people to type in strange commands or clicking through dialog boxes is a breeding ground for mistakes.  

A common mistake is not to include everything in the automated build.  

<mark style="background: #BABD00;">Rule of thumb:</mark> anyone should be able to bring in a virgin machine, check the sources out of the repository, issue a single command, and have a running system on their machine.

### <mark style="background: #BABD00;">Keep the Build Fast:</mark>

One primary goal of Continuous Integration is to provide rapid feedback.  

A CI activity whereby a build takes a long time is counter-productive.  

Most consider a build that takes an hour to be totally unreasonable. 10 minutes is reasonable.  

Recall - It's worth putting in concentrated effort to make it happen, because every minute you reduce off the build time is a minute saved for each developer every time they commit. Since CI demands frequent commits, this adds up to a lot of time.  

One approach to reducing overall build time is to use a multi-stage build process.

### <mark style="background: #BABD00;">CI/CD Pipeline:</mark>

![](https://i.imgur.com/Csy2L12.png)

### <mark style="background: #BABD00;">Acknowledgements:</mark>

The majority of the content in these slides were taken from the following online resources:  

DevOps Fundamentals - Introduction to DevOps by by Thiago Almeida and David Tesar. (Microsoft)  

http://www.itproguy.com/devops-practices  

https://www.thoughtworks.com/insights/blog/infrastructure-code-reason-smile  

https://www.red-gate.com/simple-talk/sysadmin/powershell/powershell-desired-state-configuration-the-basics/  

https://martinfowler.com/articles/continuousIntegration.html  

https://puppet.com/solutions/infrastructure-as-code  

https://www.thoughtworks.com/continuous-integration

# <mark style="background: #BABD00;">19 DevOps - Continuous Delivery:</mark>

### <mark style="background: #BABD00;">What is Continuous Delivery (CD) ?</mark>

Continuous Delivery is the ability to get changes of all types - including new features, configuration changes, bug fixes and experiments—into production, or into the hands of <mark style="background: #BABD00;">users</mark>, <mark style="background: #BABD00;">safely</mark> and quickly in a <mark style="background: #BABD00;">sustainable</mark> way.  

Our goal is to make deployments whether of a large-scale distributed system, a complex production environment, an embedded system, or an app—predictable, routine affairs that can be performed on demand.  

We achieve all this by ensuring our code is always in a deployable state, even in the face of teams of thousands of developers making changes on a daily basis.

![](https://i.imgur.com/Vbn2Y7g.png)

### <mark style="background: #BABD00;">Why Continuous Delivery?</mark>

It is often assumed that if we want to deploy software more frequently, we must accept lower levels of stability and reliability in our systems. 

High performance teams consistently deliver services faster and more reliably than their low performing competition.  

CD provides an distinct competitive advantage for organisations who embrace it

### <mark style="background: #BABD00;">Benefits of Continuous Delivery?</mark>

<mark style="background: #BABD00;">There are six key benefits of Continuous Delivery:</mark>  
- Low risk releases.  
- Faster time to market.  
- Higher Quality.  
- Lower costs.  
- Better Products.  
- Happier Teams.

The primary goal of continuous delivery is to make software deployments painless, low-risk events that can be performed at any time, on demand.  

By applying patterns such as blue-green deployments it is relatively straightforward to achieve zero-downtime deployments that are undetectable to users  

A pattern is "a named strategy for solving a recurring problem". 

Describes the core of the solution to the problem in such a way that you can use this solution a million times over without ever doing it the same way twice.

<mark style="background: #BABD00;">Blue-Green Deployments:</mark>  
- One of the challenges with automating deployment is the cut-over itself, taking software from the final stage of testing to live production.  
- You usually need to do this quickly in order to minimise downtime.  
- The blue-green deployment approach does this by ensuring you have two production environments, as identical as possible.

![](https://i.imgur.com/Wlr1m68.png)

Blue-green deployment also gives you a rapid way to rollback - if anything goes wrong you switch the router back to your blue environment.

<mark style="background: #BABD00;">Faster time to market:</mark>  
- It’s not uncommon for the integration and test/fix phase of the traditional phased software delivery lifecycle to consume weeks or even months.  
- By automating the build and deployment, environment provisioning, and regression testing processes, We also avoid the large amounts of re-work that plague the phased approach.

<mark style="background: #BABD00;">Higher Quality:</mark>  
- When developers have automated tools that discover regressions within minutes, teams are freed to focus their effort on user research and higher level testing activities such as exploratory testing, usability testing, and performance and security testing.  
- By building a deployment pipeline, these activities can be performed continuously throughout the delivery process, ensuring quality is built in to products and services from the beginning.

<mark style="background: #BABD00;">Higher Quality:</mark>  
- When developers have automated tools that discover regressions within minutes, teams are freed to focus their effort on user research and higher level testing activities such as exploratory testing, usability testing, and performance and security testing.  
- By building a deployment pipeline, these activities can be performed continuously throughout the delivery process, ensuring quality is built in to products and services from the beginning.

<mark style="background: #BABD00;">Better Products:</mark>  
- Continuous delivery makes it economic to work in small  batches.  
- We can get feedback from users throughout the delivery lifecycle based on working software.  
- Techniques such as <mark style="background: #BABD00;">A/B testing</mark> enable us to take a hypothesis-driven approach to product development whereby we can test ideas with users before building out whole features  
- This means we can avoid the 2/3 of features we build that deliver zero or negative value to our businesses.

### <mark style="background: #BABD00;">Benefits of Continuous Delivery?</mark>

<mark style="background: #BABD00;">A/B Testing:</mark>
![](https://i.imgur.com/qfyWeco.png)

<mark style="background: #BABD00;">Happier Teams:</mark>  
- Continuous Delivery makes releases less painful and reduces team burnout.  
- When we release more frequently, software delivery teams can engage more actively with users, learn which ideas work and which don’t, and see first-hand the outcomes of the work they have done.  
- By removing the low-value painful activities associated with software delivery, we can focus on what we care about most - delivering value to our customers.

### <mark style="background: #BABD00;">Five Principles of Continuous Delivery:</mark>

<mark style="background: #BABD00;">There are five principles at the heart of continuous delivery:</mark>  
- Build quality in.  
- Work in small batches.  
- Computers perform repetitive tasks, people solve problems.  
- Relentlessly pursue continuous improvement.  
- Everyone is responsible.

<mark style="background: #BABD00;">Build Quality In:</mark>  
- W. Edwards Deming, a key figure in the history of the Lean movement offered 14 key principles for management.  
- Principle three states, “Cease dependence on inspection to achieve quality. Eliminate the need for inspection on a mass basis by building quality into the product in the first place.”  
- It’s much cheaper to fix problems and defects if we find them immediately—ideally before they are ever checked into version control, by running automated tests locally
- Creating and evolving feedback loops to detect problems as early as possible is an essential and never-ending work in continuous delivery.  
- If we find a problem in our exploratory testing, we must not only fix it, but then ask: How could we have caught the problem with an automated acceptance test?  
- When an acceptance test fails, we should ask: Could we have written a unit test to catch this problem?

<mark style="background: #BABD00;">Work in Small Batches:</mark>  
- In traditional phased approaches to software development, handoffs from dev to test or test to IT operations consist of whole releases: months worth of work by teams consisting of tens or hundreds of people.  
- In Continuous Delivery, we take the opposite approach, and try and get every change in version control as far towards release as we can, getting comprehensive feedback as rapidly as possible.  
- Working in small batches has many benefits. It reduces the time it takes to get feedback on our work, makes it easier to triage and remediate problems, increases efficiency and motivation, and prevents us from succumbing to the sunk cost fallacy.
- <mark style="background: #BABD00;">Sunk Cost Fallacy:</mark> Reasoning that further investment is  warranted on the fact that the resources already invested will be lost otherwise, not taking into consideration the overall losses involved in the further investment (Short term thinking).  
- The reason we work in small batches is because of the large fixed cost of handing off changes.  
- A key goal of continuous delivery is to change the economics of the software delivery process to make it economically viable to work in small batches so we can obtain the many benefits of this approach.

### <mark style="background: #BABD00;">Computers perform repetitive tasks, people solve problems. </mark> 

One of the earliest philosophical ideas of the Toyota tradition is jidoka, sometimes translated as "automation with a human touch."  

Jidoka is one of the two pillars of the Toyota Production System along with just-in-time.  

The goal is for computers to perform simple, repetitive tasks, such as regression testing, so that humans can focus on problem-solving.  

Thus computers and people complement each other.

### <mark style="background: #BABD00;">Toyota Jidoka</mark>  

Jidoka sometimes is called autonomation, meaning automation with human intelligence.  

This is because it gives equipment the ability to distinguish good parts from bad autonomously, without being monitored by an operator.  

This eliminates the need for operators to continuously watch machines and leads in turn to large productivity gains because one operator can handle several machines, often termed multi-process handling.

![](https://i.imgur.com/AAxJSDX.png)

### <mark style="background: #BABD00;">Computers perform repetitive tasks, people solve problems.</mark>  

Many people worry that automation will put them out of a job.  

This is not the goal. There will never be a shortage of work in a successful company.  

Rather, people are freed up from mindless drudge-work to focus on higher value activities.  

This also has the benefit of improving quality, since humans are at their most error-prone when performing mindless tasks

### <mark style="background: #BABD00;">Relentlessly pursue continuous improvement:</mark>  

Continuous improvement, or kaizen in Japanese, is another key idea from the Lean movement.  

“Kaizen opportunities are infinite. Don’t think you have made things better than before and be at ease... This would be like the student who becomes proud because they bested their master two times out of three in fencing..... it is important to have the attitude in our daily work that just underneath one kaizen idea is yet another one” - Taiichi Ohno (Toyota Lean)  

Don’t treat transformation as a project to be embarked on and then completed so we can return to business as usual. Treats improvement work as an essential part of their daily work, and where nobody is satisfied with the status quo.

### <mark style="background: #BABD00;">The continuous improvement cycle:</mark>

![](https://i.imgur.com/dWTwwAC.png)

### <mark style="background: #BABD00;">Everyone is responsible:</mark>  

In high performing organisations, nothing is "somebody else’s problem"  

Developers are responsible for the quality and stability of the software they build. Operations teams are responsible for helping developers build quality in.  

Everyone works together to achieve the organisational level goals, rather than optimising for what’s best for their team or department.

<mark style="background: #BABD00;">People make local optimisations that reduce the overall performance of the organisation often because:</mark>  
- poor management systems such as annual budgeting cycles
- incentives that reward the wrong behaviours  
- rewarding developers for increasing their velocity or writing more code.  
- rewarding testers based on the number of bugs they find

<mark style="background: #BABD00;">Most people want to do the right thing:</mark>  
- However, they will adapt their behaviour based on how they are rewarded.  
- Therefore, it is very important to create fast feedback loops from the things that really matter: how customers react to what we build for them, and the impact on our organisation

### <mark style="background: #BABD00;">Continuous delivery rests on three foundations:</mark> 

Comprehensive configuration management  

Continuous integration (covered in previous session).  

Continuous testing.

### <mark style="background: #BABD00;">Comprehensive Configuration Management:</mark>

<mark style="background: #BABD00;">The Goals of Configuration Management.</mark>  
- <mark style="background: #BABD00;">Reproducibility:</mark> We should be able to provision any environment in a fully automated fashion, and know that any new environment reproduced from the same configuration is identical.  
- <mark style="background: #BABD00;">Traceability:</mark> We should be able to pick any environment and be able to determine quickly and precisely the versions of every dependency used to create that environment.  
- We also want to be able to compare previous versions of an environment and see what has changed between them.

### <mark style="background: #BABD00;">The Benefits of Configuration Management:</mark>  
- Disaster recovery  
- Auditability  
- Higher quality  
- Response to defects  
- Capacity management

<mark style="background: #BABD00;">Disaster recovery:</mark> When something goes wrong with one of our environments, for example a hardware failure or a security breach, we need to be able to reproduce that environment in a deterministic amount of time in order to be able to restore service  

<mark style="background: #BABD00;">Auditability</mark> (related to System Integrity): be able to show the path backwards from every deployment to the elements it came from, including their version.  

Comprehensive configuration management, combined with deployment pipelines, enable this.

<mark style="background: #BABD00;">Higher quality:</mark>  
- The software delivery process is often subject to long delays waiting for development, testing and production environments to be prepared.  
- When this can be done automatically from version control, we can get feedback on the impact of our changes much more rapidly, enabling us to build quality in to our software

<mark style="background: #BABD00;">Response to defects:</mark>  
- When we discover a critical defect, or a vulnerability in some component of our system, we want to get a new version of our software released as quickly as possible. 
- Many organisations have an emergency process for this type of change which goes faster by bypassing some of the testing and auditing.  
- This presents an especially serious dilemma in safety-critical systems.  
- Our goal should be to be able to use our normal release process for emergency fixes—which is precisely what continuous delivery enables, on the basis of comprehensive configuration management.

### <mark style="background: #BABD00;">Continuous Testing:</mark>

The key to building quality into our software is making sure we can get fast feedback on the impact of changes.  

Traditionally, extensive use was made of manual inspection of code changes and manual testing (normally done in a phase following "dev complete"). 

<mark style="background: #BABD00;">This approach has several limitations:</mark> 
- Manual regression testing takes a long time, is expensive, and creates a bottleneck that prevents us releasing software more frequently.  
- Manual tests and inspections are not very reliable, since humans are notoriously poor at performing repetitive tasks.  
- Software evolves all the time, but the test document does not evolve to match

Our goal is to run many different types of tests—both manual and automated—continually throughout the delivery process

![](https://i.imgur.com/CykgCmJ.png)

Once we have continuous integration and test automation in place, we create a deployment pipeline (the key pattern in continuous delivery).  

<mark style="background: #BABD00;">In the deployment pipeline pattern, every change runs a build that:</mark>  
- creates packages that can be deployed to any environment and  
- runs unit tests (and possibly other tasks such as static analysis)  

giving feedback to developers in the space of a few minutes.  

Packages that pass this set of tests have more comprehensive automated acceptance tests run against them.

### <mark style="background: #BABD00;">Deployment Pipeline:</mark>

Once we have packages that pass all the automated tests, they are available for self-service deployment to other environments for activities such as exploratory testing, usability testing, and ultimately release.  

Complex products and services may have sophisticated deployment pipelines; a simple, linear pipeline is shown on the next slide

<mark style="background: #BABD00;">Sequence Diagram:</mark>
![](https://i.imgur.com/VDuDKkw.png)

<mark style="background: #BABD00;">Conceptual diagram:</mark>
![](https://i.imgur.com/onfd3YF.png)


### <mark style="background: #BABD00;">Deployment Pipeline – Release Candidates:</mark> 

In the deployment pipeline, every change is effectively a release candidate.  

The job of the deployment pipeline is to catch known issues.  

If we can’t detect any known problems, we should feel comfortable releasing any packages that have gone through it.  

If we aren’t, or if we discover defects later, it means we need to improve our pipeline, perhaps adding or updating some tests.

### <mark style="background: #BABD00;">Deployment Pipeline – Parallelise the Activities.</mark>  

Our goal should be to find problems as soon as possible, and make the lead time from check-in to release as short as possible.  

Thus we want to parallelise the activities in the deployment pipeline, not have many stages executing in series.  

<mark style="background: #BABD00;">There is also a feedback process:</mark> if we discover bugs in exploratory testing, we should be looking to improve our automated tests.  

If we discover a defect in the acceptance tests, we should be looking to improve our unit tests (most of our defects should be discovered through unit testing).

### <mark style="background: #BABD00;">Canary Deployments – what is it?</mark>

<mark style="background: #BABD00;">A deployment strategy that gradually rolls out a new version to a subset of users.</mark>  
- Release to 5% of users  
- Monitor metrics and feedback  
- Expand to 25%, continue to monitor metrics and feedback  
- If all is well, then release to 100% of users.  

Allows monitoring for issues before a full-scale release..  

Inspired by the practice of using canaries in coal mines to detect danger early.  

More and more commonly used in Kubernetes, CI/CD and GCP, AWS and Azure pipelines.

### <mark style="background: #BABD00;">Canary Deployments: Benefits, Limitations and Best Practices</mark>

<mark style="background: #BABD00;">Benefits:</mark>  
- Reduces risk of widespread failure.  
- Enables real-world testing with minimal impact.  
- Improves confidence in releases 
- Early Feedback. Canary deployments shorten feedback loops on new features delivered to target environments.  

<mark style="background: #BABD00;">Limitations:</mark>  
- <mark style="background: #BABD00;">Added Complexity:</mark> Teams have two environments to maintain, as well as additional application code, services, and components.  
- <mark style="background: #BABD00;">Technical Challenges:</mark> Routing to subsets of users for new versions can be error-prone, time-consuming, and complex.  
- <mark style="background: #BABD00;">Less Control:</mark> The more software runs on the client side, the less amenable it is to canary deployments.  

<mark style="background: #BABD00;">Best Practices:</mark>  
- Use robust monitoring and alerting systems  
- Automate rollbacks for faster response to issues.  
- Communicate clearly with stakeholders.

### <mark style="background: #BABD00;">Blue Green Deployments vs Canary Deployments:</mark>

![](https://i.imgur.com/nIy8tpL.png)

### <mark style="background: #BABD00;">Implementing Continuous Delivery:</mark>

![](https://i.imgur.com/5XLj1GW.png)

# <mark style="background: #BABD00;">20 Required Reading CA2:</mark>

# <mark style="background: #BABD00;">Difference between Stateless and Stateful Protocol</mark>

[Link](https://www.geeksforgeeks.org/difference-between-stateless-and-stateful-protocol/)

In networking, how interactions between clients and servers are managed greatly affects system performance. There are two main types of protocols for this purpose: <mark style="background: #BABD00;">stateless</mark> and <mark style="background: #BABD00;">stateful</mark> protocols. 

<mark style="background: #BABD00;">Stateless</mark> protocols do not maintain state information, so a server does not need to retain information from prior requests. This simplifies server design and optimises resource utilisation. 

In contrast, <mark style="background: #BABD00;">stateful</mark> protocols maintain session information, allowing for more consistent interaction between clients and servers. 

Understanding the characteristics and differences of these protocols is crucial for properly designing network systems.

### <mark style="background: #BABD00;">What is the Stateless Protocol?</mark>

Stateless Protocols are a type of network protocols in which the Client sends a request to the server and the server responds back according to the current state. 

It does not require the server to retain session information or status about each communicating partner for multiple requests. 

<mark style="background: #BABD00;">HTTP</mark> (Hypertext Transfer Protocol), <mark style="background: #BABD00;">UDP</mark> (User Datagram Protocol), and <mark style="background: #BABD00;">DNS</mark> (Domain Name System) are examples of <mark style="background: #BABD00;">Stateless</mark> Protocols. 

<mark style="background: #BABD00;">Salient Features of Stateless Protocols</mark>
- Stateless Protocols simplify the design of the Server.
- The stateless protocol requires fewer resources because the system does not need to keep track of the multiple link communications and the session details.
- In Stateless Protocols each information packet travels on its own without reference to any other packet.
- Each communication in Stateless Protocol is discrete and unrelated to those that precedes or follow.

### <mark style="background: #BABD00;">What is Stateful Protocol?</mark>

In Stateful Protocols, if a client sends a request to the server then it expects some kind of response, if it does not get any response then it resends the request. 

<mark style="background: #BABD00;">FTP</mark> (File Transfer Protocol), <mark style="background: #BABD00;">TCP</mark>, and <mark style="background: #BABD00;">Telnet</mark> are the example of Stateful Protocols. 

<mark style="background: #BABD00;">Salient Features of Stateful Protocol:</mark>
- Stateful Protocols provide better performance to the client by keeping track of the connection information.
- Stateful Applications require Backing storage.
- Stateful requests are always dependent on the server-side state.
- TCP sessions follow a stateful protocol because both systems maintain information about the session itself during its life.

### <mark style="background: #BABD00;">Comparisons Between Stateless and Stateful Protocol</mark>

![](https://i.imgur.com/85ibE2V.png)
![](https://i.imgur.com/LRKLAa0.png)

### <mark style="background: #BABD00;">Conclusion</mark>

There are two types of protocols: <mark style="background: #BABD00;">Stateless</mark> and <mark style="background: #BABD00;">Stateful</mark>. Each type has its benefits and pitfalls that qualify it for use in some contexts and not others. 

Since <mark style="background: #BABD00;">stateless</mark> protocols do not retain session specific details, the simplicity in design of servers and the management of resources is well adopted, especially in applications that do not necessarily require session information of clients. 

On the other hand, <mark style="background: #BABD00;">stateful</mark> protocols possess better interactivity by maintaining session information that is advantageous for those applications that require session continuity and reliability. By elucidating these differences, one is better placed to determine the right protocol for budgeting purposes and in meeting the profound demands of the business’s specific network.

### <mark style="background: #BABD00;">Difference Between Stateless and Stateful Protocol – FAQs</mark>

<mark style="background: #BABD00;">What is the key benefit of using stateless protocols?</mark>
- The main advantage concerning the employment of stateless protocols can be recognised in its relative simplicity and the fairly low demands put on the necessary resources. 
- Since the session information is not required to be stored on the server, it also means that the design is easier and the server load is less.

<mark style="background: #BABD00;">How do stateful protocols enhance client-server communication?</mark>
- Stateful protocols improve the engagement between devices because it holds information regarding the connection between the engaging requests which in turn makes the engagement to be much more continuous and reliable as compared to stateless. 
- For cases where it is necessary to monitor particular active sessions, this is quite helpful.

<mark style="background: #BABD00;">Can you give an example of when to use a stateless protocol?</mark>
- Connectionless protocols are appropriate for HTTP for web browsing where every request from the client does not depend on the other as the connection will not be persistent. 
- As a result, it should be okay for mainly, low-risk/low-value, operational type activities.

<mark style="background: #BABD00;">Can you give an example of when to use a stateless protocol?</mark>
- Reliable protocols are ideal in any system where the context of the session must be constantly kept and used such in the case of FTP or Telnet where the two entities must talk to each other in a one-to-one fashion.

# <mark style="background: #BABD00;">Why use serverless computing? | Pros and cons of serverless</mark>

[Link](https://www.cloudflare.com/en-gb/learning/serverless/why-use-serverless/)

### <mark style="background: #BABD00;">Why use serverless computing?</mark>

Serverless computing offers a number of advantages over traditional cloud-based or server-centric infrastructure. 

For many developers, serverless architectures offer greater scalability, more flexibility, and quicker time to release, all at a reduced cost. 

With serverless architectures, developers do not need to worry about purchasing, provisioning, and managing backend servers. However, serverless computing is not a magic bullet for all web application developers.

### <mark style="background: #BABD00;">How does serverless computing work?</mark>

Serverless computing is an architecture in which a vendor provides backend services as they are needed. To learn more about serverless computing, see [What is serverless computing?](https://www.cloudflare.com/learning/serverless/what-is-serverless/)

### <mark style="background: #BABD00;">What are the advantages of serverless computing?</mark>

<mark style="background: #BABD00;">No server management is necessary:</mark>
Although 'serverless' computing does actually take place on servers, developers never have to deal with the servers. They are managed by the vendor. This can reduce the investment necessary in DevOps, which lowers expenses, and it also frees up developers to create and expand their applications without being constrained by server capacity.

<mark style="background: #BABD00;">Developers are only charged for the server space they use, reducing cost:</mark>
As in a 'pay-as-you-go' phone plan, developers are only charged for what they use. Code only runs when backend functions are needed by the serverless application, and the code automatically scales up as needed. Provisioning is dynamic, precise, and real-time. Some services are so exact that they break their charges down into 100-millisecond increments. In contrast, in a traditional 'server-full' architecture, developers have to project in advance how much server capacity they will need and then purchase that capacity, whether they end up using it or not.

<mark style="background: #BABD00;">Serverless architectures are inherently scalable:</mark>
Imagine if the post office could somehow magically add and decommission delivery trucks at will, increasing the size of its fleet as the amount of mail spikes (say, just before Mother's Day) and decreasing its fleet for times when fewer deliveries are necessary. That's essentially what serverless applications are able to do.

Applications built with a serverless infrastructure will scale automatically as the user base grows or usage increases. If a function needs to be run in multiple instances, the vendor's servers will start up, run, and end them as they are needed, often using containers. (The function will start up more quickly if it has been run recently – see 'Performance may be affected' below.) As a result, a serverless application will be able to handle an unusually high number of requests just as well as it can process a single request from a single user. A traditionally structured application with a fixed amount of server space can be overwhelmed by a sudden increase in usage.

<mark style="background: #BABD00;">Quick deployments and updates are possible:</mark>
Using a serverless infrastructure, there is no need to upload code to servers or do any backend configuration in order to release a working version of an application. Developers can very quickly upload bits of code and release a new product. They can upload code all at once or one function at a time, since the application is not a single monolithic stack but rather a collection of functions provisioned by the vendor.

This also makes it possible to quickly update, patch, fix, or add new features to an application. It is not necessary to make changes to the whole application; instead, developers can update the application one function at a time.

<mark style="background: #BABD00;">Code can run closer to the end user, decreasing latency:</mark>
Because the application is not hosted on an [origin server](https://www.cloudflare.com/learning/cdn/glossary/origin-server/), its code can be run from anywhere. It is therefore possible, depending on the vendor used, to run application functions on servers that are close to the end user. This reduces latency because requests from the user no longer have to travel all the way to an origin server. [Cloudflare Workers](https://www.cloudflare.com/products/cloudflare-workers/) enables this kind of serverless latency reduction.

### <mark style="background: #BABD00;">What are the disadvantages of serverless computing?</mark>

<mark style="background: #BABD00;">Testing and debugging become more challenging:</mark>
It is difficult to replicate the serverless environment in order to see how code will actually perform once deployed. Debugging is more complicated because developers do not have visibility into backend processes, and because the application is broken up into separate, smaller functions. The [Cloudflare Workers Playground](https://cloudflareworkers.com/) is a sandbox that helps reduce friction in testing and debugging

<mark style="background: #BABD00;">Serverless computing introduces new security concerns:</mark>
When vendors run the entire backend, it may not be possible to fully vet their security, which can especially be a problem for applications that handle personal or sensitive data.

Because companies are not assigned their own discrete physical servers, serverless providers will often be running code from several of their customers on a single server at any given time. This issue of sharing machinery with other parties is known as 'multitenancy' – think of several companies trying to lease and work in a single office at the same time. Multitenancy can affect application performance and, if the multi-tenant servers are not configured properly, could result in data exposure. Multitenancy has little to no impact for networks that sandbox functions correctly and have powerful enough infrastructure. For instance, Cloudflare runs a 15-Tbps network with enough excess capacity to mitigate service degradation, and all [serverless functions](https://blog.cloudflare.com/introducing-cloudflare-workers/) hosted by Cloudflare run in their own sandbox (via the [Chrome V8 engine](https://blog.cloudflare.com/introducing-cloudflare-workers/)).

<mark style="background: #BABD00;">Serverless architectures are not built for long-running processes:</mark>
This limits the kinds of applications that can cost-effectively run in a serverless architecture. Because serverless providers charge for the amount of time code is running, it may cost more to run an application with long-running processes in a serverless infrastructure compared to a traditional one.

<mark style="background: #BABD00;">Performance may be affected:</mark>
Because it's not constantly running, serverless code may need to 'boot up' when it is used. This start-up time may degrade performance. However, if a piece of code is used regularly, the serverless provider will keep it ready to be activated – a request for this ready-to-go code is called a 'warm start.' A request for code that hasn't been used in a while is called a 'cold start.'

Cloudflare Workers largely avoids the cold-starting issue by using the Chrome V8 engine, which in most cases is able to start up and run JavaScript code in under 5 milliseconds. If the code is already running, the response time is under a millisecond. [Learn more about the performance of different serverless platforms](https://www.cloudflare.com/learning/serverless/serverless-performance/).

<mark style="background: #BABD00;">Vendor lock-in is a risk:</mark>
Allowing a vendor to provide all backend services for an application inevitably increases reliance on that vendor. Setting up a serverless architecture with one vendor can make it difficult to switch vendors if necessary, especially since each vendor offers slightly different features and workflows. ([Cloudflare Workers](https://www.cloudflare.com/products/cloudflare-workers/) are easier to migrate because they are written in JavaScript and written against the widely used service workers API.)

### <mark style="background: #BABD00;">Who should use a serverless architecture?</mark>

Developers who want to decrease their go-to-market time and build lightweight, flexible applications that can be expanded or updated quickly may benefit greatly from serverless computing.

Serverless architectures will reduce costs for applications that see inconsistent usage, with peak periods alternating with times of little to no traffic. For such applications, purchasing a server or a block of servers that are constantly running and always available, even when unused, may be a waste of resources. A serverless setup will respond instantly when needed and will not incur costs when at rest.

Also, developers who want to push some or all of their application functions close to end users for reduced latency will require at least a partially serverless architecture, since doing so necessitates moving some processes out of the origin server.

### <mark style="background: #BABD00;">When should developers avoid using a serverless architecture?</mark>

There are cases when it makes more sense, both from a cost perspective and from a system architecture perspective, to use dedicated servers that are either self-managed or offered as a service. 

For instance, large applications with a fairly constant, predictable workload may require a traditional setup, and in such cases the traditional setup is probably less expensive.

Additionally, it may be prohibitively difficult to migrate legacy applications to a new infrastructure with an entirely different architecture.

### <mark style="background: #BABD00;">How does Cloudflare help developers build serverless architectures?</mark>

[Cloudflare Workers](https://www.cloudflare.com/products/cloudflare-workers/) is a product that enables developers to write JavaScript functions and deploy them at the edge of the Cloudflare network. This makes it possible to run application code in a serverless architecture as close to the end user as possible, minimising latency.

# <mark style="background: #BABD00;">What is a Message Broker?</mark>

[Link](https://www.ibm.com/topics/message-brokers)

A <mark style="background: #BABD00;">message broker</mark> is software that enables applications, systems and services to communicate with each other and exchange information.

The message broker does this by translating messages between formal messaging protocols. This allows interdependent services to “talk” with one another directly, even if they were written in different languages or implemented on different platforms.

Message brokers are software modules within messaging middleware or message-oriented middleware (MOM) solutions. This type of middleware provides developers with a standardised means of handling the flow of data between an application’s components so that they can focus on its core logic. It can serve as a distributed communications layer that allows applications spanning multiple platforms to communicate internally.

Message brokers can validate, store, route, and deliver messages to the appropriate destinations. They serve as intermediaries between other applications, allowing senders to issue messages without knowing where the receivers are, whether or not they are active, or how many of them there are. This facilitates decoupling of processes and services within systems.

In order to provide reliable message storage and guaranteed delivery, message brokers often rely on a substructure or component called a [message queue](https://www.ibm.com/topics/message-queues) that stores and orders the messages until the consuming applications can process them. In a message queue, messages are stored in the exact order in which they were transmitted and remain in the queue until receipt is confirmed.

Asynchronous messaging refers to the type of inter-application communication that message brokers make possible. It prevents the loss of valuable data and enables systems to continue functioning even in the face of the intermittent connectivity or latency issues common on public [networks](https://www.ibm.com/topics/networking). 

Asynchronous messaging guarantees that messages will be delivered once (and once only) in the correct order relative to other messages.

Message brokers may comprise of queue managers to handle the interactions between multiple message queues, as well as services providing data routing, message translation, persistence, and client state management functionalities.

# <mark style="background: #BABD00;">What is a Message Queue?</mark>

[Link](https://aws.amazon.com/message-queue/)

A message queue is a form of asynchronous service-to-service communication used in serverless and microservices architectures. Messages are stored on the queue until they are processed and deleted. Each message is processed only once, by a single consumer. Message queues can be used to decouple heavyweight processing, to buffer or batch work, and to smooth spiky workloads.

Below are several resources to help you better understand message queues in the broad sense. To learn about message queues on AWS, visit our [Amazon Simple Queue Service (SQS)](https://aws.amazon.com/sqs) website.

### <mark style="background: #BABD00;">Message Queue Basics</mark>

In modern cloud architecture, applications are decoupled into smaller, independent building blocks that are easier to develop, deploy and maintain. 

Message queues provide communication and coordination for these distributed applications. 

Message queues can significantly simplify coding of decoupled applications, while improving performance, reliability and scalability.

Message queues allow different parts of a system to communicate and process operations asynchronously. 

A message queue provides a lightweight buffer which temporarily stores messages, and endpoints that allow software components to connect to the queue in order to send and receive messages. 

The messages are usually small, and can be things like requests, replies, error messages, or just plain information. To send a message, a component called a producer adds a message to the queue. 

The message is stored on the queue until another component called a consumer retrieves the message and does something with it.

![](https://i.imgur.com/GYzhkKO.png)

Many producers and consumers can use the queue, but each message is processed only once, by a single consumer. For this reason, this messaging pattern is often called one-to-one, or point-to-point, communications. When a message needs to be processed by more than one consumer, message queues can be combined with Pub/Sub messaging in a fanout design pattern. See "[What is Pub/Sub messaging?](https://aws.amazon.com/what-is/pub-sub-messaging/)" for details, and visit our [Amazon Simple Notification Service (SNS)](https://aws.amazon.com/migration-acceleration-program/) website for an overview of Pub/Sub messaging on AWS.

# <mark style="background: #BABD00;">What is a key-value database?</mark>

[Link](https://aws.amazon.com/nosql/key-value/)

A [key-value database](https://aws.amazon.com/dynamodb/) is a type of non-relational database, also known as [NoSQL database](https://aws.amazon.com/nosql/), that uses a simple key-value method to store data. It stores data as a collection of key-value pairs in which a key serves as a unique identifier. Both keys and values can be anything, ranging from simple objects to complex compound objects. Key-value databases (or key-value stores) are highly partitionable and allow horizontal scaling at a level that other types of databases cannot achieve.

### <mark style="background: #BABD00;">What are the advantages of key-value databases</mark>

Traditional [relational databases](https://aws.amazon.com/relational-database/) ([SQL databases](https://aws.amazon.com/rds/)) store data in the form of tables containing rows and columns. They enforce a rigid structure on data and are not optimal for every use case. 

On the other hand, key-value databases are NoSQL databases. They allow flexible database schemas and improved performance at scale for certain use cases. 

<mark style="background: #BABD00;">The advantages of key-value stores include:</mark>
- <mark style="background: #BABD00;">Scalability</mark> As every user query requires data interaction, databases can often become a bottleneck in application performance. Several strategies to solve the issue, such as replication and [sharding](https://aws.amazon.com/what-is/database-sharding/), add complexity to the application code. Many key-value databases provide built-in support for advanced scaling features. They scale horizontally and automatically distribute data across servers to reduce bottlenecks at a single server.
- <mark style="background: #BABD00;">Ease of use:</mark> Key-value databases follow the object-oriented paradigm that allows developers to map real-world objects directly to software objects. Several programming languages, such as Java, also follow the same paradigm. Instead of mapping their code objects to multiple underlying tables, engineers can create key-value pairs that match their code objects. This makes key-value stores more intuitive for developers to use.
- <mark style="background: #BABD00;">Performance:</mark> Key-value databases process constant read-write operations with low-overhead server calls. Improved latency and reduced response time give better performance at scale. They are based on simple, single-table structures rather than multiple interrelated tables. Unlike relational databases, key-value databases don't have to perform resource-intensive table joins, which makes them much faster.

### <mark style="background: #BABD00;">What are the use cases of key-value databases?</mark>

You can use key-value database systems as the primary database for your application or to handle niche requirements. We give some example key-value database use cases below.

<mark style="background: #BABD00;">Session management:</mark>
A session-oriented application, such as a web application, starts a session when a user logs in to an application and is active until the user logs out or the session times out. During this period, the application stores all user session attributes either in the main memory or in a database. User session data may include profile information, messages, personalised data and themes, recommendations, targeted promotions, and discounts.

Each user session has a unique identifier. Session data is never queried by anything other than a primary key, so a fast key-value store is a better fit for session data. In general, key-value databases may provide smaller per-page overhead than relational databases.

<mark style="background: #BABD00;">Shopping cart:</mark>
An e-commerce website may receive billions of orders per second during the holiday shopping season. A key-value database can handle the scaling of large amounts of data and extremely high volumes of state changes, while also servicing millions of simultaneous users through distributed processing and storage. Key-value stores also have built-in redundancy, which can handle the loss of storage nodes.

<mark style="background: #BABD00;">Metadata storage engine:</mark>
Your key-value store can act as an underlying storage layer for higher levels of data access. For example, you can scale throughput and concurrency for media and entertainment workloads such as real-time video streaming and interactive content. You can also build out your game platform with player data, session history, and leader-boards for millions of concurrent users.

<mark style="background: #BABD00;">Caching:</mark>
You can use a key-value database for storing data temporarily for faster retrieval. For example, social media applications can store frequently accessed data like news feed content. In-memory data caching systems also use key-value stores to accelerate application responses.

### <mark style="background: #BABD00;">How do key-value databases work</mark>

Key-value databases work by organising all data as a set of key-value pairs. You can think of the key as a question and the value as the answer to the question. In the example below, the primary key is a composite of two keys, Product ID and Type. The Product ID is the partition key which describes the partition in which the item will be stored. The Type is the sort key, which determines the order in which items will be stored in disk. The combination of the Partition Key and the Sort Key forms a unique primary key, which maps to a single value in the database.

In this example, the data object book has attributes like title, author, and publishing date. Every book data object has a key called ``BookID``. You can directly link the ``BookID`` and associated book object in the key-value store. In addition, you can retrieve data by looking up the ``BookID`` in the table. Also, each item has its own schema, making key-value stores highly flexible for storing data of varying structures.

![](https://i.imgur.com/xY4i81N.png)

### <mark style="background: #BABD00;">What are the features of key-value databases</mark>

Depending on the solution you choose, your key-value store can provide several additional features as listed below.

<mark style="background: #BABD00;">Support for complex data types:</mark>
Key-value stores provide support for defined data types like integers and text. However, many of them can also support more complex objects like arrays, nested dictionaries, images, videos, and semi-structured data. By giving the database more information about your data, there is room for more storage and query performance optimisation.

<mark style="background: #BABD00;">No need for table joins:</mark>
Key-value databases don't need to perform any resource-intensive table joins. Their flexibility accommodates all the needed information in a single table. This is one of the reasons key-value stores perform so well.

<mark style="background: #BABD00;">Sorted keys:</mark>
A key-value store can sort keys so that data is stored systematically and for implementing partitioning. For example, keys may be sorted:
- Alphabetically or numerically
- Chronologically
- By data size

Consider a key-value store that uses the customer's email address as the unique key. Email addresses can be sorted alphabetically, so all data for A-J email lists are stored on server 1, K-S on server 2, and so on.

<mark style="background: #BABD00;">Secondary key support:</mark>
Some key-value stores allow you to define two or more different keys or secondary indexes to access the same data. For example, you can store customer data by key email address and key phone number.

<mark style="background: #BABD00;">Replication:</mark>
Many key-value stores offer built-in replication support by automatically copying data across multiple storage nodes. This helps with auto-recovery from disasters; you still have your data in case of server failure.

<mark style="background: #BABD00;">Partitioning:</mark>
Partitioning is how you distribute data across nodes. Many key-value databases provide default partitioning options. Some also give you the option to define input parameters for your partitions. For example, you could partition numerical keys into groups of 1000. Advanced key-value databases also provide automatic support for distributing your key-value database across multiple geographical locations. This improves application availability and reliability because you can respond to queries close to the user's location.

<mark style="background: #BABD00;">ACID support:</mark>
Atomicity, Consistency, Isolation, and Durability ([ACID](https://docs.aws.amazon.com/athena/latest/ug/acid-transactions.html)) are database properties that ensure data accuracy and reliability in all circumstances. For instance, if you are making multiple changes to your data in a sequence, atomicity requires that all changes go through in order. If one change fails, everything fails.

Advanced key-value databases provide native, server-side support for ACID. This simplifies the developer experience of making coordinated, all-or-nothing changes to multiple items both within and across tables. With transaction support, developers can extend the scale, performance, and enterprise benefits to a broader set of mission-critical workloads.

### <mark style="background: #BABD00;">What are the limitations of key-value databases</mark>

Key-value databases do require some trade-offs, as with any kind of technology choice.

<mark style="background: #BABD00;">Absence of complex queries:</mark>
As key-value databases don't support complex queries, developers must work around this in the code. Data operations are mainly through simple query language terms like ``get``, ``put``, and ``delete``. There are limitations to how much you can filter and sort data before accessing it.

<mark style="background: #BABD00;">Schema mismanagement:</mark>
Key-value store design does not enforce a schema on developers. Anyone can modify the schema in the database program. Development teams have to plan the data model systematically to avoid long-term problems. The lack of a tight schema also means that the application is responsible for the proper interpretation of the data it consumes, often referred to as 'schema on read'.

# <mark style="background: #BABD00;">What is a GitOps workflow?</mark>

Managing IT infrastructure can be challenging, but teams that use well-known software development practices, including version control, code review, and CI/CD pipelines, find the process more convenient. By using config files, the same infrastructure environment is deployed each time. Many teams know that this workflow increases efficiency, collaboration, and stability, but they may wonder what it means to adopt GitOps.

### <mark style="background: #BABD00;">Three components of GitOps workflows</mark>

[Link](https://about.gitlab.com/topics/gitops/gitops-workflow/)

As a software development framework, GitOps has three main parts to its workflow, including infrastructure as code, merge requests, and CI/CD pipelines.

1. <mark style="background: #BABD00;">Infrastructure as Code (IaC)</mark>
2. <mark style="background: #BABD00;">Merge Requests (MR)</mark>
3. <mark style="background: #BABD00;">Continuous Integration and Continuous Deployment (CI/CD)</mark>

### <mark style="background: #BABD00;">1. Infrastructure as code (IaC)</mark>

[IaC Link](https://about.gitlab.com/topics/gitops/gitops-workflow/#-infrastructure-as-code-iac)

The first step in a GitOps workflow is defining all [infrastructure as code](https://about.gitlab.com/topics/gitops/infrastructure-as-code/). IaC automates the IT infrastructure provisioning by using configuration files. 

IaC is a DevOps practice that supports teams to version infrastructure to improve consistency across machines to reduce deployment friction. 

Infrastructure code undergoes a similar process as application code with touchpoints in continuous integration, version control, testing, and continuous deployment. 

Automation leads to more [efficient](https://about.gitlab.com/blog/2020/04/17/why-gitops-should-be-workflow-of-choice/) development, increased consistency, and [faster](https://about.gitlab.com/blog/2021/02/24/production-grade-infra-devsecops-with-five-minute-production/) time to market.

Managing [infrastructure](https://about.gitlab.com/blog/2020/11/09/lessons-in-iteration-from-new-infrastructure-team/) has traditionally been a manual process involving large teams maintaining physical servers. Each machine often has its own configuration, leading to snowflake environments. 

With infrastructure as code, teams have increased visibility, consistency, stability, and scalability.

### <mark style="background: #BABD00;">2. Merge requests (MRs)</mark>

[MRs Link](https://about.gitlab.com/topics/gitops/gitops-workflow/#-merge-requests-mrs)

Declarative tools, such as Kubernetes, enable config files to be [version controlled](https://about.gitlab.com/blog/2020/11/12/migrating-your-version-control-to-git/) by Git, an open source version control system that tracks code changes. 

Using a Git repository as the single source of truth for infrastructure definitions, GitOps benefits from a robust audit trail. 

The second aspect of GitOps workflows involve merge requests, which serve as the [change function](https://about.gitlab.com/blog/2020/10/13/merge-request-reviewers/) for infrastructure updates.

Teams collaborate in merge requests through [code reviews](https://about.gitlab.com/blog/2021/01/25/mr-reviews-with-vs-code/), comments, and suggestions. A merge commits to the [main](https://about.gitlab.com/blog/2021/03/10/new-git-default-branch-name/) branch and acts as an audit log. 

Built-in rollback features enable teams to revert to a desired state and explore innovative ways to approach difficult challenges. Merge requests facilitate experimentation and provide a safe way for team members to receive fast [feedback](https://about.gitlab.com/blog/2021/03/18/iteration-and-code-review/) from their peers and subject matter experts.

### <mark style="background: #BABD00;">3. Continuous integration and continuous deployment (CI/CD)</mark>

[CI/CDL ink](https://about.gitlab.com/topics/gitops/gitops-workflow/#-continuous-integration-and-continuous-deployment-cicd)

GitOps automates infrastructure management using a Git workflow with [effective](https://about.gitlab.com/blog/2020/07/29/effective-ci-cd-pipelines/) continuous integration and continuous deployment. 

After code is merged to the main branch, the CI/CD pipeline initiates the [change](https://about.gitlab.com/blog/2021/02/22/pipeline-editor-overview/) in the environment. 

Manual changes and human error can cause configuration drift and snowflake environments, but GitOps automation and continuous deployment overwrites them so the environment always [deploys](https://about.gitlab.com/blog/2021/02/05/ci-deployment-and-environments/) a consistent desired state.

# <mark style="background: #BABD00;">The 3 Core principles of ZeroTrust</mark>

[Link](https://www.twingate.com/blog/the-3-core-principles-of-zero-trust)

Zero Trust has been a topic of cybersecurity for over two decades, gaining prominence in 2010 when John Kindervag championed the concept.

Today, as cyber threats evolve and organisational perimeters expand with remote work and cloud integration, [interest in Zero Trust is higher than ever](https://trends.google.com/trends/explore?date=all&geo=US&q=zero%20trust&hl=en). This makes it a perfect opportunity to revisit the robust foundations of Zero Trust Network Access (ZTNA).

![](https://i.imgur.com/F0TR3W4.png)

In this guide, we’ll delve into the three fundamental principles of Zero Trust: Least Privilege Access, Always Verify, and Risk Mitigation. Each principle is critical for building a resilient and dynamic security environment where threats are not only recognised but also effectively contained. Join us as we explore how these principles can fortify your organisation against the ever-changing landscape of cyber threats.

- `Least Privilege Access`
- `Always Verify`
- `Risk Mitigation`

### <mark style="background: #BABD00;">What is Zero Trust Security?</mark>

Zero Trust Security is a cybersecurity strategy that challenges the conventional perimeter-based security models, which have increasingly shown their limitations in the face of modern cyber threats and evolving work environments. 

Traditional security models operate under the assumption that everything inside an organisation’s network can be trusted. However, this assumption has become flawed due to the rising sophistication of cyber attacks and the fact that insiders can often be threats themselves.

In the face of evolving cyber threats and changing work environments, traditional perimeter-based security models are proving inadequate. Enter ZTNA, a paradigm shift in cybersecurity that embodies the principle of “never trust, always verify.”  
  
### <mark style="background: #BABD00;">Least Privilege Access</mark>

In a Zero Trust architecture, access controls are dynamically and strictly enforced to ensure robust security. 

<mark style="background: #BABD00;">The five distinct levels of access that are particularly relevant within a Zero Trust framework:</mark>
1. <mark style="background: #BABD00;">No Access:</mark> This is the default setting for any user or device. Access is not granted until explicit authentication and authorisation are achieved, reinforcing the security from the ground up.
2. <mark style="background: #BABD00;">Public Access:</mark> This level allows users to access publicly available information or resources without the need for authentication. It's designed for maximum accessibility while still maintaining overarching security protocols.
3. <mark style="background: #BABD00;">General Access:</mark> Within an organisation, general access typically includes access to basic organisational tools such as email. This level is meant for day-to-day operational activities by regular staff members.
4. <mark style="background: #BABD00;">Administrative Access:</mark> Reserved for IT and security personnel, this is the highest level of access. It includes comprehensive privileges over all systems and applications, enabling these authorised users to modify, delete, or configure high-level settings as required for system management and security.
5. <mark style="background: #BABD00;">Privileged Access:</mark> At this level, users and systems are granted only the minimum levels of access—or permissions—necessary to perform specific functions. This careful allocation of privileges is crucial for minimising the attack surface and limiting the potential damage from security breaches or insider threats. This foundational principle of granting the least privilege necessary to complete your tasks is the core of the Zero Trust model.

Each of these access levels plays a vital role in the enforcement of Zero Trust principles, ensuring that security is maintained through meticulous control over who can access what within your network.

### <mark style="background: #BABD00;">Always Verify</mark>

In the Zero Trust model, the concept of implicit trust is completely abandoned in favour of constant verification. This approach operates under the assumption that a security breach is already present within your system.

Consequently, Zero Trust protocols strictly limit access privileges to only those necessary for specific tasks and continuously scan for signs of malicious activity. Implementing Zero Trust can significantly mitigate your risks associated with data breaches, ransomware, and insider threats.

Although this model imposes stricter access controls, it streamlines your organisation’s cybersecurity framework, facilitating a more manageable and secure system environment. This enhanced security architecture is crucial for safeguarding your data and assets.  
  
### <mark style="background: #BABD00;">Risk Mitigation</mark>

To effectively minimise the blast radius within a network, the Zero Trust framework advocates for an 'assume breach' approach. By segmenting the network into smaller, secure zones, this strategy enhances control over access and sharply curtails the possibility for threats to move laterally within the system.

This segmentation not only restricts access to sensitive areas but also contains potential breaches to isolated segments, dramatically reducing the overall risk and impact of security threats. This proactive and compartmentalised approach is essential for robustly defending against and swiftly responding to cybersecurity threats.

"Imagine your computer network is like a city, and each service or application is a building within that city. The 'blast radius' refers to how much damage a potential security breach could cause—just like how far the impact of an explosion might reach in a real city.

In cybersecurity, if a hacker gains unauthorised access to part of the network, the blast radius is the extent to which they can move from that entry point to other parts of the network. 

With a larger blast radius, hackers can access more data and cause more damage. By limiting the blast radius, you're essentially building walls or barriers between different parts of your "city" (or network). 

If one barrier is compromised, only those within that area would be impacted. The damage doesn't spread to other buildings behind other barriers."

<mark style="background: #BABD00;">TL;DR:</mark> the blast radius in cybersecurity is about the damage a breach can cause in a network. Strategies like network segmentation contain breaches and minimise this damage.

# <mark style="background: #BABD00;">21 Lab Notes CA2</mark>

# <mark style="background: #BABD00;">Week 5 - Docker:</mark>

![](https://i.imgur.com/MhqrXXK.png)

"Docker is a set of platform as a service (PaaS) products that use OS-level virtualisation to deliver software in packages called containers." - [from Wikipedia](https://en.wikipedia.org/wiki/Docker_(software)).

<mark style="background: #BABD00;">So stripping the jargon we get two definitions:</mark>
1. Docker is a set of tools to deliver software in containers.
2. Containers are packages of software.

![](https://i.imgur.com/8GLas4x.png)

# <mark style="background: #BABD00;">Week 8:</mark>

### <mark style="background: #BABD00;">API Gateway -  Qwik Start:</mark>

API Gateway enables you to provide secure access to your services through a well-defined REST API that is consistent across all of your services, regardless of service implementation. 

<mark style="background: #BABD00;">A consistent API:</mark>
- Makes it easy for app developers to consume your services.
- Enables you to change the backend service implementation without affecting the public API.
- Enables you to take advantage of the scaling, monitoring, and security features built into the Google Cloud.

API Gateway sits in front of a deployed backend service and handles all incoming requests.

### <mark style="background: #BABD00;">Pub/Sub: Qwik Start - Console</mark>

Pub/Sub is a messaging service for exchanging event data among applications and services. A producer of data publishes messages to a Pub/Sub topic. A consumer creates a subscription to that topic. 

Subscribers either pull messages from a subscription or are configured as webhooks for push subscriptions. Every subscriber must acknowledge each message within a configurable window of time.

A publisher application creates and sends messages to a topic. Subscriber applications create a subscriber to a topic to receive messages from it.

Cloud Pub/Sub is an asynchronous messaging service designed to be highly reliable and scalable.

### <mark style="background: #BABD00;">Cloud Run Functions: Qwik Start - Console</mark>

Cloud Run function is a piece of code that runs in response to an event, such as an HTTP request, a message from a messaging service, or a file upload. Cloud events are _things_ that happen in your cloud environment. These might be things like changes to data in a database, files added to a storage system, or a new virtual machine instance being created.

Since Cloud Run functions are event-driven, they only run when something happens. This makes them a good choice for tasks that need to be done quickly or that don't need to be running all the time.

<mark style="background: #BABD00;">For example, you can use a Cloud Run function to:</mark>
- automatically generate thumbnails for images that are uploaded to Cloud Storage.
- send a notification to a user's phone when a new message is received in Pub/Sub.
- process data from a Cloud Firestore database and generate a report.

You can write your code in any language that supports Node.js, and you can deploy your code to the cloud with a few clicks. Once your Cloud Run function is deployed, it will automatically start running in response to events.

Cloud Run functions is a serverless execution environment for event driven services on Google Cloud.

# <mark style="background: #BABD00;">Week 9:</mark>

### <mark style="background: #BABD00;">Network Load Balancer:</mark>

External passthrough Network Load Balancers are regional, layer 4 load balancers that distribute external traffic among backends (instance groups or network endpoint groups (NEGs)) in the same region as the load balancer. These backends must be in the same region and project but can be in different VPC networks. These load balancers are built on [Maglev](https://research.google/pubs/maglev-a-fast-and-reliable-software-network-load-balancer/) and the [Andromeda network virtualisation stack](https://cloudplatform.googleblog.com/2014/04/enter-andromeda-zone-google-cloud-platforms-latest-networking-stack.html).

<mark style="background: #BABD00;">External passthrough Network Load Balancers can receive traffic from:</mark>
- Any client on the internet
- Google Cloud VMs with external IPs
- Google Cloud VMs that have internet access through Cloud NAT or instance-based NAT

External passthrough <mark style="background: #BABD00;">Network Load Balancers</mark> are <mark style="background: #BABD00;">not proxies</mark>. The load balancer itself doesn't terminate user connections. 

Load-balanced packets are sent to the backend VMs with their source and destination IP addresses, protocol, and, if applicable, ports, unchanged. The backend VMs then terminate user connections. 

Responses from the backend VMs go directly to the clients, not back through the load balancer. This process is known as direct server return (DSR).

<mark style="background: #BABD00;">Backend service-based external passthrough Network Load Balancers support the following features:</mark>
- <mark style="background: #BABD00;">Managed and unmanaged instance group backends.</mark> Backend service-based external passthrough Network Load Balancers support both managed and unmanaged instance groups as backends. Managed instance groups automate certain aspects of backend management and provide better scalability and reliability as compared to unmanaged instance groups.
- <mark style="background: #BABD00;">Zonal NEG backends:</mark> Backend service-based external passthrough Network Load Balancers support using zonal NEGs with `GCE_VM_IP` endpoints. Zonal NEG `GCE_VM_IP` endpoints let you do the following:
    - Forward packets to any network interface, not just `nic0`.
    - Place the same `GCE_VM_IP` endpoint in two or more zonal NEGs connected to different backend services.
- <mark style="background: #BABD00;">Support for multiple protocols:</mark> Backend service-based external passthrough Network Load Balancers can load-balance TCP, UDP, ESP, GRE, ICMP, and ICMPv6 traffic.
- <mark style="background: #BABD00;">Support for IPv6 connectivity:</mark> Backend service-based external passthrough Network Load Balancers can handle both IPv4 and IPv6 traffic.
- <mark style="background: #BABD00;">Fine-grained traffic distribution control:</mark> A backend service allows [traffic to be distributed](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#traffic-distribution) according to a configurable [session affinity](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#session-affinity), [connection tracking mode](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#tracking-mode), and [weighted load balancing](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#weighted-lb). The backend service can also be configured to enable [connection draining](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#connection_draining) and designate [failover backends](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#failover) for the load balancer. Most of these settings have default values that let you get started quickly.
- <mark style="background: #BABD00;">Support for non-legacy health checks:</mark> Backend service-based external passthrough Network Load Balancers let you use [health checks](https://cloud.google.com/load-balancing/docs/network/networklb-backend-service#health-checks) that match the type of traffic (TCP, SSL, HTTP, HTTPS, or HTTP/2) that they are distributing.
- <mark style="background: #BABD00;">Google Cloud Armor integration:</mark> Google Cloud Armor supports advanced network DDoS protection for external passthrough Network Load Balancers. For more information, see [Configure advanced network DDoS protection](https://cloud.google.com/armor/docs/advanced-network-ddos).
- <mark style="background: #BABD00;">GKE integration:</mark> If you are building applications in GKE, we recommend that you use the built-in [GKE Service controller](https://cloud.google.com/kubernetes-engine/docs/concepts/service), which deploys Google Cloud load balancers on behalf of GKE users. This is the same as the standalone load balancing architecture described on this page, except that its lifecycle is fully automated and controlled by GKE.

<mark style="background: #BABD00;">Related GKE documentation:</mark> 
- [LoadBalancer Service concepts](https://cloud.google.com/kubernetes-engine/docs/concepts/service-load-balancer)
- [Exposing applications using Services](https://cloud.google.com/kubernetes-engine/docs/how-to/exposing-apps)

### <mark style="background: #BABD00;">Application Load Balancer</mark>

This document introduces the concepts that you need to understand how to configure an external Application Load Balancer.

An external Application Load Balancer is a proxy-based Layer 7 load balancer that enables you to run and scale your services behind a single external IP address. 

The external Application Load Balancer distributes HTTP and HTTPS traffic to backends hosted on a variety of Google Cloud platforms (such as Compute Engine, Google Kubernetes Engine (GKE), Cloud Storage, and so on), as well as external backends connected over the internet or via hybrid connectivity. 
For details, see [Application Load Balancer overview: Use cases](https://cloud.google.com/load-balancing/docs/application-load-balancer#use-cases).

<mark style="background: #BABD00;">Modes of operation:</mark>
- <mark style="background: #BABD00;">Global external Application Load Balancer</mark> This is a global load balancer that is implemented as a managed service on [Google Front Ends (GFEs)](https://cloud.google.com/docs/security/infrastructure/design#google-frontend-service). It uses the open-source [Envoy proxy](https://www.envoyproxy.io/) to support [advanced traffic management](https://cloud.google.com/load-balancing/docs/https/traffic-management-global) capabilities such as traffic mirroring, weight-based traffic splitting, request/response-based header transformations, and more.
- <mark style="background: #BABD00;">Classic Application Load Balancer:</mark> This is the classic external Application Load Balancer that is global in Premium Tier but can be configured to be regional in Standard Tier. This load balancer is implemented on [Google Front Ends (GFEs)](https://cloud.google.com/docs/security/infrastructure/design#google-frontend-service). GFEs are distributed globally and operate together using Google's global network and control plane.
- <mark style="background: #BABD00;">Regional external Application Load Balancer:</mark> This is a regional load balancer that is implemented as a managed service on the open-source [Envoy proxy](https://www.envoyproxy.io/). It includes [advanced traffic management](https://cloud.google.com/load-balancing/docs/https/traffic-management-regional) capabilities such as traffic mirroring, weight-based traffic splitting, request/response-based header transformations, and more.

### <mark style="background: #BABD00;">IAM Custom Roles:</mark>

Cloud IAM provides the right tools to manage resource permissions with minimum fuss and high automation. 

You don't directly grant users permissions. Instead, you grant them roles, which bundle one or more permissions. 

This allows you to map job functions within your company to groups and roles. Users get access only to what they need to get the job done, and admins can easily grant default permissions to entire groups of users.

<mark style="background: #BABD00;">There are two kinds of roles in Cloud IAM:</mark>
- Predefined Roles
- Custom Roles

<mark style="background: #BABD00;">Predefined roles:</mark> are created and maintained by Google. Their permissions are automatically updated as necessary, such as when new features or services are added to Google Cloud.

<mark style="background: #BABD00;">Custom roles</mark> are user-defined, and allow you to bundle one or more supported permissions to meet your specific needs. Custom roles are not maintained by Google; when new permissions, features, or services are added to Google Cloud, your custom roles will not be updated automatically. 

You create a custom role by combining one or more of the available Cloud IAM permissions. Permissions allow users to perform specific actions on Google Cloud resources.

Cloud IAM also provides the ability to create customised Cloud IAM roles. You can create a custom Cloud IAM role with one or more permissions and then grant that custom role to users. Cloud IAM provides a UI and API for creating and managing custom roles.

<mark style="background: #BABD00;">Key Point:</mark> Custom roles enable you to enforce the principle of least privilege, ensuring that the user and service accounts in your organisation have only the permissions essential to performing their intended functions.

<mark style="background: #BABD00;">Note:</mark> You can create a custom role at the organisation level and at the project level. However, you cannot create custom roles at the folder level.

You create a custom role by combining one or more of the available Cloud IAM permissions. Permissions allow users to perform specific actions on Google Cloud resources.

### <mark style="background: #BABD00;">Importing Data to a firestore database:</mark>

![](https://i.imgur.com/NyigvF8.png)

# <mark style="background: #BABD00;">Week 10:</mark>

### <mark style="background: #BABD00;">Build a Serverless Web App with Firebase</mark>

### <mark style="background: #BABD00;">Hosting a Web App on Google Cloud Using Compute Engine</mark>

There are many ways to deploy web sites within Google Cloud. Each solution offers different features, capabilities, and levels of control. 

Compute Engine offers a deep level of control over the infrastructure used to run a web site, but also requires a little more operational management compared to solutions like Google Kubernetes Engines (GKE), App Engine, or others. 

With Compute Engine, you have fine-grained control of aspects of the infrastructure, including the virtual machines, load balancers, and more.

<mark style="background: #BABD00;">Note:</mark> In a production environment, you may want to separate each microservice into their own instance and instance group to allow them to scale independently.

<mark style="background: #BABD00;">Note:</mark> Separate health checks for load balancing and for auto-healing will be used. Health checks for load balancing can and should be more aggressive because these health checks determine whether an instance receives user traffic. You want to catch non-responsive instances quickly so you can redirect traffic if necessary. In contrast, health checking for auto-healing causes Compute Engine to proactively replace failing instances, so this health check should be more conservative than a load balancing health check.

# <mark style="background: #BABD00;">Week 11:</mark>

### <mark style="background: #BABD00;">VPC Networking Fundamentals</mark>

Google Cloud <mark style="background: #BABD00;">Virtual Private Cloud (VPC)</mark> provides networking functionality to Compute Engine virtual machine (VM) instances, Kubernetes Engine containers and App Engine Flex. In other words, without a VPC network you cannot create VM instances, containers or App Engine applications. Therefore, each Google Cloud project has a <mark style="background: #BABD00;">default</mark> network to get you started.

You can think of a VPC network the same way you would think of a physical network, except that it is virtualised within Google Cloud. 

A VPC network is a global resource which consists of a list of regional virtual subnetworks (subnets) in data centres, all connected by a global wide area network (WAN). VPC networks are logically isolated from each other in Google Cloud.

Routes tell VM instances and the VPC network how to send traffic from an instance to a destination, either inside the network or outside of Google Cloud.

Each VPC network comes with some default routes to route traffic among its subnets and send traffic from eligible instances to the Internet.

Each VPC network implements a distributed virtual firewall that you can configure. Firewall rules allow you to control which packets are allowed to travel to which destinations.

Every VPC network has two implied firewall rules that block all incoming connections and allow all outgoing connections.

<mark style="background: #BABD00;">Notice that there are 4 Ingress firewall rules for the default network:</mark>
- ``default-allow-icmp``
- ``default-allow-internal``
- ``default-allow-rdp``
- ``default-allow-ssh``

These firewall rules allow <mark style="background: #BABD00;">ICMP</mark>, <mark style="background: #BABD00;">RDP</mark> and <mark style="background: #BABD00;">SSH</mark> ingress traffic from anywhere (0.0.0.0/0) and all **TCP**, **UDP** and **ICMP** traffic within the network (10.128.0.0/9). The <mark style="background: #BABD00;">Targets</mark>, <mark style="background: #BABD00;">Source filters</mark>, <mark style="background: #BABD00;">Protocols/ports</mark> and <mark style="background: #BABD00;">Action</mark> columns explain these rules.

The <mark style="background: #BABD00;">External IP addresses</mark> for both VM instances are ephemeral. If an instance is stopped, any ephemeral external IP addresses assigned to the instance are released back into the general Compute Engine pool and become available for use by other projects.

When a stopped instance is started again, a new ephemeral external IP address is assigned to the instance. Alternatively, you can reserve a static external IP address, which assigns the address to your project indefinitely until you explicitly release it.

### <mark style="background: #BABD00;">Service Accounts and Roles: Fundamentals</mark>

Service accounts are a special type of Google account that grant permissions to virtual machines instead of end users. 

Service accounts are primarily used to ensure safe, managed connections to APIs and Google Cloud services. 

Granting access to trusted connections and rejecting malicious ones is a must-have security feature for any Google Cloud project.

A service account is a special Google account that belongs to your application or a [virtual machine](https://cloud.google.com/compute/docs/instances/) (VM) instead of an individual end user. 

Your application uses the service account to [call the Google API of a service](https://developers.google.com/identity/protocols/OAuth2ServiceAccount#authorisingrequests), so that the users aren't directly involved.

For example, a Compute Engine VM may run as a service account, and that account can be given permissions to access the resources it needs. This way the service account is the identity of the service, and the service account's permissions control which resources the service can access.

A service account is identified by its email address, which is unique to the account.

 <mark style="background: #BABD00;">User-managed service accounts:</mark>
When you create a new Cloud project using Google Cloud console and if Compute Engine API is enabled for your project, a Compute Engine Service account is created for you by default. It is identifiable using the email:

`PROJECT_NUMBER-compute@developer.gserviceaccount.com`

If your project contains an App Engine application, the default App Engine service account is created in your project by default. It is identifiable using the email:

`PROJECT_ID@appspot.gserviceaccount.com`

<mark style="background: #BABD00;">Google-managed service accounts:</mark>
In addition to the user-managed service accounts, you might see some additional service accounts in your project’s IAM policy or in the console. These service accounts are created and owned by Google. These accounts represent different Google services and each account is automatically granted IAM roles to access your Google Cloud project.

<mark style="background: #BABD00;">Google APIs service account:</mark>
An example of a Google-managed service account is a Google API service account identifiable using the email:

`PROJECT_NUMBER@cloudservices.gserviceaccount.com`

This service account is designed specifically to run internal Google processes on your behalf and is not listed in the <mark style="background: #BABD00;">Service Accounts</mark> section of the console. 

By default, the account is automatically granted the project editor role on the project and is listed in the <mark style="background: #BABD00;">IAM</mark> section of the console. This service account is deleted only when the project is deleted.

<mark style="background: #BABD00;">Understanding IAM roles:</mark>
When an identity calls a Google Cloud API, Google Cloud Identity and Access Management requires that the identity has the appropriate permissions to use the resource. You can grant permissions by granting roles to a user, a group, or a service account.

<mark style="background: #BABD00;">There are three types of roles in Cloud IAM:</mark>
- <mark style="background: #BABD00;">Primitive roles:</mark> which include the Owner, Editor, and Viewer roles that existed prior to the introduction of Cloud IAM.
- <mark style="background: #BABD00;">Predefined roles</mark> which provide granular access for a specific service and are managed by Google Cloud.
- <mark style="background: #BABD00;">Custom roles:</mark> which provide granular access according to a user-specified list of permissions.

### <mark style="background: #BABD00;">Cloud Run Functions: Qwik Start - Command Line</mark>

A Cloud Run function is a piece of code that runs in response to an event, such as an HTTP request, a message from a messaging service, or a file upload. Cloud events are _things_ that happen in your cloud environment. These might be things like changes to data in a database, files added to a storage system, or a new virtual machine instance being created.

Since Cloud Run functions are event-driven, they only run when something happens. This makes them a good choice for tasks that need to be done quickly or that don't need to be running all the time.

<mark style="background: #BABD00;">For example, you can use a Cloud Run function to:</mark>
- automatically generate thumbnails for images that are uploaded to Cloud Storage.
- send a notification to a user's phone when a new message is received in Pub/Sub.
- process data from a Cloud Firestore database and generate a report.

You can write your code in any language that supports Node.js, and you can deploy your code to the cloud with a few clicks. Once your Cloud Run function is deployed, it will automatically start running in response to events.

<mark style="background: #BABD00;">Note:</mark> Cloud Run functions are event driven, meaning a trigger type must be specified. When deploying a new function, `--trigger-topic`, `--trigger-bucket`, or `--trigger-http` are common trigger events. When deploying an update to an existing function, the function keeps the existing trigger unless otherwise specified.

Serverless lets you write and deploy code without the hassle of managing the underlying infrastructure.
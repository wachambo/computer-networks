### Computer Networks DEF
Networking supports communication between two or more programs running on physically distant machines.
- WWW browser, mail, remote access to DB, remote shared files, download files...

### Network Topologies
Is its basic architecture, how components are logically connected.
* Point to point: technologies like RS232 simple serial lines 9,6Kbps, Fiber 2,5Gb
  * Short distance: dial-up lines (PPP protocol)
  * Long distance (SONET protocol)
* Star
  * LAN ATM, LAN Wireless
* Shared bus
  * Single line: LAN Ethernet
  * Token Ring: LAN FDDI

### Connecting different Topologies
* **NIC** (Network Internet Controller): provides the ability to access the transmission media cable or air, and process low-level network information.
* **Repeater:** receive a signal, cleans it of noise and regenerate it (Physical layer)
* **Hub:** repeater with multiple ports (Phy layer)
* **Bridge:** connect 2 networks segments (Data Link layer)
* **Switch:** like a Hub but only forwards the frames involved in the communication based on the MAC address in the packet, not all
* **Router:** forward packets or datagrams between different networks (Network layer)
* **Modem:** modulator-demodulator, connect network nodes via wire not originally designed for digital network traffic
* **Firewall:** control network security access


### OSI model
Open System Interconnection model.  
Is a conceptual model.  
Protocols enabled an entity in one host to interact with a corresponding entity at the same layer in another host.  



At each level, 2 entities (layer-N peers) exchange protocol data units (PDUs) by means of a layer-N protocol.  
Layer N-1 adds headers or footers, or both, to the PDU of layer N, composing a PDU of layer N-1

### Physical layer (OSI)
Basic transmission between all the hardware network technologies.  
Defines the means of transmitting raw bits rather than logical data packets over a physical link connecting network nodes.  
The bit stream may be grouped into code words or symbols and converted to a physical signal.  
Provides an electrical, mechanical, and procedural interface to the transmission medium.  
Specifies the shapes and properties of the electrical connectors, the frequencies, the modulation scheme to use.  
Protocols:
* Ethernet phy layer
* 802.11 WiFi phy layer
* DSL
* SONET
* Bluethoot phy layer

### RS232 Protocol
Standard communication protocol for linking computer and its peripheral devices to allow serial data Exchange


* **DTE** Data Terminal Equipment: end converter user info or reconverter the receive signal. 
* **DCE** Data Communication Equipment: between DTE’s i.e modem
* **TX** transmiter
* **RX** reciver 
* **GN** ground

### Syncronized data encoding
1. Unipolar: 1/+,  0/-
2. Polar
  1. NRZ (Non-Return-Zero): 1/+,  0/-(or zero)

  2. NRZS (NRZ-Space): 1/no change,  0/change
  3. NRZI (NRZ-Inverted): 1/transition,  0/no transition
3. Bipolar: +, -,  zero

### Self synchronizing data Encoding
1. Manchester: Data = Clock XOR Manchester

2. Differential Manchester:
  * In the data half-period makes a transition for 0 and no transition for 1
  * In clock half-period always begins with a transition from low to high or from high to low

3. 4B/5B + MLT3: 
  * 4B5B: maps groups of four bits onto groups of 5 bits
  * MLT3: cycles sequentially through the voltage levels −1, 0, +1. It moves to the next state to transmit a 1 bit, and stays in the same state to transmit a 0 bit

4. 8B/10B + PAM5
  * 4B5B: maps groups of four bits onto groups of 5 bits
  * PAM5: Pulse-Amplitude Modulation, the message is encoded in the amplitude of a series of signal pulses


### Radio Frecuency data Encoding: varying one or more properties of the carrier signal
* **AM** (Amplitude modulation)
* **FM** (Frecuency mod)
* **PM** (Phase mod)
* **QAM** = PM + AM

### Data Link (OSI)
Transfers data between adjacent network nodes in a WAN or between nodes on the same LAN segment.
And provides the means to detect and possibly correct errors that may occur in the physical layer
Sublayers:
* LLC (Logical Link Control): provides multiplexing mechanisms that make it possible for several network protocols (IP, IPX, Decnet and Appletalk) to coexist within a multipoint network and to be transported over the same network medium. It can also provide flow control and ARQ (automatic repeat request) error management mechanisms.
  * Protocols:
    * X.25
    * HDLC
    * PPP
* MAC (Media Access Control): provides addressing and channel access control mechanisms that make it possible for several network nodes to communicate within a multiple access network that incorporates a shared medium
  * Protocols:
    * CSMA/CD (in Ethernet), CSMA/CA (in WiFi WLAN)
    * Token bus, Token ring,..

### MAC Transmission
* Unicast
* Multicast
* Broadcast

### Physical or MAC Address
The local network addresses used in IEEE 802 and FDDI networks
A MAC address is a unique serial number.  
This makes it possible for data packets to be delivered to a destination within a subnetwork, i.e. hosts interconnected by some combination of repeaters, hubs, bridges and switches, but not by network layer routers. Thus, for example, when an IP packet reaches its destination (sub)network, the destination IP address is resolved with the ARP (Address Resolution Protocol) into MAC


### Channel access control mechanism
MAC layer provides a channel access control mechanism aka Multiple Access Protocol. This makes it possible for several stations connected to the same physical medium to share it.  
* Fixed assignment
FDMA (Frecuency Division Multiple Access)
TDMA (Time …)
* Contention-based: any computer in the network can transmit data at any time (first come-first served)
* Token-based or Reservation-based

### CSMA/CD (Carrier Sense Multiple Access with Collision Detection)



### Ethernet frame
A data packet on an Ethernet link is called an _Ethernet packet_, which transports an **Ethernet frame** as payload



### Network (OSI)
Responsible for packet forwarding including routing through intermediate routers, whereas the data link layer is responsible for media access control, flow control and error checking.  
Provides the functional and procedural means of transferring variable-length data sequences (datagrams) from a source to a destination host via one or more networks.  
Datagram delivery at the network layer is **not guaranteed to be reliable.**  
Protocols:
* IP
* ICMP
* ARP

### Network Connection model
* Connection-oriented comunication:
  Session or a semi-permanent connection is established before any useful data can be transferred, and where a stream of data is delivered in the same order as it was sent
* Connectionless comunication:
  Method used in packet switching networks by which each data unit is individually addressed and routed based on information carried in each unit, rather than in the setup information of a prearranged, fixed data channel as in Connection-oriented communication.

### Network Host Addressing
Every host in the network must have a unique address that determines where it is. This address is normally assigned from a hierarchical system.

### Network Message Fordwarding
Since many networks are partitioned into subnetworks and connect to other networks for wide-area communications, networks use specialized hosts, called gateways or routers, to forward packets between networks.













### IP Addressing space
1. Structure
  * IPv4 – 32 bits

  * IPv6 – 128 bits
2. Classes
3. Special addreses
  * Multicast: all class D addresses 
  * All class E addresses reserved -> Broadcast: 255.255.255.255 and others
  * Loopback 127.0.0.1/8
…

4. Networks / Subnetworks: logically visible subdivision of an IP network





### IP Protocol
IP packet consist of a header and a data section.

* IHL: Internet Header Length
* DSCP: Differenciated Services
* Identification: indentify the group of fragments of a single IP datagram
* Flags: to control or indentify fragments

### Host configuration in IP network

### DCHP (Dynamic Host Configuration Protol)
Networking protocol used on IP networks for dynamically distributing network configuration parameters, such as IP addresses.  
Computers request IP addresses and networking parameters automatically from a DHCP server, reducing the need for a network administrator or a user to configure these settings manually.

* DHCP DISCOVER
* DHCP OFFER
* DHCP REQUEST
* DHCP ACK/NACK
* DHCP RELEASE
* 
### ARP Protocol (Address Resolution Protocol)
Used for resolution of Network layer addresses into Link layer addresses, a critical function in multiple-access networks


### Routing algorithms

### Routing as routing and forwarding functions
Routing is the process of selecting best paths in a network.  
In packet switching networks, routing directs(controls) packet forwarding through intermediate nodes (routers, bridges, gateways, firewalls, or switches.  
General-purposecomputers can also forward packets and perform routing, though they are not specialized hardware and may suffer from limited performance). 
**How?** using routing tables which maintain a record of the routes to various network destinations. Thus, constructing routing tables, which are held in the router's memory, is very important for efficient routing. Most routing algorithms use only one network path at a time. Multipath routing techniques enable the use of multiple alternative paths.  

**Packet forwarding** is the relaying(transmission) of packets from one network segment to another by nodes in a computer network: move packets from router’s input to appropiate router output.  
Forwarding models:
* **Unicast** delivers a message to a single specific node
* **Broadcast** delivers a message to all nodes in the network
* **Multicast** delivers a message to a group of nodes that have expressed interest in receiving the message
* **Anycast** delivers a message to anyone out of a group of nodes, typically the one nearest to the source
geocast delivers a message to a geographic area

### Routing algorithm properties
1. Correctness: The routing should be done properly and correctly so that the packets may reach their proper destination.
2. Simplicity: The routing should be done in a simple manner so that the overhead is as low as possible. 
3. Robustness: Once a major network becomes operative, it may be expected to run continuously for years without any failures. The routing should handle hardware and software failures and should be able to deal with changes in the topology and traffic without requiring all jobs in all hosts to be aborted and the network rebooted every time some router goes down.
4. Stability: The routing algorithms should be stable under all possible circumstances.
5. Fairness: Every node connected to the network should get a fair chance of transmitting their packets. This is generally done on a first come first serve basis.
6. Optimality: The routing should be optimal in terms of throughput and minimizing mean packet delays. 

### Adaptive routing algorithms (Dynamic routing algorithms)
Change their routing decisions to reflect changes in the topology and in traffic as well. These get their routing information from adjacent routers or from all routers. The optimization parameters are the distance, number of hops and estimated transit time.  
Protocols:
* **RIP**
* **OSPF**

### Nonadaptive routing algorithms (Static routing algorithms)
Do not base their routing decisions on measurements and estimates of the current traffic and topology. Instead the route to be taken in going from one node to the other is computed in advance, off-line, and downloaded to the routers when the network is booted.

### The optimality principle
If a router J is on the optimal path from router I to router K, then the optimal path from J to K also follows the same route.  
**Proof:** if there was a better way from J to K, then you could use that.  

If you apply the optimality principle then you can form a tree by taking the optimal path from every other router to a single router, B. The tree is rooted at B. Since it is a tree you don't have loops, so you know that each frame will be delivered in a finite number of hops. Of course finding the set of optimal trees is a lot harder in practice than in theory, but it still provides a goal for all real routing algorithms.


### Static routing algorithms
1. Shortest path routing and Dijkstra algorithm:
Problem of finding a path between two nodes(routers) in a graph(network) such that the sum of the weights (number of hops, geographic distance, mean queuing/transmission delay, bandwidth, cost) of its constituent edges is minimized.   
**Dijkstra alg:** For a given source node in the graph, the algorithm finds the path with lowest cost (i.e. the shortest path) between that vertex and every other vertex




2. Routing by flooding:

### Dynamic routing algortithm
1. Distance Vector Routing and Bellman-Ford alg.
  E.g: Routing Information Protocol (RIP).  
  
  The whole algorithm doesn’t require a global picture, all participating routers only know about their direct connections to their neighbours and no others. Finding the shortest route is a distributed task, all routers exchange information and incrementally improve their forwarding tables until they are stable.  
  
  Steps:
  1. Send
  2. Receive
  3. Measure
  4. Calculate


  At this point, all the routers (A,B,C,D) have new "shortest-paths" for their DV (distance vector that are from them to another router via a neighbor). They each broadcast this new DV to all their neighbors.
  E.g: A receives a DV from C that tells A there is a path via C to D, with a distance of 5. Since the current "shortest-path" to C is 23, then A knows it has a path to D that costs 23+5=28

  **The Count-to-Infinite Prolem:**  
  The Bellman–Ford algorithm does not prevent routing loops. The core of the count-to-infinity problem is that if A tells B that it has a path somewhere, there is no way for B to know if the path has B as a part of it

2. Link state routing
  E.g: Open-Shortest-Path-First protocol (OSPF)

  * Learning about the neighbors
  * Measuring line cost
  * Building link state packets
  * Distributing the link state packets
  * Computing the new routes

### Transport (OSI)
Provides the functional and procedural means (resources) of transferring variable-length data sequences from a source to a destination host (end-to-end) via one or more networks, while maintaining the quality of service functions.

### Main transport layer functions
1. **Multiplexing/process-to-process communication:**
  Computer applications will each listen for information on their own ports, which enables the use of more than one network service at the same time

2. **End-to-end reliable communication:**
  Error recovery by means of (through) error detecting code and automatic repeat request (ARQ) protocol. The ARQ protocol also provides flow control, which may be combined with congestion avoidance.

### Transport layer services
1. **Connection-oriented:** 
  The communication session is established before any useful data can be transferred, and where a stream of data is delivered in the same order as it was sent.
  The communication may be a circuit switched connection, or a packet-mode virtual circuit connection.

2. **Same order delivery:**
  The network layer doesn't generally guarantee that packets of data will arrive in the same order that they were sent.
This is usually done through the use of segment numbering.

3. **Reliable data:**
  Packets may be lost during transport due to network congestion and errors. By means of an error detection code, such as a checksum, the transport protocol may check that the data is not corrupted, and verify correct receipt by sending an ACK or NACK message to the sender.
Automatic repeat request (ARQ protocol) schemes may be used to retransmit lost or corrupted data.

4. **Flow control:**
  The rate of data transmission between two nodes must sometimes be managed to prevent a fast sender from transmitting more data than can be supported by the receiving data buffer, causing a buffer overrun



5. **Congestion avoidance:**
  Network congestion occurs when a link or node is carrying so much data that its quality of service deteriorates. Typical effects include queueing delay, packet loss or the blocking of new connections
  For example, ARQ may keep the network in a congested state; this situation can be avoided by adding congestion avoidance to the flow control. 

6. **Byte orientation:**
  Data are processed bytewise (one byte at a time). That may involve transmission of additional bits as terminators, means of error recovery, etc.

7. **Ports:**
  Can provide multiple endpoints on a single node. 
Is an application-specific software construct serving as a communications endpoint to uniquely identify different applications or processes running on a single computer and thereby enable them to share a single physical connection.


### TCP (Transmission Control Protocol)
The protocol corresponds to the transport layer of TCP/IP suite. TCP provides a communication service at an intermediate level between an application program and the Internet Protocol (IP).  

TCP provides thee services for delivery of a stream of octets (bytes) between programs running on computers connected to a local area network, intranet or the public Internet:
* **Reliable:** guarantees that all bytes received will be identical with bytes sent and in the correct order. Acknowledgment with retransmission technique is used: requires the receiver to respond with an acknowledgment message as it receives the data.
* **Ordered and error-checked:** due to network congestion and other unpredictable network behavior, IP packets can be lost, duplicated, or delivered out of order. TCP detects these problems, requests retransmission of lost data, rearranges out-of-order data


While IP handles actual delivery of the data, TCP keeps track of the individual units of data transmission, called segments, that a message is divided into for efficient routing through the network.  

When an application program desires to send a large chunk of data (data stream) across the Internet using IP, the software can issue a single request to TCP and let TCP handle the IP details: divides it into chunks, and adds a TCP header creating a TCP segment. The TCP segment is then encapsulated into an IP datagram, and exchanged with peers.

### TCP Segment structure
A TCP segment consists of a segment header and a data section

* Data offset: size
* Control bits (NS, CWR, ECE, ACK….)
* Window Size: for Flow control

\* The term TCP packet appears in both informal and formal usage, whereas in more precise terminology segment refers to the TCP Protocol Data Unit (PDU), datagram to the IP PDU, and frame to the data link layer PDU

### TCP operation (3 phases)
1. TCP Connection stablishment
  * TCP 3-way handshake
    After Server executes LISTEN or ACCEPT, the Client execs CONNECT:





2. TCP Data transfer
  * TCP send-receive buffers
  * TCP acknowledgment
    * Packet loss case
      Timers must be used to handle the cases that TPDU's are lost.

    * ACK loss case
      Timers must be used to handle the cases that TPDU's are lost.


    * ACK delayed case
      The connection is automatically terminated if no TPDU is received for a certain number of seconds.


  * TCP sliding window: 
    Conceptually, each packet is assigned a unique consecutive sequence number, and the receiver uses the numbers to place received packets in the correct order, discarding duplicate packets and identifying missing ones. The problem with this is that there is no limit on the size of the sequence numbers that can be required.
    By placing limits on the number of packets that can be transmitted or received at any given time, a sliding window protocol allows an unlimited number of packets to be communicated using fixed-size sequence numbers

  * Sliding window performance
  * TCP flow control and congestion avoidance
Receiver changes window according to buffer consumption by application.
When the Window = 0, the sender don’t send segments

3. TCP Termination


### UDP (User Datagram Protocol)
Main functions:  
Computer applications can send messages, in this case referred to as datagrams, to other hosts on an Internet Protocol(IP) network without prior communications to set up special transmission channels or data paths.



### UDP segment structure


* Length: header + data
* Checksum: used for error-checking of the header and data
  UDP checksum calculation:
  All 16-bit words are summed using one's complement arithmetic (all 0s are converted into 1s and all 1s are converted into 0s) and puts this checksum value in UDP checksum field.

  In the receiver:  All 16-bit words are added including checksum. If receiver side checksum contains any 0 than, error is detected. So,the packet is discarded by receiver.

### UDP operation
UDP uses a simple transmission model with a minimum of protocol mechanism.  
It has no handshaking dialogues, and thus exposes any unreliability of the underlying network protocol to the user's program. As this is normally IP over unreliable media, there is no guarantee of delivery, ordering, or duplicate protection.  
UDP provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram.  

**TCP:**
  1. Reliable
  2. Ordered
  3. Heavyweight: needs 3 packets to set up a socket connection. Also handles reliability and congestion control.
  4. Streaming: data is read as a byte stream
**UDP:**
  1. UNReliable
  2. NOT Ordered
  3. Lightweight: no ordering of messages, no tracking connections, etc
  4. Datagrams: packets are sent individually and are checked for integrity only if they arrive
  5. NO congestion control

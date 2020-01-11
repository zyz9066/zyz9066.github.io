---
layout: post
title:  "Networking Basics"
date:   2018-07-01
tags:  [networking]
---
# Network Topologies
## Logical and Physical network Topologies
Physical topologies
* Refers to the physical layout of the wires in a network

Logical topologies
* Refers to how data moves through the network
* Refers to the pattern of data flow in a network

Networks can have different physical and logical topologies:
* Physical layout of wires in network follows one pattern.
* Data moves through the network in a different pattern.

## Mesh, Bus, and Ring Topologies
### Two Types of Mesh Topologies
Full mesh
* All devices directly connected to all other devices
* Provides full redundancy
* Most expensive type of topology
* Requires multiple NICs and cables for each node
* Most likely to be found in WAN environments

Partial mesh
* All devices directly connected to at least two other devices
* Provides strong redundancy but not full redundancy
* Not as expensive as full mesh

* multiple NICs and cable runs on each machine
* Most likely found in a WAN environment
* The Internet is a partial mesh.

### Bus Topology
* It is one of the oldest networking topologies.
* All nodes connect directly to main cable called the bus.
* It is simple to put together.
* Only one node can send a signal at a time.

* Contention is used to determine which node sends signal.
* The more nodes active, the more collisions on network.
* After collision, all nodes again contend to send signal.

* Too many collisions overload and bring down network.
* This is recommended for networks with 30 nodes or less.

* Least expensive of the various topologies
* Single bad node or cable brings down whole network
* Not part of current TA/EIA 568-C standard

### Ring Topology
* An older network topology
* Similar to bus topology but connected in a circle
* Packets move in ring around network
* Each node given opportunity to send a signal
* No contention between nodes

* Heavy traffic will not bring down network.
* Heavy traffic will slow down network.
* Single damaged node or cable can bring down network.
* This is not part of current TIA/EIA 568-C standard.

## Star and Hybrid Star Topologies
### Hierarchical Star Topology
* Most common topology used in LANs
* More expensive than bus because needs more cables
* Won't bring down network with one damaged node
* All nodes connected to a central hub or switch
* Easy to troubleshoot

* It's susceptible to a single point of failure.
* If whole network goes down, central device is a problem.
* If only single node goes down, that node is the problem.
* This is only topology recognized in TIA/EIA 568-C standard.

### Hybrid Star Topology
* Combines normal star topology with some other topology
* Physical hybrid star topologies
* Physical-logical hybrid star topologies

### Hybrid Star Topology
* Network containing two or more physical topologies
* Part of network ring another part star
* Switches linked as bus, but nodes connected as star

### Physical-Logical Hybrid Star Topology
* Network physically looks one way but functions differently
* Ring network that looks like a star
* Star network using hub
* Network looks like a star but works like a bus

### Physical-Logical Hybrid Star Ring Topology
### Physical-Logical Hybrid Star Bus Topology
## Point-to-Point and Point-to-Multipoint Topologies
### Point-to-Point Topologies
* Connects two nodes directly to each other with no intervening device
* Used to connect two ends of a WAN connection
* Used to connect computer directly to switch
* Used to connect switches or routers to each other

### Point-to-Multipoint Topologies
* Cross-over cable connecting two computers
* Is often part of a hybrid system
* Point to multipoint is same, except one device connects directly to more than one other device

## Client Server and Peer-to-Peer Network Management Models
### Peer-to-Peer Network
* Computer responsible for own security and management
* Each computer managed as separate device
* Usually only used for very small network
* Microsoft limits to only 10 systems per network
* Homegroup and Workstation are peer to peer.

* It is used in small businesses of two or three computers.
* Most home networks are peer-to-peer model networks.

### Client Server Network Model
* All devices access resources through central server.
* Devices needing access to network are called clients.
* Device/devices controlling access are called servers.

* Network management overseen by server.
* Security build around access to the server.
* Server allows or restricts access to network resources.
* Server controls who is allowed to log on to network.
* If server goes down, no one is able to access network.

## CSMA/CD and CSMA/CA
### Contention-Based Network Access
* Computers competing for network access
* Two types of contention-based access

Carrier Sensing Media Access/Collision Detection
* CSMA/CD
* Method most commonly used by wired Ethernet

Carrier Sensing Media Access/Collision Avoidance
* CSMA/CA

### CSMA/CD
Collision Detection
* Node listens for traffic on network.
* If traffic not heard, node releases packet onto network.
* If two nodes release packets at the same time, the packets hit each other and a collision occurs.
* A collision causes a power spike heard by all nodes.
* A collision destroys the data contained in the two packets.

CSMA/CA Operation
* If no collision, then transmission was successful.
* Network is now freed up for another node to transmit.

Collision Response
* If collision occurs, all nodes start internal clock set to a random number of milliseconds.
* When time runs down, each node can attempt to send a new transmission.

### CSMA/CA
* Work similarly to CSMA/CD
* Releases warning packet before releasing data packet
* If other nodes hear warning packet, they won't transmit.
* Once data packet heard, other nodes are able to transmit.
* Two warning packets transmitted at same time cause a collision.

## Internet vs. Intranets and Extranets
### Internet
* Worldwide publicly accessible infrastructure of cables, routers, switches, and servers
* Used to carry a wide variety of services

### Services Carried on the Internet
* Worldwide Web
* Email
* File Transfer Protocol
* VoIP
* Streaming video
* Online gaming
* Many other services

### Intranets
* Privately accessible infrastructure of cables, routers, switches, and servers
* Generally limited to a single company, organization, or group of companies
* Used to carry a wide variety of services like the Internet

### Extranets
* Privately held WAN infrastructure
* Generally owned by one company or organizations
* May allow others access for a fee for specific purposes
* Can be an intranet with selective business-related access
* Used to carry a wide variety of services like Internet
* Examples: Microsoft Azure and Amazon Web Services

# Network Implementations
## WANs and MANs
### WANs
* Stands for wide area networks
* One large network that covers a large geographic area
* Internet -- best-know WAN
* Can be many smaller networks linked into one large one
* Called an enterprise network when owned by one org
* Use routers and switches to connect up network

### MANs
* Stands for metropolitan area networks
* Uses same technology as WANs
* Covers an area of only 50 kilometers or so across
* Term falling out of use
* Term WAN used to apply to both WANs and MANs

## LANs, WLANs, and PANs
### LANs
* Limited in size
* Can be as small as a single room or big as a building
* Can also span several buildings close together

* TIA/EIA 568-C standard defines characteristics of LANs
* Normally uses twisted pair cabling to connect devices
* Should use CAT 6 or 6A in current LAN builds
* Hierarchical star only topology recognized by 568-C
* LAN nodes tied together with switches or hubs
* Can use fiber optic cables to connect switches

### WLANs
* Stands for wireless local area networks
* Is a standard LAN that uses wireless technologies
* Wireless technologies commonly referred to as Wi-Fi
* Wi-Fi technologies defined by IEEE 802.11 standard
* IEEE 802.11ac -- most current Wi-Fi standard
* More advanced IEEE 802.11ax standard being developed

### PANs
* Stands for personal area networks
* Defined by IEEE 802.15 standard group
* Primarily uses Blue Tooth technologies for connecting
* Limited range of less than 30 feet
* Devices like keyboards and mice can use PANs to connect to a computer

* Many phone use PANs to connect accessories.
* Earbuds to use phones while driving use PANs.
* Some watches use PANs to connect to smartphones.
* Infrared (IrDA) can also be used.

## SCADA/ICS and Medianets
### SCADA/ICS
* SCADA stands for Supervisory Control and Data Acquisition
* ICS stands for Industrial Control System
* Both refer to networks and technologies used to control industrial application

SCADA is a subset of ICS:
* SCADA describes systems that span large geographic areas.
* Examples include pipelines, power distribution, and water.

ICS is more generic in use:
* Normally refers to smaller scale systems
* Industrial automation
* Control system for power plant
* Control system for factory

### Medianets
* Networks optimized for distributing large video applications and similar technologies
* Examples: Hulu, Netflix, WebEx, and GoToMeeting
* Uses smart bandwidth detection systems
* Allows medianets to adjust to higher or lower bandwidth devices
* Provides smooth video transmission on any platform

# OSI Model
## Intro to OSI Model
### OSI Model
* Stands for Open Systems Interconnection Reference Model
* Created as a reference model and teaching aid
* Not intended to reflect any actual network architecture

* Device to teach how protocols work with networks to carry data
* Model for organizations creating new protocols

|Application Layer|
|Presentation Layer|
|Session Layer|
|Transport Layer|
|Network Layer|
|Data Link Layer|
|Physical Layer|

## Two Parts of the OSI Model
Abstract model: The actual model with its seven layers  
Set of specifically created protocols: Protocols not actually used in any network system

## Published by Two Organizations in 1984
* International Standards Organization (ISO)
* Published as ISO 7498 standard
* Telecommunications Standardization Sector of the International Telecommunications Union (ITU-T)
* Published under ITU-T X.200

[The OSI Model's Seven Layers Defined and Functions Explained](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model)
## Physical Layer
* Bottom layer
* Concerned with physical transmission of raw data
* Transmits data in the form of 1s and 0s
* Defines encoding methods to transmit data
* Defines how bits are placed on media
* Defines how to know when bits start and stop

* Defines specifications for media usage
* Defines kinds of media permitted
* Defines how physical connections are made
* Defines pin usage in physical connections
* Specifies standards that apply to specific types of media

## Data Link Layer
* Provides error-free transmission from one node to the next over physical media
* Establishes and terminates links between nodes
* Responsible for traffic control
* Transmits and receives frames sequentially

* Responsible for frame acknowledgment
* Provides and expects frame acknowledgment
* Detects and recovers from errors on physical layer
* Retransmits nonacknowledged frames
* Handles duplicate frame receipt

* Responsible for frame delimiting
* Creates and recognizes frame boundaries
* Responsible for error checking
* Checks received frames for data integrity
* Provides media access management
* Determines when node is allowed to use physical media

## Network Layer
* Controls the operations of the subnetwork it is on
* Determines best physical path for data
* Uses network conditions to choose best path
* Uses priority of service to determine best path
* Uses other factors to determine best path

### Network Layer Provides Several Functions
Routing
* Routes frames among connected networks

Subnet traffic control
* Allows routers to send instructions to sending nodes to "throttle back" frame transmissions when buffers are filled

Frame fragmentation
* Determines frame size of routers located down stream
* Frame size called maximum transmission unit size
* Allows router to fragment frame into smaller sizes if needed
* Reassembles the full frame at destination

Logical-physical address mapping
* Translates logical addresses into physical addresses

Subnet usage accounting
* Has function that allows device to keep track of frames forwarded by subnet intermediate systems
* Use this to produce billing information

### Network Layer Communications Subnets
* Build headers used by network layer on other devices to route packets to destination
* Relieve higher layers of the need-to-know data transmission and switching technologies
* Use protocols on lower layers to send data to destinations separated by intermediate nodes
* Send information between adjacent nodes

## Transport Layer
* Ensures messages delivered error-free
* Ensures messages delivered in sequence
* Ensures messages delivered with no loss or duplication
* Relieves higher protocols of concern for transfer of data
* Size and complexity of transport protocols dependent on service provide by network layer

### Message Segmentation Function
* Accepts messages from session layer
* Splits message into smaller units
* Imposes message size limits on network layer protocols
* Prepares header for each smaller unit created
* Passes smaller units to network layer
* Reassembles message at destination

* Header for smaller units contain certain elements
* Header contains start and end flags
* Header contains sequence information

### Other Transport Layer Functions
Message acknowledgment
* Provides reliable end-to-delivery of messages
* End-to-end delivery accompanied by acknowledgment

Message traffic control
* Controls rate of traffic sent when no buffers available

Session multiplexing
* Breaks all the data coming in on one link into separate data streams
* Those data streams called sessions
* Tracks which message belongs to which session

### End-to-End Layers
* Transport layer and above layers not responsible for transmission between nodes
* Transport and above layers responsible for source to destination transmission
* Source-to-destination transmissions also called end-to-end transmissions
* Upper layers not concerned with underlying communications facility

## Session Layer
* Responsible for establishing sessions between processes running on different computers
* Provides several functions to accomplish this
* Session establishment, maintenance, and termination
* Session support

### Establishment Maintenance Termination
* Allows application processes on different machines to do several things between the machines
* Allows processes to establish a connection
* Allows processes to use a connection
* Allows processes to terminate a connection
* Each connection called a session

### Session Support
* Performs the function of allowing processes to communicate over network
* Performs security
* Performs name recognition
* Performs logging on
* Performs other functions that are less common

## Presentation Layer
* Formats data to be presented to the application layer
* Translator for the network
* At sending station translates data from application layer format to common format
* At receiving station translates data from common format to format used by application layer

### Presentation Layer Functions
Character code translation
* ASCII to EBCDIC

Data conversion
* Bit order
* CR-CR/LF
* Integer-floating point

Data compression
* reduces number of bits needed to transmit data

Data encryption
* Encryption of data for security purposes
* Encryption of passwords

## Application Layer
* Serves as window for uses and applications to access network services
* Provides a variety of commonly used functions

### Application Layer Common Functions
* Resource sharing
* Device redirection
* Remote file access
* Remote printer access

* Network management
* Directory services
* Email
* Instant messaging

## Encapsulation and De-encapsulation
* Each layer of OSI model adds a header to the data.
* Layers also create a unit used to send or receive data.
* The process of moving data down the OSI model is called encapsulation.
* The process of moving data up the OSI model is called de-encapsulation.

### Each Layer Has an Encapsulation Unit
* Information on application layer through session layer is called data.
* Transport layer converts data to segments.
* Network layer converts segments to packets.
* Data link layer converts packets to frames.
* Physical layer converts frames to bits.

| Application Layer | Data |
| Presentation Layer | Data |
| Session Layer | Data |
| Transport Layer | Segment |
| Network Layer | Packet |
| Data Link Layer | Frame |
| Physical Layer | Bits |

## How the Layers Work Together

|**Operating System**|||||||<small>Data</small>||
|**Application Layer**||||||<small>Application Header</small>|<small>Data</small>||
|**Presentation Layer**|||||<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>||
|**Session Layer**||||<small>Session Header</small>|<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>||
|**Transport Layer**|||<small>Transport Header</small>|<small>Session Header</small>|<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>||
|**Network Layer**||<small>Network Header</small>|<small>Transport Header</small>|<small>Session Header</small>|<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>||
|**Data Link Layer**|<small>Data Link Header</small>|<small>Network Header</small>|<small>Transport Header</small>|<small>Session Header</small>|<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>|<small>Data Link Trailer</small>|
|**Physical Layer**|<small>Data Link Header</small>|<small>Network Header</small>|<small>Transport Header</small>|<small>Session Header</small>|<small>Presentation Header</small>|<small>Application Header</small>|<small>Data</small>|<small>Data Link Trailer</small>|

Sending OS/Receiving OS
# TCP/IP Model
## TCP/IP Suite
* Group of protocols designed to work together to send data across a network  
* Named after two major protocols in the suite
TCP -- Transport Control Protocol  
IP -- Internet Protocol
* Contains a large number of protocols that are able to carry many different network functions

* It is an open protocol suite.
* Suite is free for all to use.
* New protocols can be freely developed as needed.
* It is the protocol used by the Internet.
* Pretty much all existing networks use TCP/IP as their main transmission protocol.

## TCP/IP Model
* Was created by the Department of Defense in the 1970s
* Is a reduced version of the OSI model
* Is based on and around the TCP/IP protocol suite

Has four layers:
* Application layer
* Transport layer
* Internet layer
* Network access or network interface layer

* All TCP/IP protocols are located on the top three layers.
* Protocols located on bottom layer are not part of the TCP/IP suite.
* Each layer corresponds to one or more OSI model layers.

### TCP/IP Reference Model

|Application Layer|SMTP, FTP, HTTP, DNS, TFTP, RIP, SNMP|
|Transport Layer|TCP, UDP|
|Internet Layer|ARP, RARP, IP, IGMP, ICMP|
|Network Interface Layer|Ethernet, 802.11 Wireless LAN, Frame Relay, ATM|

## Application Layer
* Defines protocols, services, and processes that allow programs and users to interface with the network
* Defines how programs interface with the transport layer services to use the network

### Common Application Layer Protocols
* HTTP
* Telnet
* FTP
* TFTP
* SNMP
* DNS
* SMTP
* X Windows

## Transport Layer
* Provides communications session management between host computers
* Defines level of service and status of connections used when transporting data

### Common Transport Layer Protocols
* TCP
* UDP
* RTP

## Internet Layer
* Internet layer packages data into IP datagrams called packets.
* Header of packet contains source and destination information.
* Internet layer uses this information to forward packets between hosts across the network.
* It performs routing of IP packets.

### Common Internet Layer Protocols
* IP
* ICMP
* ARP
* RARP

## Network Interface Layer
* Sometimes called Network Access Layer
* Specifies how data is physically sent though a network
* Specifies how bits are electrically signaled by hardware
* Defines how hardware devices interface with network medium
* Examples: Coaxial cable, optical cable, and twisted pair cable

### Standards Defined by This Layer
* Ethernet
* Token Ring
* FDDI
* X.25
* Frame Relay
* RS-232
* V.35

## TCP/IP vs. OSI Model

|Application Layer|Application Layer<br>Presentation Layer<br>Session Layer|
|Transport Layer|Session Layer<br>Transport Layer|
|Internet Layer|Network Layer<br>Data Link Layer|
|Network Interface Layer|Data Link Layer<br>Physical Layer|

# Commonly Used Network Devices
## NICs
* Stands for network interface card or controller
* Allows a computer or other device to access the network
* Can come in the form of an expansion card
* Can be built into the motherboard
* Works on layers 1 and 2 of the OSI model

### NIC Must Match Technology Being Used
* Needs to match media technology
Using 802.11n Wi-Fi, use 802.11n NIC  
Using UTP cabling, use UTP NIC
* Needs to match the speed being used
Gigabit Ethernet speed network use Gigabit Ethernet NIC
* Needs to match network architecture
If you have a Token Ring network, then use a Token Ring NIC
If you have an Ethernet network, then use an Ethernet NIC

## Hubs
* Order technology
* Technology is falling out of use in favor of switches
* Work on layer 1 of the OSI model
* Logically function as a bus topology
* Too many hosts can result in constant collisions

### Three Main Types of Hub
* Passive hubs
* Active hubs
* Intelligent hubs

#### Passive Hubs
* Work like cable splitters
* The more devices, the weaker the signal to each device

#### Active Hubs
* Need a power source
* Power added to the signal when passed though port
* Prevents weakening of signal by multiple devices being attached
* Repeats signal to all hosts connected to hub

* They can be used to connect multiple hubs.
* When connecting hubs, must follow 5-4-3 rule.
* No more than 5 segments can be linked together.
* Up to 4 linking devices only can be used to form segments.
* Only 3 segments can be populated by computers.

##### 5-4-3 Rule
#### Intelligent Hubs
* They are really active hubs with additional features.
* Some have network diagnostic abilities.
* Some have management abilities.
* Intelligent hubs with other abilities are available.

## Bridges
* Device used to break up a network into smaller segments
* Is an older technology
* Works on layer 2 of the OSI model
* Can read frames to determine if they are allowed to pass

## Switches
* A device used to connect multiple computers together
* Primarily works on layer 2 of the OSI model
* Some can work on layer 2 as well as higher layers
* When a switch can work on more than 1 layer, it is called a multilayer switch.

#### Basic Switch
* Most common type of switch
* Is essentially a multiport bridge
* Used to separate larger networks into smaller segments
* These segments called collision domains

* Use ports to set up point-to-point connections between devices connected to the affected ports
* Results in no collisions on network
* Allows different ports to communicate at full speed
* Makes it harder to listen in to traffic on the network

* Commonly used to convert media from one type to another
* Some switches have fiber coming into them
* But send signals out over copper twisted pair wires

#### Managed and Unmanaged Switches
* Management switches
Are programmable  
Used to control how data behaves on the network  
Most often found in corporate environments
* Unmanaged switches
They generally come with a default configuration.  
Most can only be changed within predefined limits.  
Some cannot be changed at all.  
Most home or SOHO switches are unmanaged.

## Routers
* Move data around large networks like WANs
* Primarily use layers 3 and 4 of the OSI model
* Are intelligent
* Make independent decisions about sending data

### Criteria Used to Determine Route
* Hops
* Network traffic
* Network throughput
* Network reliability
* Create tables based off this information
* Update tables to always know best route

### Routers Are Programmable
* Have to have their interfaces configured
* Have to be told which networks they are connected to
* Have to define criteria for what is not allowed though routers
* Can be programmed for multiple protocols

## Access Points
* Devices that allow computers to access the network
* Commonly used to connect home computers to Internet
* Can either be wired to wireless
* Home and SOHO access points are commonly wireless
* Wireless access points are also called WAPs

### Wireless Access Points Very Common
* Wireless public access points are found in many areas
* Used in libraries
* Used in restaurants
* Used in airports
* Many other locations

### WAPs Also Type of Connectivity Device
* Used to offer wireless access to a network
* Can offer several features like authentication and encryption
* Combine the role of switches and routers
* Can be programmed to a limited extent

# Conclusion
[Networking Fundamentals](https://social.technet.microsoft.com/wiki/contents/articles/8172.exam-98-366-networking-fundamentals.aspx)  
[Training and Certification Portal](https://social.technet.microsoft.com/wiki/contents/articles/7656.wiki-training-and-certification-portal.aspx)

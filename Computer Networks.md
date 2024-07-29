### Types of Networks

|                        |         **PAN**         |      **LAN**       |               **CAN**                |          **MAN**          |       **WAN**        |
| ---------------------- | :---------------------: | :----------------: | :----------------------------------: | :-----------------------: | :------------------: |
| **Full Form**          |  Personal Area Network  | Local Area Network |         Campus Area Network          | Metropolitan Area Network |  Wide Area Network   |
| **Technology**         | Bluetooth, IrDA, Zigbee |  Ethernet, Wi-Fi   |               Ethernet               |      FDDI, CDDI, ATM      | Leased Line, Dial-Up |
| **Range**              |       1 m - 100 m       |       < 2 Km       |             1 Km - 5 Km              |       5 Km - 50 Km        |       > 50 Km        |
| **Transmission Speed** |        Very High        |     Very High      |                 High                 |          Average          |         Low          |
| **Area**               |      Within a Room      |  Within Building   | Within University, Corporate offices |        Within City        |   Within Countries   |
| **Ownership**          |         Private         |      Private       |               Private                |     Private or Public     |  Private or Public   |
| **Maintenance**        |        Very Easy        |        Easy        |               Moderate               |         Difficult         |    Very Difficult    |
| **Error rate & Cost**  |        Very Low         |        Low         |               Moderate               |           High            |      Very High       |

### Protocols

Set of rules that govern data communication.

### Layering

Decomposing the network into more manageable components (layers). There are two architectures of layering the network:

1. The **OSI** model
2. The **TCP/IP** model
---
# OSI Model

- OSI -> Open System Interconnection
- It is a model for designing a network architecture that is flexible, robust and interoperable.
- Developed by ISO - International Standards for Organisations.
- Has 7 layers:
<img src = "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Finsights.profitap.com%2Fhs-fs%2Fhubfs%2FThe%25207%2520Layers%2520of%2520OSI.png%3Fwidth%3D560%26name%3DThe%25207%2520Layers%2520of%2520OSI.png&f=1&nofb=1&ipt=e495cebc35be8aa4dbb9af2a03ac5cd1f160d524eb52c6ee3694b7944a7806c8&ipo=images" height = 400>

## Physical Layer

- Last layer in Sender side, First layer in Receiver side
- Deals with hardware, i.e. physical devices:
	- Topologies
	- Cables, Connectors etc.
	- Hubs, Repeaters, Routers etc.
- Deals with Signal type and Signal Transmission method

Data unit here is a **Bit**, the smallest unit of digital information (either 0 or 1).

A Node can either send, receive or do both. Depending on what they do, they are categorized into:
- **Simplex** -> Only send or receive.
- **Half-Duplex** -> Can send and receive both, but not simultaneously. Only one process at a time is permitted.
- **Duplex** -> Can send and receive both, and can perform simultaneously.

## Data Link Layer

Deals with:
- Errors when they are detected in this flow
- How long a node should be allowed to transmit or receive data
- How much data should be allowed to transmit

There are two sub-layers in this layer:

- **MAC** -> Media Access Control:
	- MAC Address is a unique hardware identification number.
	- This is given to a device at the time of manufacture. 
	- It lives on NICs (Network Interface Cards)

- **LLC** -> Logical Link Control:
	- Handles framing addressing and flow control.

Data unit in this layer is a **frame**. 

A frame consists of a *frame header*, *frame body* and *frame trailer*.
- *Header* includes MAC addresses of source and destination nodes.
- *Body* contains the bits being transmitted.
- *Trailer* contains error detection information.

## Network Layer

Deals with:
- Communications between Nodes or Networks or both
- **Routers** specialize in this layer as they facilitate this functionality

Data unit here is a **data packet**. 

A data packet consists of a frame, plus an *IP Address* information wrapper.

### IP Address

Internet Protocol Address
- IP Addresses are network identifiers, i.e. these help in identifying a device in a network.
- There are two types:
	- IPv4 -> Internet Protocol version 4; written in decimal
	- IPv6 -> Internet Protocol version 6; written in hexadecimal

## Transport Layer

Deals with:
- Line Discipline, Flow control, Error control
- Data packet segmentation

Transport layer also has understanding of message. So it can control flow by not sending the whole message at a time, and hence reduce network congestion.

**Transmission Control Protocol (TCP)** and **User Datagram Protocol (UDP)** are the most known protocols in Transport layer.

Data unit here is:
- **Data packet** for TCP
- **Datagram** for UDP

TCP:
- is a connection-oriented protocol
- prioritizes on data quality over speed
- establishes a connection with receiver node and requires a handshake during data is transmitted. The handshake confirms data was received. If not, TCP demands a retry.
- also ensures packets are delivered or reassembled in correct order

UDP:
- is a connection-less protocol
- prioritizes speed over quality
- doesn't require a *handshake*; thus it can send data faster, although not guaranteed that all of the data reaches the receiver
- doesn't ensure the packets are in order, unless the information is split into datagrams and they have a sequence number

TCP and UDP both send to specific ports of a network device, which has an IP address. The combination of IP Address and Port number is called a **socket**. 

## Session Layer

A **Session** is a connection established between two specific end-user applications.

So this layer establishes, maintains and terminates sessions.

- Client-Server Model: Client is the one requesting information, Server is the one with the information and is being requested for it.
- Request and Response Model: While a session is live, there are continuous back-and-forth requests and responses. If the requested information doesn't exist, the response is something like "I don't have this information".

Examples of Protocols in this layer are:
- NetBIOS -> Network Basic Input Output System
- RPC -> Remote Procedure Call

## Presentation Layer

Deals with:
- Data formatting, such as character encoding and conversions
- Data encryption

This layer makes sure that end-user applications operating here can successfully consume data and display it.

Data formatting is in three methods:
- ASCII -> American Standard Code for Information Interchange
- EBDCIC -> Extended Binary-Coded Decimal Interchange Code
- Unicode

Encryption is done in two methods:
- SSL
- TLS

 > TLS is the successor of SSL

## Application Layer

This is the topmost layer, responsible for supporting services used by end-user applications.

Protocols working in this layer include:
- File Transfer Protocol (FTP)
- Secure Shell (SSH)
- Simple Mail Transfer Protocol (SMTP)
- Internet Message Access Protocol (IMAP)
- Domain Name Service (DNS)
- Hypertext Transfer Protocol (HTTP)
---
# TCP/IP

- TCP/IP -> Transmission Control Protocol / Internet Protocol
- Developed prior to OSI model
- Developed by ARPANET
- Unlike OSI model, TCP/IP is actually implemented
- Has 4 / 5 layers:
<img src = "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdocs.mevspace.com%2Fen%2Fstatic%2F83c05c5fac51fd68cd8938dbd408db61%2Fa94c1%2Ftcp-ip-model.png&f=1&nofb=1&ipt=c4c293e0c313c41dd3f461ede6fc76020279c0725d5d9e40ef18ccaddb7cafc6&ipo=images" height = 600>
- The *Network Interface layer* is sometimes split up just like OSI model into:
	- Data layer
	- Physical layer


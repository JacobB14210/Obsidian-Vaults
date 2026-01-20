# Networking Basics
## Networking Overview
- Wedding cake architecture: Layers provide services to the layer below it
- Application to application layer communication
## Physical Layer
- Network interface: Device connecting computer to a network
	- Ethernet card, wifi adapter, cellphone antenna
	- A computing device may have multiple network interfaces
- Most LANs broadcast frames
## Data Link Layer
- Data Link Layer: Responsible for data transmission in a LAN
	- Examples: Ethernet and wifi
- Logical Link Layer
	- Services for flow control, acks, and correction physical errors
- Medium Access Control (MAC) layer
	- Defines the protocol for data transfers
	- Most Network interfaces come with a predefined MAC address (48 bit number in hex)
	- Organizations use MAC addresses to identify computers on their network
## Networking Layer
- Network Layer: Principle responsibilities are routing a delivery
- Connectionless: Each packet is transported independently from other packets
- Unreliable: Delivery on a best effort basis
- IP Packets
	- IPv4: 32 bit addresses
	- IPv6: 128 bit addresses
## Transport Layer
- Transport Layer protocols may guarantee QoS including
	- Reliable data transfer
	- Message sequencing
	- An ability to distinguish data from multiple concurrent apps
- TCP connections established by a 3 way handshake
	- Client requests a connection by sending out a SYN packet
	- Server responds by sending a SYN/ACK packet, indicating an ack for the connection
	- Client responds with ACK to the server establishing connection
## Application Layer
- Application Layer: One closest to the end users, and the one application developers deal with
	- Examples: HTTP for the web, SMTP, POP, IMAP for email
	- IANA assigns port numbers for these services
## Protocols
- Protocols: Defines rules for communication between computers
- Low level protocols: Connectionless and connection oriented
	- Connectionless: Send out data as soon as enough to transmit
		- Typically stateless
	- Connection-oriented protocol: Provides a reliable connection stream between two nodes
		- Consists of set up, transmission, and tear down phases
- Higher level protocols may be asynchronous
# TCP IP in Depth
# IP Layer
- Connectionless: Each packet is transported independently from other packets
- IP packets: Encapsulate TCP and UDP packets
	- Encapsulate into link layer frames
- Unreliable: A "best effort" service
	- Delivery on a best effort basis
	- No ACKs, packets may be lost, reordered, corrupted, or dup'd
	- Errors communicate back via ICMP messages
- IP addresses and Packets
- IP header includes
	- Source and destination addresses
	- Type of service
	- Header check sum
	- Packet length
	- Time to live
	- IP protocol version
	- Fragmentation: Information for reassembly if data is split into multiple packets
	- Protocol information
- Routers bridges two or more networks
- Internet Control Message Protocol (ICMP)
	- Used for network testing and debugging
	- Simple messages encapsulated in single IP packets
	- Considered a network layer protocol
## Network Address Translation
- Private addresses: Address for only your private network
- Public address: Address for the outside world to view
# TCP Layer
- TCP guarantees:
	- reliable data transfer
		- Sends an ACK to indicate successful receipt of the packet
	- In order delivery of messages
	- Ability to distinguish data from multiple concurrent applications on the same host
- TCP and UDP use same port numbers for same apps
	- Ports 0 - 1023 are reserved for use by known protocols
	- Ports 1024 - 49151 are known as user ports, and should be used by most user programs for listening to connections and the like
	- Ports 49152 - 65535 are private ports used for dynamic allocation by socket libraries
- 
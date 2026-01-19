# Networking Overview
- Wedding cake architecture: Layers provide services to the layer below it
- Application to application layer communication
# Physical Layer
- Network interface: Device connecting computer to a network
	- Ethernet card, wifi adapter, cellphone antenna
	- A computing device may have multiple network interfaces
- Most LANs broadcast frames
# Data Link Layer
- Data Link Layer: Responsible for data transmission in a LAN
	- Examples: Ethernet and wifi
- Logical Link Layer
	- Services for flow control, acks, and correction physical errors
- Medium Access Control (MAC) layer
	- Defines the protocol for data transfers
	- Most Network interfaces come with a predefined MAC address (48 bit number in hex)
	- Organizations use MAC addresses to identify computers on their network
# Networking Layer
- Network Layer: Principle responsibilities are routing a delivery
- Connectionless: Each packet is transported independently from other packets
- Unreliable: Delivery on a best effort basis
- IP Packets
	- IPv4: 32 bit addresses
	- IPv6: 128 bit addresses
# Transport Layer
- Transport Layer protocols may guarantee QoS including
	- Reliable data transfer
	- Message sequencing
	- An ability to distinguish data from multiple concurrent apps
- TCP connections established by a 3 way handshake
	- Client requests a connection by sending out a SYN packet
	- Server responds by sending a SYN/ACK packet, indicating an ack for the connection
	- Client responds with ACK to the server establishing connection
# Application Layer
- 
## The TCP/IP Model

The TCP/IP model describes how data travels across networks, using four layers:

1.  **Application Layer:** This is the user-facing layer, providing network services to applications. Examples include:
    *   HTTP (Web Browsing)
    *   SMTP (Email)
    *   DNS (Domain Name Resolution)
    *   FTP (File Transfer)

2.  **Transport Layer:** Responsible for end-to-end data delivery.  Key protocols:
    *   TCP (Transmission Control Protocol): Reliable, ordered, and error-checked delivery. Used when data integrity is crucial.
    *   UDP (User Datagram Protocol): Connectionless, unreliable delivery.  Faster, but doesn't guarantee delivery or order. Used when speed is paramount (e.g., streaming).

3.  **Network Layer (Internet Layer):** Routes data packets across networks using IP addresses. The primary protocol is:
    *   IP (Internet Protocol): Defines how devices are addressed and packets are routed.

4.  **Link Layer (Network Interface Layer):** Handles the physical transmission of data over the network medium (e.g., Ethernet, Wi-Fi).  Interacts with hardware.

**How it Works (Simplified):**

1.  You interact with an application (Application Layer).
2.  The application uses a protocol (e.g., HTTP, SMTP).
3.  The Transport Layer (TCP or UDP) segments and adds headers.
4.  The Network Layer (IP) adds IP addresses, creating packets.
5.  The Link Layer formats packets into frames for transmission.
6.  The process reverses at the receiver to reconstruct the data.

## The OSI Model

The Open Systems Interconnection (OSI) model is a conceptual framework that describes how network devices communicate. It divides the communication process into seven distinct layers, each with specific functions. Understanding the OSI model is crucial for network troubleshooting, security analysis, and general networking knowledge.

Here's a breakdown of the seven layers:

1.  **Application Layer:** This is the layer closest to the user, providing network services to applications. It's where users interact with the network. Examples of protocols at this layer include:
    *   HTTP (Hypertext Transfer Protocol): Web browsing
    *   SMTP (Simple Mail Transfer Protocol): Email
    *   DNS (Domain Name System): Domain name resolution

2.  **Presentation Layer:** This layer is responsible for data formatting and encryption. It ensures that data is presented in a consistent format regardless of the underlying system.  It handles things like character encoding and data compression.

3.  **Session Layer:** This layer manages communication sessions between applications. It establishes, maintains, and terminates connections.  It handles things like synchronization and checkpoints.

4.  **Transport Layer:** This layer provides reliable end-to-end delivery of data between applications. It segments data, adds headers, and handles flow control and error correction.  Key protocols include:
    *   TCP (Transmission Control Protocol): Reliable, ordered, and error-checked delivery.
    *   UDP (User Datagram Protocol): Connectionless, unreliable delivery (faster, used for streaming).

5.  **Network Layer:** This layer is responsible for routing data packets across networks. It adds IP addresses to packets for routing. The primary protocol is:
    *   IP (Internet Protocol): Addressing and routing packets.

6.  **Data Link Layer:** This layer handles data transmission within a local network. It formats data into frames and includes MAC addresses for identifying devices on the same network.  It also handles error detection and correction at the link level.

7.  **Physical Layer:** This is the lowest layer and is responsible for the physical transmission of data over the network medium (e.g., cables, wireless signals). It defines electrical and physical specifications.

**How it works (Simplified):**

Imagine you're sending a message:

1.  You compose the message in an application (Application Layer).
2.  The message is formatted and potentially encrypted (Presentation Layer).
3.  A session is established (Session Layer).
4.  The message is segmented and prepared for transport (Transport Layer).
5.  IP addresses are added for routing (Network Layer).
6.  The data is framed with MAC addresses for local delivery (Data Link Layer).
7.  The bits are transmitted over the physical medium (Physical Layer).

The process is reversed at the recipient's end.

**Key Points:**

*   The OSI model is a *reference model*.  It's a conceptual framework, and actual implementations may not perfectly match it.
*   Understanding the OSI model helps in troubleshooting network issues, as you can isolate the problem to a specific layer.
*   While the TCP/IP model is more commonly used in practice, the OSI model is still valuable for understanding networking concepts.

## IPv4 Packet Header Fields

An IPv4 packet header contains 13 fields:

1.  **Version (VER):** (4 bits) Indicates the protocol version (IPv4 in this case).
2.  **IP Header Length (HLEN or IHL):**  Indicates the header length, marking the start of the data segment.
3.  **Type of Service (ToS):**  Provides information to routers for packet prioritization to maintain Quality of Service (QoS).
4.  **Total Length:** The total length of the IP packet (header + data), up to 65,535 bytes.
5.  **Identification:** A unique identifier for fragments of a fragmented IP packet, allowing reassembly at the destination.
6.  **Flags:** Provides information about fragmentation (whether the packet has been fragmented and if more fragments follow).
7.  **Fragmentation Offset:** Indicates the position of a fragment within the original packet.
8.  **Time to Live (TTL):** Prevents packets from looping indefinitely.  A counter decremented at each hop; when it reaches zero, the packet is discarded, and an ICMP Time Exceeded message is sent.
9.  **Protocol:** Specifies the protocol used for the data portion of the packet.
10. **Header Checksum:** Detects corruption in the IP header during transit. Corrupted packets are discarded.
11. **Source IP Address:** The IPv4 address of the sending device.
12. **Destination IP Address:** The IPv4 address of the receiving device.
13. **Options:** Allows for security options (if HLEN > 5). Communicates these options to routing devices.

# Network Traffic Monitoring

## IP addresses
The Internet Protocol (IP) is a set of standards for routing and addressing data packets between devices on a network, forming the basis for all internet communications. IP ensures that packets reach their destinations. There are two versions of IP: IPv4 and IPv6, each with different packet header structures.

**IPv4** is the most widely used version and has thirteen fields in its header:
1. **Version**: Indicates the IP version (IPv4).
2. **Internet Header Length (IHL)**: Specifies the length of the IPv4 header.
3. **Type of Service (ToS)**: Provides packet priority for delivery.
4. **Total Length**: Specifies the entire packet's length (header + data).
5. **Identification**: Identifies packet fragments for reassembly.
6. **Flags**: Provides packet fragmentation information.
7. **Fragment Offset**: Identifies the correct sequence of fragments.
8. **Time to Live (TTL)**: Limits how long a packet circulates in the network.
9. **Protocol**: Specifies the protocol for the data portion.
10. **Header Checksum**: Used for error-checking the header.
11. **Source Address**: Specifies the sender's address.
12. **Destination Address**: Specifies the receiver's address.
13. **Options**: Optional field for applying security options.

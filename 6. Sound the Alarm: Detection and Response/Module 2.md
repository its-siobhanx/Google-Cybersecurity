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

**IPv6**, which offers a larger address space than IPv4, has been increasingly adopted. Its header contains eight fields:

1. **Version**: Indicates the IP version (IPv6).
2. **Traffic Class**: Specifies the packet's priority or class for delivery.
3. **Flow Label**: Identifies packets of a flow, which is a sequence from a specific source.
4. **Payload Length**: Specifies the length of the data portion of the packet.
5. **Next Header**: Indicates the type of header following the IPv6 header (e.g., TCP).
6. **Hop Limit**: Similar to IPv4's TTL, it limits how long a packet can travel in the network.
7. **Source Address**: Specifies the sender's address.
8. **Destination Address**: Specifies the receiver's address.

[Wireshark](https://www.wireshark.org/docs/wsug_html/)
[TCP dump](https://www.tcpdump.org/)


Common Ports
  Port 22 - SSH, SFTP.
  Port 80 - HTTP.
OSI - Open Systems Interconnection: Describes the different activities that occur on a system.
  The 7 OSI Layers - Please Do Not Throw Sausage Pizza Away.
    1. Physical - Basic equipment such as copper wires or fiberoptic cables.
      MAC Address - Media Access Control Address. Assigned to the NIC (Network Interface Card). AKA physical address or hardware address.
    2. Data Link - Switches operate here. Formats data into frames and delivers to systems within the local network using MAC address.
    3. Network - Sends information between systems outside the local network using IP addresses.
    4. Transport - Provides end-to-end communication services using TCP or UDP.
    5. Session - Establishes, manages, and terminates sessions.
    6. Presentation - Translates data into a standard format that can be understood by the application. Encryption and compression also occur at        this level.
    7. Application - Provides network services to applications.
  Encapsulation/Decapsulation - As data moves down the OSI layers, it is wrapped in headers allowing the data to reach its intended destination, 
  and also provide a return address so the request can be fulfilled. As it moves back up the layers, these headers are removed.
Networking Protocols - Provide rules which allow computers to communicate with each other over the network.
  TCP - Transmission Control Protocol. Establishes session via three way handshake (SYN-SYN/ACK-ACK). Guarenteed delivery.
  IP - Internet Protocol. Identifies host in a TCP/IP network and delivers data to and from these addresses.
    IPv4 - 32 bit. Octets.
    IPv6 - Hexadecimal.
  UDP - User Datagram Protocol. No session. Send and hope for the best.
  HTTP - Hypertext Transfer Protocol. Uses port 80.
  HTTPS - Hypertext Transfer Protocol Secure.
  SMTP - Simple Message Transfer Protocol.
  ICMP - Internet Control Message Protocol. Tests basic connectivitiy. Commonly used for DoS attacks and therefore commonly blocked at the         firewall and router.
    PING - Checks for connectivity.
    Tracert - Trace network paths.
  ARP - Address Resolution Protocol. Resolves IPv4 addresses to MAC addresses. ARP works within a LAN.
Insecure Protocols - The following should NOT be used on modern networks because they are insecure and lack encryption.
  FTP - File Transfer Protocol. Transmits data in cleartext.
  TFTP - Use to transfer smaller amounts of data. Not a necessary protocol and often disabled.
  SSL - Secure Sockets Layer. Used to be the primary way to secure HTTP but has been compromised and no long recommended for use.
Secure Protocols
  TLS - Transport Layer Security. The approved replacement for SSL used to secure HTTP.
  IPsec - Used to encrypt IP traffic.
  SSH - Secure Shell. Used to encrypt data in transit and can be used to encrypt other protocols such as FTP. Used TCP Port 22.
  SCP - Secure Copy. Based on SSH. Used to copy encrypted data.
  SFTP - Secure File Transfer Protocol. An extension of SSH used to encrypt FTP. Uses TCP Port 22.
  

Common Ports
  Port 22 - SSH, SFTP. It makes sense that these two use the same port since SFTP uses SSH.
  Port 80 - HTTP.
  Port 443 - HTTPS.
  TCP Port 25 - SMTP.
  TCP Port 110 - POP3.
  TCP Port 587 - SMTPS.
  TCP Port 995 - POP3S.
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
Networking Protocols - Provide rules which allow computers to communicate with each other over the network. These are kind of like different languages the computers speak.
  Common Protocols
    TCP - Transmission Control Protocol. Establishes session via three way handshake (SYN-SYN/ACK-ACK). Guarenteed delivery.
    IP - Internet Protocol. Identifies host in a TCP/IP network and delivers data to and from these addresses.
      IPv4 - 32 bit. Octets.
      IPv6 - Hexadecimal.
    UDP - User Datagram Protocol. No session. Send and hope for the best.
    HTTP - Hypertext Transfer Protocol. Uses port 80.
    HTTPS - Hypertext Transfer Protocol Secure.
    SMTP - Simple Mail Transfer Protocol.
    ICMP - Internet Control Message Protocol. Tests basic connectivitiy. Commonly used for DoS attacks and therefore commonly blocked at the         firewall and router.
      PING - Checks for connectivity.
      Tracert - Trace network paths.
    ARP - Address Resolution Protocol. Resolves IPv4 addresses to MAC addresses. ARP works within a LAN.
  Insecure Protocols for DIT - The following should NOT be used on modern networks because they are insecure and lack encryption.
    FTP - File Transfer Protocol. Transmits data in cleartext.
    TFTP - Use to transfer smaller amounts of data. Not a necessary protocol and often disabled.
    SSL - Secure Sockets Layer. Used to be the primary way to secure HTTP but has been compromised and no long recommended for use. Vulerable to     the POODLE attack.
  Secure Protocols for DIT
    TLS - Transport Layer Security. The approved replacement for SSL used to secure HTTP. Used to encrypt many different protocols.
    IPsec - Used to encrypt IP traffic.
    SSH - Secure Shell. Used to encrypt data in transit and can be used to encrypt other protocols such as FTP. Used TCP Port 22.
    SCP - Secure Copy. Based on SSH. Used to copy encrypted data.
    SFTP - Secure File Transfer Protocol. An extension of SSH used to encrypt FTP. Uses TCP Port 22.
    FTPS - File Transfer Protocol Secure. Obviously very similar to SFTP, except FTPS uses TLS instead of SSH.
  Email and Web Protocols
    SMTP - Simple Mail Transfer Protocol. Transfers EMAIL between clients and SMTP servers. The secure version is SMTPS.
    SMTPS - Simple Mail Transfer Protocol Secure. Encrypted using TLS.
    POP3 - Post Office Protocol. Transfers emails from servers to end users. The secure version has the same name.

# Common Ports 
#### Not to be confused with physical ports found in switches. These are logical ports, which are numbers embeded in packets.
 * TCP Port 22 - SSH, SFTP. It makes sense that these two use the same port since SFTP uses SSH.
 * TCP Port 25 - SMTP.
 * TCP Port 53 - DNS zone transfers. 
 * TCP Port 80 - HTTP.
 * TCP Port 110 - POP3.
 * TCP Port 143 - IMAP4.
 * TCP Port 389 - LDAP.
 * TCP Port 443 - HTTPS.
 * TCP Port 587 - SMTPS.
 * TCP Port 636 - LDAPS.
 * TCP Port 993 - IMAP (secure version).
 * TCP Port 995 - POP3 (secure version).
 * TCP Port 3389 - RDP.
 * UDP Port 53 - DNS client queries. 
 * UDP Port 161 & 162 - SNMPv3.
# OSI Model - Open Systems Interconnection
#### Describes the different activities that occur on a system.
## The 7 OSI Layers
#### Mnemonic: Please Do Not Throw Sausage Pizza Away.
 1. Physical - Wires, cables.
 2. Data Link - Switches, NICs, MAC address.
 3. Network - IP addresses, packet forwarding, routing.
 4. Transport - TCP/UDP, port numbers.
 5. Session - Establishes, manages, and terminates sessions.
 6. Presentation - Encryption, decryption, compression.
 7. Application - Closest to the end user (HTTP, FTP, DNS).
#### As data moves down the OSI layers, it is wrapped in headers allowing the data to reach its intended destination, and also provide a return address so the request can be fulfilled. As it moves back up the layers, these headers are removed. This is known as encapsulation and decapsulation.
# Networking Protocols
#### Provide rules which allow computers to communicate with each other over the network. These are kind of like different languages the computers speak.
## Common Protocols
 * TCP - Transmission Control Protocol. Establishes session via three way handshake (SYN-SYN/ACK-ACK). Guarenteed delivery.
 * IP - Internet Protocol. No session. Send data and hope for the best.
   + IPv4
   + IPv6
 * UDP - User Datagram Protocol.
 * HTTP - Hypertext Transfer Protocol.
 * HTTPS - Hypertext Transfer Protocol Secure.
 * SMTP - Simple Mail Transfer Protocol.
 * ICMP - Internet Control Message Protocol.
   + PING - Checks for connectivity.
   + Tracert - Trace network paths.
  * ARP - Address Resolution Protocol. Resolves IPv4 addresses to MAC addresses.
## Insecure Protocols for DIT
#### The following should NOT be used on modern networks because they are insecure and lack encryption.
 * FTP - File Transfer Protocol. Transmits data in cleartext. Converted to SFTP by SSH or FTPS by TLS.
 * TFTP - Trivial File Transfer Protocol. Use to transfer smaller amounts of data. Not a necessary protocol and often disabled.
 * SSL - Secure Sockets Layer. Used to be the primary way to secure HTTP but has been compromised and no long recommended for use. Replaced by TLS. Vulerable to the POODLE attack.
## Secure Protocols for DIT
 * TLS - Transport Layer Security. The approved replacement for SSL used to secure HTTP. Used to encrypt many different protocols, such as FTPS.
 * IPsec - Used to encrypt IP traffic.
 * SSH - Secure Shell. Used to encrypt data in transit and can be used to encrypt other protocols such as SFTP and SCP. Used TCP Port 22.
 * SCP - Secure Copy. Based on SSH. Used to copy encrypted data.
 * SFTP - Secure File Transfer Protocol. An extension of SSH used to encrypt FTP. Uses TCP Port 22.
 * FTPS - File Transfer Protocol Secure. Obviously very similar to SFTP, except FTPS uses TLS instead of SSH.
## Email and Web Protocols
 * SMTP - Simple Mail Transfer Protocol. Transfers EMAIL between clients and SMTP servers. The secure version is SMTPS.
 * SMTPS - Simple Mail Transfer Protocol Secure. Encrypted using TLS.
 * POP3 - Post Office Protocol. Transfers emails from servers to end users. The secure version has the same name.
 * IMAP4 - Internet Message Access Protocol. Used to store emails on a server and allow users to organize emails into folders on the server.
 * HTTP - Hypertext Transfer Protocol. Transmits web traffic between browsers and web servers.
 * HTTPS - Hypertext Transfer Protocol Secure. Uses TLS to encrypt HTTP.
## Email Authentification Methods
 * SPF - Sender Policy Framework. Used DNS records to define the IP addresses that are authorized to send emails from certain domains.
 * DKIM - DomainKeys Identified Mail. Used public key cryptography to sign and verify an emails domain and content.
 * DMARC - Domain Based Authentification, Reporting, and Conformance.
 * Email Gateway - Acts as a barrier between an organizations internal mail and the external internet.
## Directory Services
 * AD DS - Active Directory Domain Service. Used by Microsoft. Provides authorization and authentication services for a network. Uses LDAP          encrypted with TLS.
 * LDAP - Lightweight Directory Access Protocol.
 * LDAPS - Lightweight Directory Access Protocol Secure. Encrypts LDAP using TLS.
## Voice and Video Service
 * UDP - User Datagram Protocol. Preferred over TCP for voice and video.
 * RTP - Realtime Transfer Protocol. Delivers audio and video over IP networks.
 * SRTP - Secure Realtime Transfer Protocol Secure.
 * VoIP - Voice over Internet Protocol.
 * SIP - Session Initiation Protocol.
## Remote Access Services
 * Telenet - Data sent in cleartext, so no longer used.
 * RDP - Remote Desktop Protocol. Uses SSH for security.
 * VPN - Virtual Private Network.
 * OpenSSH - Open Secure Shell. Used to simplifies the use of SSH to connect remotely to servers.
    + Open SSH Commands:
       - ssh-keygen - creates a public/private key pair.
       - ssh-copy-id - copies the public key to the server.
## Time Sychronizations Services
 * NTP - Network Time Protocol.
## Network Allocation Services
 * DHCP - Dynamic Host Configuration Protocol.
# Basic Network Concepts
 * IPv4 - Internet Protocol Version 4. Uses 32-bit IP addresses expresses in dotted decimal format. There are public and private IP addresses.
 * ISP - Internet Service Provider. Purchase a range of public IP addresses and issue them to customers.
 * IPv6 - IPv4 was exausted back in 2011, so the IETF (Internet Engineering Task Force) created IPv6. Uses 128-bit IP addresses expressed in hexadecimal format.
 * DNS - Domain Name System.
    + Zone Files:
       - A - Host record. Holds the host name and IPv4 address.
       - AAAA - Holds the host name and IPv6 address.
       - PTR - Pointer Record. A PTR (Pointer) record is used in reverse DNS lookups, where the query starts with an IP address and returns the associated domain name, as opposed to the more common forward lookup, which starts with a domain name and returns its IP address.
       - MX - Mail Exchanger. Identifies mail servers. The mail server with the lowest preference is the primary mail server.
       - CNAME - Cononical Name. Used when a single system has multiple names associated with a single IP address.
       - SOA - Start of Authority. Contains information about a domain or zone.
       - DNSSEC - Domain Name System Security Extension. Adds a RRSIG.
          * RRSIG - Resource Record Signature. Provides data integrity and authentication to prevent DNS poisoning.
       - DNS poisoning - AKA DNS cache poinsoning. Occurs when attackers change the IP address associated with domain name to that of a malicious website. Connects users with malicious websites instead of the intended website.
# Basic Network Infrastructure
 * Host - Any device with an IP address.
 * Switch - Connects hosts together to create a network. Creates connections using switches. Pays attention to and remembers the MAC address 
    associated with each port for future use.
   + Unicast - One to one traffic.
   + Broadcast - One to all traffic.
   + Switch Hardening: Improves security of switched.
      - Port Security - Disable unused ports. MAC filetering.
      - MAC Filtering - Assign MACs to speicific ports.
      - STP/RSTP - Spanning Tree Protocol and Rapid Spanning Tree Protocol provide boradcast storm prevention and loop prevention.
      - Switching Loop - Occurs when two ports of a switch are connected.
      - BPDU Guard - Bridge Protocol Data Unit Guard watches for switching loops.
 * Router - Connects multiple network segments into a single network and routs traffic between the segments.
    + Router Hardening:
       - ACL - Access Control Lists. Identifies traffic to be allowed and traffic to be denied. Also used in firewalls. Filters traffic                  based on IP address, ports, and protocols based on rules.
       - Implicit Deny - All traffic that is not explicity allowed (based on the rules) is automatically denied. The last rule in the                    ACL.
    + Default Gateway - The router is the default gateway of a network connecting the LAN to the internet.
    + Routing Table - Guides packets towards their destination via the most optimal path possible.
    + Route Command - The route command can be used to display and manipulate the routing table on a Linux computer.
 * SNMP - Simple Network Management Protocol. Monitors and manages network devices such as switches and routers. Does NOT transfer data over a network.
    + SNMP Traps - SNMP agents send information through notifications to SNMP managers. These notifications are known as SNMP traps or device traps.
    + SNMPv3 - Version 1 and version 2 both have vulnerabilities, but version 3 uses encryption. Used to provide secure management of a system.
 * Firewalls -  Monitors and manages incoming and outgoing traffic.
    + Host Based Firewall - Monitors traffic passing through the NIC, or individual host.
    + Network Based Firewall - Monitors traffing passing through the network.
    + Stateless Firewall - Uses rules implemented in ACLs to filter traffic. A router using an ACL is very similar to a stateless firewall. Treats each network packet as its own event. Fast, but no context awareness. Does not provide highest level of security.
    + Stateful Firewall - AKA layer 4 (transport) firewall. Monitors data in the context of states within a session.
    + Firewall Rules
       * Permission - Green Light: PERMIT and ALLOW. Red Light: DENY.
       * Protocol - Typically TCP or UDP. ICMP (internet control message protocol) can be blocked to prevent being PINGed.
       * Source - Permit or deny data coming from specific IP addresses.
       * Destination - Permit or deny data going to specific IP addresses.
       * Port - Permit or deny data based on the port.
       * Implicit Deny - The last rule. Deny any traffic not explicitly allowed. DENY ANY ANY, DENY ANY, or DROP ALL.
    + WAF - Web Application Firewall. Provides and added lay of protection for web applications. Designed specifically for web based attacks.
    + NGFW - Next Gen Firewall. AKA Layer 7 (application) firewall. They provide for deep packet inspection and look through every layer of the OSI model.
    + Fail States - Firewalls are designed to either fail open or fail closed.
       - Fail Open - Allows ALL traffic to pass after failing. Maintains system available but provides NO security.
       - Fail Closed - Allows NO traffic to pass after failing. Maintains security but system becomes unavilable. This is the one security professionals prefer for obvious reasons.
# Network Designs
 * Security Zones - Rather than being connected directly to the internet, networks are divided into security zones. The goal of having security zones is to reduce the attack surface of a network.
    + Intranet - Internal private network.
    + Extranet - Part of the private network than can be accessed by authorized external entitites.
    + DMZ - Demilitarized Zone. AKA screened subnet. A security zone between a private network and the internet. It's like the front porch of your internal network. Provides a layer of protections for servers that are accessible from the internet. Systems accessed by the general public should always be placed in the DMZ or screen subnet.
 * NAT Gateway - Network Address Translation Gateway. Protocol that translate public IP addresses to private IP addresses. Hides internal computers from the internet. Not compatible with IPsec. The NAT gateway is the actual device that does the tanslation.
    + Static NAT - 1 public IP address to 1 private IP address.
    + Dynamic NAT - Changes to public IP address that private IP addresses use.
    + PAT - Port Address Translation. A common form of NAT.
 * Physical Isolation and Air Gaps - Ensures networks are completely separated from eachother through the use of a physical separation.
 * Logical Separation and Segmentation -
    + Firewalls
    + Routers
    + VLANs - Virtual Local Area Network. Separate traffic on the same physical network using switches. Can be used to separate networks based on type of traffic or connect users on separate networks.
 * Network Appliances
 * Proxy Servers - The middle man between the private network and the internet.
    + Caching - Proxy servers "remember" the pages you search. Then, instead of retrieving the page from the domain server in the future, it just pulls it from the cache. Cache in this context is just temporary storage. It comes with a TTL (time to live). This prevents you from retrieving a stale page.
    + Content Filtering - Examine user requests before passing the request along. Unauthorized sites are added to a block list.
    + Logs - Proxy severs also log user requests.
    + Forward Proxy (retrieving) - Fetches data from the internet for you.
    + Reverse Proxy (sending) - Passes data along to the internet for you.
 * UTM - Unified Threat Management. A single solution that combines multiple security controls. Provides:
    + URL Filtering
    + Content Inspection
    + Malware Inspection
    + DDoS (distributed denial of service) Mitigator
 * Jump Server - A hardened server in a DMZ or screened subnet which adminstrators can "jump" through and use OpenSSH to do adminstrative stuff on remote servers within the internal network.
 * ZTNA - Zero Trust Network Access.
    + Adaptive Identity Authentication.
    + Control Plane - Handles authentication, authorization, and policy enforcement.
       - PE - Policy Engine. Grants access.
       - PA - Policy Administrator. The communication middle man between the PEP and PE.
       - Policy Decision Point - PE + PA.
    + Data Plane - Handles traffic of data between resource and user. This is the delivery path.
       - Subject
       - System
       - PEP - Policy Enforcement Point.
       - Enterprise Resource
    + SASE - Secure Access Service Edge. Combines network and security functions and delivers them as an intergrated cloud system.

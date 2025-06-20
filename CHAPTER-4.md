# Advances Security Devices
#### This is primarily about IDSs and IPSs
 * IDS - Intrusion Detection System. Can only DETECT and attack. Cannot PREVENT an attack.
    + HIDS - Host-Based Intrusion Detection System. Can monitor all traffic that passes through a host system like a server or workstation. Monitors traffic that passes through the NIC. Has expanded to be installed on internet facing servers. Helps detect malware which traditional antivirus software might miss. Often installed on every workstation as an extra layer of protection than just traditional antivirus software.
    + NIDS - Network-Based Intrusion Detection System. Monitors traffic that passes through a network. Sensors or collectors are installed on layer 3 devices such as switches, routers, and firewalls. Reports to a NIDS console. Does not decrypt so it can only read plaintext (data that has not be encrypted).
      - Port Tap/Port Mirror - Configuring a port to direct all traffic it recieves through a single port. This single port is then directed to a NIDS sensor, which then reports to a NIDS console.
    + Primary Detection Methods:
       - Signature Based - Based on known attacks and vulnerabilities.
          * SYN Flood
       - Trend Based - AKA anomaly based. Based on deviations from the norm.
          * Zero Day Vulnerability - A vulnerability that is unknown to the vendor and therfore has no patch. These are obviously unknown, and so not detected through signature based detection.
    + Aggregator -
    + IDS Errors:
      - False Positive - IDS triggers alert but nothing is actually going on. This is like the IDS crying "wolf!" If your IDS is too sensitive, actual alerts/alarms will be ignored.
      - False Negative - IDS does NOT trigger an alert about SOMETHING is actually going on. If your IDS is not sensitive enough, it will fail to detect actual attacks.
      - IDS Threshold - Administrators set the IDS threshold to minimize false positives and false negatives, and maximize true positive and true negatives, in a delicate balance.
 * IPS - Intrusion Prevention System. Prevent attacks by detecting them and stopping them before they reach their target. This is an extension of IDS. A big difference with IPSs is that they are "in-line" with data streams, while IDSs sit "out-of-band." This allows IPSs to actually block traffic, while IDSs can only monitor traffic. For this reason, it is said that IPSs are active, while IDSs are passive.
    + Protocol Analyzer -
 * SCADA - 
 * APT - Advanced Persistent Threats.
    + Remote Access Trojan. Installed onto devices through fishing or malware attacks. Allows attackers to send data via an authorized users computer thus bypassing a firewall. This malicious activity could then be stopped by an IPS.
# Honey
#### There are many different ways to trick attackers. A network might be riddled with tricks, traps, and decoys to sabotage an attacker.
* Honeypot - A decoy server used to decieve, divert, and gather intelligence about attacks (especially zero day attacks).
* Honeynet - A group of honeypots with a separate network. Mimics the functionality of a live network. It could actually consist of a single powerful server acting as several virtual systems, but the attacker will not be able to tell is the systems are physical or virtual.
* Honeyfile - A file designed to attract the attention of a hacker through the clever use of naming the file. For example, "password.txt." This might waste an attacers time skimming through bogus files, which is what we want.
* Honeytokens - A honeytoken can be contained within a honeyfile, but really its like a fake username or password used to track an attacker. Its like a boguss ID card left sitting out. If the attacker falls for it and uses that ID card, we can then track every door he accesses using that ID card.
# Wireless Networks
* WLAN -
* PAN -
* AP - Access Point. As the name suggest, its just an access point to the network. All wireless routers are APs, but not all APs are wireless routers. Some APs just give you access to the network but not the internet.
* WAN
* SSID - Service Set Identifyer. The name given to the wireless network. If your AP comes with a default SSID, its a good idea to change it.
* MAC Filtering - Just as MAC fltering can be used to harden switches, it can also be used to harden wireless routers. Most wireless routers allow you to specific which MAC address to allow, and then it will block all others. This way, no one else can connect to your wireless network, even if they have the password. Unless they spoof their MAC address.
   + Wireless Sniffer - Allows someone to determine which MAC addresses a wireless router allows.
* Site Survery -
   + Wifi Analyzer - A tool used in site surveys.
   + Heat Map - This is where the term "hot spot" comes from. The opposite of a hot spot is a "dead spot."
   + Foot Printing - Overlay the heat map onto the blueprint of the building, and you get foot printing. Now you can easily tell where in the building you have hot spots and dead spots.
* WEP - Wired Equivalent Privacy. Deprecated. Susceptible to IV attacks.
* WPA - Wi-Fi Protected Access. Deprecated.
* WPA2 - Much more secure than WPA. Uses AES (advances encryption standars) and CCMP (I'm not even going to say what that stands for). It can operate in 3 modes:
   + Open - No security. All data transferred in cleartext.
   + PSK - Pre-shared Key. Users access the wireless network anonymously using a password or pass key.
   + Enterprise - User access the network using unique credentials such as a username and password.
      - RADIUS Server - 802.1X server.
      - RADIUS Port - 1812.
      - Shared Secret
   + RADIUS - Remote Authentication Dial-In User Service.
* WPA3 - Newest generation. Just like WPA2, it has 3 modes:
   + Enhanced Open - Unlike the open mode of WPA2, enhanced open provides security through encryption. Used for guest accounts.
   + SAE - Simultaneous Authentication of Equals. Its like PSK mode of WPA2, but more secure.
   + Enterprise - Pretty much the same as WPA2.
# Authentication Protocols
* EAP - Extensible Authentication Protocol. Has many variations:
   + PMK - Pairwise Master Key
   + PTK - Pairwise Transient Key
   + PEAP - Requires certificates on servers but not clients.
   + EAP-FAST - Supports PAC instead of certificates.
   + EAP-TLS - Requires certificated on servers AND clients.
   + EAP-TTLS - Requires certificates on servers but not clients.
#### EAP-FAST supports PAC (Protected Access Credentials) instead of certificates. PEAP and EAP-TTLS requires certificates on the servers but not the clients. EAP-TLS requires certificates on the server and clients.
* RADIUS Federation -
* IEEE 802.1X - Used for port security. Good for exposed ports that people may or may not have to plug into to gain access to the network.
* Captive Portals -
# Wireless Attacks
* Disassociation Attack -
* WPS Attack -
* Rogue AP -
* Evil Twin Attack -
* Jamming/Interference Attack -
* IV Attack -
* NFC Attack -
* RFID Attack -
   + Snffing/Eavesdropping -
   + Cloning -
   + DoS -
* Bluetooth Attack -
   + Bluejacking -
   + Bluesnarfing -
   + Bluebugging -
* Wirless Replay Attack -
* Wireless Audit -
  + War Driving -
  + War Flying -
# Virtual Private Networks
* VPN Concentrator -
* IPsec - IPsec is used to establish VPNs.
   + Tunnel Mode - Used to encrypt data as it travels over a public network like the internet. Hides the prive destination IP address.
   + Transport Mode - Only encrypts the payload. Used with data travelling within a private network, not through a public network.
   + AH - Authentication Header.
   + ESP - Encapsulating Security Payload. The encryption protocol IPsec uses. Also provides integrity.
   + IKE - Internet Key Exchange. Port 500.
   + SA -
   + Protocol ID: 50
* TLS -
   + SSTP - Secure Socket Tunneling Protocol. Useful when data must go through a NAT. Uses port 443.
   + OpenVPN -
   + OpenConnect -
* Split Tunnel -
* Full Tunnel -

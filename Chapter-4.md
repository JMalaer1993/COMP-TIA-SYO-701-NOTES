# Advances Security Devices
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

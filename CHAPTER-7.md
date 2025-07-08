# Protecting Against Advanced Attacks
## Types of Attacks
* DoS - Denial of Service. Only 1 attacker.
* DDos - Distributed Denial of Service. 2 or more attackers.
  + Resource exhaustion. This is the goal of DoS.
  + Reflected - Send from spoofed IP address.
  + Amplified - Small request generates large response.
  + Indications:
    - Extremely high NIC activity.
    - Other resources like memory are exhausted.
* SYN Flood - A type of DoS attack. The attacker sends a SYN request, but never responds to the SYN/ACK. Instead, he just keeps sending SYN requests, never completing the 3-way TCP handshake. This blocks legitimate users from establishing a connection.
* Forgery - Think faking a signature, or identity theft.
  + Spoofing - A form of forgery where you steal the targets identity by claiming their IP address. You can also spoof an email address or MAC address, but it seems to involve stealing addresses.
* On Path Attack/MitM Attack - Monitoring, interception, modification.
  + SSH - Secure Shell is suceptible to MitM attacks, but it gives warnings if the previously establishes keys have changed. That's a strong indication.
  + Indication: Delay. Certificate warnings.
* SSL Stripping - Changes HTTPS to HTTP.
  + Indication - "Not Secure" warning on the browser. The URL suddenly includes HTTP instead of HTTPS.
* DNS Poisoning Attack - Attempts to modify or currupt data stored on a DNS server. That you you might be directed to a malicious IP address when trying to go to a safe website.
  + DNSSEC
* Pharming Attack - Very similar to DNS poisoning. The major difference is the instead of changing the DNS data on the DNS server, he changes it on the host device, because DNS information is also stored in the cache of some devices.

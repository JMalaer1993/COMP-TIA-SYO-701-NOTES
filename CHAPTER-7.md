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
  + Indication: "Not Secure" warning on the browser. The URL suddenly includes HTTP instead of HTTPS.
* DNS Poisoning Attack - Attempts to modify or currupt data stored on a DNS server. That you you might be directed to a malicious IP address when trying to go to a safe website.
  + DNSSEC
* Pharming Attack - Very similar to DNS poisoning. The major difference is the instead of changing the DNS data on the DNS server, it interrupts the DNS resolution process.
  + Indication: You try to go to one website and end up on another website.
* URL Redirection - Redirects users from a legitmate URL to a malcious one. May be used to bypass URL filters or mask malicious intent.
* Domain Hijacking - Attacker takes control of a registered domain and makes malicious changes to it without permission.
* DNS Filtering - Black access to specific domains such as those that are known to be malicious.
* DNS Sinkhole - Redirects malicous DNS request to a harmless server.
* DNS Log Files - Log DNS queries from users. These are a good incident investigation tool.
* Replay Attack - The attacker eavesdrops traffic with a recorder, and then replays the recorder to trick the system into thinking its legitimate. Times stamps, session tokens, MFA, and onces are ways to prevent these attacks.
  + Credential Replay - A type of replay attack in which the attacker replays the credentials to gain access.
## Secure Coding
* Input Validation - This is really important so take a moment to digest this one. Ensuring user input is safe, expected, and constrained.
  + Verify Proper Characters
  + Blocking HTML Code
  + Prevent Certain Characters
  + Range Check
* Client Side Input Validation - Input is checked at the browser. This is really just the first layer of defense, but it is not the most secure because it is easily bypased by various techniques, such as disable JavaScript.
* Server Side Input Valifation - This is the the second layer of protection and is more secure than client side input validation. Input is check on the backend server.
* Race Condition - Two or more operations or requests occur at the same time and create unintended problems.
  + TOCTOU - Time of Check to Time of Use. Attacker exploit this time gab to anipulate results.
* Error/Exception Handling - Programs should handle errors gracefully.
  + Error Message - A very generic error message should be displayed to users.
  + Logs - More detailed information about the error should be recorded in the logs. This is to prevent giving away information to attackers.
* Code Obfuscation - Making code dificult to read to prevent reverse engineering. The downside is that it makes collaboration and debugging more difficult.
* Software Diversity - Use several different code bases to prevent an attacker from explointing the same vulnerability across the board. If he successfully exploits one code, he might not be able to exploit the other codes.
* Outsourced Code Development - Assess for the following vulernabilties:
  + Code works as expected.
  + Vulnerable code.
  + Malicious code.
  + Lack of updates.
* Data Exposure - Just encrypt data.
* HTTP Headers -
* Secure Cookies -
* Code Signing
* Analyzing/Reviewing Code
  - Static Code Analysis
  - Manual Code Review
  - Dynamic Code Analysis
    + Fuzzing
  - Sandboxing
  - Package Monitoring

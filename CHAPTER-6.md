# Threats, Vulnerabilities, and Common Attacks
## Understanding Threat Actors
* Threat Actor Types
  + APT - Advanced persistent threats. Highly sophisticate and well-funded group of attackers. Often linked to nation states. Utilize a long-term strategy.
  + Nation State Attacker - Backed and employed be governments.
    - China
    - Iran
    - Russia
    - North Korea
  + Organized Crime - Primarily motivated by money.
  + Hacker -
    - Script Kiddie - Unskilled Attacker. Uses premade tools with little sophistication.
    - White Hat (ethical hacker)
    - Black Hack (malicious)
    - Grey Hat
  + Hacktivist - Driven by political, ideological, or social motivations. Anonymous is an example.
  + Insider Threat - Someone working within the organization. Could be malicous or unintentional.
  + Competitor - Rare. Think Google trying to steal information from Microsoft.
* Threat Actor Attributes
  + Internal
  + External
  + Resources/Funding
  + Sophistication/Capability
* Threat Actor Motivations
  + Data Exfiltration
  + Chaos
  + Money
  + Blackmail
  + Service Disruption
  + Political/Philosophical Beliefs
  + Ethical (White Hats)
  + Revenge
  + Espionage
  + War
# Threat Vectors and Attack Surfaces
* Threat Vectors - How an attacker gets in.
  + Message Based - Uses communication platforms.
  + Image Based - Uses stegnography.
  + File Based - Malicious attachments or files. 
  + Voice Call - Social engineering.
  + Removable Device - Physical access via USB.
  + Software Based - Exploiting vulnerable applications.
  + System Based - Exploiting misconfigurations of vulnerabilities in a system.
  + Network Based - Exploiting unsecure networks.
  + Supply Chain - Infected vendor software/hardware.
  + Open Ports - Unused services exposed to the internet.
  + Default Credentials - Like default admin accounts.
* Attack Surface - The sum total of the ways an attacker could get into your system. The sum of all entry points that could be exploited.
* Shadow IT - Unmonitored and unofficial IT. Its a problem because since it is not tracked, it is not managed, and increases attack surface.
#### Attack surfaces expands with shadow ITs, IoTs, and poor configurations.
## Malware
* Malware - Any software that is intentionally designed to cause damage, gain unauthorized access, or perform malicious actions.
* Malware Types
  + Virus - Injects itself into a HOST program and then executes whenever the user runs that program.
    - Defense: Antivirus software and avoiding untrusted files.
  + Worms - SELF-replicating without user interaction and spreads through networks.
    - Defense: Firwalls and network segmentation.
  + Logic Bomb - Triggered by a condition or time.
    - Defense: Change monitoring and file integrity tools.
  + Trojans - Malware disguised as something useful like antivirus software.
  + Drive By Downloads - Malware is downloaded automatically after visiting a website.
  + Scareware - Fake threats like a pop up notifcation saying you are infected with a virus and need to download antivirus software.
  + RAT - Remote Access Trojan. Gives attack remote control of you device.
    - Defense: Endpoint detection and network monitoring. 
  + Keyloggers - Can be used to capture username and password, which can be mitigated through 2FA. But, they can still see everything else you write.
  + Spyware - Secretly gathers information.
    - Defense: Anti-spyware and monitoring tools
  + Rootkit - Operates at the kernal or admin level. Hides its presence and/or other malware.
  + Ransomware - Encrypts files locking users out of their own data. Demands money for the encryption key.
    - Defense: Backup all your important data.
  + Bloatware - Unwanted software that slows your system down.
* Indications of Malware Attacks
  + Extra Traffic
  + Data Exfiltration
  + Encrypted Traffic - Prevents DLP from knowning the type of data that is being exfiltrated.
  + Blacklisted Destination IPs
  + Outgoing Spam
## Common Attacks
* Social Engineering - Exploit human vulnerabilities, not technical vulnerabilities.
  + Impersonation - Attacker pretends to be someone else.
    - Catch Me If You Can
  + Shoulder Surfing - Watching over someones shoulder to see what they're typing.
    - Defense: Screen filters and awareness of surroundings.
  + Disinformation - Spreading false information to mislead or proke action.
  + Tailgating - Following closely behind someone and pigging backing off their credentials.
    - Defense: Control vestibules or mantraps.
  + Dumpster Diving - Digging through the trash for sensitive information.
    - Defense: Shredding/Burning
  + Watering Hole Attack - Compromise an insecure site frequented by the target group.
  + BEC - Business Email Compromise. Posing as an executive in email.
  + Typosquatting - Registering domain names very similar to legitimate ones to receive accidental traffic.
  + Brand Impersonation - Copying the look of a trusted brand.
  + Elicitation - Gaining information without asking for it directly. The attacker will use conversations tricks to get you to reveal information voluntarily.
    - Active Listening
    - Reflective Quesitoning - Asking open ended questions to encourage the target to talk more.
    - False Statements - Hoping the target will correct you and inadvertently reveal sensitive information.
    - Bracketing - Saying a range of numbers and hoping the target gives you the eact number.
  + Pretexting - A form of social engineering that uses a false story or scenario to justify a request for sensitive information. Just regular ol impersonation has no story or pretext or context.
* Message Based Attacks
  + Spam - Unwanted email. May not be malicious. Just annoying.
  + SPIM - Spam over Instant Messaging. May include malware or fake links.
  + Phishing - Sending emails with malicious links.
    - Emails from friends
    - Malware
    - Validating Email Addresses
    - 419 Scam
  + Spear Phishing - Phishing but targeting a specific person or group rather than a generic message sent to thousands of people. May use real names and job titles.
    - Defense: Email signatures (validates who send the message)
  + Whaling - Targeting high value people like CEOs.
  + Vishing - Phishing over a voice call.
  + Smishing - Phishing over text.
#### All it takes is one click for an attacker to gain nearly unlimited access to your entire network. Things to watch out for include fake login pages, attachments, requests for sensitive information, and emotional triggers like urgency or fear.
* Phishing Explained (Simplified)
  1. Intial Vector: Email with malicious link or attachment.
  2. User Action: Click link or attachment (game over).
  3. Payload: Credential harvesting, RAT, ransomware, spyware, ect.
  4. Post-Compromise: Data theft privilege escalation, backdoor accounts, lateral movement, ect.
## Blocking Attacks
* Common Malware Security Controls
  + UTM - Unified Threat Management. All in one securiy appliance (firewall, IDS, anti-malware, ect).
  + Anti-Viruse Software - Blocks more than viruses.
    - Signature Based - Based on KNOWN patterns.
    - Heuristic Based - Detects UNKNOWN malware behavior.
  + Spam Filter/Anti-Malware on Mail Gateway - This is a HUGE attack vector, so it stops attacks early.
  + Anti-Malware Software on All Systems - Provides host level protection.
  + Firewalls - Controls traffic based on rules.
    - ACL - Access Control List.
  + File Integrity Monitors - Detects unauthorized file chamges using hashes.
## Social Engineering Factors
* Authority - Claiming power or a certain role to gain compliance.
  + Impersonation - Pretending to be someone else.
  + Whaling - Targeting executives (high value targets).
  + Vishing - Voice phishing.
* Intimidation - Using threats or pressure to gain compliance.
* Consensus - Group Think/Social Proof. Following the heard.
* Scarcity - There's not enough to go around.
* Urgency - Time pressure.
* Familiarity - Building rapport.
  + Shoulder Surfing - You may allow someone you like to look over your shoulder while you work.
  + Tailgating - You may allow someone you like to follow closely behind you into a restricted access room.
* Trust - Exploiting perceived legitimacy.
## Threat Intelligence Sources
* OSINT - Open Source Intelligence. Available to the public.
* Closed/Proprietary Intelligence - Not available to the public. Usually higher quality and more targeted than OSINT.
* Vulernerability Databases
  + NVD - National Vulerability Database. 
    - NIST - National Institute of Standards and Technology. Manages NVD.
  + CVE - Common Vulnerabilties and Exposure. Standardized ID system for known vulnerabilities. Example: CVE-2023-123456
    - MITRE Corporation. Mangages CVE.
* TAXII - Trusted Automated eXchange of Indicator Information. Used to transport intel.
* STIX - Stuctured Threat Information Expression. Format of intel.
* AIS - Automated Indicator Sharing. Federal threat sharing.
  + CISA - Cybersecurity Infrastructure Security Agency. Manages AIS.
* Dark Web - Websites you can't reach through Google. Requires software/credentials to access.
* Infomation Sharing Organizations - Straight forward.
* IoC - Indicators of Compromise. Clues a system has be compromised.
* Predictive Analysis - Using analytics to forecast future attacks.
* Threat Maps - Real time visualizations of worldwide cyber activity.
* Repositories - Public collectiong of tools, code, files, or threat intelligence.
  + Github
    - The Awesome Threat Intelligence Repository
* Research Sources - Just know these exist.
  + Vendor Websites
  + Conferences
  + Local Industry Groups
  + Information SHaring Centers
  + Academic Journals
  + FRC
    - IETF - Internet Engineering Task Force.
  + Social Media

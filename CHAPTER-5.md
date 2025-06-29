# Securing Hosts and Data
## Virtualization
* Virtualization - Running multiple vitrual systems (VMs) on a single physical system using a hypervisor. Saves costs, supports isolation, and provides test environments.
* VM - Virtual Machines. A software-based emulation of a physical computer. Can be isolated, duplicated, or rolled back with snapshots.
* Hypervisor - Software that creates and manages VMs. 
* Host - The physical system that runs the hypervisor and hosts VMs.
* Guest - A VM running on a host.
* Cloud Scalability - Abilitity to manualy increase resources to meet demand.
* Cloud Elasticity - Ability to automatically increase/decrease resources based on demand.
* Thin Client - A minimalistic computer that relies of a server for computing tasks. Minimal hardware. Outsources processing to server.
* VDI - Virtual Desktop Infrastructure. Hosts users desktops on VMs centrally. Makes it really easy to update and patch all desktops from one location.
* Containerization - Runs apps in isolated environments using a shared OS kernel. Faster and lighter than VMs. Its a way to package and run applications with everything they already need within an isolated environment. Unlike VMs they do NOT need their own OS. They share an OS kernel with other containers. This makes them lightweight. Ideal for cloud-native applications.
  + Docker
  + Kubernetes (K8s)
  + Podman
* VM Escape - Malware in a VM breaks out and interacts with other VMs or the host. Mitigated by isolating VMs and PATCHING hypervisors.
* VM Sprawl - Accumulating and losing track of VMs. When the VMs are poorly managed they present a security risk.
* Resource Reuse - Recycling virtual infrastructure. 
* Replication - Like copying and pasting VMs into different locations, just like copying and pasting a file in different places.
* VM Cancer - Code is like the DNA of software. If the DNA is corrupted, replicating that software will result in repoducing that corrupted DNA, like cancer.
* Snapshots - A captured image of a VMs state. Usually taken before implementing a risky updates or changes. Can be used to roll a VM back to its previously captured state. Imagine you are about to undergo an experimental treatment, so that doctors save your current physical state as snapshot. If the procedure severaly damages you, the doctors could just use that snapshot to recreate you in your original state before the procedure.
## Implementing Security Systems
* Endpoint - Any device that connects to a network (PC, phone, IoT).
* Endpoint Security
  + Antivirus Software - Detects and removes KNOWN MALWARE (signature-based detection)
  + EDR - Endpoint Detection and Response. Monitors and responds to ADVANCED threats at endpoints. 
  + XDR - Extended Detection and Response. Integrates EDR + network + cloud data into a single platform. 
  + HIPS - Detects and blocks malicious activity on a host in real time.
  + Application Allow/Block Lists
* Hardening - Reducing attack surface through various means such as:
  + Disabling unused features:
    - Ports
    - Protocols
    - Software
  + Changing default passwords
  + Staying up-to-date with patches.
* Configuration Management - Tracking and controlling system settings to ensure consistent security posture.
* Baseline - Known secure starting state for a system. 
  + Establish
  + Deploy
  + Maintain
* Master Images - Preconfigured VM images with hardened settings. Secure baseline. Enables fast deployment of VMs with fewer vulnerabilties.
  + Integrity Measurements - Identifies deviations from the baseline.
* Patch Management - A process for regularly applying software updates to ensure your systems are up-to-date with most recent patches.
* Change Manegement - A formal process for requesting, testing, approving, and documenting changes to your systems. Reduces unintentional distruptions or vulnerabilities. The key goals of change management are to avoid unintended consequences of changes and to document changes.
## System Integrity and Boot Integrity
#### These feautures prevent tampering with your system from the moment it powers on.
* FDE - Full Disk Encryption. Encrypts the entire storage drive. Protects data at rest, even if the drive is stolen.
* SED - Self Encrypting Drive. A drive with built-in hardware encryption. No additional software is needed. Useful for securing laptops and mobile devices.
* Boot Integrity - Ensures the OS and firmware have not been tampered with during startup.
* Measured Boot - Logs each step of the boot process.
* Secure Boot - Ensures only authorized, signed, and trusted coded runs at startup. Protects against rootkits and bootkits.
## Firmware and Security Hardware
#### These are low level system controls.
* BIOS - Basic Input/Output Systems. Legacy firmware that serves and an interface between hardware in OS. Replaced by UEFI.
* UEFI - Unified Extensible Firmware Interface. Secure replacement for BIOS.
* TPM - Trusted Platform Modules. A chip on the motherboard that perform encryption tasks (key storage, integrity checks).
  + Hardware Root of Trust - Uses TPM to ensure trust starts the boot. All subsequent code must be verified.
  + Secure Boot
  + Measured Boot
* Remote Attestion - TPM sends cryptographic proof of system integrity to remote server.
## Cryptographic Hardware
* HSM - Hardware Security Module. EXTERNAL device the handles cryptographic operations (key generation, encryption).
* microSD HSM - A tiny HSM that fits in tablets and smartphones or anything with a microSD slot.
## Hardware Lifecylce
* Decommisioning - A process of wiping/destroying data from retired systems.
* Lagacy Hardware - Older systems that lack the most advanced technology. No longer being made. Presents a security risk because patches are no longer being released.
* EOL Hardware - End of Life hardware. No longer recieves updates, patches, or supports from vendors.
## Protecting Data
* Encrpytion - Best way to protect confidentiality of data at rest or in transit.
  + Column Encrpytion - Encrypt certain fields like credit card numbers, but not names or phone numbers.
  + Row Encryption - Encrypt all data associated with a person.
* Data Exfltration - The unauthorized transfer of data out of a system. Common goal of malware.
* DLP - Data Loss Prevention. Monitors and blocks unauthorized data movement. Monitors outgoing traffic.
* Removeable Media - USBs, external drives. Often banned. Remember USB = UCMJ? That used to be a friendly little reminder attached to ever USB port on every computer on the ship I used to be stationed on which stated that if you plug anything into the USB port, even a phone charger, you're going to captains mast.
* NTFS - New Technology File System. Windows file with built in security features.
* Data in Use -
* TEE -
   + SGX -
## Cloud Concepts
* Cloud Computing - Delivery of computing services over the internet.
* Cloud Delivery Models - For Security+ purposed, its important to recognize that the burden of security responsiblity is placed on the user and the CSP (cloud service provider) in different proprotions in each of these models.
  + SaaS - Software as a Service. A specific sofware is provided to a user. The CSP is resonsible for nearly all security.
     - Web Based Email
  + PaaS - Platform as a Service. Less customization but less maintenance. Its like renting an already funished and decorated office space so all you have to worry about is your job.
    - Serverless Computing 
  + IaaS - Infrastructure as a Service. More customization but more maintenance. Its like renting out an empty building. Its on you to bring in all the furnature and decorations. Its a lot more work but you totally control your environment.
* Cloud Deployment Models
  + Public Cloud - A cloud anyone can pay to access. Owned by a third party (Google, Microsoft, Amazon).
  + Private Cloud - Not everyone can access it. Usually reserved for a company or organization.
  + Community Cloud - Kind of like a private cloud, but multiple companies or organizations may access it.
  + Hybrid Cloud - A cloud that has the combined characterists of the above type of clouds.
* Multi-Cloud - Some organizations may use multiple CSPs to increase resilience.
* API - Application Programming Interface. Interfaces that allow applications to talk to eachother.
  - Amazon Delivery Tracking.
* API Attacks - APIs are common attack vectors.
  + Authentication
  + Authorization
  + TLS
* Microservices - Breaking apps into small independent services.
* MSSP - Managaged Security Service Provider. Sometimes small companies hire MSSP to handle security.
* MSP - Manged Service Provider. Like MSSP but broader. Handle IT services.
* Middleware - Software layer between OS and application.
* Security Considerations - The following are import factors to consider when using cloud.
  + Availability
  + Resilience - Ability to recover from failure.
  + Cost
  + Responsiveness - Speed.
  + Scalability - Ability to grow.
  + Segementation - Logical separation (like VLANs).
* Premises - Datacenters or servers can be on or off premises.
  + On - Hosted by local company/organization.
    - SSO - One login can grant access to multiple systems.
    - Maintenance - Company/organization manages everything.
    - Centralized (reduces cost) vs. Decentralized (increases resiliency)
  + Off - Hosted by third-party.
    - Maintenance - Third-party handles maintenance.
    - Location - You might not know where you data is stored unless its specific in the contract.
 * CASB - Cloud Access Security Broker. Provides an additional layer of security on top of the security already provided by the CSP. Especially relevant when multiple CSPs are involved.
 * Cloud Based DLP
 * NGSWG - Next Generation Secure Web Gateway. Combines a proxy server and stateless frewall. Can filter URLs and scan for malware.
 * Cloud Firewalls - Use ACL just like other firewalls, except YOU can't modify them.
   + Security Groups - Allows you to modify the firewall rules the affect YOUR resources.
 * IaC - Infrastructure as Code.
 * SDN - Software Defined Network. Separates the control plane from the data plane. The data plane stays in the hardware, but the control plane becomes defines by the software.
   + SD-WAN - Software Defined Wide Area Network.
 * Edge Computing - The practice of storing and processing data close the the device that actually generates and uses that data. Minimizes latency.
   + Cruise Control
 * Fog Computing - Similar to edge computing but processes happen between the device and the cloud. Fog sits on the ground while the cloud is further away.
 * CSA - Cloud Security Alliance
   + CCSK - Certificate of Cloud Security Knowledge.
   + CCM
  ## Mobile Device
  * Features - The following are common features of mobile devices.
    + WNI - Wireless Network Interface.
    + Local Data Storage
    + OS
    + Install Applications
    + Bluetooth
    + NFC - Near Field Communication.
    + GPS
    + Movement Sensors
    + Camera
    + Microphone
  * Deployment Models
    + Corporate Owned
    + COPE - Corporate Owned Personally Enabled. The corporation owns the device but you keep it.
    + BYOD - You own the device.
    + CYOD - You own the device, but you have to choose from a list of devices.
  * Connection Methods
    + Cellular
    + Wi-FI
    + Bluetooth
  * MDM
    + UEM - Unified Endpoint Management.
    + MAM - Mobile Application Management.
      - Third Party Application Store
    + Storage Segmentation
    + Content Management
    + Containerization - Especially useful for BYOD
    + Full Device Encryption
    + Authentication
      - Context Aware Authentication
      - Passwords
      - PINS
      - Biometrics
      - Push Notifications
    + Screen Locks
    + Remote Wipes
    + Geolocations
    + Geofencing - Applications only work when mobile device is within a certain area.
    + GPS Tagging - A GPS stamp associated with files, like pictures.
    + MDM Application - Assigns unique digital IDs to endpoint devices.
  # MD Vulnerabilities
  * Jailbreaking
  * Rooting
  * Firmware
    + Custom Firmware
  * OTA Updates
  * Sideloading
  * Tethering/Hotspots
  * WiFi Direct
  # Other Random Concepts
  * Embedded Systems - A device that has a specific/dedicated function and uses a computer to perform that function.
    + SoC - System on a Chip. A circuit that includes a full computing system.
    + RTOS - Real Time Operating System. A system that reacts to input within a short period of time.
  * Embedded System Constraints
    + Compute
    + Cryptographic
    + Power
    + Ease of Deployment
    + Cost
    + Inability to Patch
  * IoT - This is the way I think about it. The internet of things is made up of devices that can send/recieve messages through the internet. One day in the future, using technology such as nueralink, these devices might be able to communicate directly with our brain, sending us information we might not ordinarily have, or allowing us to control them directly with out mind. Imagine being at work, but being able to see the inside of your house, feed your dog, mow you lawn, turn off your lights, lock your doors, and clean the floor through these devices just by thinking about it. I just learned this is actually called BCI (brain computer interface).
    + UAV - Unmanned Aerial Vehicle.
  * ICS - Industrial Control System.
  * SCADA - Supervisory Control and Data Acquisition. Controls the ICS. Used in isolated networks not connected to the internet and often has an IPS.
    + Manufacturing
    + Facilities
    + Energy
    + Logistics

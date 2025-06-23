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
* VM Escape - Malware in a VM breaks out and interacts with other VMs or the host. Mitigated by isolating VMs and pathing hypervisors.
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
* Hardening - Reducing attack surface through various means such as disabling unused features (ports/protocols/software), changing default passwords, and staying up-to-date with patches.
* Configuration Management - Tracking and controlling system settings to ensure consistent security posture.
* Baseline - Known secure starting state for a system.
  + Establish
  + Deploy
  + Maintain
* Master Images - Preconfigured VM images with hardened settings. Secure baseline. Enables fast deployment of VMs with fewer vulnerabilties.
* Patch Management - A process for regularly applying software updates to ensure your systems are up-to-date with most recent patches.
* Change Manegement - A formal process for requesting, testing, approving, and documenting changes to your systems. Reduces unintentional distruptions or vulnerabilities.

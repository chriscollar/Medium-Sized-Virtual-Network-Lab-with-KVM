# Medium-Sized-Virtual-Network-Lab-with-KVM
## Overview
This project aims to create a medium-sized virtual network using Virtual Machine Manager (VMC) to gain hands-on experience with pfSense, Windows Server, and virtualization. The network will be built to simulate a real-world business network with multiple VLANs, servers, and devices. The primary objectives include configuring network infrastructure, setting up security policies, and ensuring seamless internal communication between all components.

Network Configuration
The network will utilize the 10.11.0.0/16 address space, divided into several VLANs to separate different types of traffic. This address is being used to avoid conflict with home network. The Vlan set up can be found below.

| Vlan | Description |
| --- | --- |
| VLAN 2 | Servers (Domain Controllers, File Server, Print Server) |
| VLAN 10 | Cameras |
| VLAN 20 | Printers |
| VLAN 30 | Phones |
| VLAN 40 | IT Hosts |
| VLAN 50 | Sales Hosts |
| VLAN 60 | Payroll Hosts |

## Objectives
### Install and configure pfSense as the primary firewall and router.
Set up NAT for internet access and configure firewall rules to manage traffic between VLANs.

### Deploying Domain Controllers
Install and configure two Windows Server Domain Controllers for load balancing and redundancy.
Connect the Domain Controllers to pfSense and integrate them into VLAN 2.

### Adding Additional Servers
Deploy a file server and print server, ensuring both are properly connected to VLAN 2.
Configure failover on the file server for redundancy and print management on the print server.

### Simulating Security Cameras
Set up a cloud server to act as a remote storage solution for cameras.
Deploy a minimal Debian VM to simulate cameras and establish a connection with the cloud server.

### Configuring the Print Server
Install and configure simulated network printers on the Windows Print Server.
Manage and share printers using Windows Print Management.

### Implementing Phones & DHCP
Configure DHCP for phones and assign them to the correct VLAN (VLAN 30).

### Setting Up Departmental Workstations
Deploy Windows 11 VMs for IT, Sales, and Payroll departments.
Assign each department’s hosts to their respective VLANs and ensure DHCP is functioning properly.

### Finalizing Network Communication
Conduct testing to ensure full communication across all VLANs while maintaining security policies.
This project serves as a real-world learning experience in managing a virtualized business network, providing valuable hands-on practice in network administration, security, and IT infrastructure.

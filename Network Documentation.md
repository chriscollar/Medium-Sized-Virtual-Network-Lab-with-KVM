# Network Documentation

## Overview
This virtual network simulates a medium-sized business environment using Virtual Manager(KVM). The network includes a pfSense firewall/router, Windows Server-based Active Directory infrastructure, and multiple VLANs to segment traffic efficiently. 

## pfSense Configuration
pfSense serves as both the router and firewall for this environment, utilizing NAT to provide internet access. The virtual machines (VMs) within the internal network communicate through pfSense, which acts as the gateway for all VLANs. The firewall is configured with appropriate rules to allow necessary traffic while maintaining security.

### Network Connections
The network interfaces will be designed as if the equipment was a Netgate Physical Hardware on the network. How it is set up is outlined below.
- **WAN Interface**: Simulates an internet connection.
- **LAN Interface**: Connects to internal VLANs and provides routing between them.
- **Firewall Rules**: Configured to allow internal traffic while restricting unauthorized access.

## Server Infrastructure
Server Insfrastucture is designed primarily as a Windows environment utilizing Windows Server 2022 with Load Balancing. File Server will be running a minimal deployment of Ubuntu Server. The Ubuntu Servers are set with failover to prevent data loss. 
- **Domain Controllers**: Two Windows Server VMs configured in VLAN 2 for redundancy and load balancing.
- **File Server**: 2 Ubuntu Servers connected to VLAN 2. One Server acts as the failover Server. If the primary server goes down the secondary takes over.
- **Print Server**: A Windows Server machine managing simulated printers. We will be utilizing Print Management to simulate Printers on the network.
- **Cloud Server**: A Rocky Linux VM will be configured to act as a cloud storage solution for cameras, connected through NAT.

## Cameras
As mentioned above we will be simulating a Cloud Server for camera footage. To simulate cameras we will use 9 (3 per department) debian minimal distribution VMs to act as cameras. They will be connected to the cloud server.

## Active Directory (AD) and Departmental Roles
This environment includes three departments: IT, Sales, and Payroll, each with five members. Group permissions are assigned based on roles within AD.

### IT Department
1. **Director of IT** - Domain Admin, Full Control over all resources.
2. **Senior IT Admin** - Full access to Group Policy, DNS, and DHCP.
3. **Network Engineer** - Manages firewall rules, VLANs, and networking infrastructure
4. **Junior IT Tech** - Can reset and unlock accounts without delegation.
5. **Help Desk** - Can reset passwords via delegation but cannot unlock accounts or modify AD objects.

### Sales Department
1. **Sales Director** - Access to all sales data and management reports.
2. **Sales Manager** - Can create and modify records within the CRM.
3. **Sales Representative** - Limited access to customer data and sales tools.
4. **Marketing Specialist** - Access to marketing materials and campaign management.
5. **Customer Support** - Can log and track customer requests.

### Payroll Department
1. **Payroll Manager** - Full access to payroll records and employee salaries.
2. **HR Administrator** - Manages employee records but cannot modify salary details.
3. **Payroll Assistant** - Limited access to payroll processing.
4. **Compliance Officer** - Can review payroll reports for auditing.
5. **Benefits Coordinator** - Manages employee benefits and insurance records.

## Conclusion
This virtualized environment provides a realistic simulation of a business network with proper segmentation, security measures, and role-based access controls. The combination of pfSense, Windows Server, and Linux-based infrastructure offers a comprehensive learning experience for IT professionals.

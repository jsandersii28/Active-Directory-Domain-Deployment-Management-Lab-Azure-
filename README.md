# Active Directory Lab: Domain Controller Setup, User & Group Management, and GPO Configuration

## Objective

The objective of this Active Directory lab was to build and manage a fully functional domain environment in Azure. The focus was on configuring a domain controller, managing users and groups, joining client machines, and applying Group Policy to simulate real-world IT administration and support tasks.


### Skills Learned

- Active Directory domain setup and configuration in a cloud environment (Azure)
- User, group, and organizational unit (OU) management
- Domain Controller deployment and basic administration using Windows Server
- Client machine domain join and connectivity troubleshooting
- Group Policy creation, configuration, and enforcement
- Identity and access management fundamentals
- System administration and environment configuration
- Problem-solving and troubleshooting in a simulated IT environment

### Tools Used

- Microsoft Azure (Virtual Machine deployment and management)
- Windows Server (Active Directory Domain Services)
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- Windows 11 Client Machine
- Azure Virtual Network (VNet) & Networking Configuration

## Steps

Deployed Windows Server VM in Azure:
- Provisioned a virtual machine in Microsoft Azure using Windows Server 2022 Datacenter (Azure Edition). Configured the VM with a 2 vCPU / 16 GB RAM size to ensure smooth performance for Active Directory operations. Verified successful deployment, running status, and network configuration.

![Image 3-17-26 at 5 34 PM](https://github.com/user-attachments/assets/9c07f73c-12ed-44c2-887d-f247078ec99e)

Configured Static Private IP for Domain Controller:
- Updated the network interface settings in Microsoft Azure to assign a static private IP address to the virtual machine. This ensures consistent internal addressing, which is critical for a domain controller to maintain reliable communication with clients and services within the virtual network.

![Image 3-17-26 at 5 39 PM](https://github.com/user-attachments/assets/05f449fb-1a1e-4568-aa1d-d0f9225ac633)




![Image 3-17-26 at 5 41 PM](https://github.com/user-attachments/assets/ba9e4cf8-283e-47d1-bb26-e8c5dabcaf25)


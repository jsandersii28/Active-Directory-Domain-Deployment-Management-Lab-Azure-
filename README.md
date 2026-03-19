# Azure Cloud & Identity Management: Active Directory Fundamentals Lab

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

Connected to VM via Azure Bastion:
- Established a secure remote connection to the virtual machine using Microsoft Azure Bastion. No inbound ports were exposed during VM deployment, enhancing security by preventing direct public access. Used Bastion to connect over RDP (port 3389) through the Azure portal, authenticating with VM credentials to begin server configuration.

![Image 3-17-26 at 5 41 PM](https://github.com/user-attachments/assets/ba9e4cf8-283e-47d1-bb26-e8c5dabcaf25)

Installed Active Directory and Core Network Services:
- Configured server roles using Server Manager in Windows Server 2022, including Active Directory Domain Services (AD DS), DNS, and DHCP. These roles establish the foundation for centralized identity management, domain control, and network resource allocation within the lab environment. Group Policy Management was also included to enable administrative control over user and system configurations.

![Image 3-17-26 at 5 45 PM](https://github.com/user-attachments/assets/3d94f97d-50ee-4af1-a905-e04362b618e9)

Promoted Server to Domain Controller & Created New Forest:
- Used the Active Directory Domain Services configuration wizard to promote the server to a domain controller. Deployed a new forest and configured the root domain name labtest.com, establishing the foundation for domain-based authentication, user management, and centralized administration within the lab environment.

![Image 3-17-26 at 6 18 PM](https://github.com/user-attachments/assets/c71b2c6a-3bf1-41d3-aec6-a95ba356169c)

Created Organizational Unit (OU) Structure and Initial User in Active Directory:
- Used Active Directory Users and Computers (ADUC) to create a structured OU hierarchy. Established a parent OU named “Branch 1” with sub-OUs for Users, Computers, and Groups to logically organize directory objects. Created an initial user account (Joe Jefferson) within the Users OU to begin populating the domain. This structure supports efficient management and delegation within the environment.

![Image 3-17-26 at 6 35 PM](https://github.com/user-attachments/assets/9f30f4ff-c2a4-42d3-b35f-86c8af9b385b)


Created Security Groups and Assigned Users:
- Used ADUC to create security groups for "IT Workers" and "HR Workers" within the domain. As well as, assigned users to their respective groups to simulate role-based access control.

![Image 3-18-26 at 6 44 AM](https://github.com/user-attachments/assets/92bfe6fe-2c5d-4ecb-9948-cbcabeb12c0f)

Simulated Password Reset:
- Performed a password reset for a user account using ADUC. After verifying user identity of course, reset the password and enforced a password change at next logon to maintain security best practices.

![Image 3-18-26 at 6 49 AM](https://github.com/user-attachments/assets/f2c6dfde-699d-4334-aa1a-68cd7e11c0cb)

Provisioned Client VM for Domain Join Testing:
- Deployed an additional virtual machine in Microsoft Azure to simulate a client workstation. Configured the VM within the same virtual network and subnet as the domain controller to ensure proper network communication.

![Image 3-18-26 at 5 52 PM](https://github.com/user-attachments/assets/d238d0b1-c7b0-48ab-bb93-8fabec6b7cb8)

Configured Client VM to Use Domain Controller for DNS:
- Updated DNS settings on the client virtual machine to point to the domain controller’s private IP address (10.0.0.4). In a cloud-based lab environment, this ensures the client can resolve domain services and successfully communicate with Active Directory.

Attempted Domain Join & Identified DNS Resolution Issue:
- Initiated domain join process on the client machine by configuring it to join "labtest.com". Encountered an error indicating the domain could not be resolved, highlighting a DNS-related issue.

![Image 3-18-26 at 6 06 PM](https://github.com/user-attachments/assets/e158954b-d5d9-4aa4-838a-9583f038fc4c)

Diagnosed DNS Misconfiguration Using ipconfig /all:
- Used Command Prompt to run ipconfig /all on the client machine to verify network configuration. Identified that the DNS server was incorrectly set to an external address instead of the domain controller’s private IP. This misconfiguration prevented proper domain name resolution, explaining the failed domain join attempt and guiding the next troubleshooting step.

![Image 3-18-26 at 6 09 PM](https://github.com/user-attachments/assets/865fa6d3-e7d8-43d5-b7c0-33a72aedf17e)

Corrected DNS Configuration on Client Machine:
- Manually updated the client machine’s network settings to use the domain controller’s private IP address (10.0.0.4) as its preferred DNS server. This change ensures proper domain name resolution and enables communication with Active Directory services.

![Image 3-18-26 at 6 11 PM](https://github.com/user-attachments/assets/b78331a0-e9ad-4e8f-99f8-afa9647766f8)

Verified DNS Resolution and Connectivity to Domain Controller:
- Used Command Prompt to ping the domain controller to confirm successful DNS resolution and network connectivity. The successful replies verified that the client machine could properly resolve and communicate with the domain controller after correcting DNS settings, confirming readiness for domain join operations.

![Image 3-18-26 at 6 17 PM](https://github.com/user-attachments/assets/2a8f5be7-c689-4114-91df-91ccbd19317a)


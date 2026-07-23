<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Ticket Lifecycle: Intake Through Resolution</h1>
This tutorial outlines the lifecycle of a ticket from intake to resolution within the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to create, work, and resolves tickets within osTicket](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Ticket Lifecycle Stages</h2>

- Intake
- Assignment and Communication
- Working the Issue
- Resolution

<h2>Lifecycle Stages</h2>

<p>
Windows Server 2022 virtual machine deployed within the existing Azure lab environment.
</p>
<p>
<img width="1911" height="912" alt="Screenshot 1" src="https://github.com/user-attachments/assets/5add5cc8-44a4-4097-92ab-fa45730e6674" />
</p>
<p>
A new Windows Server 2022 virtual machine named VM-DC-01 was deployed into the existing Azure environment created during the Azure Networking Lab. The server was connected to the existing virtual network and subnet, allowing it to communicate with other virtual machines already present within the lab environment.

After deployment, the virtual machine was successfully started and accessed using Remote Desktop Protocol (RDP), confirming that the server was operational and ready for Active Directory Domain Services installation
</p>
<br />

<p>
Windows Server renamed to DC01 in preparation for Active Directory deployment.
</p>
<p>
<img width="1914" height="1017" alt="Screenshot 2" src="https://github.com/user-attachments/assets/85783d3b-7265-42b9-a592-cea4db53a91d" />
</p>
<p>
The Windows Server computer name was changed from the default hostname to DC01 using the Windows system settings. After renaming the server, the virtual machine was restarted to apply the change. Once the restart was complete, the server was accessed again through Remote Desktop to verify that the new computer name had been applied successfully.
</p>
<br />

<p>
Configured a static private IP assignment for the Domain Controller.
</p>
<p>
<img width="1907" height="872" alt="Screenshot 3" src="https://github.com/user-attachments/assets/dcc29965-c59a-4b68-91de-155cd4e78016" />
</p>
<p>
The network interface for VM-DC-01 was configured to use a static private IP assignment within the existing Azure virtual network. The current private IP address was retained while changing the assignment from Dynamic to Static, ensuring the server maintains a consistent internal network address throughout the remainder of the lab.
</p>
<br />

<p>
Active Directory Domain Services role successfully installed on the Windows Server.
</p>
<p>
<img width="1918" height="1031" alt="Screenshot 4" src="https://github.com/user-attachments/assets/24f3bb1c-bc78-423f-ab31-03850d61a86e" />
</p>
<p>
The Active Directory Domain Services (AD DS) server role was installed using the Add Roles and Features Wizard in Server Manager. After the installation completed successfully, the server was ready to be promoted to a Domain Controller by creating a new Active Directory forest.
</p>
<br />

<p>
Configured a new Active Directory forest and prepared the server for Domain Controller promotion.
</p>
<p>
<img width="1917" height="1033" alt="Screenshot 5" src="https://github.com/user-attachments/assets/7ede7bbb-8b0d-4816-948e-1271242f5d49" />
</p>
<p>
The Active Directory Domain Services Configuration Wizard was used to create a new Active Directory forest named homelab.local. Default settings were retained for the DNS Server, Global Catalog, NetBIOS name, and database locations. After the prerequisite checks completed successfully, the server was ready to be promoted to a Domain Controller.
</p>
<br />

<p>
Active Directory Users and Computers displaying the newly created homelab.local domain.
</p>
<p>
<img width="1885" height="979" alt="Screenshot 6" src="https://github.com/user-attachments/assets/a814e045-2d3b-4cd9-8f9c-33af51b510aa" />
</p>
<p>
After the server was promoted to a Domain Controller, Active Directory Users and Computers was opened to verify that the homelab.local domain had been created successfully. The default Active Directory containers were visible, confirming that the domain was operational and ready for additional organizational units, users, and groups to be created.
</p>
<br />

<p>
Organizational Units created within the homelab.local Active Directory domain.
</p>
<p>
<img width="1884" height="999" alt="Screenshot 7" src="https://github.com/user-attachments/assets/ef7d7fb8-d82b-4aa8-9a95-187e89376611" />
</p>
<p>
Five Organizational Units (OUs) were created within the homelab.local domain using Active Directory Users and Computers. The OUs Corporate, Users, Groups, Computers, and Service Accounts were added to organize Active Directory objects and prepare the domain for creating users, security groups, and computer accounts later in the lab.
</p>
<br />

<p>
User accounts created within the Users Organizational Unit.
</p>
<p>
<img width="1898" height="998" alt="Screenshot 8" src="https://github.com/user-attachments/assets/ded05550-6073-4c5f-9f75-0666d5a7cd9e" />
</p>
<p>
Three user accounts were created within the Users Organizational Unit using Active Directory Users and Computers. Each account was configured with a username and password, providing user objects that will be used throughout the remainder of the lab for group membership management, authentication, and administrative tasks.
</p>
<br />

<p>
Departmental Organizational Units created within the Corporate Organizational Unit.
</p>
<p>
<img width="1899" height="997" alt="Screenshot 9" src="https://github.com/user-attachments/assets/537e65bc-b7ff-4dd2-8d99-634ae8a71019" />
</p>
<p>
Four departmental Organizational Units were created within the Corporate Organizational Unit to represent different departments in the organization. The IT, Human Resources, Sales, and Finance OUs provide a structured location for user accounts and make it easier to organize Active Directory objects throughout the lab.
</p>
<br />

<p>
User accounts created and organized into their respective departmental Organizational Units.
</p>
<p>
<img width="1902" height="985" alt="Screenshot 10" src="https://github.com/user-attachments/assets/68744ac2-565f-4b72-be4a-9dc2aeae1f9f" />
</p>
<p>
Four user accounts were created within the Corporate Organizational Unit and placed into their respective departmental Organizational Units. Organizing user accounts by department provides a logical Active Directory structure and prepares the environment for managing permissions, security groups, and Group Policy in later stages of the lab.
</p>
<br />

<p>
Security groups created within the Groups Organizational Unit.
</p>
<p>
<img width="1894" height="980" alt="Screenshot 11" src="https://github.com/user-attachments/assets/858a9e88-bed5-4a37-bca7-2829931bebbf" />
</p>
<p>
Four Global Security Groups were created within the Groups Organizational Unit using Active Directory Users and Computers. The groups IT_Admins, HR_Users, Sales_Users, and Finance_Users were created to organize user permissions based on departmental roles.
</p>
<br />

<p>
John Smith added as a member of the IT_Admins security group.
</p>
<p>
<img width="1895" height="983" alt="Screenshot 12" src="https://github.com/user-attachments/assets/0ceaf6f3-131a-4218-9971-d8f6b5f85824" />
</p>
<p>
User accounts were added to their corresponding Global Security Groups using the Members tab within the group's properties. In this example, John Smith was added to the IT_Admins security group. The remaining departmental users were assigned to their respective security groups using the same process.
</p>
<br />

<p>
Windows 10 client configured to communicate with the Domain Controller using DNS.
</p>
<p>
<img width="1767" height="1003" alt="Screenshot 13" src="https://github.com/user-attachments/assets/364a6dbe-28d5-453e-a2df-ee0cbd52d4b9" />
</p>
<p>
The preferred DNS server on VM-Client-01 was updated to use the private IP address of DC01. After refreshing the DNS configuration, connectivity to the Domain Controller was verified by successfully pinging DC01, confirming that the client could locate the server on the network.
</p>
<br />

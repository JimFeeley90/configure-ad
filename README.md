# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory Users and Computers
- Promote Server To Domain Controller
- Setup a New Forest as Mydomain.com 
- Create an Organizational Unit (OU) called “_EMPLOYEES”
- Create a New OU Named “_ADMINS”



<h2>Deployment and Configuration Steps</h2>

<p>
<img src=https://i.imgur.com/K8o2wHM.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src=https://i.imgur.com/1CwDPSI.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src=https://i.imgur.com/Cxy615X.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
  
<p>
<h2>Install and configure Active Directory Domain Services: To install and configure Active Directory Domain Services (AD DS), start by opening the "Server Manager" on your Windows Server. Click on "Manage" and then select "Add Roles and Features." In the wizard, choose "Role-based or feature-based installation" and select the server you want to install AD DS on. From the list of roles, check "Active Directory Domain Services" and follow the prompts to install.  </h2>
</p>
<br />

<p>
<img src=https://i.imgur.com/TmfcD8u.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src=https://i.imgur.com/FVIW9Ur.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>Promote Server to Domain Controller: To promote a server to a Domain Controller, first, ensure that Active Directory Domain Services (AD DS) is installed on the server. Open "Server Manager" and click on the notification flag at the top, then select "Promote this server to a domain controller." In the "Active Directory Domain Services Configuration Wizard," choose whether you are adding the server to an existing domain or creating a new domain. For a new domain, enter the desired domain name and configure domain and forest functional levels. Set a Directory Services Restore Mode (DSRM) password, and review the configuration before proceeding. Click "Next" and then "Install." The server will automatically restart to complete the promotion, and it will now function as a Domain Controller for your Active Directory environment.</h2>
<p>

</p>
<br />

<p>
<img src=https://i.imgur.com/0Awwx3Z.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Add a new forest: To add a new forest in Active Directory, open "Server Manager" on your Windows Server and ensure that the Active Directory Domain Services (AD DS) role is installed. Once installed, click on the notification flag in "Server Manager" and select "Promote this server to a domain controller." In the "Active Directory Domain Services Configuration Wizard," choose the option to create a new forest. Enter the desired domain name for your forest, such as "example.com," and configure the forest and domain functional levels. Set a Directory Services Restore Mode (DSRM) password, and review your settings. Click "Next" and then "Install." The server will restart to complete the process, and it will now be the first Domain Controller in the newly created forest.</h2> 
</p>
<br/>

<img src=https://i.imgur.com/jltuJwt.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Create Employee and Admin Organizational units: To create Employee and Admin Organizational Units (OUs) in Active Directory, open "Active Directory Users and Computers" on your Domain Controller. Right-click on your domain name and select "New" > "Organizational Unit." Name the first OU as "Employees" and click "OK." Repeat the process to create the "Admins" OU. These OUs will help organize and manage user accounts, with the "Employees" OU containing general staff accounts and the "Admins" OU containing administrative accounts. After creation, you can move existing user accounts into the appropriate OUs by right-clicking on the user account, selecting "Move," and choosing the correct OU. This structure helps apply specific group policies and permissions to different sets of users.</h2>

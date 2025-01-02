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

- Step 1: Prepare the Active Directory Infrastructure
- Step 2: Deploy Active Directory
- Step 3: Create Users Using PowerShell
- Step 4: Implement Group Policy and Manage Accounts

<h2>Deployment and Configuration Steps</h2>

<p>
<img src=AD 1 12.23.44 PM.png/>
</p>
<p>
Configuring Active Directory (AD) in Azure begins with setting up the infrastructure. Start by provisioning two virtual machines (VMs) in Azure: one for the Domain Controller running Windows Server 2022 and another as a client machine with Windows 10. Ensure both VMs are connected to a common virtual network and assign static private IP addresses for consistent connectivity. On the Domain Controller, install the Active Directory Domain Services (AD DS) role through the Server Manager. This step establishes the foundation for deploying AD by enabling the necessary features and ensuring the server is ready to be promoted to a domain controller.
</p>
<br />

<p>
<img src="AD 1 12.23.44 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the infrastructure is ready, deploy Active Directory by promoting the server to a domain controller. During the promotion process, create a new forest and specify the domain name (e.g., mydomain.local). After a restart, verify that the AD installation is successful by accessing the Active Directory Users and Computers (ADUC) management console. Additionally, test the DNS functionality to ensure that the domain controller can resolve names within the domain, as DNS plays a crucial role in AD operations. This stage establishes a functional AD environment that supports user management and authentication.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
With AD deployed, focus on creating users and implementing policies. Use PowerShell to create user accounts efficiently, either individually or through scripts for bulk operations. Once users are created, configure Group Policies via the Group Policy Management Console (GPMC) to enforce security settings, manage permissions, or deploy software across the domain. Apply the policies by running the gpupdate /force command on client machines, and test the configurations to ensure they work as intended. These steps provide centralized control over the domain, enhancing security and streamlining administrative tasks.
</p>
<br />

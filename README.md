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

- Create a Domain Controller and Client Virtual Machine
- Install Active Directory Domain Services
- Create admin and non-admin user accounts
- Join the Client VM to the domain
- Set up Remote Desktop for non-admin users

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/13Pmn7b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/cQBFXM3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, we create a Domain Controller (DC) with Windows Server 2022 and a Client Virtual Machine (VM) with Windows 10 in Azure. We test connectivity between the two computers in the command-line using the ping command from the Client VM. Once connectivity is established, we change DC's virtual Network Interface Card (NIC) to static in Azure.
</p>
<br />

<p>
<img src="https://i.imgur.com/vXBMUuQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wpOAhQV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we install Active Directory through the Server Manager on the DC. Once downloaded, we promote the server to a Domain Controller. In the Deployment Configuration, we'll add a new forest (which we named "mydomain.com"). Within the domain we create admin and non-admin user accounts.
</p>
<br />

<p>
<img src="https://i.imgur.com/t3nr0xk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Client Machine, we join the computer to the newly created domain. We can verify it was successful when it's listed under the Computer in Active Directory Users and Computers.
</p>
<br />

<p>
<img src="https://i.imgur.com/U0PN9GN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lastly, within the Client Machine we set up Remote Desktop for non-admin users to be able to login to any machine joined to the domain.
</p>
<br />

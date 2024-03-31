<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create our Resources in Azure. We will need to create a Resource Group and two Virtual Machines. One Virtual Machine will need to operate on Windows Server (DC-1) and the other one on Windows 10 (Client-1).
- Ensure the Connectivity between Azure Virtual Machines. Remote Desktop into Client-1 and do a ping test on the Private IP address of DC-1. If you're having an issue, then Remote Desktop into DC-1 and enable ICMPv4 on Windows Firewall.
- Install Active Directory on DC-1. In DC-1 you can open Server Manger and begin downloading by clicking on add roles and features. Once finished we will be able to create Admin and Regular User Accounts. 
- Client-1 will now need to be joined to the domain we created through installing Active Directory. This will require changing the DNS settings of Client-1 to match the Private IP address of DC-1. Log into DC-1 as the Admin we created and now we can create additional users and log into Client-1 with them to make sure they are working correctly.

<h2>Deployment and Configuration Steps</h2>

![20240329_223300](https://github.com/tylermartin12368/configure-ad/assets/161632103/6fa92709-5cd2-4889-9537-a53429f33c80)
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![20240329_230736](https://github.com/tylermartin12368/configure-ad/assets/161632103/074f393a-62af-4e23-8fbc-fac14c892ca5)
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![20240329_233600](https://github.com/tylermartin12368/configure-ad/assets/161632103/9e9a8daf-32a8-43a8-817b-51ffd08d5921)
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com/watch?v=lzHRxxSmQXc&t=132s)

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
- Install Active Directory on DC-1. In DC-1 you can open Server Manger and begin downloading by clicking on add roles and features. Once finished we will be able to turn Active Directory into a domain controller. 
- Client-1 will now need to be joined to the domain we created through installing Active Directory. This will require changing the DNS settings of Client-1 to match the Private IP address of DC-1. Log into DC-1 as the Admin we created and now we can create additional users and log into Client-1 with them to make sure they are working correctly.

<h2>Deployment and Configuration Steps</h2>

![20240329_223300](https://github.com/tylermartin12368/configure-ad/assets/161632103/6fa92709-5cd2-4889-9537-a53429f33c80)
</p>
<p>
On DC-1, Active Directory can be installed by going into Server Manager. The download begins by clicking on the option "Add roles and features" in Server Manager. When going through the before you begin download section, make sure in Server Roles that you pick Active Directory Domain Services. After the installation is complete, then Active Directory Domain Services will need to be turned into a domain controller. This can be done by clicking on the flag symbol on the top right of the Server Manager and clicking on "Promote this server to a domain controller". All that will be left to do is create a domain name and a password and Active Directory will be fully setup.   
</p>
<br />

![20240329_230736](https://github.com/tylermartin12368/configure-ad/assets/161632103/074f393a-62af-4e23-8fbc-fac14c892ca5)
</p>
<p>
With Active Directory fully setup in DC-1, now we can go to Client-1 and join it to the domain that was created. To make this happen, we will need to go into Azure and change the DNS settings to match the Private IP address of DC-1. In the Azure Portal go to Virtual Machines and pick Client 1, then go into Networking and click on the highlighted section right next to Network Interface. Next you will go to DNS servers and inside that section, a custom DNS can be created which we will setup to match the Private IP address of DC-1. After setting up the custom DNS, then Client-1 will need to be restarted in order to flush the DNS cache. Relog into Client 1 after restart is completed and now Client-1 should be able to join the domain that was created.     
</p>
<br />

![20240329_233600](https://github.com/tylermartin12368/configure-ad/assets/161632103/9e9a8daf-32a8-43a8-817b-51ffd08d5921)
</p>
<p>
With Client-1 joined to the domain, the admin can setup up Client-1 to allow everyone who is a user to have access to remote desktop. Log into Client-1 as the Admin and open up System. Select Remote desktop and click on "Select users that can remotely access this PC". From their type domain users and click on Check Names and hit ok. This will allow all domain users to now have access to logging into Client-1. In DC-1 more users can be created that will all be able to have access to Client-1. Make sure to sign in as Admin into DC-1 and open up Windows PowerShell ISE as Administrator. A new folder will need to be created in WIndows PowerShell ISE to place our code that will allow the creation of additional users. 
</p>
<br />

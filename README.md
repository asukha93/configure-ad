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

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/j8Nw4hg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
During step 1, the Azure resources were established. The Domain Controller VM, named "DC-1" and running Windows Server 2022, was created, along with the concurrent creation of the Resource Group and Virtual Network (Vnet). The Domain Controller's Network Interface Card (NIC) was configured with a static private IP address. Additionally, a Client VM named "Client-1" was also created within the same Resource Group and Vnet that had been set up for DC-1. To verify the connectivity and topology, the Network Watcher tool was employed to confirm that both VMs were part of the same network.
</p>
<br />

<p>
<img src="https://i.imgur.com/XsPnH0R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
For step 2, the connectivity between the client ("Client-1") and the Domain Controller ("DC-1") was confirmed through the following steps:

Logging into Client-1: Initially, you logged into "Client-1" using Remote Desktop.

Ping Test: A ping test was performed from "Client-1" to "DC-1's" private IP address using the command ping -t to create a continuous ping request.

Enabling ICMPv4: To allow the ping request to pass through the local Windows Firewall on "DC-1," ICMPv4 was enabled.

Verification: After enabling ICMPv4 on "DC-1," you logged back into "Client-1" and verified that the ping was successful.

These actions were taken to ensure that there is proper network connectivity and communication between "Client-1" and "DC-1."
</p>
<br />

<p>
<img src="https://i.imgur.com/FL1U3Jy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In step 3, the following actions were taken on "DC-1":

Installation of Active Directory Domain Services (AD DS): You logged into "DC-1" and installed Active Directory Domain Services.

"DC-1" was promoted to a Domain Controller, and a new forest was established with the domain name "mydomain.com."

Restart Remote Desktop: After the promotion, the Remote Desktop connection was restarted.

Logging in as User: Upon restarting the Remote Desktop, you logged back into "DC-1" using the username "mydomain.com\labuser."

These steps were executed to set up Active Directory on "DC-1" and establish a new forest with the specified domain name, followed by logging in as the user "mydomain.com\labuser."

</p>
<br />

<p>
<img src="https://i.imgur.com/TipCSQW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In step 4, Remote Desktop was configured for non-administrative users, and the username "jane_admin" was used. PowerShell Integrated Scripting Environment (PowerShell ISE) was opened as an administrator. A new script file was created, and the necessary code was pasted into the script file. Upon running the script, user accounts were created. These newly created accounts can now be viewed in Active Directory within the appropriate organizational unit.
</p>
<br />

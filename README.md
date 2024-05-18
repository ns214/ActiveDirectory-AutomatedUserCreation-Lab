<h1>Creating accounts in Active Directory using PowerShell</h1>

<h2>Description</h2>
This lab simulates a private corporate network, with a domain controller running Windows Server 2019 and a client machine running Windows 10. A PowerShell script is run to automate the creation of 1000 new user accounts in Active Directory.    <br />

<br />

The domain controller VM has been configured with a NAT network adapter for connection to the internet, and also an internal network adapter for the private network. Windows server was properly configured with NAT/RAS, DHCP, and Active Directory Domain Services to allow for new users to seamlessly join the network, access shared resources, and receive dynamic IP addresses within the specified range (172.16.0.100-200). <br />

<br />

The Windows 10 machine was then added to the domain to test/prove the functionality of the network.<br />
<br />


<h2>Utilities Used</h2>

- <b>Virtual Box</b> 
- <b>Active Directory</b>
- <b>DHCP</b>
- <b>Server Manager</b>
- <b>Command Prompt</b>


<h2>Environments Used </h2>

- <b>Windows Server 2019</b>
- <b>Windows 10</b>

<h2>Walk-through:</h2>

<p align="center">
PowerShell script reads a file called "names.txt" which contains my own name at the top, followed by 999 randomly generated names. It takes all entries, and creates active directory accounts with usernames following the same format. "(Neil Stafford = nstafford)": <br/>
 
![Image Description Here](https://github.com/ns214/ActiveDirectory-AutomatedUserCreation-Lab/blob/main/Powershell%20Script.png?raw=true)
<br />
<br />
On the domain controller, the DHCP settings show that the device "CLIENT1" successfully connected to the network and was given the IP address 172.16.0.100:  <br/>

![Image Description Here](https://github.com/ns214/ActiveDirectory-AutomatedUserCreation-Lab/blob/main/DHCP%20-%20CLIENT1%20Connected.png?raw=true)
<br />
<br />
Also in DHCP settings, I set the gateway as 172.16.0.1. This is necessary to ensure that devices connected to the network can communicate with the internet:<br/>

![Image Description Here](https://github.com/ns214/ActiveDirectory-AutomatedUserCreation-Lab/blob/main/DHCP%20-%20Domain%20Gateway.png?raw=true)
<br />
<br />
After adding "CLIENT1" to "mydomain.com", I successfully logged into the user account that the powershell script created for me and confirmed its connection by running whoami and ipconfig at the command prompt:  <br/>

![Image Description Here](https://github.com/ns214/ActiveDirectory-AutomatedUserCreation-Lab/blob/main/CLIENT1%20-%20whoami,%20ipconfig.png?raw=true)
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

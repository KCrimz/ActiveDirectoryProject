<h1>Active Directory Project</h1>

<h2>Description</h2>
THis project focuses on using virtual machines to create a Domain Controller and client computer newtork. We will install and create both machines along with configuring AD DS (active Directory) while making sure Internet and internal connections are given.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used</h2>

- <b>Windows 10</b>
- <b>Windows 2019 Server</b>

<h2>Skills:</h2>     
-Virtual machine setup and configuration
-IP , DHCP, and DNS netowrking configurations for individual devices
-Troubleshooting for each
-small corporate esk layout
-AD DS Basic setup and adding clients to Domain

<h2>Walk Through:</h2>

<p> Download/installoracle box virtualization: https://www.virtualbox.org/wiki/Downloads </p>
<p> Download Windows server 2019 ISO: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019 </p>
<p> Download Windows 10 ISO: https://www.microsoft.com/en-us/software-download/windows10 </p>


<p> Create Virtual Machine with windows 10 OS with the following parameters and settings. Install windows server 2019 On this machine <p/>
<img src="https://imgur.com/XfY5mxy.gif"/>

OPTIONAL: Go to devices menu top of the VM and inesert guest additions CD, go to  "thisPC" and run the AMD64 in Virtual guesbox for smoother experience in the VM

Now we Setup Our IP adressing and routing in newtork/adapter options. Label each to prevent confusion from internet and internal connections. Give internal IPv4 a manual configuration as such
<img src="https://imgur.com/ccxdjum.gif"/>

<p>INSTALL AD DS (active Directory domain Services) and do post delpoyment configuration for your needs and create a domain. Computer will restart</p> 
<img src="https://imgur.com/w3w9OT0.gif"/>

<p>CREATE a Dedicated ADMIN account for your Domain to better harden security. A speaerate organization Unit helps and folloow your companies naming Schema ( I do password never expires for the puposses of this Project haha). Add used to your DOMAIN ADMINS. Login to this account on windows </p>
<img src="https://imgur.com/TVWt2wD.gif"/>

Now we are going to install NAS/RAT to allow internet connectivity to client through the Domain controller. Setup routing and remote access though your Internet NAT we previously labeled with our internal connection for your DC local
<img src="https://imgur.com/InALAaw.gif"/> <img src="https://imgur.com/J8rSWag.gif"/>

<p>SETUP and install DHCP server on the domain controller So client can get an IP address to utilize the internet connection. Assign a scope of 172.16.0.100-200 mask of 24 and gateway 172.16.0.1 (DC IP address) and lease duration based on what your limits are on connections
AUTHORIZE the DHCP server. Configure local server to use internet connection for this lab. DONT recommend in an live enviornement on DC Double check that your Server option in IPv4 hs a routher with the DC IP adress of 172.16.0.1 as it handles these connections</p>
<img src="https://imgur.com/6BsGNXp.gif"/>

<p>ADD users to AD DS (for the puroses of this lab I used a script with a name generated file) then we can begin to setup the Client PC. Create a new VM with the windows 10 ISO following configurations shown and an internal NIC. You dont have to use a product key for this lab and make sure to use windows 10 PRO to be able to join the DC. Choose the Option "I dont have internet" when prompted during setup as we will address that after. Continue with limited setup ( unless you want to re create a whole Miscorsoft account haha )</p>
<img src="https://imgur.com/oHBPb6g.gif"/>

Verify after setup and user creation that you have Internet connectivity. Go to Command line (CMD) and type "ipconfig /all" Verify the Defauly gateway DHCP server and DNS server are all in good order
<img src="https://imgur.com/O2gdxzA.gif"/>

Rename the computer appropriately in rename PC advanced so we can also join the domain in my case "mydomain.com" and login with proger credentials. Computer will restart upon confirming
<img src="https://imgur.com/S8OwRlh.gif"/>

We can now see on the server VM that in DHCP the CLient 1 computer now has a Lease in DHCP and that that machine has also been added to active directory so users may have acess to it. Try adding a new or using an existing user in AD DS to log into the newly connected Windows 10 computer EZ
<img src="https://imgur.com/PHiyisf.gif"/>

LAB FINISHED!!!
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

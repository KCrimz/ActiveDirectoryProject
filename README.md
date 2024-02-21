<h1>Active Directory Project</h1>

<h2>Description</h2>
THis project focuses on using virtual machines to create a Domain Controller and client computer newtork. We will install and create both machines along with configuring AD DS (active Directory)
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used</h2>

- <b>Windows 10</b>
- <b>Windows 2019 Server</b>       

<h2>Walk Through:</h2>

<p> Download oracle box virtualization: https://www.virtualbox.org/wiki/Downloads </p>
<p> Download Windows server 2019 ISO: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019 </p>
<p> Download Windowns 10 ISO: https://www.microsoft.com/en-us/software-download/windows10 </p>


<p> Create Virtual Machine with windows 10 OS with the following parameters and settings. Install windows server 2019 On this machine <p/>
<img src="https://imgur.com/XfY5mxy.gif"/>

OPTIONAL: Go to devices menu top of the VM and inesert guest additions CD, go to  "thisPC" and run the AMD64 in Virtual guesbox for smoother experience in the VM

Now we Setup Our IP adressing and routing in newtork/adapter options. Label each to prevent confusion from internet and internal connections. Give internal IPv4 a manual configuration as such
<img src="https://imgur.com/vi3SVLi.gif"/>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

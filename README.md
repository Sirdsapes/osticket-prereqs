<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Web Server: Apache or IIS
- PHP 8.0 - 8.1
- MySQL Database: 5.0+

<h2>Installation Steps</h2>

We need to first create resource groups to install our the VM on using Azure.
<p>
<a href="https://ibb.co/bJn1hLj"><img src="https://i.ibb.co/tX5Bfcw/Resource-Azure-Arrow.png" alt="Resource-Azure-Arrow" border="0"></a>
<a href="https://ibb.co/SBc3KvT"><img src="https://i.ibb.co/9WhrqYX/Create-Resource-G.png" alt="Create-Resource-G" border="0"></a>
<a href="https://ibb.co/10xt2RS"><img src="https://i.ibb.co/WH14KBT/RG-Success.png" alt="RG-Success" border="0"></a>
</p>
<p>
After our resource group is created, we will then set up a VM to install osTicket onto. Make sure the VM is created within the resource group just made, i.e. RG-osTicket.
</p>
<br />

<p>
<a href="https://ibb.co/s1T7zwX"><img src="https://i.ibb.co/FYQpCwd/VM-Create.png" alt="VM-Create" border="0"></a>
<a href="https://ibb.co/qrcJ6GW"><img src="https://i.ibb.co/wzPctHw/VM-Setup.png" alt="VM-Setup" border="0"></a>
<a href="https://ibb.co/BZfFymY"><img src="https://i.ibb.co/9TpSbJd/VM-Setup-Network.png" alt="VM-Setup-Network" border="0"></a>
<a href="https://ibb.co/4FsR4xW"><img src="https://i.ibb.co/XWyxFTX/VM-Create-2.png" alt="VM-Create-2" border="0"></a>
</p>
<p>
After the VM has been successfully deployed, we need to remote into it. Copy the IP of the VM and then open Remote Desktop Connection using Windows. Paste the public IP address into the Computer field and click Connect. When prompted to enter your credential, remember the username and password that was used to create the VM. Click Yes to connect to the VM.
</p>
<br />

<p>
<a href="https://ibb.co/7NnqsMQ"><img src="https://i.ibb.co/yB6rHvp/VM-IP.png" alt="VM-IP" border="0"></a>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/6tNVcG7/Remote-Desk.png" alt="Remote-Desk" border="0"></a>
  
<a href="https://imgbb.com/"><img src="https://i.ibb.co/pZyNJbm/Connection.png" alt="Connection" border="0"></a>

<a href="https://ibb.co/2kq4TwC"><img src="https://i.ibb.co/vj1nSbT/Remote-Desk-Welcome.png" alt="Remote-Desk-Welcome" border="0"></a>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

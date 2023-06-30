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
-We need to install the prerequisites for osTicket now, starting with IIS. Open the Control Panel by typing Control Panel in the search box of the Windows taskbar. Click Programs; click Turn Windows features on or off; scroll down to Internet Information Services and check the box on the left. Expand the World Wide Web services section; expand the Applications Development Features section and check CGI; expand Common HTTP Features and check all; then click OK. 
  
-To test everything is working properly, open a browser and enter 127.0.0.1. If it doesn't work, try reinstalling IIS by unchecking Internet Information Services in Control Panel, clicking OK, then rechecking IIS and pressing OK.
</p>
<br />

<p>
<a href="https://ibb.co/wsfKw67"><img src="https://i.ibb.co/jRSLW4z/IIS-Prompt.png" alt="IIS-Prompt" border="0"></a>

<a href="https://ibb.co/Z2mRWR6"><img src="https://i.ibb.co/FHVkgkb/IIS-Test.png" alt="IIS-Test" border="0"></a>
</p>
<p>
-Next, download PHP Manager For IIS (PHPManagerForIIS_V1.5.0.msi) -- current version is preferred -- and install it. After installing PHPManager, download Rewrite Module (rewrite_amd64_en-US.msi). After both programs are installed, we need to create a PHP directory on the local HDD.

-Right-click the C: drive, go to Folder, and click New, and name the folder PHP. We then need to download PHP to fill the folder. Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into the PHP folder.

-We then need to download VC_redist.x86.exe and install when complete.

-Following that, we need to install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Open the mysql file; do a Typical install. Launch the MySQL Server Instance Configuration Wizard. Click Standard Configuration; keep service name MySQL; set up a password and then click Execute.
</p>
<br />

<p>
<a href="https://ibb.co/jwWP7Xw"><img src="https://i.ibb.co/myXVQWy/PHP-Folder.png" alt="PHP-Folder" border="0"></a>
<a href="https://ibb.co/pPcJrpm"><img src="https://i.ibb.co/3s2BYHJ/PHP-Ext.png" alt="PHP-Ext" border="0"></a>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/QKFPXH4/SQL-Inst.png" alt="SQL-Inst" border="0"></a>
  
<a href="https://imgbb.com/"><img src="https://i.ibb.co/TtnncSt/SQL-Config.png" alt="SQL-Config" border="0"></a>

<a href="https://imgbb.com/"><img src="https://i.ibb.co/YcLwBMH/SQL-Install.png" alt="SQL-Install" border="0"></a>
</p>
<p>
-After MySQL has finished, run IIS as Administrator (right-click and select Run as Administrator). 
  
-Open PHP Manager. You'll see "PHP is not enabled. Register new PHP version to enable PHP via FastCGI." Click Register new PHP version. In the new window, click the 3 dots and locate the php-cgi.exe in the PHP directory we created earlier. Restart server by clicking the name VM-osTicket Home and then Restart in the Actions box on the right.
</p>
<br />

<p>
<a href="https://ibb.co/86RgBkq"><img src="https://i.ibb.co/yWMFR2t/SQL-Window.png" alt="SQL-Window" border="0"></a>
<a href="https://ibb.co/HhqMJK9"><img src="https://i.ibb.co/rdHLWQX/SQL-Reg.png" alt="SQL-Reg" border="0"></a>
<a href="https://ibb.co/dkHZ1vW"><img src="https://i.ibb.co/8PQkTwK/Restart-VM.png" alt="Restart-VM" border="0"></a>
</p>
<p>
-Next, we install osTicket (osTicket v1.15.8 zip). There will be an upload foler in the zip file which you will drag-and-drop into the wwwroot folder located in C: inetpub and then wwwroot. Rename the upload folder you just moved to osTicket. Reopen IIS and restart the server just like before.
-Open osTicket from the IIS window by clicking the osTicket folder under Sites; click "Browse *:80" located on the right panel.
</p>
<br />

<p>
<a href="https://ibb.co/3hz9XP4"><img src="https://i.ibb.co/DKpHXjz/upload-OS.png" alt="upload-OS" border="0"></a>
<a href="https://ibb.co/RTBr98v"><img src="https://i.ibb.co/VYQnt6j/OSTick.png" alt="OSTick" border="0"></a>
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

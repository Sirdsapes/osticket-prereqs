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

-We need to first create resource groups to install our the VM on using Azure.

-The name of the resource group will be RG-osTicket.

-Remember to click Create after validation has passed.
<p>
<a href="https://ibb.co/bJn1hLj"><img src="https://i.ibb.co/tX5Bfcw/Resource-Azure-Arrow.png" alt="Resource-Azure-Arrow" border="0"></a>
<a href="https://ibb.co/SBc3KvT"><img src="https://i.ibb.co/9WhrqYX/Create-Resource-G.png" alt="Create-Resource-G" border="0"></a>
<a href="https://ibb.co/10xt2RS"><img src="https://i.ibb.co/WH14KBT/RG-Success.png" alt="RG-Success" border="0"></a>
</p>
<p>
-After our resource group is created, we will then set up a VM to install osTicket onto. Make sure the VM is created within the resource group just made, i.e. RG-osTicket.
</p>
<br />

<p>
<a href="https://ibb.co/s1T7zwX"><img src="https://i.ibb.co/FYQpCwd/VM-Create.png" alt="VM-Create" border="0"></a>
<a href="https://ibb.co/qrcJ6GW"><img src="https://i.ibb.co/wzPctHw/VM-Setup.png" alt="VM-Setup" border="0"></a>
<a href="https://ibb.co/BZfFymY"><img src="https://i.ibb.co/9TpSbJd/VM-Setup-Network.png" alt="VM-Setup-Network" border="0"></a>
<a href="https://ibb.co/4FsR4xW"><img src="https://i.ibb.co/XWyxFTX/VM-Create-2.png" alt="VM-Create-2" border="0"></a>
</p>
<p>
-After the VM has been successfully deployed, we need to remote into it. Copy the IP of the VM and then open Remote Desktop Connection using Windows. Paste the public IP address into the Computer field and click Connect. When prompted to enter your credential, remember the username and password that was used to create the VM. Click Yes to connect to the VM. 
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
  
-Open osTicket from the IIS window by clicking the osTicket folder under Sites; click "Browse *:80" located on the right panel and osTicket should open.

-Some services appear to not be working -- as indicated by the X. Go back to IIS and click PHP Manager within the osTicket folder and click "Enable or disable an extension". Enable the disabled extensions (php_imap.dll, php_intl.dll, php_opcache.dll) by clicking an extension and then Enable under Actions. 

-Refresh osTicket in the browser to see the extensions now enabled.

-In C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename "ost-sampleconfig" to "ost-config". Open the Properties of ost-config and go to the Security tab, click Advanced, Disable inheritance, and Remove all permissions. 

-Click Add and Select a principal. Add Everyone and give them Full control. Everyone should now have permission to modify the ost-config file.
</p>
<br />

<p>
<a href="https://ibb.co/3hz9XP4"><img src="https://i.ibb.co/DKpHXjz/upload-OS.png" alt="upload-OS" border="0"></a>
<a href="https://ibb.co/RTBr98v"><img src="https://i.ibb.co/VYQnt6j/OSTick.png" alt="OSTick" border="0"></a>
<a href="https://ibb.co/SwWsc8z"><img src="https://i.ibb.co/k2kHJft/OSTick-Succ.png" alt="OSTick-Succ" border="0"></a>
<a href="https://ibb.co/LNj5NsL"><img src="https://i.ibb.co/rd8sdXC/OS-Enab.png" alt="OS-Enab" border="0"></a>
<a href="https://ibb.co/DKFFqMM"><img src="https://i.ibb.co/kcTTdDD/Exten-Enab.png" alt="Exten-Enab" border="0"></a>
<a href="https://ibb.co/mNfQk7z"><img src="https://i.ibb.co/fDjmf70/Os-Enabl.png" alt="Os-Enabl" border="0"></a>
<a href="https://ibb.co/VvFRsj7"><img src="https://i.ibb.co/Hrc6jFW/OST-Config.png" alt="OST-Config" border="0"></a>
<a href="https://ibb.co/z7fmq4r"><img src="https://i.ibb.co/RBHgRD9/Advan-Sec.png" alt="Advan-Sec" border="0"></a>
<a href="https://ibb.co/k4JF386"><img src="https://i.ibb.co/StcpQn7/Permission.png" alt="Permission" border="0"></a>
</p>
<p>
-We will continue setting up osTicket in the browser. Click Continue. Fill out the necessary System Settings and Admin User information.
  
-We need to install HeidiSQL (HeidiSQL_12.3.0.6589_Setup) to finish the Database Settings portion. Once Heidi is finished downloading and installing, click New, enter your username and password that was used for the MySQL set up and click Open. In the new window, right-click Unnamed and create a new Databas named osTicket.

-Back in the osTicket browser window, we enter in the relevant information and install.

</p>
<br />

<p>
<a href="https://ibb.co/mNfQk7z"><img src="https://i.ibb.co/fDjmf70/Os-Enabl.png" alt="Os-Enabl" border="0"></a>
<a href="https://ibb.co/tbsCZHw"><img src="https://i.ibb.co/nDck3wq/OS-Info.png" alt="OS-Info" border="0"></a>
<a href="https://ibb.co/qd7pqB6"><img src="https://i.ibb.co/DtzQc4d/Heidi.png" alt="Heidi" border="0"></a>
<a href="https://ibb.co/1qcML9m"><img src="https://i.ibb.co/d2ZtrQ5/Heidi-Dat.png" alt="Heidi-Dat" border="0"></a>
<a href="https://ibb.co/rZsV0TK"><img src="https://i.ibb.co/qR5vjXL/Heidi-Ost.png" alt="Heidi-Ost" border="0"></a>
<a href="https://ibb.co/G251WNX"><img src="https://i.ibb.co/Z8MwB73/Os-Tick-Inst.png" alt="Os-Tick-Inst" border="0"></a>
</p>
<p>
If everything was done correctly, osTicket will have installed. People will now be able to create tickets.
</p>
<br />

<p>
<a href="https://ibb.co/2vWfn3y"><img src="https://i.ibb.co/9bcC8HN/OST-Succ.png" alt="OST-Succ" border="0"></a>
<a href="https://ibb.co/XD9g1Z7"><img src="https://i.ibb.co/Sc28bXt/OS-Login.png" alt="OS-Login" border="0"></a>
<a href="https://ibb.co/3r6TR4R"><img src="https://i.ibb.co/Lkj0NYN/Os-Tick-Tick.png" alt="Os-Tick-Tick" border="0"></a>
</p>
<p>

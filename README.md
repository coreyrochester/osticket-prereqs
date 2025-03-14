<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- An Azure subscription 
- Windows 10  
- Virtual Machine 
- Remote Destop Connection 


<h2>Installation Steps</h2>

<p>
<img src="![image](https://github.com/user-attachments/assets/42128f56-f580-4ebc-b2d7-a97e2e359e14)
"/>
</p>
<p>
Within the VM you have created, download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
</p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/e929417f-d2c7-4923-8ce9-c362a781e786)
"/>
</p>
<p>
-Install/Enable the windows feature Internet Information Services (IIS) with CGI
- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
-From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/a2668633-e70a-4faf-b7bc-d79c66408e36)
"/>
</p>
<p>
-Create a new folder in the C: Drive and rename it "PHP"
  -From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
-From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
-From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  Follow the directions on what to click found below
1.Typical Setup ->
2.Launch Configuration Wizard (after install) ->
3.Standard Configuration ->
Username: root
Password: root
*NOTE* This is not a password we would normally use this is just for the sake of an example. DO NOT USE THIS IN REAL WORLD PRACTISE 


</p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/c4c5bf91-165c-4a1f-9d19-e987e600f2c6)
"/>
</p> Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

<p>

</p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/43ff1865-db19-4e6e-a0e4-e5da20166386)
"/>
</p> From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”

<p>

</p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/cb59f794-0b3a-4179-8c91-ae6d376819cb)
"/>
</p> Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

<p>

</p>

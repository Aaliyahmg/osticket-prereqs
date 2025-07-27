# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. Create the Azure VM
Name: osticket-vm
OS: Windows 10
vCPUs: 4
Username: labuser
Password: osTicketPassword1!
Log in: Use Remote Desktop (RDP) to connect.
Download & Prepare osTicket Files
  
2.Download osTicket-Installation-Files.zip and unzip it to the Desktop.
The folder should be named "osTicket-Installation-Files".

3. Install Required Software
Enable IIS (Internet Information Services) with CGI:
Open "Turn Windows features on or off".
Enable:
Internet Information Services (IIS)
World Wide Web Services → Application Development Features → CGI
Install from the "osTicket-Installation-Files" folder:
PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
Rewrite Module (rewrite_amd64_en-US.msi)
Set Up PHP:
Create folder: C:\PHP
Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP
Install Dependencies:
VC_redist.x86.exe (Required for PHP)
MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Choose Typical Setup
Run Configuration Wizard after install
Use Standard Configuration
Username: root
Password: root


</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4. Configure IIS & PHP

Open IIS as Admin
Register PHP:
Go to PHP Manager → Set path to C:\PHP\php-cgi.exe
Restart IIS (Stop & Start the server)
5. Install osTicket

Unzip osTicket-v1.15.8.zip from the installation folder.
Copy the "upload" folder to C:\inetpub\wwwroot.
Rename "upload" to "osTicket".
Restart IIS again.
6. Fix Missing PHP Extensions

Open IIS → PHP Manager → Enable or disable extensions
Enable:
php_imap.dll
php_intl.dll
php_opcache.dll
Refresh the osTicket page in your browser.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


Rename Config File:
Go to C:\inetpub\wwwroot\osTicket\include
Rename ost-sampleconfig.php → ost-config.php
Set Permissions:
Right-click ost-config.php → Properties → Security
Disable inheritance → Remove all permissions
Add Everyone → Full Control
8. Set Up Database with HeidiSQL

Install HeidiSQL from the installation folder.
Open HeidiSQL → New Session:
Username: root
Password: root
Create a new database: osTicket
9. Complete osTicket Setup in Browser

Open: http://localhost/osTicket
Fill in:
Helpdesk Name
Default Email
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click "Install Now!"
10. Final Steps

Login Page: http://localhost/osTicket/scp/login.php
End-User URL: http://localhost/osTicket/

</p>
<br />

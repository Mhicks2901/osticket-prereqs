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

- Azure Subscription
- Files For Install https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

- Create a resource Group in Azure
- Create an Azure Virtual Machine in Windows 10
  - Name (whatever you choose)
  - username (whatever you choose)
  - Password (whatever you choose)

After making our Virtual Machine we will log into it using remote desktop. Inside our Virtual machine we will need to install/enable IIS in Windows
 - Go into your control panel (inside the VM)
 - Inside the control panel go into programs and than Turn on Windows features on or off
   <p>
     <img src="https://i.imgur.com/D50bfHe.png" width="400" height="200"/>
   </p>
   <P>
     <img src="https://i.imgur.com/H8zPq8j.png"
   </P>
     
   - Make sure the Internet Information Services box is checked.
   - Then turn on the World Wide Web Services is checked.
   - Then go into the Application Development Features and then check the CGI box. Collapse that folder
   - Then go into Common HTTP Features and make sure ALL folders are checked. Then okay and wait for the files to be installed

- From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP
- From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- From the Installation Files, download and install VC_redist.x86.exe.
- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  - Typical Setup
  - Launch Configuration Wizard (after install)
  - Stand Configuration
  - Choose a password
 - Open IIS as an Admin
   <P>
   <img src="https://i.imgur.com/naKiFJv.png"/>
   </P>
 - Register PHP from within IIS
   <P>
     <img src="https://i.imgur.com/2WYoWxq.png"/>
   </P>

      - Browse to your directory of C:\PHP
 - Reload IIS (Open IIS, Stop and Start the server)
   <P>
     <img src="https://i.imgur.com/tPxLSDP.png"/> 
   </P>
 - Install osTicket
   - Download osTicket from the Installation Files Folder
   - Extract and copy “upload” folder to c:\inetpub\wwwroot
   - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
     
- Reload IIS (Open IIS, Stop and Start the server)
- Go to sites -> Default -> osTicket
  - On the right, click “Browse *:80” 
 <P>
  <img src="https://i.imgur.com/noybem3.png"/>
</P>  
  
- Some extensions may not be enabled
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
  - Enable: php_imap.dll
  - Enable: php_intl.dll
  - Enable: php_opcache.dll
  - Refresh the osTicket site in your browse, observe the changes
 
- Rename: ost-config.php
  - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

- Assign Permissions: ost-config.php
  - Disable inheritance -> Remove all
  - New permissions -> Everyone -> All

- Continue Setting up osTicket in the browser (click Continue)
  - Choose a name for the helpdesk
  - Add email address so you can receive email from customers
    
- From the Installation Files, download and install HeidiSQL.
  - Open Heidi SQL
  - Create a new session, make your desired username and password
  - Connect to the session
  - Create a database named by your choosing
 
- Continue Setting up osticket in the browser
  - In MySQL put in your database name, username and password

- Clean up
   - Delete C:\inetpub\wwwroot\osTicket\setup
   - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  

  









 
   


   


  
  




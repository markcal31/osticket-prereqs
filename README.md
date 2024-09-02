<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab I will demonstrate the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Enable Internet Information Services
- Install PHP Manager for IIS
- Install Rewrite Module
- Install VC Redist
- Install MYSQL
- Install osTicket
- Install HeidiSQL
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>
<p>
Create an Azure Virtual Machine 
<br>- Windows 10, 4 vCPUs </b>
<br>- Name: Vm-osticket </b>
<br>- Username: labuser </b> 
<br>- Password: osTicketPassword1! </b>
</p>

![image](https://github.com/user-attachments/assets/5c10b98c-650f-414c-a63d-d3fe2c605191)

<p>
Install / Enable IIS in Windows WITH
CGI and Common HTTP Features 
<br>-  World Wide Web Services -> Application Development Features -> </b>
<br>- [X] CGI </b>
<br>- [X] Common HTTP Features </b> 
</p>

![image](https://github.com/user-attachments/assets/cd3daf8a-65bb-45cd-9376-f829e7090278)

<p>
AND IIS Management Console
<br>-  Internet Information Services -> Web Management Tools -> IIS Management Console </b>
<br>- [X]  IIS Management Console </b>
</p>

![image](https://github.com/user-attachments/assets/b6f028f4-a2f3-485f-b0ac-8a4acdd018d6)

<p>
<br>-  From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) </b>
</p>
<p>
<br>-  From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi) </b>
</p>
<p>
<br>-  Create the directory C:\PHP </b>
</p>

![image](https://github.com/user-attachments/assets/9e4ab7c8-2692-40ef-a53e-983bc872ae57)

<p>
<br>-  From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP </b>
</p>

![image](https://github.com/user-attachments/assets/5c3286d0-ff13-4e4d-8cef-c0d67edb5598)

<p>
<br>-  from the installation files, download and install VC_redist.x86.exe</b>
</p>

![image](https://github.com/user-attachments/assets/a26121fb-f721-4455-81a1-d601cbd939ec)

<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
<br>- Typical Setup -> </b>
<br>- Standard Configuration -> </b>
<br>- Password1 </b>
</p>

![image](https://github.com/user-attachments/assets/4e355080-822c-4133-9409-e298a9d8672b)

<p>
<br>- Open IIS as an Admin</b>
</p>

![image](https://github.com/user-attachments/assets/f608096c-e1a5-46b0-a588-dd2e691b4dfe)

<p>
<br>- Register PHP from within IIS</b>
</p>

![image](https://github.com/user-attachments/assets/ada0559d-d839-4daf-8bfe-5c7bc929c3b7)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

![image](https://github.com/user-attachments/assets/607cd130-9d3d-43b0-83d2-84c52a21a044)

<p>
Install osTicket v1.15.8
<br>- Download osTicket from the Installation Files Folder </b>
<br>- Extract and copy “upload” folder to c:\inetpub\wwwroot </b>
<br>- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” </b>
</p>

![image](https://github.com/user-attachments/assets/46a6ee19-0512-46ff-ba27-eadc4c016256)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

<p>
Go to sites -> Default -> osTicket
<br>- On the right, click “Browse *:80” </b>
</p>

![image](https://github.com/user-attachments/assets/e02c2986-67ec-4590-b7af-cb4dbdeba568)

<p>
enable extensions
<br>- Go back to IIS, sites -> Default -> osTicket </b>
<br>- Double-click PHP Manager </b>
<br>- Click “Enable or disable an extension” </b>
  <br>- Enable: php_imap.dll </b>
  <br>- Enable: php_intl.dll </b>
  <br>- Enable: php_opcache.dll </b>
<br>- Refresh the osTicket site in your browse, observe the changes </b>
</p>

![image](https://github.com/user-attachments/assets/cf08536d-f16f-40a2-840a-69790d8f0d61)

<p>
Rename: ost-config.php
<br>- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php </b>
<br>- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

![image](https://github.com/user-attachments/assets/1d172731-528f-4d79-94e7-79974d73a534)

<p>
Assign Permissions: ost-config.php
<br>- Disable inheritance -> Remove All </b>
<br>- New Permissions -> Everyone -> All </b>
</p>

![image](https://github.com/user-attachments/assets/6066a7f9-6ab1-4059-b25b-45f4585b36db)

![image](https://github.com/user-attachments/assets/462e0570-f8df-4256-bbfe-bb2dd8e0c37b)

![image](https://github.com/user-attachments/assets/3219ca3a-d7bf-4120-ac36-b5fe6f4e39ae)

<p>
Continue Setting up osTicket in the browser (click Continue)
</p>

![image](https://github.com/user-attachments/assets/b6f58aee-874d-4ce2-a808-c20b56349e24)

<p>
From the Installation Files, download and install HeidiSQL
<br>- Open Heidi SQL </b>
<br>- Create a new session, root/Password1 </b>
<br>- Connect to the session </b>
<br>- Create a database called “osTicket” </b>
</p>

![image](https://github.com/user-attachments/assets/5ee07609-8a68-4f46-a869-13741b60fce8)

![image](https://github.com/user-attachments/assets/5b5145ae-ee5b-4167-8a1b-d8790565e128)


<p>
Continue Setting up osticket in the browser
<br>- MySQL Database: osTicket </b>
<br>- Click “Install Now!” </b>
</p>

![image](https://github.com/user-attachments/assets/3503152f-d028-4f26-9e29-0bb0add1b467)

<p>
Browse to the help desk login page: http://localhost/osTicket/scp/login.php
</p>

<p>
Continue Setting up osticket in the browser
<br>- Delete: C:\inetpub\wwwroot\osTicket\setup </b>
<br>- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

Congradulations!  osTicket is now ready for use!

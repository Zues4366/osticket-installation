<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket Installation</h1>

For the installation of osTicket, I will use Azure to set up a new virtual machine and prep osTicket from the ground up.

<h1>Files Used in Lab</h1>

![image](https://github.com/Zues4366/osticket-installation/assets/33434045/f8e98e1d-d3d8-46fe-83b1-6f7a38086f09)


<h1>Installation Steps</h1>

Before downloading any files, the Internet Information Services (IIS) needs to be enabled along with the CGI since we are creating the ticketing system locally.

![image](https://github.com/Zues4366/osticket-installation/assets/33434045/c25f9429-f192-43d9-8353-20e8ddc39031)


We download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi), Rewrite Module (rewrite_amd64_en-US.msi),VC_redist.x86.exe, MySQL 5.5.62 (MySQL-5.5.62-win32.msi)
Now before we download and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip), we need to create the directory C:\PHP in the Local Disk. We will be unzipping the contents of PHP 7.3.8 into the directory.

After these files have been installed, we open IIS as an Admin, and from there we register the PHP directory in the PHP manager, the php.cgi is in the PHP file directory that we just unzip to. This requires a restart of the IIS so we will stop and start the server.

![image](https://github.com/Zues4366/osticket-installation/assets/33434045/53e13dc9-d262-43cb-8593-a704a9cdeba1)


We can finally download and install the osTicket v.1.15.8. From the file we extract and copy the "upload" folder to C:\intelpub\wwwroot. We also rename the "upload" folder to "osTicket"
Going back to  the IIS Manager, we go to Sites -> Default -> osTicket. We open "Browse *:80" to open osTicket in the browser. We go back to the manager to enable the extensions require to run the ticketing system.
We will be enabling these extensions:
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll

![image](https://github.com/Zues4366/osticket-installation/assets/33434045/4f7819cf-f64a-426f-a576-b2101d6ea0f9)


Refresh the osTicket site and the changes should happen.

We head back into C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to rename ost-sampleconfig.php -> ost-config.php
With the ost-config.ph, we go into its properties to assign permissions. We will disable inheritance to remove all and assign new permissions to "Everyone" to have full control.

To properly manage the SQL, we download the Heidi SQL to set it up to be used in osTicket. We create a new session and database of any name. 

Within the landing page of the osTicket, we will set up the SQL Database and install it to be able to be used.
Example:
![image](https://github.com/Zues4366/osticket-installation/assets/33434045/4d953527-b540-4e81-92c1-69ca21f63dea)

<h1>Clean Up</h1>
For a little bit of cleanup, we will be deleting C:\inetpub\wwwroot\osTicket\setup and changing back the permissions of the ost-config.php to "Read" now that the ticketing system is complete.

<h1>Congratulations</h1>

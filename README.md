<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket Installation</h1>

For the installation of osTicket, I will use Azure to set up a new virtual machine and prep osTicket from the ground up.

<h1>Files Used in Lab</h1>


<h1>Installation Steps</h1>

Before downloading any files, the Internet Information Services (IIS) needs to be enabled along with the CGI since we are creating the ticketing system locally.

We download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi), Rewrite Module (rewrite_amd64_en-US.msi),VC_redist.x86.exe, MySQL 5.5.62 (MySQL-5.5.62-win32.msi)
Now before we download and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip), we need to create the directory C:\PHP in the Local Disk. We will be unzipping the contents of PHP 7.3.8 into the directory.

After these files have been installed, we open IIS as an Admin, and from there we register the PHP directory in the PHP manager. We will have to reload the IIS(Stop and Start the server).

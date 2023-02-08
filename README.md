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

- Azure Virtual Machine
- osTicket Installation Files
- HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Welcome to my first tutorial! First things first: we'll be creating a resource group in the Azure portal, and then creating a 4vcpu Windows virtual machine in said resource group. We'll call the resource group "osTicket" and the virtual machine "VM1". You can call the resource group and VM anything you'd like, and you can use anywhere between a 2vcpu and 4vcpu machine.
</p>
<br />

<p>
<img src="https://imgur.com/tjyhWNI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the deployment is complete, click on "Go To Resource". From this screen, we'll copy the public IP of the VM and open Remote Desktop. Paste the IP in the first box, then click Connect->More Choices->Use A Different Account->then input your login info and click OK. Click yes, and then wait for the VM to log in and connect.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After navigating to the home screen, we're ready to start gathering and downloading the prerequisites for osTicket. First, we'll have to enable IIS on the VM. Access the control panel, from here click on Programs->Turn Windows Features On or Off, then check the box next to Internet Information Services, then expand IIS->expand World Wide Web Services->expand Application Development Features->check the CGI box.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now that IIS is enabled, we'll need to install the Web Platform Installer. Navigate to <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">this link</a> in the VM. It includes everything we'll need to fulfill the prerequisites. Download the PHP Manager file from that folder. CLick Download Anyway when promptedm, then click open file. Click through the prompts to finish installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we'll download the rewrite module from the folder with the installation documents. Click Download Anyway when prompted, and then open the file and install. Click through the prompts->Install->Finish.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now navigate to the C drive and create a new folder named PHP.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate back to the Installation Files and download the PHP 7.3.8 file, then click download anyway.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to "Downloads" in file explorer. Right click the new php download->Extract All->Browse->This PC->C: Drive->PHP folder->Selcet Folder->Extract. Once completed, navigate back to the Installation Files and download and install the VC redistributable. CLick through the prompts to install, then navigate back to the Installation Files.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once there, download and install MySQL 5.5.62. Click through the initial two prompts and then select Typical->Install->Finish. Then the configuration wizard should show up. From there, click through the first prompt and then select Standard Configuration. Then set a password, click through the remaining prompts, and click execute. Finally, hit finish to close the configuration wizard.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, in VM1, navigate to IIS  and run it as an administrator. Click PHP Manager in the menu then click Register New PHP Version->Browse (three dots)->PHP folder->php-cgi->OK. Now restart the server.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate back to the Installation Files and download and install osTicket, and then copy the upload file into the c:\inetpub\wwwroot folder. Once it's done copying, rename upload to "osTicket". Then, reload IIS again.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In IIS, go to sites->Default->osTicket. On the right hand side of the screen, click on "Browse *:80". It should automatically redirect to a web browser.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once here, notice the red Xs in the list. Let's fix some of those. Go back to IIS and click sites->Default->osTicket->PHP Manager->Enable or Disable an Extension. From here enable the following: php_imap.dll, php_intl.dll, and php_opcache.dll. Refresh the osTicket webpage and notice the differences.
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

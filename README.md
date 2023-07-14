# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
</p>
<p>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Requirements </h2>

- Microsoft Azure (Virtual Machine)
- Heidi SQL
- osTicket Installation Files (Link Provided Below)
<h2> Tutorial Instructions 
<h3> Step 1: Install / Enable IIS in Windows </h3> Access the "Control Panel", "Programs", then "Programs and Features". Then select "Turn Windows features on or off" on the left. On the pop up window, select the box for "Internet Information Services."
</p>
<br />
<img src="https://i.imgur.com/hDMysuo.png" height="80%" width="80%" alt="Enable IIS"/>

</p>
<p>
<h3> Step 2: Install Web Platform Installer </h3> Click the following link for the required downloads https://bit.ly/3WFRPdg. 
Now download the Web Platform Installer and open it.
</p>
<br />

<p>
<img src="https://i.imgur.com/kOh6Ezy.png" height="80%" width="80%" alt="Web Platform Installer"/>
</p>
<p>
From inside the application you will search and install "MySQL 5.5," all "PHP" versions up until 7.3.25. As pictured below, some of the files will fail to download, however the links for those can also be found on the aforementioned install link. 
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/RtPT3ki.png" height="80%" width="80%" alt="Download Failures"/>
</p>
<p>
<h3> Step 3: Install osTicket v1.15.8 </h3> Click the link from within the lab files to download osTicket. Once it is in your "Downloads" folder, right click the folder and click "Extract All" to create another folder that we will use later. 
</p>
<br />
<img src="https://i.imgur.com/KMC03rb.png" height="80%" width="80%" alt="Extract All"/>
In the "Downloads" folder open osTicket, and we are going to copy the upload folder. Navigate to "This PC', "Windows (C:)", "inetpub", "wwwroot", and paste within wwwroot. Next, simply rename the "upload" folder to "osTicket".
</p>
<br />
<h3> Step 4: Reload IIS </h3> Go back to IIS by typing it in the Start menu. Click "Restart" on the right side. On the left side click "Sites", "Default Web Site", "osTicket", then on the right side click "Browse *:80". This should open a web browser to osTicket.
</p>
<br />
<img src="https://i.imgur.com/yDjIe1l.png" height="80%" width="80%" alt="Restart IIS"/>
</p>
<p>
<h3> Step 5: Enable Extensions in IIS </h3> Now we are going to go back to IIS Manager. Once again, you can find this by typing it in the Start menu. Navigate to "Sites", "Default", "osTicket", double click on "PHP Manager" and then click "Enable or Disable an Extension". Enable the following extensions: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Then, you can refresh osTicket site in your browser.
</p>
<br />
<img src="https://i.imgur.com/YeSYmiK.png" height="80%" width="80%" alt="enable php"/>
</p>
<p>
<h3> Step 6: Rename ost-config.php </h3> In file explorer go back to the osTicket folder and click on the file "Include". Next rename "ost-sampleconfig.php" to "ost-config.php". It's critical that you do not make an error at this step.
</p>
<br />
<img src="https://i.imgur.com/ECwKXOp.png" height="80%" width="80%" alt="rename ost-config"/>
</p>
<p>
<h3> Step 7: Assign Permissions to ost-config.php </h3> Next we need to assign permissions to ost-config.php. To do that, right click on ost-config.php, go to "Properties", "Security", "Advanced", and "Disable Inheritance". From here we are going to click "Add" so we can add our own permissions. Next click "Select Principal", and type in "Everyone" in the space provided. Click "Check Names", "Ok", and then you want to allow "Full Control".
</p>
<br />
<img src="https://i.imgur.com/6SmEdXP.png" height="80%" width="80%" alt="ost-config permissions 1"/>
</p>
<p>
<h3> Step 8: Continue osTicket Setup in Browser </h3> Setup the name and database information in osTicket. It is important to keep note of the login and password information for later. 
</p>
<p>
<h3> Step 9: Download and Install HeidiSQL </h3> Go to the install files I have provided, and download HeidiSQL. Open the file in "Downloads" and install.
</p>
<br />
<img src="https://i.imgur.com/vHJIhVC.png" height="80%" width="80%" alt="HeidiSQL"/>
</p>
<p>
Next click "New" in HeidiSQL and enter the password you created for MySQL at the beginning of this lab, and open. Right click "Unnamed" and create a new database called "osTicket".
</p>
<br />
<img src="https://i.imgur.com/xwNtYY0.png" height="80%" width="80%" alt="new database"/>
</p>
<p>
Back in osTicket in the browser you can enter the information for MySQL database which we named "osTicket", the MySQL Username which at the beginning of the lab we named "root", and finally the password you created. Click "Install Now", and osTicket should now be installed successfully.
</P>
<br />
<img src="https://i.imgur.com/bLQ99x4.png" height="80%" width="80%" alt="Congrats"/>

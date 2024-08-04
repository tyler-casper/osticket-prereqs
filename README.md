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

- Install/Enable IIS in Windows with CGI and Common HTTP Features & IIS Managment Console
- Install PHP Manager for IIS
- Install Rewrite Module
- Create the directory C:/PHP
- Download PHP 7.3.8 and extract the contents into C:/PHP
- Install VC Redlist.x.86.exe
- Install MySQL 5.5.62
- Open IIS as an Admin
- Register PHP from withen IIS
- Reload IIS
- Install osTicket v1.15.8

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/58ce6e40-38b9-4ef5-81f1-39fcd6b82751)


After installing osTicket, you will need to open the zip file and copy the "upload" folder into the inetpub wwwroot folder like so. Afterwards, rename the "upload" folder to "osTicket", and restart your iis server.

![image](https://github.com/user-attachments/assets/43939df4-5f80-41ef-bccc-49fcdfcc49bd)


Afterwards, you'll open Sites, Default Web Site, and finally osTicket. From here you'll click on Browse *:80 (http)

![image](https://github.com/user-attachments/assets/28d854be-fd90-44d9-a425-5690f650f980)

If done correctly, you should see this page. You'll notice some of the rows contain red x's, in order to change them, go back to your IIS server and click PHP Manager. You'll then click on "Enable or Disable Extensions".  

![image](https://github.com/user-attachments/assets/c134b183-f5c0-4a21-9195-82666ec7ee25)

From here you will see a list of extensions. You will enable the ones circled in red. These are php_imap.dll, php_intl.dll and php_opcache.dll. If you go back and refresh your osTicket page, you'll notice the extensions we enabled will now have green check marks next to them.

![image](https://github.com/user-attachments/assets/6487bc5a-5ba4-4328-8c70-c4c64e2ab953)

From here, browse back to your wwwroot folder, open the osTicket folder that we renamed from earlier, open the "include"" folder, and scroll down until you see the "ost-sampleconfig.php" folder. We will rename this to "ost-config.php". Essentially just removing the "sample" from the file name. Afterwards, right click on the  "ost-config.php" folder, navigate to "Security", then click "Advanced". Click "Disable Inheritance", and in the following popup window, click the bottom option, "Remove all inherited permissions from this object". Click "Add", then, "Select a Principal". In the "Enter the object name to select" box, type the word "everyone", and click the "Check Names" box.

![image](https://github.com/user-attachments/assets/a4c2e0e4-aab7-41c0-8299-bf448f64899e)

For now, just give everyone "Full Control". You can the click "Apply", and "OK" until you've backed out of the windows we opened. From here, navigate back to your osTicket in your browser and click "Continue". From here, continue setting up osTicket with all the credentials you need. From here you will need to install HeidiSQL if you haven't done so already. 

![image](https://github.com/user-attachments/assets/226d8b4e-f717-41b3-b47d-086aa715f12e)

After opening MySQL, log in with the credentials you used to set it up earlier. You should be logged in to your MySQL server at this point. You now need to create a new Database within HeidiSQL.

![image](https://github.com/user-attachments/assets/6d994d46-af64-408d-8b29-beaa3d0c31b7)

To do this, right click "Unnamed", click "Create New", and then click "Database". Make sure you name the database, "osTicket", or it won't work correctly. From here go back to osTicket on your browser and fill out your database settings and click "Install". If all is done correctly, osTicket should be operational.








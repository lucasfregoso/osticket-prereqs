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

- Windows 10 Pro</b> (22H2)

<h2>List of Prerequisites</h2>

- Step 1
- Step 2
- Step 3
- Step 4
- Step 5

(Images going from left to right)
<h2>Installation Steps</h2>

Step 1
<p>
<img width="1545" alt="RG and VM for OsTicket" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8ff3dea7-1c06-4a93-98c3-90e9983992e6">
</p>
<p>
Our first step in setting up an osTicket is to create a resource group in Azure. Begin by searching for "Resource Groups" and creating a new one, giving it a name and ensuring it has a subscription. 

Once validated, proceed to create a virtual machine by searching for "Virtual Machines" and filling in the required details, such as the virtual machine name, image, region, username, and password. 

After everything is set up, open the virtual machine using Microsoft Remote Desktop and start the lab. 
</p>
<br />

Step 2
<p>
<img width="1595" alt="Screenshot 2023-09-25 at 9 49 56 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8addaef5-387c-4d46-ac9a-9a2c854794ab">

</p>
<p>
To begin, open the Control Panel and navigate to "Programs and Features." Click on "Turn Windows features on or off." 

Next, locate "Internet Information Services", check the box, expand it, and then expand "World Wide Web Services" and "Application Development Features." 

Ensure that "CGI" is checked to define the IIS environment. Then, under "Common HTTP Features", verify that all options are checked. Click "OK" to apply changes. 

To confirm everything is set up correctly, open your browser and enter the default loopback address or localhost (127.0.0.1). This should display the default IIS website, indicating the setup was successful. 
</p>
<br />

Step 3
<p>
<img width="1631" alt="Screenshot 2023-09-25 at 10 43 42 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/fc8f877c-09a6-4215-9a72-c84d62105201">
</p>
<p>
📦 Setting Up Key Requirements for the osTicket System
To ensure our osTicket system runs smoothly, we’ll now install several essential components. Follow the steps below carefully:

🔁 Install the Rewrite Module

Click on the link provided to download the Rewrite Module.
Go to your Downloads folder once the file finishes downloading.
Open the installer.
Agree to the terms and conditions.
Follow the prompts to complete the installation.

📂 Set Up PHP Environment 

Create a new folder on your C: drive called: PHP.
Download PHP version 7.3.8 from the official website or trusted source.
Once downloaded, extract the contents of the ZIP file.
Move or extract all files into the C:\PHP folder.
All PHP files should now be inside that folder.

🔧 Install Required Software

Download and install the Microsoft Visual C++ Redistributable (2015–2019 version recommended).
Make sure to choose the correct version for your system (x86 or x64).

Next, download the latest stable version of MySQL Server.
Run the installer and go through the setup process.
Set a root password when prompted.
Note any important configuration details such as the port number.
Ensure the MySQL service is running after installation.

</p>
<br />

Step 4
<p>
<img width="1631" alt="Screenshot 2023-09-25 at 11 37 12 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/90859a89-c128-4aa0-b50b-c11c82a4eeb5">
</p>
<p>
⚙️ Configuring IIS and Setting Up osTicket
Now that the core components are installed, we’ll proceed with configuring IIS and preparing osTicket for installation.

🖥️ Register PHP with IIS

Open IIS Manager as an administrator.
Within IIS, register PHP by linking it to your installed PHP directory.
Once registered, restart IIS to ensure the PHP module is recognized and active.

📥 Download and Prepare osTicket

Download the osTicket installation file from the provided instruction list.
Extract the downloaded ZIP file.
Inside the extracted folder, locate the upload directory.
Copy the entire upload folder to:
C:\inetpub\wwwroot
Once copied, rename the upload folder to osTicket.

🌐 Launch osTicket Installer in Browser

Go back to IIS Manager.
Navigate to:
Sites → Default Web Site → osTicket
On the far right-hand side of IIS, click on ‘Browse *:80’.
This should open your web browser and take you to the osTicket installer page.
If you see this, you’re on the right track!

🔌 Enable Required PHP Extensions

Back in IIS Manager, navigate again to:
Sites → Default Web Site → osTicket
Double-click on PHP Manager.

Under the PHP extensions section, enable the following required extensions:

php_imap.dll
php_intl.dll
php_opcache.dll

</p>
<br />

Step 5
<p>
<img width="771" alt="Screenshot 2023-09-26 at 12 13 47 AM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/07fc8e46-c92f-4750-9e52-0ba8dac20dc5">
</p>
<p>
Finally, we rename our root file to ost-config.php and assign permissions on this file so that everyone is able to do anything to this file since the osTicket installer needs to interact and maanipulate with this file. To do this we go properties from this file, go to security, then to advanced, disable inheritance, and remove all permissions. Afterwards, we add new permissions and allow 'everyone' to have full control. Then, we continue setting up osTicket and install Heidi SQL, which will allow us to connect the MySQL server that we installed earlier and set up a database that the osTicket is going to use. We create the database in Heidi SQL once it's downloaded and call it 'osTicket' and fill out the remaaining info on the osTicket installer website. Lastly, we'll get a 'congratulations' text if we did it right and after this we do a clean up to make everything comes full circle and login to make that works too.
</p>
<br />
Step 5 Continued
<img width="1525" alt="Screenshot 2023-09-26 at 12 14 57 AM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/08c20dd6-774c-4f87-a5bf-7a208a784696">

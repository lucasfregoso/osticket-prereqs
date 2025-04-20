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
☁️ Setting Up Your Environment in Azure for osTicket
Let’s begin the osTicket setup by creating the foundational components in Microsoft Azure.

🧱 Create a Resource Group
Start by logging into the Azure Portal.
In the search bar at the top, type "Resource Groups" and select it.
Click on “+ Create” to start a new resource group.
Give your resource group a meaningful name.
Ensure it is tied to an active subscription.
Click Review + Create, then Create once validation passes.

💻 Create a Virtual Machine
After your resource group is created, go back to the search bar and type "Virtual Machines".
Click “+ Create” to start setting up a new VM.

Fill in the required details:

Virtual Machine Name
Region (choose the region closest to you)
Image (e.g., Windows Server 2019)
Username and Password (you’ll use these to log in later)
Make sure all configurations are correct.
Click Review + Create, then Create once Azure validates your settings.

🖥️ Connect to the Virtual Machine
Once the virtual machine is deployed, go to its overview page.
Click on “Connect” and select RDP (Remote Desktop Protocol).
Download the RDP file provided by Azure.
Open the file using Microsoft Remote Desktop.
Enter your login credentials and start the virtual lab environment.

</p>
<br />

Step 2
<p>
<img width="1595" alt="Screenshot 2023-09-25 at 9 49 56 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8addaef5-387c-4d46-ac9a-9a2c854794ab">

</p>
<p>
🌐 Enabling IIS on Windows
Before installing osTicket, we need to set up the Internet Information Services (IIS) environment properly.

⚙️ Enable IIS and Required Features
Open the Control Panel.
Navigate to Programs → Programs and Features.
On the left-hand side, click “Turn Windows features on or off."

📂 Configure IIS Components
In the Windows Features window, locate and check the box for “Internet Information Services.”
Expand “Internet Information Services” → “World Wide Web Services” → “Application Development Features.”
Ensure “CGI” is checked — this is essential for defining the IIS environment.
Next, under “Common HTTP Features,” make sure the following are all checked:
Static Content
Default Document
Directory Browsing
HTTP Errors
HTTP Redirection
Click “OK” to apply and install the features.

✅ Verify IIS Installation
Once installation is complete:

Open your preferred web browser.
Enter either localhost or the loopback IP 127.0.0.1 in the address bar.
If IIS is installed correctly, you’ll see the default IIS welcome page, confirming your setup was successful.

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
🛠️ Final Configuration and Setup of osTicket
We’re almost there! Let’s finish configuring osTicket and prepare the database connection.

📄 Rename and Set Permissions for the Config File
Navigate to the osTicket directory inside:
C:\inetpub\wwwroot\osTicket

Locate the file named:
ost-config.sample.php

Rename it to:
ost-config.php

Right-click the renamed file and select Properties.
Go to the Security tab, then click Advanced.
Click Disable inheritance and remove all existing permissions.
Now, click Add, choose ‘Everyone’, and grant Full Control.
Apply and save the changes.

This step is necessary to allow the osTicket installer to read from and write to the config file during setup.

🧩 Complete the osTicket Web Installer
Go back to the osTicket web installer in your browser.
Continue the setup steps by entering the required information, including site name, admin credentials, and database details.

🗃️ Install and Use HeidiSQL for Database Setup
Download and install HeidiSQL.
Use it to connect to the MySQL Server that was installed earlier.
Once connected, create a new database named:
osTicket

Fill in the remaining database connection details in the osTicket web installer.
This includes database name (osTicket), MySQL username, and password.

🎉 Finish and Verify Installation
If everything is set up correctly, you’ll see a “Congratulations” message confirming the successful installation.

To wrap things up:

Perform any recommended cleanup steps (e.g., removing the setup directory if prompted).
Log in to the osTicket Admin Panel to verify everything works as expected.

</p>
<br />
Step 5 Continued
<img width="1525" alt="Screenshot 2023-09-26 at 12 14 57 AM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/08c20dd6-774c-4f87-a5bf-7a208a784696">

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
Our first step in creating an osTicket system we create our resource group through Azure and we do that by searching up 'Resource Groups' and create one. From there we just add a name to it and make sure it has a subscription. Then, once it gets validated we move on to creating a virtual machine and we do this by searching for 'virual machines' and fill out all the details that we need, which include virtual machine name, image, region, username/password, etc. After this, once everything is set up we will open our virtual machine through microsoft remote desktop and get started with the lab.
</p>
<br />

Step 2
<p>
<img width="1595" alt="Screenshot 2023-09-25 at 9 49 56 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8addaef5-387c-4d46-ac9a-9a2c854794ab">

</p>
<p>
To start off, we go into control panel and under 'Programs and Features' we click on 'Turn Windows features on/off.' We then go to 'Internet Information Services' and check off the box, expand this box, expand 'World Wide Web Services', expand 'Application Development Features', and check CGI, which is what defines the environment for IIS. Then we go to 'Common HTTP Features' and make sure that everything there is checked as well. Next, we just select OK and these changes will be applied. To double check, we could just load up the default loopback address or our local host (127.0.0.1), which will bring us to the default IIS website and that lets us know we did this correctly.
</p>
<br />

Step 3
<p>
<img width="1631" alt="Screenshot 2023-09-25 at 10 43 42 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/fc8f877c-09a6-4215-9a72-c84d62105201">
</p>
<p>
For the next part, we will install a few key requirements for out osTicketing System to function properly. So, from our instruction list we will install Rewrite Module by clicking on the link provided, go to 'downloads'in our files, open it up, agree to the terms/conditions, and install it. Then, we make a folder called 'PHP' on our c: drive, download 'PHP 7.3.8', onced it's downloaded we extract it into our PHP folder, and everything will get dumped into there. After this, we install both C++ Redistributable and MySQL Server.
</p>
<br />

Step 4
<p>
<img width="1631" alt="Screenshot 2023-09-25 at 11 37 12 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/90859a89-c128-4aa0-b50b-c11c82a4eeb5">
</p>
<p>
Now, we open up IIS as an admin, register PHP from within the the IIS, restart it to make sure that it is registered, and then download the osTicket file from our list of instructions. Next, we extracted and copied the 'upload' (which came from the osTickett file we downloaded) folder into c:\inetpub\www.root and then renamed the 'upload' file to 'osTicket.' After this, we go back to IIS and go to sites-->Default-->osTicket and towards the very right we click 'Browse*:80', which will bring us to the 'osTicket installer' website and means we are on the right path. After this, we go back to IIS to enable some extensions since a couple of them will not be enabled at first. So, we go back to IIS and head to sites-->Default-->osTicket and double click on PHP Manager and enable the following: php_imap.dll, php_intl.dll, php_opcache.dll. 
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

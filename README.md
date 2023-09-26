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

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5


<h2>Installation Steps</h2>

<p>
<img width="1545" alt="RG and VM for OsTicket" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8ff3dea7-1c06-4a93-98c3-90e9983992e6">
</p>
<p>
Our first step in creating an osTicket system we create our resource group through Azure and we do that by searching up 'Resource Groups' and create one. From there we just add a name to it and make sure it has a subscription. Then, once it gets validated we move on to creating a virtual machine and we do this by searching for 'virual machines' and fill out all the details that we need, which include virtual machine name, image, region, username/password, etc. After this, once everything is set up we will open our virtual machine through microsoft remote desktop and get started with the lab.
</p>
<br />

<p>
<img width="1595" alt="Screenshot 2023-09-25 at 9 49 56 PM" src="https://github.com/lucasfregoso/osticket-prereqs/assets/144977615/8addaef5-387c-4d46-ac9a-9a2c854794ab">

</p>
<p>
To start off, we go into control panel and under 'Programs and Features' we click on 'Turn Windows features on/off.' We then go to 'Internet Information Services' and check off the box, expand this box, expand 'World Wide Web Services', expand 'Application Development Features', and check CGI, which is what defines the environment for IIS. Then we go to 'Common HTTP Features' and make sure that everything there is checked as well. Next, we just select OK and these changes will be applied. To double check, we could just load up the default loopback address or our local host (127.0.0.1), which will bring us to the default IIS website and that lets us know we did this correctly.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

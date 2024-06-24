# Active Directory Setup and Demonstration
I will be demonstrating the setup for both Windows Server 2022 in a virtual box manager and Active Directory.



<h2>Windows Server 2022 Installation in VM VirtualBox Manager</h2>

 1. Download Oracle VM VirtualBox Manager.
 2. Download an evaluation copy of Windows Server 2022 from Microsoft's website.
 3. Once installed, open program.
 4. Create a new virtual machine.
 5. Select the Windows Server ISO file and flag "Skip Unattended Installation"
    - This will allow user to install the Desktop Experience Version of the OS. If not, the unattended installation will install the server core OS which runs exclusively in the Windows CLI, unless there is a script provided to specify the correct evaluation copy.

<img src="https://i.imgur.com/SJaHKyY.png" height="60%" width="60%" alt="VM Setup 1"/>

 6. Run through the entire setup process to complete the Virtual Machine set up. If necessary, there are plenty of YouTube videos out there that go through the installation process in-depth.
 7. Once setup is complete, open the VM.
 8. Click next on the first prompt and press "Install now".

<img src="https://i.imgur.com/CfP8Y7V.png" height="60%" width="60%" alt="OS Installation 1"/>

 9. I am installing Windows Server 2022 Standard Evaluation (Desktop Experience). This is not an upgrade so I went through the Custom installation option and selected my drive to install the system to.

<img src="https://i.imgur.com/jmbxuG0.png" height="60%" width="60%" alt="OS Installation 2">>

 10. Set up the administrator user.

<img src="https://i.imgur.com/w91rO9I.png" height="60%" width="60%" alt="OS Installation 3">

 11. Press Ctrl+Alt+Del to unlock the OS. In VirtualBox, press Ctrl+Del to simulate the required keys.
 12. Sign in and Server Manager should automatically open. If it doesn't, open the start menu and search for Server Manager. Click the first app that appears.

<img src="https://i.imgur.com/8wlMQcL.png" height="60%" width="60%" alt="OS Installation 3">

<h2>Server Machine Setup</h2>
<h3>Workgroup vs. Domain</h3>

A workgroup is a logical network more suited for the home environment. Each device is independently configured to a sole user and cannot be seemlessly transfered from one device to the next. The only connection each device has in the workgroup is the network all of them are connected too. This is ideal for the home environment where the family have individual devices such as computers and each computer is uniquely configured to a different person in that household.

A domain is a logical network that is suited for companies that have plenty of employees onboard. This allows for admins who maintain the domain controller to register users and computers to the server. Once a user has there login credentials and permissions set, they will be able to log into any computer within that domain that is within their privilege to log in to. Those users and computers can then be further organized into what are called organizational units(OU). For example, there can be an OU for different offices named "California" and "Washington". Within those OUs can be sub-OUs for the Finance team and the Sales team for each California and Washington respectively and so on. I can then apply group policies to these OUs and set them up in a way where the Sales team only has access to Sales data and the Finance team can only access Finance data. 
This is a very broad description of what a domain is as what an admin can do within domain can be very complex. Domains essentially give admins an easier time when trying to organize users and devices for large companies.

<h3>Domain Controller Prep</h3>

To quickly brief, a domain controller is  essentially the domain. And furthermore are servers. These terms may be used synonymously within this demo and in the real world as well.

<h4>First things first. Set a Computer Name!</h4>

This is important because computers come with a default name that may not be too user-freindly. I want to set my server to an easy-to-remember name that also defines the entity of what the server is for. To do so, follow these steps: (Naming conventions and organization practices vary throught the professional landscape. The name I use may not be professionaly accurate but will work for this demo.)
 1. Navigate to the Settings App.
 2. Select the System path.
 3. Navigate to the About Tab.
 4. Press "Rename this PC" and enter a new name. Many of these configuration updates will require a restart and this is one of those configurations. 



 <img src="https://i.imgur.com/f85kjgm.png" height="60%" width="60%" alt="PC Rename 1">
 
 5. The Server Name is now updated:

<img src="https://i.imgur.com/bgeQd9w.png" height="60%" width="60%" alt="PC Rename 2">

<h4>Next. IP and DNS Setup!</h4>

Since this domain is the server that my company is going to use for Active Directory Domain Services (AD DS), I will need to set a static IP address and a preferred DNS address. The reason why we have to set up the DNS address is because AD DS utilizes DNS in order to perform various functions such as authentication. When we download the DNS role/tools onto the server, plenty of records will be written to the server for the server's DNS functions.
To set this up, follow these steps:

1. Navigate to the Control Panel.
2. Press Network and Internet.
3. Press Network and Sharing Center.
4. Press the connection you see on the right-hand side of the window or Press Change adapter settings. From there, I can select my current connection which is "ethernet".
5. Click Properties.
6. Double-click Internet Protocol Version 4 (TCP/IPv4).
7. In order to manually add addresses, I have to select "Use the following..." flags.
8. I can now give my server a static IP address, subnet mask, and a DNS server address.
   - The DNS server address will be the server so I used my server's IP address as the DNS server address. A loopback address can also be used.
   - Note: the computers that will set up in my company will need to utilize the correct DNS server address.

<img src="https://i.imgur.com/axxrJAH.png" height="60%" width="60%" alt="IPv4 Settings Page">


- Creating a new Forest + other options


Adding Server Roles and Features

Active Directory Users and Computers
 - Path Breakdown
 - Computers
 - Users
 - Organization Units

Setting up Shared Data and Folders


# Active Directory Setup and Demonstration
I will be demonstrating the setup for both Windows Server 2022 in a virtual box manager and Active Directory.



<h2>Windows Server 2022 Installation in VM VirtualBox Manager</h2>

 1. Download Oracle VM VirtualBox Manager.
 2. Download an evaluation copy of Windows Server 2022 from Microsoft's website.
 3. Once installed, open program.
 4. Create a new virtual machine.
 5. Select the Windows Server ISO file and flag "Skip Unattended Installation"
    - This will allow user to install the Desktop Experience Version of the OS. If not, the unattended installation will install the server core OS which wuns exclusively in the Windows CLI

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
<h3>IP and DNS Settings</h3>
<h3>Domain Controller Prep</h3>

 - Setting a static IP address on the local server machine.
 - Creating a new Forest + other options
 - Updating the DNS server to a loopback address.

Adding Server Roles and Features

Active Directory Users and Computers
 - Path Breakdown
 - Computers
 - Users
 - Organization Units

Setting up Shared Data and Folders


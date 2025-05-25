<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
In this lab we're going to walk through how to create an Active Directory home lab Environment using Oracle Virtual Box. Configuring and running this lab will help you understand how Windows networking and active directory operates, so I recommend first following this guide or video and then trying it on your own by taking notes so that you can remember all the steps by yourself. This will guarantee that the information sticks and will help you answer any questions you may have. This tutorial doesn't go over installing Oracle VirtualBox, but it does cover installing the server and client as well as a step by step of everything else, so I do recommend installing Oracle VirtualBox prior to this. Thank you!
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows Server 2019</b>
- <b>Windows 10 Pro</b>

<h2>Program walk-through:</h2>

<p align="center">
Launch Oracle VirtualBox: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a new Virtual Machine with the following settings:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Launch the virtual machine and use Windows Server 2019 iso to boot: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Follow on screen instructions to install, creating your password in the process(installation may take some time):  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once signed in, go to ethernet settings and choose "Change adapter settings":  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will see two networks based on your settings from earlier, right click on both and click Status -> Details:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Label both networks based on which is your "Internet", which should show your IP in Details and which one is your "Internal" network, which should show an APIPA address as shown below:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once labeled, right click on "Internal" network and choose properties:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double click IPv4 and set as shown below:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, right click Start and choose System -> Rename this PC:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once labeled, right click on "Internal" network and choose properties:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once labeled, right click on "Internal" network and choose Properties -> TCP/IPv4:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set to the following information for the IP address:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, Right click Windows -> System -> Rename PC in order to change the name to DC (or any identifier you would prefer). This will cause a restart:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Signing back in after restart, go to Server Manager and choose "Add roles and features":  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go through settings, choosing to add Active Directory Domain Services, choosing Add Features when prompted before installation:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once finished, go to Server Manager and click on yellow warning flag, clicking on "Promote this server to a domain controller":  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Under Deployment Configuration, choose "Add a new forest" and naming your domain anything ending with ".com":  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set your password, then continue hitting next until install, which will restart your server after finishing:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once restarted, go to Start -> Adminstrative Tools -> Active Directory Users and Computers:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From here, create a new Organizational Unit and create an User inside of that unit:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, add this user to the Domain Admins group:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You may now sign out and log in with the credentials of the new user you just created:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You may now sign out and log in with the credentials of the new user you just created:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After signing back in, go to Server Manager and click on "Add Roles and Features" once again to set up RAS/NAT:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Choose Remote Access and continue through prompts, making sure to choose Routing when asked. Click Install at the end:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once installed, go to Tools in Server Manager, and choose Routing and Remote Access:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right click on DC(local) and choose Configure and Enable Routing and Remote Access, choosing the following options through the setup:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once finished, return to "Add Roles and Features", this time choosing DHCP server to install:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once installed, go to Tools in Server Manager again and choose DHCP:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, open up dc.name.com and open up IPv4, right clicking it and choosing "New Scope...":  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From here, fill in prompts as follows:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
Once finished, we will now use a PowerShell script to populate users in our domain. Download the script from the following url: <url>https://github.com/joshmadakor1/AD_PS/archive/master.zip<url/><br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

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
<img src="https://i.imgur.com/gxweEYe.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Create a new Virtual Machine for Windows Server 2019 with the following settings:  <br/>
<img src="https://i.imgur.com/ltQam7I.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Launch the virtual machine and use Windows Server 2019 iso to boot: <br/>
<img src="https://i.imgur.com/p9e7WfW.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Follow on screen instructions to install, creating your password in the process(installation may take some time). Make sure to choose the desktop experience for this tutorial:  <br/>
<img src="https://i.imgur.com/dCJNxIy.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Once signed in, go to ethernet settings and choose "Change adapter settings":  <br/>
<img src="https://i.imgur.com/yXVwRPx.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
You will see two networks based on your settings from earlier, right click on both and click Status -> Details:  <br/>
<img src="https://i.imgur.com/RK2H8c8.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Label both networks based on which is your "Internet", which should show your IP in Details and which one is your "Internal" network, which should show an APIPA address as shown below:  <br/>
<img src="https://i.imgur.com/oROX33m.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<img src="https://i.imgur.com/MyckUls.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Once labeled, right click on "Internal" network and choose properties. Double click IPv4 and set as shown below:  <br/>
<img src="https://i.imgur.com/ul3dm9J.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Next, Right click Windows -> System -> Rename PC in order to change the name to DC (or any identifier you would prefer). This will cause a restart:  <br/>
<img src="https://i.imgur.com/7ImkaxR.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Signing back in after restart, go to Server Manager and choose "Add roles and features":  <br/>
<img src="https://i.imgur.com/O8lkOK9.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Go through settings, choosing to add Active Directory Domain Services, choosing Add Features when prompted before installation:  <br/>
<img src="https://i.imgur.com/i2iQazy.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Once finished, go to Server Manager and click on yellow warning flag, clicking on "Promote this server to a domain controller":  <br/>
<img src="https://i.imgur.com/Lx4k2Rc.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Under Deployment Configuration, choose "Add a new forest" and naming your domain anything ending with ".com":  <br/>
<img src="https://i.imgur.com/EunMGNj.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Set your password, then continue hitting next until install, which will restart your server after finishing:  <br/>
<img src="https://i.imgur.com/qs9xTlf.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Once restarted, go to Start -> Adminstrative Tools -> Active Directory Users and Computers:  <br/>
<img src="https://i.imgur.com/oW9orx8.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
From here, create a new Organizational Unit titled "_USERS" and create an User inside of that unit:  <br/>
<img src="https://i.imgur.com/Sm31Gx9.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<img src="https://i.imgur.com/mBtZP2T.jpeg" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Next, add this user to the Domain Admins group by right clicking user -> Properties -> Member Of and adding "Domain Admins":  <br/>
<img src="https://i.imgur.com/ncbL7Mi.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You may now sign out and log in with the credentials of the new user you just created:  <br/>
<img src="https://i.imgur.com/6r2FyJy.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After signing back in, go to Server Manager and click on "Add Roles and Features" once again to set up RAS/NAT:  <br/>
<img src="https://i.imgur.com/OxzABFc.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Choose Remote Access and continue through prompts, making sure to choose Routing when asked. Click Install at the end:  <br/>
<img src="https://i.imgur.com/1rVIrmB.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/EiRoGe7.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />
Once installed, go to Tools in Server Manager, and choose Routing and Remote Access:  <br/>
<img src="https://i.imgur.com/AAthu3Y.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right click on DC(local) and choose Configure and Enable Routing and Remote Access, choosing the following options through the setup:  <br/>
<img src="https://i.imgur.com/KHTFVMd.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/hxqTuWy.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5JBwvXK.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once finished, return to "Add Roles and Features", this time choosing DHCP server to install:  <br/>
<img src="https://i.imgur.com/Dp71VnQ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once installed, go to Tools in Server Manager again and choose DHCP:  <br/>
<img src="https://i.imgur.com/BBr6hA2.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, open up dc.name.com and open up IPv4, right clicking it and choosing "New Scope...":  <br/>
<img src="https://i.imgur.com/PF0UG2I.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From here, fill in prompts as follows:  <br/>
<img src="https://i.imgur.com/Vof0OI8.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RMfnJPC.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RAHwYCp.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Authorize and refresh domain:  <br/>
<img src="https://i.imgur.com/DEYFuG0.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wmMDcai.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once finished, we will now use a PowerShell script to populate users in our domain. Download the script from the following url: <url>https://github.com/joshmadakor1/AD_PS/archive/master.zip<url/><br/>
<img src="https://i.imgur.com/QrrIci9.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After installing, extract folder and add your name to .txt file in order to create a regular user with your name:<br/>
<img src="https://i.imgur.com/NgeLKUF.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open up PowerShell ISE through Windows Start, and open the CREATE_USERS file you just downloaded. Put in the following commands to allow for your file to run(you would only do this in virtualization to avoid restrictions and make sure to set your directory to wherever you placed your folder):<br/>
<img src="https://i.imgur.com/jRxxhdr.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dCJNxIy.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/XbrJtm9.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run the script, you will see the users being created. You can confirm afterwards by checking your created "_USERS" folder to see if your users were created:<br/>
<img src="https://i.imgur.com/6JQpC9n.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, leave your DC VirtualBox, and create another Virtual Machine for your Windows 10 client system with the following settings:<br/>
<img src="https://i.imgur.com/2CSgjgY.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
When prompted after starting virtual machine, choose iso for Windows 10 downloaded earlier to boot into it. Go through Windows 10 installation, making sure to choose Pro version at least to allow for Domain access:<br/>
<img src="https://i.imgur.com/57N4FpD.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lQWa3uX.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once system starts, log in with guest account created during installation. From there go to right click Start -> System -> Rename this PC(advanced), and fill out information as follows with your domain name:<br/>
<img src="https://i.imgur.com/RsISnhR.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/YrNEYmw.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FOqfu0a.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From there, you'll be asked to log in using an account on the domain and then the system will restart after joining domain:<br/>
<img src="https://i.imgur.com/TVK7WF1.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
From there, you can log in using domain from any account that you created. Your domain has been setup for any further labs you would like to continue!<br/>
<img src="https://i.imgur.com/MQb9wFV.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

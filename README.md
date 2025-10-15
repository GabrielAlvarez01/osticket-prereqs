<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Welcome to this tutorial about how to install osTicket, a useful tool that simulates a ticketing system in a help desk environment
I will leave a video demonstration where I show you how to install osTicket step by step, along with written instructions for more reference. 

<h2>I hope you can find this useful or interesting! 🧙🏻‍♂️<h2>

<h1>Video Demonstration</h1>

- ### [How to Install osTicket video](https://youtu.be/YHyzKRBQ1_I)

<h2>Environments and Technologies Used</h2>
Here you can find the prerequisites needed to install osTicket 

- Microsoft Azure (for access, you will need a Microsoft account)
- Internet Information Services (IIS)
- Download the following file for the tutorial: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

<h2>Operating Systems Used </h2>

- Windows 10 Pro, version 22H2 - x64 Gen2 with a size of Standard_D2ads_v6 - 2 vcpus, 8 GiB memory

    
<br>
<h1>Installation Steps</h1>
<br>

<br>
<h2>Step 1</h2>
<br>

<p>
<img width="1354" height="906" alt="Step 1" src="https://github.com/user-attachments/assets/9178edfa-9748-4689-a26a-057e71147b20" />
</p>

<p>
For the first step, we are going to log in to Microsoft Azure. In case this is the first time for you using Azure, you will need to create or use a Microsoft account. It is also important to mention that creating a virtual machine will require a credit card, but don´t worry, the charges for use are not expensive, and even if you are unable to pay, you have a bonus budget of $200 for 30 days if this is your first time. 
<br>

Search and click on the virtual machine on your Azure dashboard, and select "Create a virtual machine" on the first tab, provide a name to your VM (virtual machine) that will also create a research group (where you can manage your cloud resources like virtual machines), I recommend to use the version of  "Windows 10 Pro, version 22H2 - x64 Gen2 with a size of Standard_D2ads_v6 - 2 vcpus, 8 GiB memory" witch was the one I used, set a username and a password, accept the terms of use and skip the rest of tabs until you get to review+create.

Now that your VM is created, it's time to access it using remote desktop access. You can find this option in your Windows search bar; it will request an IP. You can find this IP if you go back to the virtual machines and scroll sideways to the public IP address on your virtual machine. After introducing your IP address, log in using the username and password you used to create a VM and uncheck all the switches.
</p>
<br />

<br>
<h2>step 2</h2>
<br>

<p>
<img width="1866" height="761" alt="Captura de pantalla 2025-10-14 220347" src="https://github.com/user-attachments/assets/6559f480-b872-4259-9ac1-d7a2161fd8b4" />
</p>

<p>
For step 2 of this process, download the file I left above on your VM. Once installed, extract the file on your desktop, and now let´s go to our control panel and follow this route: Uninstall a program > turn Windows features on/off> Internet Information Services > World Wide Web Services > Application development features and check CGI.

Let´s go to your VM C-drive and create a folder called "PHP", extract the file "php-7.3.8-nts-Win32-VC15-x86" from the installation file into PHP, and install php manager, rewrite_amd64, and VC redist.

We will install MySQL with the following configuration: typical setup> check the box "launch the MySQL", standard configuration, and use "root" for both username and password.
</p>

<br>
<h2>Step 3</h2>
<br>

<p>
<img width="1871" height="910" alt="Captura de pantalla 2025-10-14 222024" src="https://github.com/user-attachments/assets/49796b9f-3a96-4efe-9363-4e738b8dd243" />
</p>

<p>
For this step, open IIS (Internet Information Services) Manager as an administrator in your Windows search bar, select PHP manager, and click "register new PHP version." Browse the following route 
C:\PHP\php-cgi.exe

Go back to the PHP manager and restart your PHP (osticket\labuser in this case) by right-clicking > restart
</p>

<br />

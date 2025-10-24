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

<br>
<br />

<p>
<img width="1858" height="897" alt="Captura de pantalla 2025-10-14 222918" src="https://github.com/user-attachments/assets/d479656c-dc7b-45a9-a432-bad365b2c161" />
</p>

 <p>
     Now go back to the installation file, extract osticket (on the same installation file), and once open, copy the file "upload" into the next route: C:\inetpub\wwwroot, then change the name of "upload" to "osTicket"
 </p>

<br>
<br />

<p>
    <img width="1861" height="918" alt="Captura de pantalla 2025-10-14 223158" src="https://github.com/user-attachments/assets/ff15112a-9444-46ba-88e3-4ab2d0dcdc2e" />
</p>

<p>
In IIS, restart your PHP again and follow this route on the left side of your PHP (like in the picture above): select Sites > Default > osTicket > select browse 80 on the right side of the PHP manager dashboard. Now you should be able to see the osTicket website, but there are some requirements to complete. Let´s activate the server with SQL.
</p>

<br>
<h2>Step 4</h2>
<br>

<p>
<img width="1881" height="915" alt="Captura de pantalla 2025-10-20 220801" src="https://github.com/user-attachments/assets/0b2490b7-a271-48e0-9977-138ab9fc88d3" />
</p>

<p>
Back in IIS, by clicking on the osTicket folder, click PHP Manager, and within the list of files, find and enable: php_imap.dll, php_intl.dll, and php_opcache.dll (in the picture above, it´s how these files look enabled) 
</p>

<br>
<br />

<p>
<img width="1876" height="914" alt="Captura de pantalla 2025-10-20 220903" src="https://github.com/user-attachments/assets/568376e1-564b-4418-8d1b-2ea05c874bbf" />
    <br>
   <img width="1870" height="929" alt="Captura de pantalla 2025-10-20 221102" src="https://github.com/user-attachments/assets/269ee0ea-1da9-45ba-99a5-1ffda5422139" />
 </p>

<p>
In the C drive, go to wwwroot > osTicket > include, and change the name of the file "ost-sampleconfig.php" into "ost-config.php." Then, right-click on ost-config.php and assign permissions by selecting properties. A pop-up window will open. In there, select the security tab, then click on advanced, and select the option "disable inheritance".
<br>
<br />
On the same advanced pop-up window on the upper right corner, click on select new permissions and type everyone and apply, then click on Add to mark the checkbox "full control"
</p>

<br>
<br />

<p>
  <img width="1860" height="907" alt="Captura de pantalla 2025-10-20 222049" src="https://github.com/user-attachments/assets/2116fc72-0552-4f6d-85a0-5fac76bbe1bb" />
</p>

<p>
Let's enable the database now, and go back to the installation file to install HeidiSQL, click next in all the steps until you see the pop-up window from the picture above. Now, click "Add" located in the lower right corner and log in using the same user and Password "root"
</p>

<br>
<br />

<p>
   <img width="1860" height="913" alt="Captura de pantalla 2025-10-20 222354" src="https://github.com/user-attachments/assets/d749e109-ade8-4a6e-bb8c-2112ad3b4799" />
</p>

 <p>
     When you have logged in, right-click in "unnamed", select create new > database, name it "osTicket"
 </p>

 <br>
 <br />

 <p>
    <img width="1859" height="911" alt="Captura de pantalla 2025-10-20 223109" src="https://github.com/user-attachments/assets/e948f695-b0ac-4718-96e4-1267194a3f8f" />
 </p>

 <p>
      Regarding the osTicket website from PHP, you should be able to click on continue (end of step 3), and you will see the form to establish an account as a customer and an agent; it´s not required to use a real email or personal data. Under database settings, use the information from the picture above, and confirm 
 </p>

 <br>
 <br />

 <p>
   <img width="1159" height="808" alt="Captura de pantalla 2025-10-20 223217" src="https://github.com/user-attachments/assets/1afad44a-d986-4b51-93dd-58285da1522c" />
  </p>

  <p>
     This is how it looks once it has been successfully installed
  </p>

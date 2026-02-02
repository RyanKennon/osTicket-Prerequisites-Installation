<p align="center">
  <img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/daa445be-b28b-4116-8795-886f90dbb7ea" />
</p>

# osTicket: Prerequisites & Installation

This project focuses on installing, configuring, and deploying the osTicket support ticketing system in a Windows Server environment. I enabled Internet Information Services (IIS), downloaded and installed the necessary PHP dependencies, and configured IIS to work with PHP. I then installed osTicket, applied required extensions, configured folder permissions, and created the backend MySQL database using HeidiSQL. Finally, I completed the browser-based setup and verified that the osTicket application was successfully installed and fully operational.

---

## Environments and Technologies Used

- Microsoft Azure
- Azure Virtual Network
- Internet Information Services (IIS)
- HeidiSQL (MySQL Database Management Tool)
- Remote Desktop Protocol (RDP)

---

## Lab Objectives

- Enable and configure Internet Information Services (IIS) to support hosting the osTicket application  
- Download and install all required PHP dependencies and supporting components needed for osTicket  
- Configure IIS to properly recognize and use the correct PHP version  
- Install the osTicket web application and prepare the environment for setup  
- Download and apply necessary PHP extensions to ensure full application functionality  
- Assign appropriate NTFS folder permissions to allow osTicket to write configuration files  
- Install HeidiSQL and create the MySQL database used by osTicket  
- Complete the browser-based osTicket setup and apply required configuration settings  
- Confirm successful installation and verify that the osTicket system is fully operational  

---

## Step-by-Step Walkthrough

### Lab Environment

- **Platform:** Microsoft Azure
- **Virtual Machine:** Windows 10 Pro

<p align="center">
  <img width="1818" height="592" alt="Untitled Diagram-Page-1 drawio" src="https://github.com/user-attachments/assets/5707ad74-caf1-4f74-8372-162c5ec228a1" />
</p>

---

### 1) Enable Internet Information Services

1. In the Virtual Machine open the computers **Control Panel** and select **Programs**
2. Select **Turn windows features on or off**

<p align="center">
  <img width="918" height="613" alt="Untitled Diagram-Page-3 drawio" src="https://github.com/user-attachments/assets/99cce2ac-a046-4332-8bee-a44176d268a0" />
</p>

3. Check the box labeled **Intenet Information Services**
4. Navigate through **IIS** to **CGI** and check the box

<p align="center">
  <img width="413" height="422" alt="Untitled Diagram-Page-5 drawio" src="https://github.com/user-attachments/assets/faf586fa-dd0f-433b-a496-b78816f8c969" />
</p>

5. Complete Installation

---

### 2) Download osTicket Dependencies

1. Download and extract [osTicket Dependencies file](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) on the Virtual Machine
2. Install the **PHP Manager** and the **Rewrite Module** from the **osTicket Dependencies file**
3. On the **`C: \`** create a folder named **PHP**
4. In the **osTicket Dependencies** folder extract the file named **php** to the **PHP folder on the `C: \`**
5. Install **VC_redist** and **mysql** when asked choose **Typical Setup**
6. Launch the **MySQL configuration wizard** and choose **Standard Configuration** when asked

<p align="center">
  <img width="1118" height="731" alt="Untitled Diagram-Page-11 drawio" src="https://github.com/user-attachments/assets/15b87225-880d-4899-b937-522398e2a748" />
</p>

7. Create a **root password** and complete the wizard

---

### 3) Configure Internet Information Services and Register PHP

1. Open IIS as an admin

<p align="center">
  <img width="1079" height="697" alt="Untitled Diagram-Page-12 drawio" src="https://github.com/user-attachments/assets/57eb729d-ed40-44eb-ba18-4e54da082994" />
</p>

2. Open **PHP Manager**

<p align="center">
  <img width="1054" height="748" alt="Untitled Diagram-Page-13 drawio" src="https://github.com/user-attachments/assets/1df8470c-65f0-4b8f-b17d-6536a5a33bd6" />
</p>

3. Select **Register new PHP version**
4. Select **PHP executable** on the **`C: \`**

<p align="center">
  <img width="1245" height="915" alt="Untitled Diagram-Page-15 drawio" src="https://github.com/user-attachments/assets/2f782d80-1e2f-4f24-b7d1-824a77688c0b" />
</p>

5. **Stop** and **start** the server

<p align="center">
  <img width="1056" height="607" alt="Untitled Diagram-Page-16 drawio" src="https://github.com/user-attachments/assets/472b00a6-1ae4-4d46-8095-81fc6aff2840" />
</p>

---

### 4) Install osTicket

1. In the **osTicket Installation Files** folder extract the contents of the **osTicket** folder
2. Copy the upload folder to **`c:\inetpub\wwwroot`** and rename the folder **osTicket**

<p align="center">
  <img width="877" height="460" alt="Untitled Diagram-Page-18 drawio" src="https://github.com/user-attachments/assets/79685f5a-edf1-4a17-bd47-af44721e4281" />
</p>

3. Stop and start the server in ISS

---

### 5) Download Extensions

1. Navigate to the **osTicket** folder in IIS
2. Select **Browse 80**

<p align="center">
  <img width="1050" height="591" alt="Untitled Diagram-Page-20 drawio" src="https://github.com/user-attachments/assets/8d4fdda9-6121-4f40-a693-2e1472c125d1" />
</p>

3. Observe the site

<p align="center">
  <img width="889" height="837" alt="Untitled Diagram-Page-21 drawio" src="https://github.com/user-attachments/assets/60ce1752-3a8c-4d48-94a7-86b1d8e97b96" />
</p>

4. In IIS navigate to the **osTicket** folder select **PHP Manager**
5. Click **enable or disable extemtions**
6. Find these three extensions:
   - **php_imap**
   - **php_intl**
   - **php_opcache**
7. Right click and **enable them**

<p align="center">
  <img width="643" height="612" alt="Untitled Diagram-Page-24 drawio" src="https://github.com/user-attachments/assets/ad5f07bc-cc8c-43f2-8468-4391cd9c69e2" />
</p>

8. Refresh the **web browser** and observe the changes

<p align="center">
  <img width="845" height="821" alt="Untitled Diagram-Page-25 drawio" src="https://github.com/user-attachments/assets/be47a133-690d-490e-b433-da7be6659e9c" />
</p>

---

### 6) Grant osTicket Permissions

1. Navigate to **`C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`**
2. Rename the file to **`C:\inetpub\wwwroot\osTicket\include\ost-config.php`**
3. For the **`ost-config.php`** file right click and open **Properties**
4. Select **Security** then click **Advanced**
5. Disable inheritance then click add

<p align="center">
  <img width="1111" height="662" alt="Untitled Diagram-Page-28 drawio" src="https://github.com/user-attachments/assets/184deca2-fbb4-459c-a243-b35db85fddd9" />
</p>

6. Select a **Principle**
7. Enter **Everyone** and select **Check Names**
8. Check the box labeled **Full Control** and apply the changes

<p align="center">
  <img width="911" height="588" alt="Untitled Diagram-Page-29 drawio" src="https://github.com/user-attachments/assets/0dafc4f6-e7f3-4e9b-98cc-2d08560eb565" />
</p>

---

### 7) Install HeidiSQL

1. In the **osTicket Installation Files** folder install and launch **HeidiSQL** then select **New**

<p align="center">
  <img width="1124" height="631" alt="Untitled Diagram-Page-30 drawio" src="https://github.com/user-attachments/assets/4793b8d2-e36f-4c56-b5f1-b8f1f874a1a2" />
</p>

2. Select **New** then enter the information for the **root user** then click **open**

<p align="center">
  <img width="683" height="480" alt="Untitled Diagram-Page-31 drawio" src="https://github.com/user-attachments/assets/43fb1739-d3ca-4fe5-8017-595716d965f0" />
</p>

3. Right click **unnamed** and create a new database name **osTicket**

<p align="center">
  <img width="930" height="587" alt="Untitled Diagram-Page-32 drawio" src="https://github.com/user-attachments/assets/5a1d79c8-a893-41c0-8423-ec2026b852e9" />
</p>

---

### 8) Setup osTicket in Browser

1. Go back to **osTicket** in the browser and select **continue**
2. Fill out the helpdesk information
   - **MySQL Database:** osTicket
   - **MySQL Username and Password** enter the root user information
3. Complete the Installation

<p align="center">
  <img width="562" height="371" alt="Untitled Diagram-Page-33 drawio" src="https://github.com/user-attachments/assets/51068b9a-1417-4f8c-8211-e70db2d5bcf9" />
</p>

---

### 9) Verify Installation Success

1. Go to the osTicket helpdesk login page: [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)
2. Login to the helpdesk

<p align="center">
  <img width="975" height="389" alt="Untitled Diagram-Page-34 drawio" src="https://github.com/user-attachments/assets/bf4994b5-055b-4b06-a183-6f3278247131" />
</p>

---

## Outcome

- Successfully enabled Internet Information Services (IIS) to host the osTicket web application  
- Downloaded all required dependencies necessary for osTicket, including PHP components and supporting tools  
- Configured IIS and registered the correct PHP version to ensure proper web server functionality  
- Installed the osTicket application and prepared the environment for web-based configuration  
- Downloaded and applied the necessary PHP extensions required for osTicket to operate correctly  
- Granted appropriate folder permissions to allow osTicket to write configuration files and run without errors  
- Installed HeidiSQL and created the MySQL database used for the ticketing system  
- Completed the initial osTicket setup through the browser and applied all required configuration settings  
- Verified that osTicket installed successfully and confirmed that the web application was fully operational  

---

## Skills Demonstrated

- Enabling and configuring Internet Information Services (IIS) for hosting web applications  
- Installing and managing required dependencies for PHP-based applications  
- Registering and configuring PHP within IIS to ensure proper web server integration  
- Installing and configuring the osTicket web application  
- Applying and managing PHP extensions required for osTicket functionality  
- Setting appropriate NTFS folder permissions to support application installation and runtime operations  
- Installing and using HeidiSQL to create and manage a MySQL database  
- Completing web-based application setup and initial configuration through a browser  
- Verifying installation success and confirming operational functionality of a web-hosted service  

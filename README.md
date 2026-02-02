<p align="center">
  <img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/daa445be-b28b-4116-8795-886f90dbb7ea" />
</p>

# osTicket: Prerequisites and Installation

## PLACE OVERVIEW HERE

---

## Environments and Technologies Used

- Microsoft Azure
- Azure Virtual Network
- Internet Information Services (IIS)
- HeidiSQL (MySQL Database Management Tool)
- Remote Desktop Protocol (RDP)

---

## Lab Objective



---

## Step-by-Step Walkthrough

### Lab Environment

- **Platform:** Microsoft Azure
- **Virtual Machine:** Windows 10 Pro

## CAPTURE 1

---

### 1) Enable Internet Information Services

1. In the Virtual Machine open the computers **Control Panel** and select **Programs**

## Capture 2

2. Select **Turn windows features on or off**

## Capture 3

3. Check the box labeled **Intenet Information Services**

## Capture 4

4. Navigate through **IIS** to **CGI** and check the box

## Capture 5

5. Complete Installation

---

### 2) Download Required osTicket Dependencies

1. Download and extract [osTicket Dependencies file](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) on the Virtual Machine

## Capture 6

2. Install the **PHP Manager** and the **Rewrite Module** from the **osTicket Dependencies file**

## Capture 7

3. On the **`C: \`** create a folder named **PHP**

## Capture 8

4. In the **osTicket Dependencies** folder extract the file named **php** to the **PHP folder on the `C: \`**

## Capture 9

5. Install **VC_redist** and **mysql** when asked choose **Typical Setup**

## Capture 10

6. Launch the **MySQL configuration wizard** and choose **Standard Configuration** when asked

## Capture 11

7. Create a **root password** and complete the wizard

---

### 3) Configure Internet Information Services and Register PHP

1. Open IIS as an admin

## Capture 12

2. Open **PHP Manager**

## Capture 13

3. Select **Register new PHP version**

## Capture 14

4. Select **PHP executable** on the **`C: \`**

## Capture 15

5. **Stop** and **start** the server

## Capture 16

---

### 4) Install osTicket

1. In the **osTicket Installation Files** folder extract the contents of the **osTicket** folder

## Capture 17

2. Copy the upload folder to **`c:\inetpub\wwwroot`** and rename the folder **osTicket**

## Capture 18

3. Stop and start the server in ISS

## Capture 19

---

### 5) Download Extensions

1. Navigate to the **osTicket** folder in IIS
2. Select **Browse 80**

## Capture 20

3. Observe the site

## Capture 21

4. In IIS navigate to the **osTicket** folder select **PHP Manager**

## Capture 22

5. Click **enable or disable extemtions**

## Capture 23

6. Find these three extensions:
   - **php_imap**
   - **php_intl**
   - **php_opcache**
7. Right click and **enable them**

## Capture 24

8. Refresh the **web browser** and observe the changes

## Capture 25

---

### 6) Grant osTicket Permissions

1. Navigate to **`C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`**
2. Rename the file to **`C:\inetpub\wwwroot\osTicket\include\ost-config.php`**

## Capture 26

3. For the **`ost-config.php`** file right click and open **Properties**
4. Select **Security** then click **Advanced**

## Capture 27

5. Disable inheritance then click add

## Capture 28

6. Select a **Principle**
7. Enter **Everyone** and select **Check Names**
8. Check the box labeled **Full Control** and apply the changes

## Capture 29

---

### 7) Install HeidiSQL

1. In the **osTicket Installation Files** folder install and launch **HeidiSQL** then select **New**

## Capture 30

2. Select **New** then enter the information for the **root user** then click **open**

## Capture 31

3. Right click **unnamed** and create a new database name **osTicket**

## Capture 32

---

### 8) Setup osTicket in Browser

1. Go back to **osTicket** in the browser and select **continue**
2. Fill out the helpdesk information
   - **MySQL Database:** osTicket
   - **MySQL Username and Password** enter the root user information
3. Complete the Installation

## Capture 33

---

### 9) Confirm Installation Success

1. Go to the osTicket helpdesk login page: [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)
2. Login to the helpdesk

## Capture 34

---

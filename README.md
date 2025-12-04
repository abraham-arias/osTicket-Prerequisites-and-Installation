<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket — Prerequisites and Installation  
This project documents the full installation and configuration workflow for deploying the open-source **osTicket Help Desk Ticketing System** on a Windows Virtual Machine hosted in Microsoft Azure.  
It is designed as a realistic IT Support / Help Desk / SysAdmin lab environment.

---

## 🧰 **Environments & Technologies Used**
- Microsoft Azure (Virtual Machines)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- MySQL / HeidiSQL
- PHP (Web Platform Installer)

---

## 💻 **Operating System Used**
- **Windows 10 (21H2)**

---

## 📦 **Requirements**
- Azure subscription with ability to deploy VMs  
- Windows 10 or Windows Server Virtual Machine  
- HeidiSQL  
- osTicket installation files (provided in lab resources)  

---

# 🧪 **Tutorial Instructions**

Below is the complete installation process for osTicket, including enabling IIS, installing dependencies, configuring PHP extensions, and setting up the osTicket database.

---

## 🔹 **Step 1 — Install / Enable IIS in Windows**

Open:

**Control Panel → Programs → Programs and Features → Turn Windows features on or off**  
Enable **Internet Information Services (IIS)**.

<br/>

<img src="https://i.imgur.com/hDMysuo.png" height="80%" width="80%" alt="Enable IIS"/>

---

## 🔹 **Step 2 — Install Web Platform Installer**

Use the following link to download the required installation tools:  
➡️ https://bit.ly/3WFRPdg  

Install **Web Platform Installer**, then search for and install:

- **MySQL 5.5**
- **PHP versions up to 7.3.25**

Some downloads may fail — alternative links are provided in the lab files.

<br/>

<img src="https://i.imgur.com/kOh6Ezy.png" height="80%" width="80%" alt="Web Platform Installer"/>

<br/>

<img src="https://i.imgur.com/RtPT3ki.png" height="80%" width="80%" alt="Download Failures"/>

---

## 🔹 **Step 3 — Install osTicket v1.15.8**

Download osTicket from the lab files.  
Extract the folder:

**Downloads → osTicket → Extract All**

Navigate to:

**This PC → Windows (C:) → inetpub → wwwroot**

Paste the **upload** folder inside *wwwroot* and rename it to:

➡️ **osTicket**

<br/>

<img src="https://i.imgur.com/KMC03rb.png" height="80%" width="80%" alt="Extract All"/>

---

## 🔹 **Step 4 — Reload IIS**

Open IIS Manager from the Start Menu.

- On the right, select **Restart**
- On the left, navigate:  
  **Sites → Default Web Site → osTicket**
- Click **Browse *:80** to open osTicket in your browser

<br/>

<img src="https://i.imgur.com/yDjIe1l.png" height="80%" width="80%" alt="Restart IIS"/>

---

## 🔹 **Step 5 — Enable Required PHP Extensions**

In IIS Manager:

**Sites → Default Web Site → osTicket → PHP Manager → Enable or Disable an Extension**

Enable:

- `php_imap.dll`
- `php_intl.dll`
- `php_opcache.dll`

Refresh the osTicket page in your browser afterward.

<br/>

<img src="https://i.imgur.com/YeSYmiK.png" height="80%" width="80%" alt="enable php"/>

---

## 🔹 **Step 6 — Rename `ost-config.php`**

Navigate to:

**osTicket → include → ost-sampleconfig.php**

Rename it to:

➡️ **ost-config.php**

(Be careful — this step is critical.)

<br/>

<img src="https://i.imgur.com/ECwKXOp.png" height="80%" width="80%" alt="rename ost-config"/>

---

## 🔹 **Step 7 — Assign Permissions to `ost-config.php`**

Right-click **ost-config.php → Properties → Security → Advanced**

- Click **Disable Inheritance**
- Click **Add**
- Select principal: **Everyone**
- Assign **Full Control**

<br/>

<img src="https://i.imgur.com/6SmEdXP.png" height="80%" width="80%" alt="ost-config permissions 1"/>

---

## 🔹 **Step 8 — Continue osTicket Setup in Browser**

Return to osTicket in the browser and fill out:

- Help desk name  
- Admin login information  
- Database information (configured in next steps)

Keep credentials noted for later.

---

## 🔹 **Step 9 — Download & Install HeidiSQL**

Install HeidiSQL using the same lab download files.

<br/>

<img src="https://i.imgur.com/vHJIhVC.png" height="80%" width="80%" alt="HeidiSQL"/>

Create a new session using your MySQL root password.  
Then create a database named:

➡️ **osTicket**

<br/>

<img src="https://i.imgur.imgur.com/xwNtYY0.png" height="80%" width="80%" alt="new database"/>

Return to osTicket setup and enter:

- **Database Name:** osTicket  
- **MySQL Username:** root  
- **Password:** (created earlier)  

Click **Install Now**.

osTicket should now be successfully installed.

<br/>

<img src="https://i.imgur.com/bLQ99x4.png" height="80%" width="80%" alt="Congrats"/>

---

# 🎉 **Installation Complete!**

You now have a fully launched osTicket help desk system hosted on Azure.  
This lab demonstrates real-world experience in:

- IIS configuration  
- PHP/MySQL setup  
- Database creation  
- File permissions  
- Azure VM administration  
- Help desk system deployment  

---


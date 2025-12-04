<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket — Prerequisites & Installation  
This project demonstrates the end-to-end deployment of **osTicket**, a widely used open-source Help Desk Ticketing System, on a Windows Virtual Machine hosted in Microsoft Azure.  

This installation simulates the role of a **System Administrator or Help Desk Technician** preparing a production-ready ticketing environment — a core responsibility in real-world IT Support operations.

---

# 📘 Project Overview
The goal of this lab is to showcase hands-on experience with:

- Web server configuration (IIS)  
- PHP and MySQL setup  
- Azure VM administration  
- Application deployment  
- File permissions and security  
- Database integration  

These steps reflect real technical workflows performed by IT support engineers when deploying internal tools or troubleshooting service issues.

---

# 🧰 Technologies Used
- **Microsoft Azure** — Virtual Machines, Networking  
- **Windows 10 (21H2)**  
- **Internet Information Services (IIS)**  
- **PHP** via Web Platform Installer  
- **MySQL** / **HeidiSQL**  
- **Remote Desktop Protocol (RDP)**  

---

# 🛠️ Detailed Installation Steps

## 🔹 Step 1 — Enable Internet Information Services (IIS)
Enable IIS to host the osTicket web application.

**Control Panel → Programs → Turn Windows features on or off → Internet Information Services**

<br/>

<img src="https://i.imgur.com/hDMysuo.png" width="80%" alt="Enable IIS"/>

---

## 🔹 Step 2 — Install Web Platform Installer (WPI)
Download Web Platform Installer from the provided resources:  
👉 https://bit.ly/3WFRPdg

Use WPI to install:

- **MySQL 5.5**
- **PHP (up to v7.3.25)**
- Required PHP extensions

Some downloads may fail — alternate download links are provided in the lab package.

<br/>

<img src="https://i.imgur.com/kOh6Ezy.png" width="80%" alt="WPI"/>

<br/>

<img src="https://i.imgur.com/RtPT3ki.png" width="80%" alt="Failed downloads"/>

---

## 🔹 Step 3 — Install osTicket v1.15.8
Extract osTicket → copy the **upload** folder to:


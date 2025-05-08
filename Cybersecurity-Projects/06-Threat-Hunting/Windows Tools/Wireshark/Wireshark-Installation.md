# 🧪 How to Install Wireshark on Windows

This guide will walk you through the installation process of **Wireshark** on a Windows machine. Wireshark is an essential tool for capturing and analyzing network traffic, making it ideal for cybersecurity labs, network forensics, and threat hunting.

---

## 📦 What is Wireshark?

Wireshark is a free, open-source packet analyzer. It lets you capture and inspect network traffic in real time, which is invaluable for troubleshooting, security analysis, and more.

---

## ✅ Prerequisites

Before you begin, ensure you meet these requirements:

- **Windows 10 or later** installed
- **Administrator privileges** to install software
- A reliable **Internet connection** to download Wireshark

---

## 🧪 Installation Steps

### Step 1️⃣: Download Wireshark

1. Open the official Wireshark website:  
   👉 [Wireshark Download Page](https://www.wireshark.org/download.html)
   
2. On the download page, click to download the **Windows Installer (64-bit)** version. The file will automatically begin downloading.

> 💡 **Tip**: Make sure you only download from the official website to avoid security risks.

---

### Step 2️⃣: Run the Installer

1. Once the download is complete, locate the `.exe` file and double-click it to start the installation.
   
2. Follow the installer prompts:
   - Click **Next** through the initial screens.
   - **Accept the license agreement** to proceed.
   - Keep the default installation settings unless you need to customize them.
   
3. When you reach the screen with the **Npcap** option, ensure you **check** the box that says *Install Npcap*. This is crucial for Wireshark to capture packets.

   > ⚠️ **Important**: If you do not install Npcap, Wireshark will not be able to capture packets. Npcap is required for Wireshark to function properly.

---

### Step 3️⃣: Complete the Installation

1. Continue clicking **Next** until the installation finishes.
   
2. When prompted to install **Npcap**, allow it to complete the installation. Npcap is a packet capture driver that is necessary for Wireshark.
   
3. Once installation is complete, click **Finish** to exit the installer.

---

## 🧪 Verifying the Installation

### ✅ Launch Wireshark

1. Open **Wireshark** from the **Start menu** or search for it in the search bar.
   
2. You should see a list of **network interfaces** available on your machine. These could include:
   - `Ethernet`
   - `Wi-Fi`
   - `Loopback`

3. If you see these network interfaces, congratulations! Wireshark is installed correctly and ready to start capturing traffic.


---

## 📘 What’s Next?

With Wireshark installed, you can now:

- Start a **packet capture** to monitor real-time network traffic.
- Analyze **network protocols** and inspect packets.
- Begin **threat hunting** by inspecting suspicious network activity.

To start capturing data, simply open Wireshark, choose your **Wi-Fi** or **Ethernet** interface, and click **Start Capture**.

---

## 🔧 Troubleshooting

If you encounter any issues during installation, consider the following:

- **Npcap not installed**: If the Npcap installation step was missed or failed, you can manually download and install Npcap from [here](https://nmap.org/npcap/).
- **No interfaces available**: Ensure your network interfaces are enabled and functioning correctly. If necessary, restart your machine or reinstall Npcap.

---

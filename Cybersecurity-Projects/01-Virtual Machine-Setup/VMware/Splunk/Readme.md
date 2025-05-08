# 🔧 Splunk Installation and Setup Guide

## 📦 Project Overview
This project provides a comprehensive, step-by-step guide to installing and configuring Splunk within a virtualized environment, such as VMware. The guide also includes the optional setup of ingesting Windows Event Logs and Sysmon data into Splunk for enhanced cybersecurity monitoring and analysis.

---
## ⚡ Quick Note: Lab Machine Setup (3 Machines)

You’ll need **three machines** for this lab setup:

- **Kali Linux (Attacker Machine)**  
  Used to simulate attacks.

- **Windows (Target Machine)**  
  This is the machine being attacked.

- **Windows VM (Splunk Monitoring Machine)**  
  This VM runs **Splunk** to collect and monitor logs from both the **target Windows machine** and the **Kali attacker machine**.

> 💡 **Optional:** If you don’t want to use a third VM, you can install Splunk directly on your **main computer** instead. It’s totally up to you!
---

## 🧠 Installation of Splunk

### ⬇️ Download Splunk

1. **Navigate to the official Splunk Free download page**.  
   🔗 [Splunk Free Download](https://www.splunk.com/en_us/download.html)

2. **Create a Splunk Account**:

   * If you **don’t have an account**, you'll need to **register** to create a Splunk account. Follow the instructions to sign up and gain access to the Splunk interface.
   * If you **already have an account**, simply **log in** with your existing credentials.

3. **Select the appropriate version** based on your operating system:

   * 🪟 **Windows**: Download the `.msi` installer.
   * 🐧 **Linux**: Download the `.tgz` package.
   * 🍏 **macOS**: Select the appropriate version for macOS.

4. **Click the download link** and save the file to your local machine.

---

### 💻 Install Splunk

 **🪟 Windows**: 
  1. Run the downloaded `.msi` installer.
  2. Follow the default installation settings for a smooth and easy setup.
  3. Choose whether you want Splunk to start automatically as a service upon boot.

 **🐧 Linux**: 
  1. Download the `.tgz` package from the Splunk website.
  2. Extract the files to a directory of your choice.
  3. Follow the instructions in the README file for installation. Typically, you’ll run an installation script to configure the system.
  4. During installation, you’ll be prompted to set up the Splunk directory and select a port for accessing the Splunk web interface (default is `8000`).

### 🔐 Set Up Admin Credentials

1. After installation, access Splunk via your browser at `http://localhost:8000`.
2. You will be prompted to create an administrator username and password.
3. Make sure to choose a strong, secure password that you can remember. These credentials will be required to log in to Splunk's web interface.

### 🚀 Launch Splunk

1. Once the installation is complete, open your web browser and navigate to `http://localhost:8000`.
2. Log in using the administrator credentials you just created.
3. You should now see the Splunk dashboard, where you can begin setting up data inputs and performing log analysis.

---

## ⚙️ Optional: Set Up Data Ingestion
### Option 1: Ingest Windows Event Logs

#### 📥 Install the Splunk Universal Forwarder

To begin sending Windows event logs to your Splunk instance:

1. Download and install the Splunk Universal Forwarder on the target machine where the event logs are stored.
2. During installation, configure the Universal Forwarder to forward logs such as Application, System, and Security event logs to the Splunk server.

#### ⚙️ Configure Log Inputs in Splunk

1. In your Splunk instance, go to **Settings → Data Inputs → Add Data**.
2. Choose the **Monitor** option and select the path to the Windows event logs (e.g., `C:\Windows\System32\winevt\Logs\`).
3. Splunk will start monitoring these logs in real-time, allowing you to search and analyze them.

### Option 2: Ingest Sysmon Data

#### 🛠️ Install Sysmon

1. Sysmon is a powerful Windows monitoring tool that provides detailed event logs. 
2. Download it from [Microsoft Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon).
3. To install, run the Sysmon executable with the recommended configuration file. This will begin collecting detailed data about system activity such as process creation, network connections, and driver loading.

#### 🔄 Forward Sysmon Logs to Splunk

1. Use the Splunk Universal Forwarder to forward Sysmon logs from the monitored machine to your Splunk instance.
2. In Splunk, configure the log inputs to accept Sysmon logs from the Universal Forwarder, allowing you to analyze these advanced logs in the Splunk interface.

---

## 📝 **Wrapping Up: You're Ready for Action!**

By following this guide, you should have a fully functional Splunk instance running within a virtualized environment, ready to ingest and analyze logs from Windows Event Logs and Sysmon. This setup enhances your cybersecurity monitoring capabilities, providing insights into system activity and potential security threats.

---

## 🚀 **What’s Next?**

- **Experiment**: Explore the Splunk dashboard and start creating custom searches and dashboards.
- **Set Alerts**: Set up alerts for key cybersecurity events to stay ahead of the game.
- **Advanced Configurations**: Dive deeper into integrations with other tools and advanced features in Splunk.

---

**Thank You for Following Along!** 🌟  
We hope you’ve enjoyed setting up Splunk with us. Have any questions or suggestions? Don’t hesitate to reach out by opening an issue or contributing to the project. Happy Splunking! 🎉

---

## 🤝 **Contribute to the Project**

If you find this guide helpful or have improvements to share, feel free to fork the repo, make your changes, and submit a pull request. Let's make cybersecurity even stronger together!

---







# 🛠️ Installing Sysmon (System Monitor) – The Eyes of Windows 🕵️‍♂️

Sysmon is like a **security camera** for your computer. Once installed, it logs important activities like process launches, network connections, and more—making it super useful for threat hunting!

---

## 📦 1️⃣ Download Sysmon

| 🔧 What to Do    | ✅ Instructions                                                                                |
| ---------------- | --------------------------------------------------------------------------------------------- |
| 🔗 Download      | Go to [Sysmon Download Page](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) |
| 📁 File          | You'll get `Sysmon.zip`                                                                       |
| 📂 Extract       | Right-click → **Extract All...**                                                              |
| 📌 Target Folder | Extract to: `C:\Tools\Sysmon` (Create it if needed)                                           |

---

## ⚙️ 2️⃣ Install Sysmon using PowerShell

### 🧪 Open PowerShell (as Admin):

* Press `Win + X` → Click **Windows PowerShell (Admin)**
* Or search for **PowerShell**, right-click → **Run as Administrator**

### 🚀 Run these commands:

```powershell
cd C:\Tools\Sysmon
.\Sysmon64.exe -accepteula -i -h md5,sha256 -n -l
```
## 🔍 What each option means:

| **Option**              | **📝 What It Does**                                          |
|-------------------------|-------------------------------------------------------------|
| `-accepteula`            | Accepts license (no pop-up)                                 |
| `-i`                     | Installs Sysmon                                             |
| `-h md5,sha256`          | Logs file hashes using both MD5 & SHA256                     |
| `-n`                     | Monitors network connections                                |
| `-l`                     | Logs DLL (module) loading                                   |

✅ You now have basic logging enabled – good enough to catch things like DNS tunneling!

---

## 🧭 3️⃣ Check If Sysmon Is Working

### 📄 Open Event Viewer:
1. Press **Win + R**, type `eventvwr.msc`, hit **Enter**

### 🗂️ Navigate to Sysmon Logs:

```plaintext
Event Viewer  
└──→ Applications and Services Logs  
    └──→ Microsoft  
        └──→ Windows  
            └──→ Sysmon  
                └──→ Operational
```


✅ You should see logs like:

| **📌 Event ID** | **🔍 What It Means**            |
|-----------------|--------------------------------|
| 1               | Process creation (e.g., when a program runs) |
| 3               | Network connection attempt     |
| 7               | Module (DLL) loaded            |

---

## 🔧 4️⃣ Adding a Custom Sysmon Configuration File (Advanced Logging)

You can customize Sysmon’s logging by using a configuration file. This allows you to log additional events, like command line arguments, registry access, and more.

### 📂 Where to Find Config Files:
The official Sysmon configuration file from SwiftOnSecurity is a great starting point. You can use or modify it to suit your needs.

### ⚙️ How to Use a Custom Configuration File:

1. **Download the configuration file:**
   - Visit the SwiftOnSecurity Sysmon Config GitHub and download the latest `sysmonconfig.xml`.

2. **Place the configuration file:**
   - Save the `sysmonconfig.xml` file in your Sysmon folder (e.g., `C:\Tools\Sysmon`).

3. **Install Sysmon with the config file:**
   - Run the following command to install Sysmon with your custom config:

   ```powershell
   cd C:\Tools\Sysmon
   .\Sysmon64.exe -accepteula -c sysmonconfig.xml
   ```

### 🔍 What the Custom Config Can Log

| 🔧 **Feature**         | 📝 **Description**                                               |
|------------------------|------------------------------------------------------------------|
| **Command Line**        | Logs the command line used to launch processes                   |
| **Registry Activity**   | Logs registry key changes (valuable for detecting malware)       |
| **File Creation**       | Logs file creation and deletions                                 |
| **Network Connections** | Monitors outbound/inbound connections                            |

---

## ✅ You're All Set – What's Next?

With Sysmon successfully installed and logging enabled, you've laid the foundation for powerful endpoint visibility and threat detection on Windows.

🔍 **What You’ve Accomplished:**
- Installed Sysmon to monitor process creation, network connections, and DLL loading.
- Enabled basic logging suitable for detecting suspicious behavior like DNS tunneling.
- Learned how to verify Sysmon activity using Event Viewer.
- (Optional) Implemented a custom configuration for advanced monitoring.

🛠️ **Next Steps & Recommendations:**
- 💡 Review Sysmon logs regularly to build familiarity with normal vs. abnormal activity.
- 🔗 Integrate logs with SIEM tools like Splunk, Elastic Stack, or Microsoft Sentinel for deeper analysis and alerting.
- 🔄 Keep your Sysmon config updated – use trusted community resources like [SwiftOnSecurity's Sysmon config](https://github.com/SwiftOnSecurity/sysmon-config).
- 🧪 Try running attack simulations (e.g., using Metasploit, dnscat2) and observe Sysmon's logging in action.

🧠 **Learning Resources:**
- [Microsoft Sysmon Documentation](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
- [SwiftOnSecurity Sysmon Config](https://github.com/SwiftOnSecurity/sysmon-config)
- [Threat Hunting with Sysmon – Practical Labs](https://github.com/topics/sysmon)

---

🔐 **Stay curious. Stay secure. Keep hunting.** 🕵️‍♂️



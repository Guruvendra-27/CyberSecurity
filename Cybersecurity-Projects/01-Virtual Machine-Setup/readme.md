# 🖥️ How to Install VMware Workstation Pro on Windows

This repository provides a **detailed, beginner-friendly guide** to install **VMware Workstation Pro** on a Windows system, with all necessary steps and tips to ensure a smooth installation experience.

---

## 📌 Table of Contents

- [Prerequisites](#-prerequisites)
- [Download VMware Workstation Pro](#-step-1-download-vmware-workstation-pro)
- [Install VMware Workstation Pro](#-step-2-install-vmware-workstation-pro)
- [Post-Installation](#-step-3-launch--activate)
- [Troubleshooting Tips](#-troubleshooting-tips)
- [Screenshots (Optional)](#-screenshots-optional)
- [License](#-license)
- [Contributing](#-contributing)

---

## ✅ Prerequisites

Before installation, ensure your system meets the following:

- ✅ **Windows 10 or 11** (64-bit only)
- ✅ **Virtualization enabled** in BIOS (Intel VT-x or AMD-V)
- ✅ Minimum **4 GB RAM** (8 GB or more recommended)
- ✅ Minimum **1 GB free disk space** (more required for VMs)
- ✅ **Administrator privileges** on your system

---

## 🔽 Step 1: Download VMware Workstation Pro

1. Go to the official download page:  
   👉 [https://www.vmware.com/products/workstation-pro.html](https://www.vmware.com/products/workstation-pro.html)

2. Click **“Download Now”** under the **Workstation Pro for Windows** section.

3. Save the `.exe` installer file (e.g., `VMware-workstation-full-*.exe`) to your computer.

---

## ⚙️ Step 2: Install VMware Workstation Pro

> 💡 **Tip:** Close other applications before installation.

### 1️⃣ Launch the Installer
- Double-click the downloaded `.exe` file.
- If prompted by **User Account Control (UAC)**, click **Yes**.

### 2️⃣ Installation Wizard – Step-by-Step

| Step | Description |
|------|-------------|
| **Welcome** | Click **Next** |
| **License Agreement** | Select **"I accept the terms"**, then click **Next** |
| **Custom Setup** | Leave all settings at **default**, click **Next** |
| **User Experience Settings** | (Optional) Uncheck:<br>• Check for updates on startup<br>• Join VMware CEIP |
| **Shortcuts** | Choose whether to create **desktop/start menu shortcuts** |
| **Ready to Install** | Click **Install** |

### 3️⃣ Wait for Installation
- Takes a few minutes.
- You'll see a progress bar.

### 4️⃣ Complete Installation
- Once finished, click **Finish**.
- If prompted to **restart your system**, do so.

---

## 🏁 Step 3: Launch & Activate

1. Open **VMware Workstation Pro** from the **Start Menu** or **Desktop shortcut**.

2. Choose one of the following:
   - **Enter a license key** (if purchased)
   - **Start free 30-day trial**

3. On first run, allow any **Windows Firewall** prompts (important for networking support in VMs).

---

## 🛠️ Troubleshooting Tips

| Issue | Solution |
|-------|----------|
| VMware installer fails | Run as **Administrator** |
| VT-x / AMD-V error | Enable virtualization in BIOS |
| Network adapter not detected | Reboot PC and re-run VMware |
| Installation hangs | Disable antivirus temporarily and retry |

---

## 📸 Screenshots (Optional)

You can add screenshots in the `/screenshots` folder and embed them like this:

```markdown
![Welcome Screen](screenshots/welcome.png)

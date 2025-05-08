# 🛠️ 01 – Virtual Machine Setup

This folder contains step-by-step guides and configuration files to set up virtual machines for cybersecurity labs and testing environments.  
Two hypervisors are covered:

- **VMware** – Workstation Pro / Player  
- **Virtual-Box** – Oracle VM VirtualBox

---

## 🔍 What’s Inside

### VMware  
In the `VMware/` directory you’ll find:  
- **INSTALLATION_SETUP.md** – Detailed instructions to download, install, and configure VMware Workstation Pro (or Player) in a Windows environment.  
- **sample-vm-config.vmx** – Example VM configuration file that you can import or tweak for your lab scenarios.

### Virtual-Box  
In the `Virtual-Box/` directory you’ll find:  
- **INSTALLATION_SETUP.md** – Step-by‑step guide to install Oracle VM VirtualBox on Windows, macOS, or Linux, plus extension pack setup.  
- **sample-vm-config.vbox** – Sample VM definition file for quick import.

---

## 🚀 Getting Started

1. **Pick your hypervisor**:  
   - If you already have a VMware license or want the feature‑rich Workstation Pro, head to `VMware/INSTALLATION_SETUP.md`.  
   - Otherwise, Oracle VM VirtualBox is free and cross‑platform—see `Virtual-Box/INSTALLATION_SETUP.md`.

2. **Follow the INSTALLATION_SETUP.md** inside the chosen directory. It will walk you through downloading, installing, enabling virtualization, and configuring network adapters for lab use.

3. **Import the sample VM**:  
   - In VMware: File → Open → `sample-vm-config.vmx`  
   - In VirtualBox: File → Import Appliance → `sample-vm-config.vbox`

4. **Power on and verify** connectivity (e.g., ping your host or other VMs).

---

## ⚙️ Contributing

- Feel free to update the installation guides with screenshots, additional OS instructions, or troubleshooting tips.  
- If you add new VM configurations, include them alongside the existing `sample-vm-config.*` files and update this README.  
- Submit PRs against the `main` branch and describe your changes clearly.

---


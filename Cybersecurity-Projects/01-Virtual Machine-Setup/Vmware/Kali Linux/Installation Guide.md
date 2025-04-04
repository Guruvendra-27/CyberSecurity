

# Kali Linux on VMware Step-by-Step Installation Guide

This document provides detailed instructions for setting up Kali Linux on VMware Workstation Player. Follow these steps for a smooth installation.

---

## Table of Contents

- [Step 1: Create the Virtual Machine](#step-1-create-the-virtual-machine)
- [Step 2: Install Kali Linux](#step-2-install-kali-linux)
- [Step 3: Initial Setup](#step-3-initial-setup)
- [Step 4: Recommended Extras](#step-4-recommended-extras)

---

## Step 1: Create the Virtual Machine

1. **Launch VMware Workstation Player** and click **"Create New VM"**.
2. Select the Kali Linux ISO file when prompted.
3. **Configure the VM settings**:
   - **OS Type**: **Linux → Debian 11.x 64-bit**
   - **VM Name**: `Kali-Test`
   - **Disk**: Set to **50GB** (Select "Store as a single file").
   - **Memory**: Set to **8192MB** (8GB).
   - **Processors**: Set to **2 cores**.
4. **Customize Hardware** (optional):
   - Disable *3D acceleration* to improve performance.

---

## Step 2: Install Kali Linux

1. **Power on the VM** and select **"Graphical Install"**.
2. **Follow the installation steps**:
   - Set **Language**: **English**
   - Set **Timezone**: Your location.
   - Set **Hostname**: `kali`.
   - Choose a **Username** (e.g., `security`, `analyst`).
   - Set a strong **Password** (e.g., `Cyber$ec123!`).
3. **Partitioning**:
   - Select **Guided - Use entire disk**.
   - Choose **All files in one partition**.
4. **Software**
   - Un-Check other and Check only Following Two
   - GNOME (Recommended)
   - Default selection
4. **Install GRUB**: Install GRUB to **/dev/sda**.
5. After installation, reboot the VM.

---

## Step 3: Initial Setup

1. **Log into Kali Linux** using your credentials.
2. **Open Terminal** and run the following commands:
   ```bash
   sudo apt update && sudo apt full-upgrade -y
   sudo apt install -y open-vm-tools-desktop
   sudo reboot
3. **After reboot**, take a snapshot in VMware → Snapshot → "Fresh Install".

## Step 4: Recommended Extras

- **Install additional Kali Linux tools**:
  ```bash
  sudo apt install -y kali-linux-large

- **Enable VMware features**:

   - Shared folders.

   - Drag-and-drop between host/VM.

# Resize and Extend Kali Linux Partition on VirtualBox `.vdi` Disk

A step-by-step guide to resize VirtualBox `.vdi` disks and extend partitions in Kali Linux. This guide is designed for beginners and advanced users to providing clear instructions and troubleshooting tips.

---

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Step 1: Resize the Virtual Disk in VirtualBox](#step-1-resize-the-virtual-disk-in-virtualbox)
3. [Step 2: Extend the Partition in Kali Linux](#step-2-extend-the-partition-in-kali-linux)
4. [Troubleshooting](#troubleshooting)
5. [Contributing](#contributing)
6. [Support](#support)

---

## Prerequisites
Before starting, ensure you have the following:
- **VirtualBox** installed on your host machine.
- A **Kali Linux virtual machine** with a `.vdi` disk.
- **Administrative privileges** on both the host machine and Kali Linux.
- A **backup** or snapshot of your VM (recommended).

---

## Step 1: Resize the Virtual Disk in VirtualBox

### 1.1 Shut Down Your Kali Linux VM
- Ensure your Kali Linux VM is completely powered off. Do not leave it in a saved or paused state.

### 1.2 Open Command Prompt as Administrator
- On Windows:
  - Press `Win + R`, type `cmd`, and press `Ctrl + Shift + Enter` to open Command Prompt with Administrator privileges.
- On Linux/macOS:
  - Open a terminal.

### 1.3 Navigate to the VirtualBox Installation Directory
- On Windows:
  ```bash
  cd "C:\Program Files\Oracle\VirtualBox"
  ```
- On Linux/macOS:
  ```bash
  cd /usr/bin
  ```

### 1.4 Resize the Virtual Disk
- Use the `VBoxManage` command to resize the `.vdi` disk. For example:
  ```bash
  VBoxManage modifymedium disk "C:\path\to\dragon_7.vdi" --resize 100000
  ```
  - Replace `C:\path\to\dragon_7.vdi` with the full path to your `.vdi` file.
  - Replace `100000` with the desired size in MB (e.g., `100000` = 100GB).

### 1.5 Verify the New Disk Size
- Open VirtualBox.
- Go to **File** > **Virtual Media Manager**.
- Check that the disk size has been updated.

---

## Step 2: Extend the Partition in Kali Linux

### 2.1 Boot Into Kali Linux
- Start your Kali Linux VM.

### 2.2 Open a Terminal
- Launch a terminal in Kali Linux.

### 2.3 Install GParted (if not installed)
- GParted is a graphical partition editor. Install it using:
  ```bash
  sudo apt update && sudo apt install -y gparted
  ```

### 2.4 Launch GParted
- Run GParted with root privileges:
  ```bash
  sudo gparted
  ```

### 2.5 Identify the Correct Disk
- In GParted:
  - Select the correct disk (e.g., `/dev/sda`).
  - Locate the partition you want to resize (e.g., `/dev/sda1`).
  - You should see **unallocated space** next to the partition.

### 2.6 Resize the Partition
- Right-click the partition (e.g., `/dev/sda1`) and select **Resize/Move**.
- Drag the slider to include the unallocated space or manually enter the new size.
- Click **Resize/Move** to apply the changes.

### 2.7 Apply Changes
- Click the green checkmark (**Apply All Operations**) in GParted to confirm and apply the changes.

### 2.8 Resize the Filesystem
- After resizing the partition, run:
  ```bash
  sudo resize2fs /dev/sda1
  ```
  - Replace `/dev/sda1` with the correct partition if necessary.

### 2.9 Verify the New Disk Size
- Run the following command to confirm the new disk size:
  ```bash
  df -h
  ```
  - You should see the increased size for your root partition.

---

## Troubleshooting
### Problem 1: GParted Doesn’t Show Unallocated Space
- **Solution**:
  - Refresh the partition table in GParted.
  - Reboot your Kali Linux VM and check again.

### Problem 2: Disk Space Doesn’t Reflect After Reboot
- **Solution**:
  - Ensure you resized the partition properly in GParted.
  - Run `resize2fs` on the correct partition.

### Problem 3: `VBoxManage` Gives an Error About File Paths
- **Solution**:
  - Double-check the file path for the `.vdi` disk.
  - Ensure the path is correctly typed in the command.

---

## Contributing
If you have any improvements or suggestions, feel free to fork this project and submit a pull request! Your contributions are welcome.

---

## Support
If you found this guide helpful, consider giving it a ⭐ on GitHub! For questions or issues, open an issue in the repository.

---

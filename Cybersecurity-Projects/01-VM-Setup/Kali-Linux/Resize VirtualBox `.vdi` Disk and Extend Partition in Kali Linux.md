# Resize VirtualBox `.vdi` Disk and Extend Partition in Kali Linux

## Project Overview

This project provides a detailed guide on how to resize a `.vdi` disk file in VirtualBox and extend the partition inside Kali Linux to utilize the new disk space.

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Step 1: Resize the Virtual Disk in VirtualBox](#step-1-resize-the-virtual-disk-in-virtualbox)
- [Step 2: Extend the Partition in Kali Linux](#step-2-extend-the-partition-in-kali-linux)
- [Step 3: Reboot and Confirm](#step-3-reboot-and-confirm)
- [Troubleshooting](#troubleshooting)

---

## Prerequisites

Before starting, ensure you have the following:

- VirtualBox installed on your machine.
- A Kali Linux virtual machine with a `.vdi` disk.
- A Command Prompt with Administrator privileges for resizing the `.vdi` disk.
- Kali Linux VM running with administrative privileges to modify partitions.

---

## Step 1: Resize the Virtual Disk in VirtualBox

1. **Shut Down Your Kali Linux VM**  
    Ensure your VM is completely powered off, not in a saved or paused state.
    
2. **Open Command Prompt as Administrator**  
    Press `Win + R`, type `cmd`, and press `Ctrl + Shift + Enter`.
    
3. **Navigate to the VirtualBox Installation Directory**
    
    ```bash
    cd "C:\Program Files\Oracle\VirtualBox"  
    ```
    
4. **Resize the Virtual Disk**  
    Use the following command to resize your `.vdi` disk (adjust the path and size as necessary):
    
    ```bash
    VBoxManage modifymedium disk "C:\Kali Linux\dragon\dragon\dragon_7.vdi" --resize 100000  
    ```
    
    Replace `100000` with the desired disk size in MB (e.g., `100000` for 100GB).  
    Verify that the `.vdi` file path matches exactly where the `.vdi` file is located.
    
5. **Verify the New Disk Size**  
    In VirtualBox, go to **File** > **Virtual Media Manager** and confirm the disk size has been updated.

---

## Step 2: Extend the Partition in Kali Linux

1. **Boot Into Kali Linux**  
    Start your Kali Linux virtual machine.
    
2. **Install GParted (if not installed)**
    
    ```bash
    sudo apt update && sudo apt install -y gparted  
    ```
    
3. **Launch GParted**
    
    ```bash
    sudo gparted  
    ```
    
4. **Identify the Correct Disk**  
    In GParted, select the disk (likely `/dev/sda`).
    
5. **Resize the Partition**  
    Locate the unallocated space next to your main partition (e.g., `/dev/sda1`).  
    Right-click on `/dev/sda1` and select **Resize/Move**.  
    Adjust the partition size to utilize the unallocated space, then click **Resize**.  
    Click the **green checkmark (✔)** to apply the changes.
    
6. **Resize the Filesystem**  
    After resizing the partition, run:
    
    ```bash
    sudo resize2fs /dev/sda1  
    ```
    
7. **Verify the New Disk Size**  
    Run the following command to confirm the new disk size:
    
    ```bash
    df -h  
    ```

---

## Step 3: Reboot and Confirm

1. **Reboot the Kali Linux VM**
    
    ```bash
    sudo reboot  
    ```
    
2. **Check the Disk Space Again**  
    After rebooting, run:
    
    ```bash
    df -h  
    ```
    
    Verify that the new space is now available.

---

## Troubleshooting

- **Problem:** GParted doesn't show the unallocated space after resizing the `.vdi`.  
    **Solution:** Try refreshing the partition table in GParted, or reboot your Kali Linux VM and retry.
    
- **Problem:** The disk space doesn't reflect after reboot.  
    **Solution:** Ensure you've resized the partition properly in GParted and run `resize2fs` on the correct partition.
    
- **Problem:** `VBoxManage` gives an error about file paths.  
    **Solution:** Double-check the file path for the `.vdi` disk and ensure it's correctly typed in the command.

---

## Contributing

If you have any improvements or suggestions, feel free to fork this project and submit a pull request!

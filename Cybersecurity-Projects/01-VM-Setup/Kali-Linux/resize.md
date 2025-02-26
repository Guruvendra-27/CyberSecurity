# **Resize VirtualBox `.vdi` Disk and Extend Partition in Kali Linux**

### **Project Overview**
This guide provides a step-by-step process to resize a VirtualBox `.vdi` disk and extend the partition in Kali Linux to utilize the additional disk space. It includes detailed explanations, troubleshooting tips, and screenshots (where applicable) to ensure clarity.

---

### **Table of Contents**
1. [Prerequisites](#prerequisites)
2. [Step 1: Resize the Virtual Disk in VirtualBox](#step-1-resize-the-virtual-disk-in-virtualbox)
3. [Step 2: Extend the Partition in Kali Linux](#step-2-extend-the-partition-in-kali-linux)
   - [Step 2.6: Resize the Partition in GParted](#step-26-resize-the-partition-in-gparted)
4. [Step 3: Reboot and Confirm](#step-3-reboot-and-confirm)
5. [Troubleshooting](#troubleshooting)
6. [Contributing](#contributing)

---

### **Prerequisites**
Before starting, ensure you have the following:
1. **VirtualBox Installed**: Ensure VirtualBox is installed on your host machine.
2. **Kali Linux VM**: A Kali Linux virtual machine with a `.vdi` disk.
3. **Administrator Access**: You need administrative privileges on both your host machine (to resize the disk) and inside Kali Linux (to modify partitions).
4. **Backup**: Always back up your VM or take a snapshot in VirtualBox before making changes.

---

### **Step 1: Resize the Virtual Disk in VirtualBox**

#### **1.1 Shut Down Your Kali Linux VM**
- Ensure your Kali Linux VM is completely powered off. Do not leave it in a saved or paused state.

#### **1.2 Open Command Prompt as Administrator**
- On Windows:
  - Press `Win + R`, type `cmd`, and press `Ctrl + Shift + Enter` to open Command Prompt with Administrator privileges.
- On Linux/macOS:
  - Open a terminal.

#### **1.3 Navigate to the VirtualBox Installation Directory**
- On Windows:
  ```bash
  cd "C:\Program Files\Oracle\VirtualBox"
  ```
- On Linux/macOS:
  ```bash
  cd /usr/bin
  ```

#### **1.4 Resize the Virtual Disk**
- Use the `VBoxManage` command to resize the `.vdi` disk. For example:
  ```bash
  VBoxManage modifymedium disk "C:\path\to\dragon_7.vdi" --resize 100000
  ```
  - Replace `C:\path\to\dragon_7.vdi` with the full path to your `.vdi` file.
  - Replace `100000` with the desired size in MB (e.g., `100000` = 100GB).

#### **1.5 Verify the New Disk Size**
- Open VirtualBox.
- Go to **File** > **Virtual Media Manager**.
- Check that the disk size has been updated.

---

### **Step 2: Extend the Partition in Kali Linux**

#### **2.1 Boot Into Kali Linux**
- Start your Kali Linux VM.

#### **2.2 Open a Terminal**
- Launch a terminal in Kali Linux.

#### **2.3 Install GParted (if not installed)**
- GParted is a graphical partition editor. Install it using:
  ```bash
  sudo apt update && sudo apt install -y gparted
  ```

#### **2.4 Launch GParted**
- Run GParted with root privileges:
  ```bash
  sudo gparted
  ```

#### **2.5 Identify the Correct Disk**
- In GParted:
  - At the top-right corner, select the correct disk (e.g., `/dev/sda`). This is usually the primary disk where your Kali Linux is installed.
  - Below the disk selection, you will see a graphical representation of the partitions on the disk.
  - Look for the partition you want to resize (e.g., `/dev/sda1`). This is typically the root partition where your operating system is installed.
  - You should see **unallocated space** next to the partition. This is the space you added when resizing the `.vdi` disk.

#### **2.6 Resize the Partition**
- **Right-Click the Partition**:
  - Right-click on the partition you want to resize (e.g., `/dev/sda1`).
  - From the context menu, select **Resize/Move**.

- **Resize the Partition**:
  - A new window titled **Resize/Move /dev/sda1** will appear.
  - Here’s how to use the options in this window:
    - **Graphical Slider**:
      - Drag the slider to the right to include the unallocated space.
      - The slider allows you to visually adjust the partition size.
    - **Manual Input**:
      - Alternatively, you can manually enter the new size in the **New size (MiB)** field.
      - Ensure the new size includes the unallocated space.
    - **Free Space Following (MiB)**:
      - This field shows how much space will remain unallocated after resizing.
      - Set this to `0` if you want to use all the unallocated space.

- **Apply the Changes**:
  - Once you’ve adjusted the partition size, click **Resize/Move** in the window.
  - This action schedules the resize operation but does not apply it yet.

- **Confirm and Apply All Operations**:
  - Back in the main GParted window, click the green checkmark (**Apply All Operations**) in the toolbar.
  - A confirmation dialog will appear. Click **Apply** to proceed.
  - GParted will now resize the partition. This process may take a few minutes, depending on the size of the partition and the amount of data.

- **Verify the Resize**:
  - After the operation completes, check the partition layout in GParted:
    - The partition (e.g., `/dev/sda1`) should now show the increased size.
    - The unallocated space should no longer be visible, as it has been merged into the partition.

#### **2.7 Resize the Filesystem**
- After resizing the partition, you may need to resize the filesystem to use the new space. Run:
  ```bash
  sudo resize2fs /dev/sda1
  ```
  - Replace `/dev/sda1` with the correct partition if necessary.

#### **2.8 Verify the New Disk Size**
- Run the following command to confirm the new disk size:
  ```bash
  df -h
  ```
  - You should see the increased size for your root partition.

---

### **Step 3: Reboot and Confirm**

#### **3.1 Reboot the Kali Linux VM**
- Reboot your VM to ensure all changes are applied:
  ```bash
  sudo reboot
  ```

#### **3.2 Check the Disk Space Again**
- After rebooting, run:
  ```bash
  df -h
  ```
  - Verify that the new space is now available.

---

### **Troubleshooting**

#### **Problem 1: GParted Doesn’t Show Unallocated Space**
- **Solution**:
  - Refresh the partition table in GParted.
  - Reboot your Kali Linux VM and check again.

#### **Problem 2: Disk Space Doesn’t Reflect After Reboot**
- **Solution**:
  - Ensure you resized the partition properly in GParted.
  - Run `resize2fs` on the correct partition.

#### **Problem 3: `VBoxManage` Gives an Error About File Paths**
- **Solution**:
  - Double-check the file path for the `.vdi` disk.
  - Ensure the path is correctly typed in the command.

---

### **Contributing**
If you have any improvements or suggestions, feel free to fork this project and submit a pull request!

---

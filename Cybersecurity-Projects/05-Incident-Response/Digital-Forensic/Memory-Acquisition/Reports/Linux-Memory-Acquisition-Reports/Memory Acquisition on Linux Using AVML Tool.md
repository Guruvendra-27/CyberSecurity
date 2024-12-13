# Memory Acquisition on Linux Using AVML Tool

### Introduction
This guide outlines the steps to acquire memory from a Linux system using the AVML (Acquisition of Volatile Memory for Linux) tool. Memory acquisition is essential in forensic investigations to capture volatile data for analysis.

---

### Step-by-Step Guide

#### Step 1: Search for AVML Tool
1. Open the web browser on the Linux system.
2. Search for the **AVML Tool** to acquire Linux memory.
   
   ![search for avml](https://github.com/user-attachments/assets/6f32cdb4-01d3-4952-b965-fd7e001da7a6)


---

#### Step 2: Select Desired Version
1. Visit the official AVML GitHub repository.
2. Navigate to the **Releases** section and select the required version (e.g., **v0.2.0**).
   
   ![selecting version](https://github.com/user-attachments/assets/6c5d4c3b-a3db-4093-9edd-2d4caf173f67)
   ![selecting version v 20 0](https://github.com/user-attachments/assets/e5cea437-b16c-4b1f-8fb5-b81e97f44071)


---

#### Step 3: Download the AVML Tool
1. Copy the download link for the desired version.
   
   ![copy the avml link](https://github.com/user-attachments/assets/7838fed4-587f-4029-95ce-39e758ec77ad)


2. Use the `wget` command in the terminal to download the AVML file:
   ```bash
   wget https://github.com/microsoft/avml/releases/download/v0.2.0/avml
   ```
   ![download](https://github.com/user-attachments/assets/f404fd41-0fd7-4fc9-a8d7-f392f598477e)


---

#### Step 4: Modify File Permissions
1. Verify the file permissions:
   ```bash
   ls -al
   ```
2. Update permissions to allow execution using the `chmod` command:
   ```bash
   chmod 755 avml
   ```

   
   ![linux permission table](https://github.com/user-attachments/assets/7fef6a4d-0e57-4a3e-a5e3-557160920ccd)
   ![avml permission](https://github.com/user-attachments/assets/772f55c6-a0ab-4639-89bd-43025140d851)


---

#### Step 5: Run the AVML Tool
1. Execute the AVML tool with the following command:
   ```bash
   sudo ./avml kalimemory.raw
   ```
   - Replace `kalimemory.raw` with your desired file name.
   
   ![run avml](https://github.com/user-attachments/assets/c4a80751-ace1-42ce-9ebd-585639e9ab93)

2. The memory dump file will be saved in the root directory.

   ![avml saved](https://github.com/user-attachments/assets/dad282da-2004-4c47-8544-ff504f131ecd)


---

#### Step 6: Transfer the Memory Dump

1. Connect a USB drive to the system.
   
     ![connect pendrive](https://github.com/user-attachments/assets/1bf74210-40ff-4333-9329-eeb9d1bf0927)
     ![created folder 1](https://github.com/user-attachments/assets/459e0242-c364-4004-a073-7be1adc376a8)

   
2. Open the root folder with appropriate privileges to access the dump file:
   - Use a file manager or terminal to navigate.
   - Enter the root password if prompted.
  
     ![open the root folder as root](https://github.com/user-attachments/assets/8377e0e4-3b91-4946-b138-507ddf6edfeb)
     ![root passwd](https://github.com/user-attachments/assets/18e42507-f8d0-434d-8b18-b8607d476381)

  
3. Copy the memory dump file from the root directory to the USB drive.
   - Use the **Send To** option or a file manager for this step.
   
     ![copy the kali file](https://github.com/user-attachments/assets/c46d31ed-1f6f-4da0-9db5-a0892a4b0947)
     ![copied in to pendrive](https://github.com/user-attachments/assets/99f05138-11c1-46b7-ab99-ab18fc50ccbf)

---

#### Step 7. Safely Eject the USB Drive
Ensure the USB drive is safely ejected after transferring the memory dump. This step protects data integrity.

---

#### Step 8. Analyze the Memory Dump
Transfer the USB drive to a secure forensic workstation. Use trusted forensic tools to analyze the memory dump for malicious activity or evidence.

---

### Recommended Forensic Analysis Tools

Below are commonly used tools for analyzing Linux memory dumps:

1. **Volatility**: Extracts and analyzes forensic artifacts like running processes, open network connections, and hidden memory objects.
2. **Rekall**: A memory forensic framework tailored for in-depth analysis of Linux systems.
3. **LiME**: A lightweight tool for acquiring volatile memory on Linux systems.
4. **Wireshark**: Useful for analyzing network-related data within memory dumps.
5. **Autopsy**: Provides a graphical interface for analyzing memory and disk images.

---

### Important Notes:
- Ensure the USB drive has sufficient space for the memory dump file.
- Perform the memory acquisition process on a clean and isolated forensic system to maintain evidence integrity.
- Use verified tools to prevent tampering with or loss of evidence.

This guide provides a systematic and professional approach for Linux memory acquisition, ensuring forensic soundness throughout the process.

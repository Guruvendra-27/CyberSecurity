## Report on Disk Acquisition of Windows Using FTK Imager

---

### **Introduction**

This report describes the process of creating a disk image from a Windows computer using FTK Imager. In digital forensics, disk acquisition is a critical step, as it involves creating an exact copy of a system's storage. This ensures that the data is preserved without any alterations, allowing for thorough analysis later. FTK Imager was used to create this disk image, which will be analyzed for any potential evidence.

---

### **Process Description**

The process of acquiring the disk image followed these steps:

### **1. Downloading and Installing FTK Imager**

FTK Imager was downloaded and installed on the computer where the disk image was to be created.  
![Pasted image 20241218003751](https://github.com/user-attachments/assets/13789556-9f12-4a0b-9080-f1e3b8c2e631)
![installaion](https://github.com/user-attachments/assets/d0134317-8b88-4987-a88d-201fb05d8bc8)
![yes](https://github.com/user-attachments/assets/d8a9d63c-f993-49b6-9734-2e9da4bfd798)


### **2. Launching FTK Imager**

After installation, FTK Imager was opened. The user navigated to the **File > Create Disk Image** option in the menu to start the disk acquisition process.  
![icon](https://github.com/user-attachments/assets/8e86a6c5-4f71-4256-8f81-46c29890d058)
![ftk start yes 1](https://github.com/user-attachments/assets/445cf419-c8a4-4b92-9025-5a63435a59c7)
![create disk image](https://github.com/user-attachments/assets/99649b61-e7aa-4821-9c94-f542e873edf5)


### **3. Navigating to the Disk Image Creation Wizard**

1. **Opening the Disk Image Creation Wizard**  
    In FTK Imager, the first step is to choose the "Logical Drive" option. This ensures that only the used space on the target drive is captured, which typically contains the relevant data.  
    ![logical drive](https://github.com/user-attachments/assets/3a09c311-7eb7-4660-8f7e-51494a4617c5)

    
2. **Choosing the Drive to Image**  
    In the next screen, the user specifies which drive they wish to copy. This involves selecting the physical or logical drive that contains the data to be imaged.  
    ![select drive](https://github.com/user-attachments/assets/4f2955a0-49fc-4d43-ae08-f1bfa6efc3fc)

    
3. **Selecting the Image Format**  
    After selecting the drive, the user is prompted to choose the format for the disk image. The "Raw (dd)" format is selected because it is widely accepted by other forensic tools, ensuring compatibility for future analysis. This format captures the raw data without altering it, preserving the integrity of the original system.  
    ![select raw](https://github.com/user-attachments/assets/0a1b4aaa-4ba4-40e8-a0ca-89482b586510)

    
4. **Entering Case Information**  
    To maintain proper documentation and preserve the chain of custody, the user enters the case number and evidence identifier into the designated fields. This helps to properly document the acquisition in forensic records.  
    ![case number](https://github.com/user-attachments/assets/af220be9-fa6e-495b-8a1a-1e293fc3c134)

    
5. **Choosing the Destination Folder**  
    The user selects the destination folder where the disk image will be saved. The folder should have enough space to store the entire image file, ensuring the process proceeds smoothly.  
    ![FILE PATH](https://github.com/user-attachments/assets/fe87bd0b-eb26-4e37-9277-9fc14dc0dc09)

    
6. **Starting the Disk Imaging Process**  
    After confirming all the settings, the user clicks the “Start” button to begin the disk imaging process. FTK Imager starts creating an exact copy of the selected logical drive, capturing only the used space.  
    ![start](https://github.com/user-attachments/assets/3c03d0e2-d1b3-4989-b39c-11828f264d35)

    
7. **Creating the Disk Image**
    FTK Imager copies the active data and files from the selected logical drive. The process ensures that all relevant files and system data are captured.  
    ![disk image](https://github.com/user-attachments/assets/5db789d6-b232-4986-810d-f4e40dcd21de)

    
8. **Completion of the Disk Image**  
    Once the process is complete, FTK Imager confirms the successful creation of the disk image. The image is now ready for verification and further analysis.  
    ![disk  created](https://github.com/user-attachments/assets/cffd1062-7928-4c9e-9873-bc43ff348346)

    

---

### **4. Transferring the Disk Image**

1. **Navigating to the Saved Folder**  
    The user opens the folder where the disk image file was saved. This folder is typically predefined for storing the image during the acquisition process.
    
2. **Selecting the Disk Image File**  
    Once in the folder, the user locates the disk image file. The file is usually named according to the case number or a specific naming convention. The user right-clicks on the file to open the context menu and selects the "Extract Files" option. This allows the user to copy the disk image file to another location, such as an external storage device.  
    ![winrar option](https://github.com/user-attachments/assets/ab438adb-df2f-4f4f-b5f9-0c2dfa0cae47)

    
3. **Selecting the Destination Drive**  
    A dialog box will appear asking the user to select the destination drive. The user navigates to the external storage device (e.g., an external hard drive or USB drive) that has been prepared for secure storage. The user selects the drive where the disk image will be copied.  
    ![winrar foder](https://github.com/user-attachments/assets/59aed5eb-df3b-4c5f-b6ec-adae67db2d30)

    
4. **Copying the Disk Image to the External Drive**  
    After selecting the destination drive, the user clicks "OK" or "Start" to begin the copying process. The disk image is then transferred from the local system to the external storage device. Once the process is complete, the user can check the external storage device to confirm that the disk image file has been successfully transferred.  
    ![file extracted](https://github.com/user-attachments/assets/8ff83a61-8e09-4f82-9c37-1293fb47de30)
    ![fle copied](https://github.com/user-attachments/assets/e829b31c-db29-482d-b9a1-7cc68b1077aa)

    
5. **Safely Ejecting the Storage Device**  
    After the disk image has been successfully transferred, the external storage device is safely ejected to prevent any data corruption. This ensures that the image remains intact and secure.
    

---

### **Outcome**

The disk acquisition was successfully completed, and an exact copy of the system’s storage was created. This image contains all the system’s data, including active files and deleted data. The image will now be analyzed to identify any relevant evidence.

---

### **Forensic Analysis Tools**

The disk image will be analyzed using various forensic tools, including:

- **FTK Imager**: For verifying and exploring the disk image.
- **Autopsy**: An open-source tool for examining disk data.
- **EnCase**: A professional tool for detailed forensic analysis.
- **X-Ways Forensics**: A powerful tool for in-depth disk examination.

---

### **Recommendations**

- Ensure that the external storage device has enough space to store the entire disk image, especially for large drives.
- Keep clear and detailed records of all actions during the acquisition process, including case numbers and evidence identifiers, to preserve the chain of custody.
- Perform the disk acquisition on a secure, isolated system to prevent tampering with the data.
- Use trusted forensic tools to analyze the disk image and ensure that all important evidence is discovered.

---

### **Conclusion**

The disk acquisition process using FTK Imager was successfully completed, and the integrity of the system’s data was preserved. The disk image will be further examined using forensic tools to identify any evidence relevant to the investigation.

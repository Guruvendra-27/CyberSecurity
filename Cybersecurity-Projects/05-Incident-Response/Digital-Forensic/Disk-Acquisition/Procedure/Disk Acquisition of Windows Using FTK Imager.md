## Disk Acquisition of Windows Using FTK Imager

### Introduction

This guide explains how to acquire disk data from a Windows system using FTK Imager. Disk acquisition is a crucial step in digital forensics, allowing investigators to create exact copies of data from a drive while maintaining the integrity of the evidence. FTK Imager is a powerful tool that helps preserve forensic evidence by creating bit-by-bit copies of storage devices

---

### Tools Needed

- **FTK Imager**: A tool for creating exact copies (images) of storage devices.
- **WinRAR**: A tool for compressing files to make them easier to store and transfer.

**Download Links**:

- [FTK Imager 4.7.3.81](https://www.exterro.com/ftk-product-downloads/ftk-imager-4-7-3-81)
- [WinRAR](https://www.win-rar.com/download.html?&L=0)

---

### Step-by-Step Guide

#### Step 1: Download FTK Imager

1. Open your browser and search for **FTK Imager** on Google. 
   ![[search.png]]

2. Navigate to the FTK Imager download page.
   ![[button.png]]
3. Complete the required form to initiate the download.
   ![[fill the form.png]]
   ![[downloaded.png]]
---

#### Step 2: Install FTK Imager

1. Double-click the downloaded file to start the installation and grant administrative access when prompted.

   ![[installaion.png]]
   ![[yes.png]]
2. Follow the installation steps:
    - Accept the license agreement.
    
      ![[installation wizard.png]]
     ![[installation wizard 2.png]]
    - Choose the Different installation folder or use the default location. 
    
       ![[Pasted image 20241217223124.png]]
    - Click **Install** to complete the setup.
    - Once the installation is finished, click **Finish** to exit the wizard.
    
      ![[finsish.png]]

---

#### Step 3: Launch FTK Imager

1. Locate the **FTK Imager** shortcut on your desktop and double-click to open the program.

    ![[icon.png]]
    ![[ftk start yes 1.png]]
2. From the top menu, go to **File** > **Create Disk Image** to begin acquiring data from the disk.
    ![[create disk image.png]]

---

#### Step 4: Select Source and Destination

1. In the **Create Disk Image** wizard, select **Logical Drive** as the source type. This option captures only the used disk space of the drive.
    ![[logical drive.png]]
2. Select the specific drive you want to image and click **Next**.
    ![[select drive 1.png]]
3. Select **Raw (dd)** as the image type, as it is widely supported by forensic tools. Click **Next**.
    ![[select raw.png]]
4. Enter the required details, such as the **Case Number** and **Evidence Identifier**, to maintain the chain of custody.
    ![[case number.png]]
5. Select a destination folder and file name for the disk image. Ensure the drive has enough space for the image. Click **Finish** to proceed and  Do not Select "Automate Multiple Removable Media" Option.
    ![[FILE PATH.png]]

---

#### Step 5: Create the Disk Image

1. Review the summary information and click **Start** to begin creating the disk image.
    ![[start.png]]
2. Monitor the progress bar. The time required will depend on the size of the drive.
    ![[disk image.png]]
3. Once completed, verify the disk image is saved in the specified location.
    ![[disk  created.png]]
---

#### Step 6: Downloading and Installing WinRAR Application (Optional)

In order to Copy the Disk image file we need WinRAR Application following are the steps to Download WinRAR:
    1. Open your browser and search for "WinRAR download."
        ![[winrar file.png]]
    3. Go to the WinRAR Download Page and Download and Follow the Installation steps.
        ![[winrar download.png]]
        ![[winrar downloaded.png]]

---

#### Step 7: Transfer the Disk Image

1. Copy the disk image to an external USB drive or hard disk.  
2. Follow the installation steps:
    - To extract the file, right-click and select **Extract to**. 
     ![[winrar option.png]]

     - Choose the destination folder where you want to extract the file. 
    
       ![[winrar foder.png]]
       
     - The extraction process will begin, and the file will be copied to the selected location.

       ![[file extracted.png]]

      -  The file has been successfully copied. 
      
      ![[fle copied.png]]
       
       


#### Step 8: Safely Eject the External Storage Device

Once the file transfer is complete, safely eject the external storage device to prevent data corruption.

---

### Recommended Tools for Forensic Analysis

After acquiring the disk image, you can use the following forensic tools to analyze its contents:

- **FTK Imager**: For viewing and analyzing the acquired disk image.
- **Autopsy**: An open-source tool for investigating disk images.
- **EnCase**: A professional tool for forensic analysis and evidence management.
- **X-Ways Forensics**: A lightweight and powerful tool for analyzing disk data.

---

### Important Notes

- Ensure there is enough storage space on the destination drive for the disk image.
- Perform the acquisition on a trusted and isolated system to maintain evidence integrity.
- Document all case details, such as the Case Number and Investigator Name, to preserve the chain of custody.

By following the steps outlined in this guide, you can perform a thorough and reliable disk acquisition process, ensuring the data is preserved accurately for future forensic analysis.


## Procedure: Disk Acquisition of Windows Using FTK Imager

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
      ![search](https://github.com/user-attachments/assets/381ccb19-7ec0-4b8c-b26f-5e55dc8c7daf)

2. Navigate to the FTK Imager download page.
   ![button](https://github.com/user-attachments/assets/0c17be11-f5ae-4208-bbdb-5ba1d9faa39a)

3. Complete the required form to initiate the download.
   ![fill the form](https://github.com/user-attachments/assets/55dd60fc-8b33-4cc8-982a-f2dc4317fb2f)
   ![downloaded](https://github.com/user-attachments/assets/3ba805a1-ff9c-46f9-8eb9-18f77a0c9751)

---

#### Step 2: Install FTK Imager

1. Double-click the downloaded file to start the installation and grant administrative access when prompted.
   ![installaion](https://github.com/user-attachments/assets/5b577e9e-b210-425f-9b4d-ed891a2e8b9b)
   ![yes](https://github.com/user-attachments/assets/7ab68024-a766-43f9-9f0d-a25fb0ccd595)


2. Follow the installation steps:
    - Accept the license agreement.
      ![installation wizard](https://github.com/user-attachments/assets/dcc6d11a-6af4-4717-99b6-269e4e5f98f4)
      ![installation wizard 2](https://github.com/user-attachments/assets/0f93d734-45bd-4424-b481-694e788d7ca6)

    - Choose the Different installation folder or use the default location. 
    
       ![Pasted image 20241217223124](https://github.com/user-attachments/assets/29830158-73b1-4897-883e-87ae84793768)

    - Click **Install** to complete the setup.
    - Once the installation is finished, click **Finish** to exit the wizard.
    
      ![finsish](https://github.com/user-attachments/assets/52724971-a37b-4732-a6a8-70ae9fb59979)


---

#### Step 3: Launch FTK Imager

1. Locate the **FTK Imager** shortcut on your desktop and double-click to open the program.

    ![icon](https://github.com/user-attachments/assets/4878c72a-bc09-42c5-8582-f1b0abcfe606)
   ![ftk start yes 1](https://github.com/user-attachments/assets/21a5570a-9208-488e-95ee-df24540a51f3)


   
2. From the top menu, go to **File** > **Create Disk Image** to begin acquiring data from the disk.
    ![create disk image](https://github.com/user-attachments/assets/97f2c902-20f6-4aa5-bfe4-b293ccf24edd)

---

#### Step 4: Select Source and Destination

1. In the **Create Disk Image** wizard, select **Logical Drive** as the source type. This option captures only the used disk space of the drive.
    ![logical drive](https://github.com/user-attachments/assets/a0171916-0e7f-4fdd-9477-7bc94e31aaef)

2. Select the specific drive you want to image and click **Next**.
    ![select drive 1](https://github.com/user-attachments/assets/1cb57147-a5b5-4ace-9ba9-5fdc31021f5a)

3. Select **Raw (dd)** as the image type, as it is widely supported by forensic tools. Click **Next**.
    ![select raw](https://github.com/user-attachments/assets/19a0d7c5-9754-4e5e-aec9-c69165e38978)


4. Enter the required details, such as the **Case Number** and **Evidence Identifier**, to maintain the chain of custody.
    ![case number](https://github.com/user-attachments/assets/a8dcdd0d-2363-49d7-92d7-89c2c65ffedf)

5. Select a destination folder and file name for the disk image. Ensure the drive has enough space for the image. Click **Finish** to proceed and  Do not Select "Automate Multiple Removable Media" Option.
    ![FILE PATH](https://github.com/user-attachments/assets/4413e7a6-8266-4b02-8a48-d365012e74f8)


---

#### Step 5: Create the Disk Image

1. Review the summary information and click **Start** to begin creating the disk image.
    ![start](https://github.com/user-attachments/assets/1b1ba309-8f4b-4fd9-b3d8-dc5d9866f165)

2. Monitor the progress bar. The time required will depend on the size of the drive.
    ![disk image](https://github.com/user-attachments/assets/3af24550-bd52-4522-957d-40fd5c283079)

3. Once completed, verify the disk image is saved in the specified location.
    ![disk  created](https://github.com/user-attachments/assets/56156239-53b0-4150-be7c-06aeeb3f3ad3)

---

#### Step 6: Downloading and Installing WinRAR Application (Optional)

In order to Copy the Disk image file we need WinRAR Application following are the steps to Download WinRAR:
    1. Open your browser and search for "WinRAR download."
        ![winrar file](https://github.com/user-attachments/assets/c9b10e67-94f3-4b5b-a704-0f7eccb29438)

    3. Go to the WinRAR Download Page and Download and Follow the Installation steps.
        ![winrar download](https://github.com/user-attachments/assets/fb75350a-6aee-4cff-a589-1faab801dcf0)
        ![winrar downloaded](https://github.com/user-attachments/assets/dd382068-a115-4902-852d-7e1711ca3988)


---

#### Step 7: Transfer the Disk Image

1. Copy the disk image to an external USB drive or hard disk.  
2. Follow the installation steps:
    - To extract the file, right-click and select **Extract to**.
      ![winrar option](https://github.com/user-attachments/assets/848f53f6-c87d-4a9d-a714-74f3411fad4b)

     - Choose the destination folder where you want to extract the file.
       ![winrar foder](https://github.com/user-attachments/assets/81f8888f-2f04-4c21-b135-34db2428a569)

     - The extraction process will begin, and the file will be copied to the selected location.
       ![file extracted](https://github.com/user-attachments/assets/df18d9db-209d-442d-bec3-534550c3db98)


      -  The file has been successfully copied.
        ![fle copied](https://github.com/user-attachments/assets/82321672-3aad-4741-b565-06a5cc4fb0df)

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


# **Report: Memory Acquisition of Linux System Using AVML Tool**


## **Introduction**  
This report outlines the process of acquiring volatile memory from a Linux system using the AVML (Acquisition of Volatile Memory for Linux) tool. Memory acquisition is crucial in forensic investigations, as it captures the system’s active state. This provides important evidence about system activity, running processes, and possible malicious actions. The steps outlined below describe how the system’s memory was preserved for future analysis.

---

## **Process Overview**

##### **1. Finding the AVML Tool**  
  The first step was to search for the AVML tool using a web browser on the Linux system. The tool is available on its official GitHub repository, where the latest version can be downloaded.
![search for avml](https://github.com/user-attachments/assets/283c3069-2e38-424d-8014-f5aaf0f9a7b6)

---
##### **2. Choosing the Right Version**  
After locating the AVML repository, the **Releases** section was accessed, and the appropriate version (e.g., **v0.2.0**) was selected to ensure compatibility with the system.
![selecting version](https://github.com/user-attachments/assets/e1961d4b-6a67-4691-9581-4a7d682da546)
![selecting version v 20 0](https://github.com/user-attachments/assets/50d1fccc-4a3b-4c99-a5c8-614586350815)

---

##### **3. Downloading the AVML Tool**  
The download link for the selected version was copied, and the tool was downloaded using the `wget` command in the terminal.

```bash
wget https://github.com/microsoft/avml/releases/download/v0.2.0/avml
```

![copy the avml link](https://github.com/user-attachments/assets/b1747d57-767a-43f5-be88-34e809088fa2)
![download](https://github.com/user-attachments/assets/b9cb5606-02a6-4924-98df-21acdb199464)

---

##### **4. Changing File Permissions**  
After the tool was downloaded, the file’s permissions were checked with the `ls -al` command. The file was then made executable using the `chmod` command:

```bash
chmod 755 avml
```

![linux permission table](https://github.com/user-attachments/assets/bbfc4f8d-1687-410f-b9af-61cbc6cc87c3) 
![avml permission](https://github.com/user-attachments/assets/e1a00bb2-4d15-48f5-8e9b-97f1fd56620a)

---

##### **5. Running the AVML Tool**  
The AVML tool was executed to capture the system’s memory, using the following command:

```bash
sudo ./avml kalimemory.raw
```

Here, `kalimemory.raw` was chosen as the name for the memory dump file, and it was saved in the root directory.

![run avml](https://github.com/user-attachments/assets/97ee6888-5905-4831-83c9-3852d054784e)
![avml saved](https://github.com/user-attachments/assets/51108d78-fa42-4342-8f83-ba5090aaecfc)

---

##### **6. Transferring the Memory Dump**

1. A USB drive was connected to the system to transfer the memory dump. The root directory was accessed with the following command:

```bash
sudo nautilus /root
```

![connect pendrive](https://github.com/user-attachments/assets/987a8777-0ea4-48de-957d-e4d4eee5c683)
![created folder 1](https://github.com/user-attachments/assets/16185d9c-99e5-4700-b61c-dc2b4583106c)

2. Once in the root directory, the memory dump file was copied to the USB drive.

![open the root folder as root](https://github.com/user-attachments/assets/a149b92f-f777-43c5-8abc-9eda51155a9b)
![root passwd](https://github.com/user-attachments/assets/700e5f07-bb44-4b87-819c-8f998c844a78)
![copy the kali file](https://github.com/user-attachments/assets/21d38ad0-a1b4-4208-b8b4-29bfb71cd337)
![copied in to pendrive](https://github.com/user-attachments/assets/906070fc-4374-427d-ac96-d2107bdaeb4b)


---

##### **7. Safely Ejecting the USB Drive**  
Once the memory dump was successfully transferred, the USB drive was safely ejected to avoid data corruption during removal.

---

### **Outcome**

The memory dump was successfully created, capturing the active system memory at the time of acquisition. This file contains critical volatile data, including running processes, network connections, and system configurations. It will be further analyzed to uncover potential evidence for forensic purposes.

---

### **Forensic Analysis Tools**

The acquired memory dump will be analyzed using trusted forensic tools, including:

- **Volatility**: For extracting and analyzing memory artifacts such as processes, network connections, and hidden objects.
- **Rekall**: A powerful tool for in-depth memory forensics on Linux systems.
- **Wireshark**: Used to analyze network-related data from the memory dump.
- **LiME (Linux Memory Extractor)**: A tool designed to extract memory images from Linux systems.
- **Autopsy**: A user-friendly graphical interface for analyzing memory and disk data.

---

### **Recommendations and Notes**

- Ensure the **USB drive** has enough storage space to hold the memory dump, which should be at least as large as the system's RAM.
- Perform the memory acquisition on a **secure, isolated forensic system** to preserve the integrity of the evidence.
- Use **trusted forensic tools** to ensure the accuracy and integrity of the analysis.

---

### **Conclusion**

The memory acquisition process was completed successfully, preserving the volatile system memory for further forensic analysis. The memory dump will now be analyzed to identify possible evidence of malicious activity or system compromise.

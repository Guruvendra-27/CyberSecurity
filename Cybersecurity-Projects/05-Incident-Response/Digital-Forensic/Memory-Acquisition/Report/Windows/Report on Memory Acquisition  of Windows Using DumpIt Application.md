**Report on Memory Acquisition  of Windows Using DumpIt Application**

**Introduction**
This report documents the process of acquiring volatile memory from a Windows system using the DumpIt application. Memory acquisition captures the active state of a system, providing critical forensic evidence for digital investigations. This procedure was executed to preserve system memory for further analysis.

---

**Procedure Overview**

**1. Connecting the USB Drive**
The USB pendrive containing the DumpIt application was inserted into the affected system. The connection was verified by ensuring the pendrive appeared in the system’s file explorer.

![Connecting Pendrive 1](https://github.com/user-attachments/assets/9efa8595-93a3-4f1a-9ef7-c65e98cc6837)
![Showing Pendrive 2](https://github.com/user-attachments/assets/5657edd9-4bb5-43be-8015-24b3a9954657)

**2. Launching the DumpIt Application**
The DumpIt application was accessed by navigating to the relevant folder on the pendrive. The application was started by double-clicking its executable file.

![open the dumpit folder 1](https://github.com/user-attachments/assets/bca232f1-8dea-4ebe-a9d8-f0170d2b0324)
![starting dumpti application](https://github.com/user-attachments/assets/d836c2cf-f06f-4b27-9751-c4f984087734)

**3. Granting Administrative Access**
Administrative privileges were granted when prompted. This step ensured the application could access and acquire the system’s memory.

![click on yes](https://github.com/user-attachments/assets/6ac11ed0-a31a-4fe6-a0bd-bf8a58b7e5e7)

**4. Executing Memory Acquisition**
A command prompt window initiated by DumpIt guided the acquisition process. When prompted, “y” was entered to confirm and start memory acquisition. The application created a memory dump file on the pendrive, capturing the system’s complete memory state at the time of execution.

![dumpit it pop up window](https://github.com/user-attachments/assets/d2d5b049-4ef7-40c5-b4dd-4f63f3b007f8)
![processing started](https://github.com/user-attachments/assets/a69cf3ec-f745-4f76-9528-d0668508b072)


**5. Finalizing the Process**
Once the acquisition process completed, the memory dump file was confirmed to be saved on the pendrive. The pendrive was safely ejected to prevent data corruption.

![Memory Acquisition file created](https://github.com/user-attachments/assets/61b76576-c7c4-48fc-b076-77d811e83e2c)
![eject](https://github.com/user-attachments/assets/cb583972-d0ea-4344-a7ac-871612fb0c92)

---

**Outcome**
A memory dump file corresponding to the system’s RAM size was successfully created. This file contains the volatile data, including active processes, loaded modules, and network activity, at the time of acquisition. The file will be utilized for forensic analysis on a dedicated workstation.

---

**Forensic Analysis Tools**
The memory dump will be analyzed using trusted forensic tools. The following tools are recommended:

- **Volatility**: To extract and analyze memory artifacts, such as processes and network connections.
- **Autopsy**: For user-friendly analysis of memory and disk data.
- **FTK Imager**: For examining and validating forensic images, including memory dumps.
- **Redline**: For identifying malicious activity in memory.
- **Rekall**: To examine volatile memory images.
- **Wireshark**: For analyzing network-related data within the dump.

---

**Recommendations and Notes**
- Ensure the pendrive has sufficient space to store the memory dump, which matches the size of the system’s RAM.
- Always perform the acquisition process on a secure and isolated system.
- Use trusted forensic tools to analyze the memory dump to maintain the integrity of evidence.

**Conclusion**
The memory acquisition process was completed successfully, preserving volatile system data for forensic examination. The resulting memory dump will be analyzed to uncover evidence of potential malicious activity or system compromise.


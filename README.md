# wazuh-FIM-monitoring
File Integrity Monitoring setup using Wazuh – part of the SOC lab

# 🛡️ Wazuh Setup & File Integrity Monitoring (FIM)

This project documents the complete setup of Wazuh in a lab environment, with a focus on enabling **File Integrity Monitoring (FIM)** to detect unauthorized or malicious changes to files and directories in real-time.

📅 **Date**: June 2025  
👤 **Author**: Muhammad Aamir  

---

## 🎯 Objective

- Deploy Wazuh Manager and Dashboard in a virtualized environment.
- Connect a Windows endpoint using the Wazuh Agent.
- Configure and test File Integrity Monitoring (FIM).
- Observe, tune, and interpret alerts on the Wazuh dashboard.

---

## 🧰 Tools & Environment

| Component        | Details                                  |
|------------------|-------------------------------------------|
| Wazuh Manager    | Deployed from OVA on VirtualBox           |
| Wazuh Dashboard  | Web interface for log/alert visibility    |
| Wazuh Agent      | Installed on Windows 11 system            |
| Network Mode     | Bridged Adapter (VirtualBox)              |

---

## ⚙️ Step-by-Step Implementation

### 🔸 A. Wazuh Manager Installation
1. Downloaded OVA file from [Wazuh official site](https://wazuh.com/download/).
2. Imported into VirtualBox and configured the network to use a **Bridged Adapter**.
3. Started the VM and noted down the IP address using `ip a`.
4. Accessed the Wazuh Dashboard via `https://<wazuh-ip>`.

### 🔸 B. Wazuh Agent Setup (on Windows)
1. Downloaded Wazuh Agent for Windows.
2. Installed the agent and connected it to the Wazuh Manager IP.
3. Confirmed connection via the Wazuh Dashboard.
4. Started the agent service using `services.msc`.

### 🔸 C. File Integrity Monitoring (FIM) Configuration
1. Edited the agent config file: `ossec.conf`.
2. Enabled FIM to monitor a specific folder:
   ```xml
   <syscheck>
     <directories check_all="yes">C:\Users\AAMIR IRSHAD\Documents\Test</directories>
   </syscheck>

------
Screenshots of the lab:
A. Wazuh Manager Installation
1.	Downloaded the Wazuh OVA file from the official site.
![image](https://github.com/user-attachments/assets/4b5a911f-a9d6-4725-bd5c-e6425967a6b4)
2.	Imported into VirtualBox.
![image](https://github.com/user-attachments/assets/2a58e64e-48ec-44d4-a8e2-dee9b30fd9ad)
3.	Set Network to Bridged Adapter.
![image](https://github.com/user-attachments/assets/cf3bad95-3bc4-45b5-bc12-31f959466498)
4.	Started VM and got IP from terminal using ip a.
![image](https://github.com/user-attachments/assets/ce1cb21b-4f31-41a2-aeff-05e6302d7c35)
5.	Opened Wazuh Dashboard at: https://<wazuh-ip>.
![image](https://github.com/user-attachments/assets/2a7480b4-585e-4d06-8110-c6c469215265)

B. Install Wazuh Agent (on Windows)
1.	Downloaded the agent from the Wazuh official site.
![image](https://github.com/user-attachments/assets/7414e8c0-f8bd-4c1b-b3c0-b66959d5cb54)
2.	Installed and configured it to connect with the Wazuh Manager IP.
![image](https://github.com/user-attachments/assets/3523fb7d-779c-4364-b792-1f58e4b7951f)
3.	Checked Wazuh Dashboard to confirm connection.
![image](https://github.com/user-attachments/assets/6abb02cb-298d-494d-b59a-a7d278250c14)
4.	Started the agent service from "Services.msc".
![image](https://github.com/user-attachments/assets/29bf4ff4-19f5-4271-92cd-a28f2e5afdaf)

C. Configure File Integrity Monitoring (FIM)
1.	Edited the Wazuh agent config file (ossec.conf) to monitor a folder:
![image](https://github.com/user-attachments/assets/6538dfc7-5e11-4e40-a1d5-2486f6a00aa1)
2.	<syscheck>
3.	<directories check_all="yes">C:\Users\AAMIR IRSHAD\Documents\Test</directories>
4.	</syscheck>
![image](https://github.com/user-attachments/assets/70228a32-3d4d-4288-bb7f-dc162aa07857)
5.	Restarted Wazuh Agent service.
![image](https://github.com/user-attachments/assets/6c289889-7b0c-4a07-9dbf-acc66ecc5e62)
6.	Made a small file change to test.
![image](https://github.com/user-attachments/assets/19656030-5d86-43f2-b15e-a66fd690e008)
7.	Checked Wazuh Dashboard — alert successfully generated.
![image](https://github.com/user-attachments/assets/da6d7168-e941-4375-81d0-45caef919e59)
![image](https://github.com/user-attachments/assets/d7494603-4175-48ed-9067-67d35df89d72)
8.	Tuned the config to reduce false alerts by adding ignored paths.
![image](https://github.com/user-attachments/assets/ead01512-189f-44e3-835c-678971c270e8)

------
🔗 Connect With Me

💼 [LinkedIn](https://www.linkedin.com/in/m-aamir947/)

📧 aamirirshad947@gmail.com

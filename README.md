# wazuh-FIM-monitoring
File Integrity Monitoring setup using Wazuh – part of SOC lab

# 🛡️ Wazuh Setup & File Integrity Monitoring (FIM)

This project documents a complete setup of Wazuh in a lab environment with a focus on enabling **File Integrity Monitoring (FIM)** to detect unauthorized or malicious changes to files and directories in real time.

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
2. Imported into VirtualBox and configured network to **Bridged Adapter**.
3. Started the VM and noted down the IP address using `ip a`.
4. Accessed the Wazuh Dashboard via `https://<wazuh-ip>`.

### 🔸 B. Wazuh Agent Setup (on Windows)
1. Downloaded Wazuh Agent for Windows.
2. Installed the agent and connected it to Wazuh Manager IP.
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
🔗 Connect With Me
💼 [LinkedIn](https://www.linkedin.com/in/m-aamir947/)

📧 aamirirshad947@gmail.com

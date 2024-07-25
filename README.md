# Microsoft Sentinel (SIEM) Map With Live Cyber Attack Using A Honeypot in Azure

## Project Overview

This project demonstrates the setup and use of Microsoft Sentinel to monitor and analyze real-time cyber attacks on a vulnerable honeypot virtual machine (VM) hosted in Microsoft Azure. The VM was intentionally exposed to attract attackers, and data from failed RDP (Remote Desktop Protocol) login attempts were captured and analyzed. The analysis included mapping the geographic origin of attacks, utilizing custom PowerShell scripts and third-party APIs for geolocation.

## Screenshots and Descriptions

### 1. World Map of Failed RDP Login Attempts
![World Map of Failed RDP Login Attempts](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20174223.png)
This screenshot shows the "HoneyPotLab" workbook in Microsoft Sentinel, where failed RDP login attempts are visualized on a world map. The data represents the volume of attacks from different regions, highlighting significant activity, such as a high number of login attempts from India.

### 2. Filtering Security Events in Microsoft Sentinel
![Filtering Security Events in Microsoft Sentinel](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20173449.png)
In this image, the Logs feature in Microsoft Sentinel is being used to filter and view specific log events. The query panel shows "SecurityEvent" logs, focused on filtering for event ID 4625, which corresponds to failed login attempts.

### 3. Setting Up a New Workbook in Microsoft Sentinel
![Setting Up a New Workbook in Microsoft Sentinel](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20163219.png)
This screenshot captures the setup of a new workbook in Microsoft Sentinel, where a Kusto Query Language (KQL) query is being written to extend and extract fields such as latitude, longitude, and username from raw data logs.

### 4. Viewing Custom Logs in Log Analytics
![Viewing Custom Logs in Log Analytics](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20161131.png)
This screenshot shows the Logs section of the "law-honeypot1" workspace, focusing on custom logs related to failed RDP login attempts.

### 5. Writing Sample Log Data Using PowerShell
![Writing Sample Log Data Using PowerShell](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20021629.png)
Here, PowerShell is used to execute a script that writes sample log data to a file. The script simulates failed RDP login attempts and generates log entries to train Azure Sentinel.

### 6. Adjusting Windows Defender Firewall Settings
![Adjusting Windows Defender Firewall Settings](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-23%20231336.png)
This image shows the settings of Windows Defender Firewall on the honeypot VM. The firewall settings are adjusted, likely to disable them, making the VM more accessible for logging potential attacks.

### 7. Reviewing Firewall Rules on the VM
![Reviewing Firewall Rules on the VM](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-23%20231235.png)
In this screenshot, the Windows Defender Firewall settings panel is displayed, where firewall rules for different network profiles are reviewed or adjusted.

### 8. Viewing Failed Login Event in Event Viewer
![Viewing Failed Login Event in Event Viewer](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-23%20230457.png)
Here, an Event Viewer log entry on the VM details a failed login attempt (Event ID 4625), including information like the username used, network address, and failure reason.

### 9. Monitoring Login Activity in Event Viewer
![Monitoring Login Activity in Event Viewer](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-23%20230242.png)
This screenshot shows the Event Viewer on the VM, listing multiple security events, including successful and failed login attempts.

### 10. Connecting to the Honeypot VM
![Connecting to the Honeypot VM](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-23%20223601.png)
This image shows the Remote Desktop Connection window for connecting to the honeypot VM, a step involved in setting up or accessing the VM for review, settings adjustment, or running scripts.

## Project Steps

1. **Setup Azure Environment:**
   - Configured a virtual machine in Azure, disabling external and internal firewalls to make the VM highly discoverable.

2. **Configure Log Analytics Workspace:**
   - Established a Log Analytics Workspace in Azure to collect and analyze logs from the VM.
   - Enabled data collection for security events, focusing on failed RDP attempts.

3. **Implement Microsoft Sentinel:**
   - Set up Microsoft Sentinel to integrate with the Log Analytics Workspace.
   - Developed custom logs and fields to parse geolocation data from attacker IP addresses.

4. **Data Collection and Visualization:**
   - Used a PowerShell script to extract IP addresses from the Windows Event Viewer logs, forwarding them to a third-party API for geolocation data.
   - Mapped the geolocation data in Sentinel to visualize the source of attacks globally.

5. **Analysis and Findings:**
   - The honeypot attracted numerous attacks from various countries, with significant activity from regions such as India, the United States, and China.
   - The project provided insights into the commonality of brute force attempts and the geographical distribution of cyber threats.

## Key Data

- **Attack Sources:**
  - Major attacking countries included India, United States, Netherlands, China, and Hong Kong.
  - Detailed data available in the attached log file for further analysis.

## Conclusion

The project successfully demonstrated the setup and use of Microsoft Sentinel for monitoring real-time cyber threats. The findings highlighted the importance of strong security practices and the global nature of cyber threats.

## Project Links

- [GitHub Repository](https://github.com/danartech/Honeynet-Azure-Project)
- [Failed_rdp_log](https://github.com/danartech/Honeynet-Azure-Project/blob/main/failedrdp.log)


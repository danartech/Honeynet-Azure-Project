# Microsoft Sentinel (SIEM) Map With Live Cyber Attack Using A Honeypot in Azure

## Project Overview

This project demonstrates the setup and use of Microsoft Sentinel to monitor and analyze real-time cyber attacks on a vulnerable honeypot virtual machine (VM) hosted in Microsoft Azure. The VM was intentionally exposed to attract attackers, and data from failed RDP (Remote Desktop Protocol) login attempts were captured and analyzed. The analysis included mapping the geographic origin of attacks, utilizing custom PowerShell scripts and third-party APIs for geolocation.

![Live Cyber Attack](https://github.com/danartech/Honeynet-Azure-Project/blob/main/Screenshot%202024-07-24%20174223.png)


## Steps

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
  - Detailed data available in the attached Excel files for further analysis.

## Conclusion

The project successfully demonstrated the setup and use of Microsoft Sentinel for monitoring real-time cyber threats. The findings highlighted the importance of strong security practices and the global nature of cyber threats.

## Project Links

- [GitHub Repository](https://github.com/danartech/Honeynet-Azure-Project)
- [Failed_rdp_log](https://github.com/danartech/Honeynet-Azure-Project/blob/main/failedrdp.log)


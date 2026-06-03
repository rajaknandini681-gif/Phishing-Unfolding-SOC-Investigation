
# Phishing Attack Investigation
### SOC Analyst | TryHackMe SOC Simulator

## What is this?
A real-time SOC investigation where I analysed a live phishing attack as it unfolded inside a corporate network.Using Splunk SIEM, I traced the attack from a suspicious email all the way to a full system compromise.

##  Investigation Summary
During this investigation I uncovered a full phishing attack chain targeting a corporate network. The attacker sent a fake invoice email to employee michael.ascot, who opened a malicious 
ZIP file containing a disguised shortcut file (.lnk). This triggered a series of malicious activities including Active Directory reconnaissance, credential harvesting, financial data access, and ultimately a reverse shell giving the attacker full remote control of the compromised machine.

Total Alerts Investigated: 8
True Positives Found: 6
False Positives Found: 2
Critical Escalations: 5

## Tools Used
**Splunk** — Log analysis & threat hunting
**VirusTotal** — Domain reputation check
**Sysmon** — Windows event monitoring

## Attack Chain I Uncovered

1. Phishing email delivered to michael.ascot
2. Malicious ZIP attachment executed
3. PowerView.ps1 launched for AD reconnaissance
4. Credentials harvested from the host
5. Financial network share accessed
6. Reverse shell established to ngrok C2
7. Attacker removed evidence to hinder investigation

## 📊 Alerts Summary
| Alert | Finding | Result |
|-------|---------|--------|
| 1000 | Phishing email | ✅ True Positive |
| 1001 | TrustedInstaller.exe | ❌ False Positive |
| 1002 | KEYROAMING credentials | ✅ True Positive |
| 1005 | Malicious ZIP attachment | ✅ True Positive |
| 1010 | WUDFHost.exe | ❌ False Positive |
| 1020 | PowerView.ps1 | ✅ True Positive |
| 1022 | Financial drive mapped | ✅ True Positive |
| 1024 | Evidence deleted | ✅ True Positive |

---

##  Key IOCs
**Attacker email:** john@hatmakereurope.xyz
**Malicious file:** ImportantInvoice-Febrary.zip
**Hacking tools:** PowerView.ps1, Powercat
**C2 Server:** 2.tcp.ngrok.io:19282
**Compromised user:** michael.ascot
**Compromised host:** win-3450

---

##  What I Learned:
- How to investigate real SOC alerts
- Using Splunk for threat hunting
- Identifying attack chains step by step
- Writing professional incident reports
- Difference between True and False Positives

## Author
**TryHackMe:** rajaknandini681-gif  
**Date:** June 2026 

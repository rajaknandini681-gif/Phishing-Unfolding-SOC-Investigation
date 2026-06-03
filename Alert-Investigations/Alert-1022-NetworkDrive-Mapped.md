# Alert 1022 - Network Drive Mapped to Local Drive

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1022 |
| Type | Execution |
| Severity | Medium |
| Date | Jun 2nd 2026 at 12:36 |
| Status | Closed |

## Process Details
| Field | Value |
|-------|-------|
| Host | win-3450 |
| Process | net.exe |
| PID | 5784 |
| Parent Process | powershell.exe |
| Parent PID | 3728 |
| Command | net.exe use Z: \\FILESRV-01\SSF-FinancialRecords |
| Working Directory | C:\Users\michael.ascot\downloads\ |

## Investigation Steps

### Step 1 - Alert Review
Network drive mapped to local drive
on compromised host win-3450.
Command mapped financial server
as drive Z:
Target: \\FILESRV-01\SSF-FinancialRecords
= FINANCIAL DATA SERVER!

### Step 2 - SIEM Analysis (Splunk)
Searched for michael.ascot in Splunk.
Result: 103 events found!
Found critical evidence:
- Powercat downloaded from GitHub!
- Connected to ngrok C2 server!
- Full reverse shell established!

### Step 3 - Impact Analysis
Attacker mapped financial server
to access company financial records.
Parent process powershell.exe PID 3728
= Same as PowerView execution!
Confirms same attacker session!
Financial data accessed!

## Verdict
✅ TRUE POSITIVE

## Reason
- Financial server mapped by attacker
- Using compromised michael.ascot account
- Parent process linked to attack chain
- 103 SIEM events on same host!
- Powercat reverse shell found!
- C2 server connection established!

## IOCs
- Host: win-3450
- User: SSF\michael.ascot
- Command: net.exe use Z: \\FILESRV-01\SSF-FinancialRecords
- Financial Server: FILESRV-01
- Share: SSF-FinancialRecords
- C2 Server: 2.tcp.ngrok.io:19282
- Tool: Powercat

## Recommended Actions
- Isolate win-3450 IMMEDIATELY!
- Block 2.tcp.ngrok.io on firewall
- Disable SSF\michael.ascot account
- Check FILESRV-01 access logs
- Verify what data was stolen
- Reset ALL network credentials
- Full forensic investigation!

## Escalation
✅ Yes - Escalated!
Financial data accessed!
Reverse shell established!
Full system compromise confirmed!
Immediate incident response needed!

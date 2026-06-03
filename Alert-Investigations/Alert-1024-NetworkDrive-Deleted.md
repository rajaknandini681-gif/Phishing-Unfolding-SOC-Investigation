# Alert 1024 - Network Drive Disconnected from Local Drive

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1024 |
| Type | Execution |
| Severity | Medium |
| Date | Jun 2nd 2026 at 12:37 |
| Status | Closed |

## Process Details
| Field | Value |
|-------|-------|
| Host | win-3450 |
| Process | net.exe |
| PID | 8004 |
| Parent Process | powershell.exe |
| Parent PID | 3728 |
| Command | net.exe use Z: /delete |
| Working Directory | C:\Users\michael.ascot\downloads\ |

## Investigation Steps

### Step 1 - Alert Review
Network drive Z: disconnected
from local drive on win-3450.
Command: net.exe use Z: /delete
This happened 1 minute after
Alert 1022 (drive was mapped!)
Attacker covering tracks!

### Step 2 - Connection to Alert 1022
Alert 1022: Drive Z: MAPPED
to \\FILESRV-01\SSF-FinancialRecords
        ↓
Alert 1024: Drive Z: DELETED
        ↓
Classic attacker behavior:
Connect → Steal data → Disconnect
to hide evidence!

### Step 3 - Impact Analysis
Same parent PID 3728 as Alert 1022!
Confirms same attacker session!
Drive deleted to remove evidence
of financial data access!
Attacker tried to hide tracks!

## Verdict
✅ TRUE POSITIVE
## Reason
- Drive deleted immediately after mapping
- Same parent process as Alert 1022
- Classic evidence removal technique
- Attacker covering tracks!
- Part of ongoing attack chain
- Financial data likely exfiltrated!

## IOCs
- Host: win-3450
- User: SSF\michael.ascot
- Command: net.exe use Z: /delete
- Parent PID: 3728 (powershell.exe)
- Working Dir: C:\Users\michael.ascot\downloads\
- Related Alert: 1022

## Recommended Actions
- Verify what data was accessed
  on FILESRV-01
- Check FILESRV-01 access logs
- Isolate win-3450 immediately
- Disable SSF\michael.ascot account
- Full forensic investigation!
- Check for data exfiltration!

## Escalation
✅ Yes - Escalated!
Financial data possibly stolen!
Evidence deletion detected!
Immediate forensic investigation
required!

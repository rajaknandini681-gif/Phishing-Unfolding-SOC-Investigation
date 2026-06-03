# Alert 1020 - PowerShell Script in Downloads Folder

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1020 |
| Type | Execution |
| Severity | Low |
| Date | Jun 2nd 2026 at 12:34 |
| Status | Closed |

## Process Details
| Field | Value |
|-------|-------|
| Host | win-3450 |
| Process | powershell.exe |
| PID | 9060 |
| Event Code | 11 (File Create) |
| File Path | C:\Users\michael.ascot\Downloads\PowerView.ps1 |
| Action | File Created |

## Investigation Steps

### Step 1 - Alert Review
PowerShell script created in
Downloads folder of michael.ascot.
PowerView.ps1 is a well known
hacking tool used for Active
Directory enumeration!

### Step 2 - SIEM Analysis (Splunk)
Searched for PowerView.ps1 in Splunk.
Result: 22 events found! 
Event Action: Execute a Remote Command!
        ↓
PowerView.ps1 was NOT just created
but actively EXECUTED!

### Step 3 - Impact Analysis
PowerView.ps1 executing with:
- LDAP queries running
- DNS hostname enumeration
- Test-Connection commands
- Active Directory mapping!
Attacker actively mapping
the entire network!

## Verdict
✅ TRUE POSITIVE

## Reason
- PowerView.ps1 is known hacking tool
- Found in user Downloads folder
- Actively EXECUTED 22 times!
- LDAP queries running
- Active Directory being enumerated
- Network reconnaissance in progress!

## IOCs
- Host: win-3450
- User: michael.ascot
- File: PowerView.ps1
- Path: C:\Users\michael.ascot\Downloads\
- PID: 9060
- SIEM Events: 22!

## Recommended Actions
- Isolate win-3450 IMMEDIATELY!
- Delete PowerView.ps1
- Disable michael.ascot account
- Check lateral movement
- Full forensic investigation!
- Review all AD queries made!

## Escalation
✅ Yes - Escalated!
Active reconnaissance in progress!
Attacker mapping entire network!
Immediate isolation required!

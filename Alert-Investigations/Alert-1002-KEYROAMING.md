# Alert 1002 - Suspicious Parent Child Relationship (KEYROAMING)

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1002 |
| Type | Process |
| Severity | Low |
| Date | Jun 2nd 2026 at 12:08 |
| Status | Closed |

## Process Details
| Field | Value |
|-------|-------|
| Host | win-3451 |
| Process | taskhostw.exe |
| PID 1 | 3585 |
| PID 2 | 3945 |
| Parent Process | svchost.exe |
| Parent PID 1 | 3653 |
| Parent PID 2 | 3652 |
| Command Line | taskhostw.exe KEYROAMING |
| Location | C:\Windows\system32\ |

## Investigation Steps

### Step 1 - Alert Review
Suspicious parent child relationship
detected on host win-3451.
Process taskhostw.exe running with
unusual KEYROAMING argument.

### Step 2 - SIEM Analysis (Splunk)
Searched for taskhostw.exe in Splunk.
Result: 2 events found!
Same command running twice within
7 minutes on same host!
Different PIDs each time = automated!

### Step 3 - Analysis
KEYROAMING argument is suspicious!
Normal taskhostw.exe doesn't use
KEYROAMING repeatedly.
Running twice in short period
suggests credential harvesting!

## Verdict
✅ TRUE POSITIVE

## Reason
- KEYROAMING command executed twice!
- Same host win-3451
- 7 minutes between executions
- Possible credential harvesting
- Automated/repeated behavior

## IOCs
- Host: win-3451
- Process: taskhostw.exe
- Command: taskhostw.exe KEYROAMING
- PIDs: 3585, 3945

## Recommended Actions
- Isolate host win-3451
- Investigate credential activity
- Check for lateral movement
- Reset credentials if compromised

## Escalation
✅ Yes - Escalated!
Possible credential harvesting detected!
Requires senior analyst investigation!

# Alert 1005 - Suspicious Attachment Found in Email (INITIAL ACCESS)

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1005 |
| Type | Phishing |
| Severity | Low |
| Date | Jun 2nd 2026 at 12:13 |
| Status | Closed |

## Email Details
| Field | Value |
|-------|-------|
| Sender | john@hatmakereurope.xyz |
| Recipient | michael.ascot@tryhatme.com |
| Subject | FINAL NOTICE: Overdue Payment - Account Suspension Imminent |
| Attachment | ImportantInvoice-Febrary.zip |
| Direction | Inbound |

## Investigation Steps

### Step 1 - Alert Review
Suspicious email with ZIP attachment
sent to michael.ascot.
Subject uses urgency and legal threats
= Classic social engineering!
Note: "Febrary" misspelled = 
attacker mistake!

### Step 2 - SIEM Analysis (Splunk)
Searched for john@hatmakereurope.xyz
Result: 1 event found.

Searched for ImportantInvoice-Febrary.zip
Result: Multiple events found!
ZIP was OPENED from Outlook!
Contains: invioce.pdf.lnk
= Fake PDF (malicious shortcut!)

### Step 3 - Impact Analysis
Opening .lnk file triggered:
- PowerView.ps1 installation
- KEYROAMING credential harvesting
- Financial server access
- Powercat reverse shell!

## Verdict
✅ TRUE POSITIVE

## Reason
- Malicious ZIP attachment opened!
- Contains fake PDF (.lnk file)
- Triggered full attack chain!
- Social engineering tactics:
  urgency, legal threats, fake invoice
- Misspelled filename = attacker!
- Misspelled domain = attacker!

## IOCs
- Sender: john@hatmakereurope.xyz
- Domain: hatmakereurope.xyz
- Attachment: ImportantInvoice-Febrary.zip
- Malicious file: invioce.pdf.lnk
- Opened from: Microsoft Outlook

## Recommended Actions
- Isolate win-3450 immediately!
- Disable michael.ascot account
- Block hatmakereurope.xyz domain
- Scan all endpoints for ZIP file
- Check if other users got same email
- Full forensic investigation!

## Escalation
✅ Yes - Escalated!
This is ROOT CAUSE of entire attack!
Full system compromise occurred!
Immediate incident response needed!

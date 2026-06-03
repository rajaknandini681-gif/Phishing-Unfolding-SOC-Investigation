# Alert 1000 - Suspicious Email from External Domain

## Alert Details
| Field | Value |
|-------|-------|
| Alert ID | 1000 |
| Type | Phishing |
| Severity | Low |
| Date | Jun 1st 2026 at 06:43 |
| Status | Closed |

## Email Details
| Field | Value |
|-------|-------|
| Sender | eileen@trendymillineryco.me |
| Recipient | support@tryhatme.com |
| Subject | Inheritance Alert: Unknown Billionaire Relative Left You Their Hat Fortunes |
| Attachment | None |
| Direction | Inbound |

## Investigation Steps

### Step 1 - Alert Review
Received alert for suspicious email
from external domain trendymillineryco.me
Email contained classic 419 scam content
requesting banking details immediately.

### Step 2 - SIEM Analysis (Splunk)
Searched for sender email in Splunk.
Result: 1 event found.
No evidence of user clicking any link.
Email was caught before interaction!

### Step 3 - Domain Check (VirusTotal)
Checked trendymillineryco.me on VirusTotal.
Result: 0/91 vendors flagged it.
However domain is newly created
specifically to avoid detection!
Community results showed it linked
to known 419 phishing campaigns!

## Verdict
✅ TRUE POSITIVE

## Reason
- Classic 419 scam email
- Requesting banking details immediately
- Suspicious newly created domain
- Unknown external sender
- Social engineering tactics used

## IOCs
- Sender: eileen@trendymillineryco.me
- Domain: trendymillineryco.me

## Recommended Actions
- Block sender domain
- Delete email from mailbox
- Add domain to blocklist
- Notify recipient team

## Escalation
❌ No escalation required
Email caught before any user interaction!

# 🎣 Phishing Analysis Challenges

**Skills:** Email header analysis · IOC extraction · OSINT · Threat intelligence · URL analysis · Social engineering recognition

-----

A structured series of phishing email investigations completed as part of SOC analyst training. Each challenge involves a real `.eml` file, full header inspection, sender verification, URL extraction, and a written verdict with recommended actions.

Every report is documented the way it would be in a real SOC environment — findings numbered, evidence screenshotted, tools logged, and conclusions justified.

-----

## Challenges

### Challenge 1 — Microsoft Outlook Impersonation

**Status:** ✅ Complete  
**File:** `challenge1.eml`  
**Victim:** Dana Derringer, Mighty Solutions Inc.  
**Verdict:** Confirmed Phishing

A spoofed Microsoft Outlook email designed to steal credentials via a fake account suspension warning. The attacker used a compromised Egyptian university account routed through Microsoft 365 infrastructure — causing SPF to pass while the actual sender had no connection to Microsoft whatsoever.

Key findings:

- Display name spoofed as *Outlook Support Team*
- Actual sender: `social201511138@social.helwan.edu.eg`
- SPF passed — not because the email was legitimate, but because the attacker’s domain routes through Microsoft 365
- Email body encoded in base64 to evade plain-text security scanning
- Malicious URL flagged as Phishing by Fortinet and 6 other vendors on VirusTotal (7/91)
- Four social engineering levers in a single email: fear, urgency, authority, scarcity

📄 [View Full Report (PDF)](./Challenge_01/Phishing_Analysis_Report_Myke_.pdf)

-----

### Challenge 2 — Coming Soon

**Status:** 🔄 In progress

-----

## Tools Used

|Tool        |Purpose                                               |
|------------|------------------------------------------------------|
|Thunderbird |Rendered the email visually as the victim would see it|
|Sublime Text|Inspected raw `.eml` header and encoding              |
|nslookup    |Reverse DNS lookup and SPF TXT record query           |
|whois       |Identified IP ownership and registering organisation  |
|eioc.py     |Extracted and defanged IOCs from the raw email file   |
|VirusTotal  |Scanned extracted URL across 91 security vendors      |

-----

## Structure

```
phishing-analysis-challenges/
├── Challenge_01/
│   ├── Phishing_Analysis_Report_Myke_.pdf
│   └── screenshots/
├── Challenge_02/
│   └── (in progress)
└── README.md
```

-----

*Part of my cybersecurity portfolio — [github.com/bigmyk-e](https://github.com/bigmyk-e)*

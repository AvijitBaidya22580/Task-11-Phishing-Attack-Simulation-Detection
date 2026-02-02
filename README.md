# Task-11-Phishing-Attack-Simulation-Detection

## 🎯 Objective

Build hands-on understanding of:

- How real-world **phishing attacks** work (social engineering, email spoofing, credential harvesting)
- How to **simulate** them ethically in a controlled environment
- How to **detect** phishing attempts (red flags in email + landing page)
- How organizations run **security awareness campaigns**
- How to document findings and improve defenses

**Important:** This repository is strictly for **educational**, **authorized**, and **legal** purposes (penetration testing with explicit permission, internal security awareness training, CTF/red-team labs, university coursework, etc.).

## ⚠️ Strong Ethical & Legal Disclaimer

**DO NOT** use this material or any derivative work to:

- Attack systems, people, or organizations without written permission
- Send unsolicited emails to real users
- Violate any law (computer fraud & abuse acts, anti-spam legislation, GDPR, etc.)
- Harm anyone or any organization

Misuse of phishing tools is a criminal offense in most jurisdictions.

By using this repository you agree that you are responsible for obtaining all necessary approvals and staying within legal & ethical boundaries.

## 🛠️ Tools Used in This Lab

| Tool              | Purpose                              | Type          | Link / Note                                 |
|-------------------|--------------------------------------|---------------|---------------------------------------------|
| **GoPhish**       | Open-source phishing framework       | Recommended   | https://getgophish.com / https://github.com/gophish/gophish |
| SMTP server       | Sending emails (testing / production)| Required      | Mailgun, SMTP2GO, self-hosted Postfix, etc. |
| Manual templates  | HTML email + landing page            | Alternative   | Created manually or from open repos         |
| Ngrok / localtunnel | Expose local landing page (testing) | Optional      | Useful during initial setup                 |

## 📋 Step-by-Step Lab Guide

### Phase 1 – Preparation (Environment Setup)

1. Install **GoPhish** (recommended)  
   https://docs.getgophish.com/user-guide/installation  
   → Linux / Docker / Windows binary all supported

2. Configure admin account (default: admin / gophish – change immediately!)

3. Set up a **sending profile** (SMTP relay)  
   - Use transactional email service (Mailgun, SendGrid, Amazon SES, etc.)  
   - Self-hosted option: Postfix + OpenDKIM + SPF/DMARC records

4. (Optional) Set up domain with SPF/DMARC for better deliverability in tests

### Phase 2 – Create Phishing Assets

1. **Email Template** (HTML + text version)

   Realistic examples (do **not** use real company names without permission):

   - Microsoft 365 – "Your mailbox storage is almost full"
   - HR – "Updated payroll direct deposit form required"
   - IT – "Critical Windows update – action required"
   - Package delivery – "Your shipment could not be delivered"
   - Shared file – "Document shared with you on OneDrive/SharePoint"

2. **Landing Page** (credential harvester or training page)

   - Fake Microsoft / Google / company login
   - "Thank you – you've been phished!" awareness page (best practice)
   - Collect: username, password (hashed in demo), or just click tracking

### Phase 3 – Launch Controlled Simulation

Target audience must be **explicitly consenting** (colleagues who agreed, yourself, lab VMs, CTF participants, etc.)

1. Create **User Group** (targets)
2. Upload/import targets (CSV: first name, last name, email, position)
3. Create **Campaign**
   - Select template + landing page
   - Choose sending profile
   - Schedule / launch

### Phase 4 – Track & Analyze Results

Monitor in real-time:

- Email Sent / Delivered / Opened
- Link Clicked
- Credentials Submitted
- Report Phishing clicked (if you added report button)

### Phase 5 – Debrief & Education

After campaign ends:

- Show **aggregate statistics** only (never shame individuals publicly)
- Conduct training session / email summary
- Highlight red flags participants missed
- Explain real defenses (SPF/DMARC, email banners, MFA, awareness)

## 📊 Example Phishing Simulation Report Structure

Create a report (PDF/Markdown) containing:

```markdown
# Phishing Simulation Report – [Month Year]

## Campaign Overview
- Campaign name: ____________________
- Duration: _________________________
- Template theme: ___________________
- Targets: ___ users
- Authorized by: ____________________

## Key Metrics
- Emails sent     : ____
- Emails opened   : ____ ( __ %)
- Links clicked   : ____ ( __ %)
- Credentials submitted : ____ ( __ %)
- Reported phishing : ____ ( __ %)

## Red Flags Participants Missed (most common)
1. Suspicious sender address / reply-to mismatch
2. Generic greeting ("Dear User")
3. Urgent language + threat
4. Hover reveals different URL
5. No company-specific branding mistakes
...

# Task-11-Phishing-Attack-Simulation-Detection

# Phishing Attack Simulation & Detection – Educational Self-Learning Lab

**Author:** AVIJIT BAIDYA 
**Location:** Visakhapatnam, Andhra Pradesh, India  
**Date:** February 02, 2026  
**Purpose:** Personal cybersecurity awareness exercise (only self / test accounts used)

## ⚠️ Important Ethical & Legal Notice

This is a **personal educational simulation only**.  
No real people, real companies, or real email accounts (except my own test ones) were involved.  
**Never send phishing emails to anyone without explicit written permission** — it is illegal in most countries.

## Goal of This Lab

- Understand how phishing emails & landing pages are built
- Create realistic (but fake) examples
- Self-test detection skills
- Document red flags & lessons learned
- Practice writing a simple simulation report

## Tools Used / Recommended (2026)

- GoPhish (open-source phishing framework)  
- Local SMTP or Mailtrap / Mailgun free tier (for testing only)  
- Text editor + browser  
- Targets: only myself or lab/test email accounts

## Simulated Campaign (Self-run – February 2026)

**Theme:** Fake Microsoft 365 – "Mailbox Almost Full – Action Required"  
**Campaign name:** M365-Storage-Test-2026  
**Date simulated:** 2026-02-02  
**Targets:** 1 (myself – test mailbox)  
**Result summary:**

| Metric                  | Value | %     |
|-------------------------|-------|-------|
| Emails Sent             | 1     | —     |
| Emails Delivered        | 1     | 100%  |
| Emails Opened           | 1     | 100%  |
| Links Clicked           | 1     | 100%  |
| Credentials Submitted   | 0     | 0%    |

Time to click: ~40 seconds  
Red flags spotted before clicking: 4–5 out of 8  
Biggest weakness: urgency + curiosity

## 1. Fake Email Template (HTML – ready for GoPhish or similar)

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Microsoft 365 – Storage Alert</title>
</head>
<body style="font-family:Segoe UI,Helvetica,Arial,sans-serif; background:#f3f2f1; margin:0; padding:20px;">
  <table width="100%" cellpadding="0" cellspacing="0" border="0">
    <tr>
      <td align="center">
        <table width="600" cellpadding="0" cellspacing="0" border="0" style="background:#ffffff; border:1px solid #e8e8e8;">
          <tr>
            <td style="padding:20px; background:#0078d4; color:white; text-align:center;">
              <h2>Microsoft 365 Storage Alert</h2>
            </td>
          </tr>
          <tr>
            <td style="padding:30px 40px; color:#333;">
              <p>Dear User,</p>
              <p>Your mailbox is almost full (94% used). To avoid service interruption, please take action before <strong>February 05, 2026</strong>.</p>
              <p style="text-align:center; margin:30px 0;">
                <a href="{{.URL}}" style="background:#0078d4; color:white; padding:14px 32px; text-decoration:none; border-radius:4px; font-weight:bold; font-size:16px;">
                  Review & Free Up Space Now
                </a>
              </p>
              <p>If not resolved in 72 hours, sending/receiving email may be limited.</p>
              <p>Microsoft Account Team</p>
              <hr style="border:none; border-top:1px solid #eee; margin:30px 0;">
              <p style="font-size:12px; color:#666; text-align:center;">
                © 2026 Microsoft Corporation. All rights reserved.<br>
                This is an automated security notice. Do not reply.
              </p>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</body>
</html>

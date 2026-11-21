# Web VAPT Case Studies and Lab Practice

Anonymized writeups from a VAPT internship, plus my practice work in vulnerable labs.
All client, application, and user details have been removed. Every issue described has been fixed.
Shared with permission, for education only.

## Part 1: Real-World Findings (Anonymized)

| # | Finding | Severity | Category |
|---|---------|----------|----------|
| 1 | [Role injection in an AI chat assistant](cases/01-ai-chatbot-role-injection.md) | High (8.1) | LLM01 / A01:2021 |
| 2 | [IDOR in application records](cases/02-idor-application-records.md) | High (8.1) | A01:2021 |
| 3 | [Authorization flaw leading to user enumeration](cases/03-user-enumeration-authorization.md) | Medium (6.5) | A01:2021 |
| 4 | [OTP brute force, no rate limiting](cases/04-otp-brute-force.md) | High (9.1) | A07:2021 |
| 5 | [SQL injection in input fields](cases/05-sql-injection.md) | See case file | A03:2021 |
| 6 | [Weak file upload validation](cases/06-file-upload-validation.md) | Medium (4.3) | A04:2021 |
| 7 | [Security misconfigurations](cases/07-security-misconfigurations.md) | Low to Medium | A05:2021 |

Each case uses the same format: Observation, Impact, Recommendation.

## Part 2: Lab Practice

See [labs/README.md](labs/README.md). Labs covered: DVWA, XVWA, bWAPP.

Environment: Kali Linux, isolated VMs, host-only network.
Tools: Burp Suite, SQLmap, Nmap, Nikto, Wireshark.

## Repository layout

- cases/ : one markdown file per finding
- labs/ : notes per lab (own screenshots only)
- checklists/ : remediation checklist

## Approach

Recon, manual testing, tool-assisted checks, confirmation, CVSS v3.1 scoring, OWASP and CWE mapping, then a developer-friendly fix.

## Disclaimer

No client, target, or real data is identified here. Do not test systems you do not own or have written permission to test.

## Contact

LinkedIn: https://linkedin.com/in/ethicalknight
GitHub: https://github.com/ethicalknight

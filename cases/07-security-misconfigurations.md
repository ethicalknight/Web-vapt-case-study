# Case 07: Security Misconfigurations

Status: Fixed | Severity: Low to Medium
OWASP: A05:2021 Security Misconfiguration | CWE: 693, 614, 200

## 7a. Missing Security Headers (CVSS 5.4, AV:N/AC:L/PR:N/UI:R/S:U/C:L/I:L/A:N)
Observation: The application did not send Strict-Transport-Security, Content-Security-Policy, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, or Permissions-Policy.
Impact: Greater exposure to downgrade attacks, XSS, clickjacking, MIME sniffing, and excessive data sharing with third parties.
Recommendation: Send all six on every response, with HSTS enforcing HTTPS, a restrictive CSP, nosniff, SAMEORIGIN framing, a strict Referrer-Policy, and unused browser features disabled.

## 7b. Missing Secure Flag on Authentication Cookie (CVSS 3.1, AV:N/AC:H/PR:N/UI:R/S:U/C:L/I:N/A:N)
Observation: The authentication cookie had HttpOnly and SameSite set but not Secure.
Impact: If the site is reached over plain HTTP, the cookie could be sent without transport protection.
Recommendation: Set the Secure attribute on all authentication and session cookies.

## 7c. Server Version Disclosure (CVSS 5.3, AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:N/A:N)
Observation: The origin server revealed its software and exact version in response headers and default error pages.
Impact: Attackers can map published vulnerabilities to the exact build and shorten reconnaissance.
Recommendation: Turn off version disclosure (for Nginx, server_tokens off), strip identifying headers at a proxy or WAF, and keep the server patched.

## Reference
https://owasp.org/www-project-secure-headers/

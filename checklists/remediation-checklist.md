# Remediation Checklist

## Access control
- [ ] Ownership/authorization check on every read and write, server-side
- [ ] Unpredictable identifiers (in addition to checks, never instead)
- [ ] Personal identifiers (phone, email) never used as lookup keys

## AI features
- [ ] System/assistant messages built only on the server; clients limited to the user role
- [ ] Per-user authorization on every data action the assistant performs
- [ ] Assistant tools limited and sandboxed

## Authentication
- [ ] Rate limiting and lockout on OTP and login attempts
- [ ] Short-lived, single-use codes
- [ ] CAPTCHA after repeated failures
- [ ] Secure, HttpOnly, SameSite on authentication cookies

## Injection and uploads
- [ ] Parameterized queries; least-privilege database account; no verbose DB errors
- [ ] Uploads validated by content, allow-listed types, server-generated names, stored non-executable

## Headers and configuration
- [ ] HSTS, CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy on every response
- [ ] Server version banners disabled

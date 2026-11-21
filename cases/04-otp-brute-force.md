# Case 04: OTP Brute Force Due to Missing Rate Limiting

Status: Fixed | Severity: High | CVSS 9.1 (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:N), generalized estimate
OWASP: A07:2021 Identification and Authentication Failures | CWE: 307

## Observation
The OTP verification endpoint had no rate limiting, lockout, or CAPTCHA. Testing every possible code produced no blocking or throttling, and the correct code was accepted.

## Impact
With simple automation, an attacker could guess a valid OTP in minutes and defeat the second factor, which can lead to account takeover.

## Recommendation
- Rate-limit verification attempts with progressively longer delays.
- Lock or expire the OTP after a small number of failures.
- Add a CAPTCHA after repeated failures, and keep codes short-lived and single-use.

## Reference
https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/

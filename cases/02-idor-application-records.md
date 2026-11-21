# Case 02: IDOR in Application Records

Status: Fixed | Severity: High | CVSS 8.1 (AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:N)
OWASP: A01:2021 Broken Access Control | CWE: 639

## Observation
Application records were identified by a predictable number in the request, and the server did not check that the record belonged to the logged-in user. Changing the number gave an authenticated user access to another client's application, and the related edit and submit routes behaved the same way.

## Impact
An authenticated attacker could read and modify other clients' personal details, contact information, and application data. This is a serious confidentiality and data-integrity problem.

## Recommendation
- Verify ownership on the server for every view, edit, save, submit, and document route.
- Replace sequential identifiers with unpredictable ones, as an extra layer and never as a substitute for the check.
- Apply the same authorization logic across all related routes.

## Reference
https://owasp.org/Top10/A01_2021-Broken_Access_Control/

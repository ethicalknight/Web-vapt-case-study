# Case 03: Improper Authorization Leading to User Enumeration

Status: Fixed | Severity: Medium | CVSS 6.5 (AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:N/A:N)
OWASP: A01:2021 Broken Access Control | CWE: 285, 200

## Observation
An authenticated endpoint accepted phone and email values as parameters and returned the matching application record, including name, contact details, and application number. Changing the values returned records belonging to other people, so authorization was not enforced against the requested data.

## Impact
An authenticated user could confirm who is registered and collect applicants' contact details. This causes privacy violations and gives attackers material for phishing or follow-up attacks.

## Recommendation
- Authorize each lookup against the requesting user or role.
- Do not treat phone or email values as a form of access control.
- Avoid fetching records by personal identifiers.

## Reference
https://owasp.org/Top10/A01_2021-Broken_Access_Control/

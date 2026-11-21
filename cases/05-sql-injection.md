# Case 05: SQL Injection in Input Fields

Status: Fixed | Severity: [fill in] | CVSS [fill in vector and score]
OWASP: A03:2021 Injection | CWE: 89

## Observation
Several tested applications passed user input into database queries without safe separation of code and data. I confirmed the issue by observing how the application responded to modified input, and I stopped at confirmation. No real data was extracted.
[Add: kind of input (search, login, filter), and technique (error-based, boolean, time-based). Keep it generic. No payloads, no site details.]

## Impact
[Write the impact you actually confirmed, in one honest sentence.]

## Recommendation
- Use parameterized queries or prepared statements.
- Validate input on the server with allow-lists.
- Run the application's database account with least privilege.
- Hide database error details from users.

## Takeaway
SQL injection is decades old and still appears because a single shortcut in one query is enough.

## Reference
https://owasp.org/Top10/A03_2021-Injection/

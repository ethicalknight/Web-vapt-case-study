# Case 06: Improper File Upload Validation

Status: Fixed | Severity: Medium | CVSS 4.3 (AV:N/AC:L/PR:L/UI:N/S:U/C:N/I:L/A:N)
OWASP: A04:2021 Insecure Design | CWE: 434

## Observation
The document upload accepted a file with a double extension, and validation appeared to rely on the extension or client-supplied MIME type rather than file content. The server saved the file. The test file was not executed or parsed, so no code execution was seen.

## Impact
Weak content checks mean unexpected file types can be stored. This could be chained with other issues, for example to deliver stored XSS or XXE payloads.

## Recommendation
- Validate files by content (magic bytes), not by extension or client MIME type.
- Allow only the file types the feature needs, and reject double extensions.
- Store uploads under server-generated names in a location that cannot be executed or parsed.

## Reference
https://owasp.org/www-community/vulnerabilities/Unrestricted_File_Upload

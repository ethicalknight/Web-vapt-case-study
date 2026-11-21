# Case 01: Role Injection in an AI Chat Assistant

Status: Fixed | Severity: High | CVSS 8.1 (AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:N)
OWASP: LLM01 Prompt Injection, A01:2021 Broken Access Control | CWE: 285, 1427

## Observation
The chat request carried the full message history, including a role label for each message, and the server accepted whatever roles the client sent. By adding a message labeled as the assistant, a normal user could override the intended conversation context. The assistant then returned other users' profile details and changed another user's details on request.

## Impact
Cross-user data disclosure and unauthorized modification. Tenant isolation was broken, and the language model was effectively acting as the access control.

## Recommendation
- Build system and assistant messages only on the server, and accept only the user role from clients.
- Enforce per-user authorization on every data read and write the assistant performs.
- Limit the assistant's tools to what it needs, and sandbox any file or outbound-request capability.

## Takeaway
If an AI feature can touch user data, every action it takes needs the same permission check as any other API call.

## Reference
https://genai.owasp.org/llm-top-10/

---
name: security
description: Implement or review code that handles untrusted input, identity, permissions, secrets, persistence, or external commands. Use to identify trust boundaries and prevent exploitable behavior.
---

# Security

Start with the assets, attacker-controlled inputs, privileges, and reachable boundaries relevant to this change. Keep review proportional to exposure.

- Treat network, file, environment, database, and user input as untrusted. Parse and validate once at the boundary into a type that excludes invalid states.
- Separate authentication (who is acting) from authorization (what that actor may do). Enforce authorization server-side at the resource/action boundary; default to least privilege.
- Use parameterized database queries, safe process APIs, and context-aware output encoding. Never build commands or queries by concatenating untrusted values.
- Avoid unsafe deserialization and hand-rolled cryptography. Use maintained libraries with appropriate defaults.
- Keep secrets out of source, logs, test fixtures, command history, and error messages. Do not echo credentials while diagnosing failures.
- Check path traversal, symlink behavior, resource exhaustion, and race windows when files or unbounded inputs are involved.
- Minimize permissions and sensitive data retained. Consider deletion, retention, and backup behavior where applicable.
- Add tests for denied access and malicious boundary inputs, not only valid flows. Confirm that failure does not leak data or leave unauthorized state changes.
- Review new dependencies and permissions for the additional attack surface they introduce.

State a concrete threat and its mitigation for security-sensitive changes. Do not claim a security property based only on a type annotation or a passing happy-path test.
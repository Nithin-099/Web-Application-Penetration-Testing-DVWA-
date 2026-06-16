# Secure Coding Practices

## Input Validation

Validate all user-supplied data using allow-list approaches.

Avoid trusting:
- Forms
- URL parameters
- Cookies
- Headers

---

## Output Encoding

Encode output according to context:
- HTML Encoding
- JavaScript Encoding
- URL Encoding

This helps prevent XSS attacks.

---

## Secure Authentication

- Enforce strong password policies.
- Implement MFA.
- Store passwords using secure hashing algorithms.
- Protect against brute-force attacks.

---

## Secure Database Access

- Use prepared statements.
- Apply least privilege database accounts.
- Avoid exposing database errors.

---

## Session Security

- Use secure session identifiers.
- Regenerate sessions after login.
- Implement inactivity timeouts.
- Use Secure and HttpOnly cookies.

---

## Secure File Handling

- Validate uploaded files.
- Restrict dangerous extensions.
- Store files securely.

---

## Error Handling

Avoid exposing:
- Stack traces
- Database details
- Internal application paths

Display generic error messages to users.

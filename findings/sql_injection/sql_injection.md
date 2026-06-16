# SQL Injection

## Severity
Low,Medium,High

## Description

SQL Injection occurs when an application incorporates untrusted user input directly into SQL queries without proper validation or parameterization.

The DVWA SQL Injection module demonstrates how attackers can manipulate database queries by injecting malicious SQL statements into user-supplied input fields.

## Affected Component

DVWA SQL Injection Module

## Attack Scenario

An attacker submits specially crafted SQL syntax through an input field.

The application executes the modified query, allowing the attacker to retrieve unauthorized information from the database.
Attacked on three level severity,where using different type sql injection payloads.

## Impact

- Authentication bypass
- Database enumeration
- Unauthorized access to sensitive data
- Information disclosure

## Evidence

Screenshots :-

 screenshots/sql_injection_low_severity_payload.
 
 screenshots/sql_injection_medium_severity_payload.
 
 screenshots/sql_injection_burp_intercept.
 
 screenshots/sql_injectionn_critical_severity_payload.
 
 screenshots/sql_injection_password_cracking.

## Remediation

- Use parameterized queries
- Apply input validation
- Implement ORM frameworks
- Enforce least privilege database accounts

## References

OWASP SQL Injection Prevention Cheat Sheet

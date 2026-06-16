# Brute Force Attack

## Severity
High

## Description

A Brute Force Attack is a password guessing technique in which an attacker repeatedly attempts multiple username and password combinations until valid credentials are discovered.

The DVWA Brute Force module demonstrates how weak authentication mechanisms and the absence of account lockout controls can allow attackers to gain unauthorized access to user accounts.

## Affected Component

DVWA Brute Force Authentication Module

## Attack Scenario

The login page accepts unlimited authentication attempts without implementing rate limiting or account lockout mechanisms.

An attacker can automate login attempts using tools such as Burp Suite Intruder to test multiple password combinations against a target account.

## Tools Used

- Burp Suite
- Burp Intruder
- Web Browser

## Methodology

### Step 1: Intercept Login Request

The login request was captured using Burp Suite Proxy.

### Step 2: Send Request to Intruder

The intercepted request was forwarded to Burp Intruder for automated testing.

### Step 3: Configure Payload Positions

The password parameter was selected as the attack position.

### Step 4: Load Password List

A custom password wordlist was configured as the payload source.

### Step 5: Launch Attack

Burp Suite Intruder automatically submitted multiple password attempts.

### Step 6: Analyze Responses

Response lengths and status codes were analyzed to identify successful authentication attempts.

## Impact

- Unauthorized account access
- Credential compromise
- Privilege escalation
- Data exposure
- Account takeover

## Evidence

### Screenshot 1
Login page before testing

File:
screenshots/bruteforce_login_page.png

### Screenshot 2
Burp Suite request interception

File:
screenshots/bruteforce_proxy_intercept.png

### Screenshot 3
Intruder payload configuration

File:
screenshots/bruteforce_payload(1).png

### Screenshot 4
Intruder payload configuration

File:
screenshots/bruteforce_payload(2).png

### Screenshot 5
Password cracking running

File:
screenshots/bruteforce_attack_running.png

### Screenshot 6
Successful password discovery

File:
screenshots/bruteforce_succesful_password.png

### Screenshot 7
Login Page after giving correct credentials

File:
screenshots/bruteforce_succesful_login.png


## Risk Assessment

Likelihood: High

Impact: High

Overall Risk: High

## Remediation

### Account Lockout

Temporarily lock accounts after multiple failed login attempts.

### Rate Limiting

Limit the number of login requests allowed within a specific timeframe.

### Multi-Factor Authentication

Require an additional authentication factor beyond passwords.

### Strong Password Policy

Enforce password complexity and length requirements.

### CAPTCHA Protection

Implement CAPTCHA after repeated login failures.

### Security Monitoring

Monitor authentication logs for suspicious login activity.

## References

OWASP Authentication Cheat Sheet

OWASP Brute Force Attack Protection

Burp Suite Documentation

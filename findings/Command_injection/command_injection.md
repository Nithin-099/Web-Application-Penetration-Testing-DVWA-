# Command Injection

## Severity
Critical

## Description

Command Injection is a web application vulnerability that allows attackers to execute operating system commands through vulnerable application inputs. It occurs when user-supplied input is incorporated into system commands without proper validation or sanitization.

The DVWA Command Injection module demonstrates how attackers can manipulate application functionality to execute arbitrary commands on the underlying server.

In this assessment, Command Injection was successfully validated on the **High Security Level** implementation of DVWA.

---

## Causes of Command Injection

Command Injection vulnerabilities commonly occur due to:

- Failure to validate user input.
- Improper input sanitization.
- Reliance on blacklist filtering.
- Direct execution of shell commands.
- Unsafe use of system functions.
- Insecure coding practices.

---

# High Security Command Injection

## Severity
Critical

## Description

The High Security implementation of DVWA introduces stronger input validation mechanisms to restrict commonly used command separators.

However, improper filtering techniques may still allow attackers to bypass these controls and execute operating system commands.

## Attack Scenario

An attacker submits specially crafted input through the vulnerable functionality.

Despite enhanced validation, bypass techniques can be used to trigger unintended command execution on the server.

Tried Different types of payloads, but still did not get any response. So I went through Source code,where I found these information

 $substitutions = array(
        '||' => '',
      
        '&'  => '',
        
        ';'  => '',
        
        '| ' => '',
        
        '-'  => '',
        
        '$'  => '',
        
        '('  => '',
        
        ')'  => '',
        
        '`'  => '',

Here we can see at  '| ' => '', it has space after '| ', Instead of giving space I executed without space after it which gives the exepcted results for the payloads.

## Impact

- Remote command execution
- System information disclosure
- Unauthorized interaction with the operating system
- Potential privilege escalation
- Complete server compromise

## Evidence

Screenshots :-

screenshots/high_command_payload(1)

screenshots/high_command_payload(2)

screenshots/high_command_newfile_execution

screenshots/high_command_payload(3)

screenshots/high_command_payload(3)_info

## Risk Rating

Likelihood: Medium (2)

Impact: High (3)

Score: 6/9 – High Risk

---

## Security Recommendations

### Input Validation

Implement strict allow-list validation for all user input.

### Avoid System Calls

Avoid directly invoking operating system commands from user-controlled data.

### Principle of Least Privilege

Execute applications with minimal permissions.

### Secure Coding Practices

Use secure APIs instead of shell execution functions.

### Regular Security Testing

Conduct periodic penetration testing and secure code reviews.

---

## Conclusion

The DVWA High Security assessment demonstrated that stronger validation mechanisms can reduce exploitability but may still be bypassed if implemented incorrectly. Command Injection remains one of the most critical web application vulnerabilities due to its potential impact on confidentiality, integrity, and availability.

Organizations should prioritize secure coding practices, robust input validation, and continuous security assessments to mitigate command execution risks.

---

## References

- OWASP Command Injection
- OWASP Web Security Testing Guide
- OWASP Top 10

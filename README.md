## DVWA-Web-Penetration-Testing-Lab
Overview

This project demonstrates a full web application penetration testing assessment performed on DVWA (Damn Vulnerable Web Application) in a controlled lab environment. The objective of this project is to simulate real-world web application attacks, identify vulnerabilities, analyze security weaknesses, and document mitigation strategies based on industry-standard penetration testing methodologies.

The assessment focuses on common web vulnerabilities from the OWASP Top 10 and includes practical exploitation, traffic analysis, enumeration, and security reporting using professional cybersecurity tools.

# Objectives
Perform reconnaissance and enumeration on the target application

Identify vulnerable services and exposed endpoints

Conduct web application vulnerability assessment

Exploit common web vulnerabilities safely in a lab environment

Analyze HTTP requests and responses

Document findings and remediation recommendations

Gain hands-on penetration testing experience

# Target Application
● DVWA (Damn Vulnerable Web Application)

# Lab Environment

Component	Details

Attacker Machine	- Kali Linux

Target Application	- DVWA

Web Server	- Apache

Database	- MySQL

Testing Environment	- VirtualBox 


# Tools Used

Nmap	- Port scanning and service enumeration

Burp Suite	- Web interception and vulnerability testings

SQLMap	- Automated SQL Injection testing

Hydra	Brute force testing

Linux Terminal -	Command execution and enumeration

# Methodology
1. Reconnaissance

Host discovery

Open port identification

Service enumeration

HTTP fingerprinting

2. Web Enumeration

Directory brute forcing

Hidden endpoint discovery

HTTP header analysis

Parameter identification

3. Vulnerability Assessment

SQL Injection testing

Cross Site Scripting (XSS)

Command Injection

File Upload vulnerabilities

Broken Authentication

CSRF testing

Security Misconfiguration

4. Exploitation

Authentication bypass

Database enumeration

Payload execution

Session analysis

5. Traffic Analysis

Packet capture using Wireshark

HTTP request inspection

POST request analysis

Credential observation

6. Reporting & Remediation

# Risk analysis

Impact assessment

Security recommendations

Mitigation strategies

Nmap Reconnaissance Commands


# Example Vulnerabilities Tested
->SQL Injection	Easy,Medium,Critical

->Cross Site Scripting (XSS)	
 
  ●Reflected XSS-Low,Medium,High
  
  ●Stored XSS-Low,Medium,High

->Command Injection	Critical

->Insecure File Upload	Critical

->Brute Force Authentication	High

->CSRF	Medium


# Key Findings

1.Unsanitized user input allowed SQL Injection attacks

2.Reflected XSS vulnerabilities enabled JavaScript execution

3.Weak authentication controls allowed brute-force attacks

4.Sensitive traffic transmitted over insecure HTTP

5.File upload functionality lacked validation controls

6.Command Injection vulnerabilities enabled system command execution


## Skills Demonstrated

->Web Application Penetration Testing


->Vulnerability Assessment & Penetration Testing (VAPT)


->Network Traffic Analysis

->HTTP Request Manipulation

->Web Enumeration

->Security Reporting

->OWASP Testing Methodology

->Exploitation Techniques

->Risk Assessment

## Remediation Planning

->Security Recommendations

->Implement secure input validation

->Use parameterized SQL queries

->Enable HTTPS using SSL/TLS

->Restrict dangerous file uploads

->Apply secure authentication mechanisms

->Configure Content Security Policy (CSP)

->Harden web server configurations

->Conduct regular security assessments


## Disclaimer

This project was conducted in a controlled and authorized lab environment for educational purposes and ethical cybersecurity research only. No unauthorized systems or public targets were tested.

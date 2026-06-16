# Cross Site Scripting (XSS)

## Severity
Low, Medium, High

## Description

Cross Site Scripting (XSS) is a web application vulnerability that allows attackers to inject malicious client-side scripts into web pages viewed by other users. These scripts execute within the victim's browser under the trust relationship established with the vulnerable application.

XSS vulnerabilities can lead to session hijacking, credential theft, website defacement, redirection to malicious websites, and execution of unauthorized actions on behalf of legitimate users.

In this assessment, three different types of XSS vulnerabilities were identified and validated within DVWA:
- Reflected XSS
- Stored XSS
- DOM-Based XSS

---

## Causes of XSS

Cross Site Scripting vulnerabilities commonly occur due to:

- Failure to validate user input.
- Lack of output encoding.
- Improper input sanitization.
- Unsafe manipulation of the Document Object Model (DOM).
- Trusting user-supplied data without verification.
- Insecure JavaScript implementation.

---

# 1. Reflected XSS

## Severity
Low,Medium,High

## Description

Reflected XSS occurs when user input is immediately returned by the server in the HTTP response without proper sanitization.

The malicious script is not permanently stored on the server. Instead, it is reflected back to the victim's browser through a crafted request.

## Attack Scenario

An attacker sends a malicious URL containing JavaScript code to a victim. Once the victim clicks the link, the script executes in the browser.
1.In low level there is accepting of the script values, So I inserted script,alert payload which works and given response.
2.In medium level the website filtering the scripts, So I jumbles the script payload as <sCRipt> like these for bypassing the filtering   of scripts the payload gives the results.
3.In High level, I used HTML tag and body tag because the scripts are not allowed and the HTML tags executed succesfully. 

## Impact

- Session hijacking
- Credential theft
- User impersonation
- Redirection to malicious websites

## Evidence

Screenshots folder has the Evidence

## Sample Payload

<script>alert("XSS")</script>

## Risk Rating

# Low Security (DVWA)
   Likelihood: High (3)
   Impact: Medium (2)
   Score: 6/9 – High Risk
# Medium Security (DVWA)
   Likelihood: Medium (2)
   Impact: Medium (2)
   Score: 4/9 – Medium Risk
# High Security (DVWA)
   Likelihood: Low (1)
   Impact: Medium (2)
   Score: 2/9 – Low Risk

---

# 2. Stored XSS

## Severity
Low,Medium,High

## Description

Stored XSS occurs when malicious scripts are permanently stored by the application, usually in databases, comments, message boards, or user profiles.

Whenever another user accesses the affected page, the malicious script executes automatically.

## Attack Scenario

An attacker submits malicious JavaScript through a vulnerable input field.

The application stores the payload and delivers it to every user visiting the affected page.
1.In low level severity,the Scripts are allowed so the easy payload has kept in the Message column.
2.In medium level the name column is vulnerable not Meassage column,So by inspecting and changing the maxlenght of words and the payload is inserted in the Name column the results came succesfully.
3.In High level,the HTML tags are used same as in Name Column,where it returns the Results.

## Impact

- Persistent session hijacking
- Large-scale credential theft
- Account compromise
- Malware distribution
- Defacement

## Evidence

Screenshots folder has the Evidence

## Sample Payload

<script>alert('Stored XSS')</script>

## Risk Rating

# Low Security 
    Likelihood: High (4)
    Impact: Medium (2)
    Score: 7/9 – High Risk
# Medium Security 
   Likelihood: Medium (2)
   Impact: Medium (2.5)
   Score: 4.5/9 – Medium Risk
# High Security
   Likelihood: Low (1)
   Impact: Medium (2)
   Score: 2/9 – Low Risk

---

# 3. DOM-Based XSS

## Severity
Low,Medium,High

## Description

DOM-Based XSS occurs entirely on the client side when JavaScript modifies the Document Object Model using untrusted data without proper validation.

The vulnerable code exists within the browser rather than the server response.

## Attack Scenario

An attacker manipulates URL fragments or client-side input processed by insecure JavaScript functions.

The browser executes the injected payload locally.
1.In low level, the payload is inserted in url that gives the results.
2.In medium level,the same low level payload is inserted but it not executes.So "#" os added infront of the payload which executes succesfully.
3.In high level.,here We changed the language and excuted same payload of medium level that gives the result.

## Impact

- Client-side script execution
- Session theft
- Browser manipulation
- User redirection

## Evidence

Screenshots folder has the Evidence

## Sample Payload

#<script>alert('DOM XSS')</script>

## Risk Rating

# Low Security (DVWA)
   Likelihood: High (3)
   Impact: Medium (2)
   Score: 6/9 – High Risk
# Medium Security (DVWA)
   Likelihood: Medium (2)
   Impact: Medium (2)
   Score: 4/9 – Medium Risk
# High Security (DVWA)
  Likelihood: Low (1)
  Impact: Medium (2)
  Score: 2/9 – Low Risk

---

# Security Recommendations

## Input Validation

Validate and sanitize all user-supplied input before processing.

## Output Encoding

Encode output according to its rendering context.

## Content Security Policy (CSP)

Implement CSP headers to restrict script execution.

## Secure DOM Manipulation

Avoid unsafe JavaScript functions such as:
- innerHTML
- document.write()
- eval()

## Cookie Protection

Enable:
- HttpOnly
- Secure
- SameSite

## Security Testing

Perform regular web application security assessments and code reviews.

---

# Conclusion

The DVWA assessment demonstrated how different types of Cross Site Scripting vulnerabilities arise due to improper handling of user-controlled data. Although Reflected, Stored, and DOM-Based XSS differ in their execution methods, each presents significant risks to confidentiality, integrity, and user trust.

Proper input validation, context-aware output encoding, secure coding practices, and continuous security testing are essential to prevent XSS attacks in modern web applications.

---

# References

- OWASP Cross Site Scripting Prevention Cheat Sheet
- OWASP Top 10: Injection and XSS Guidance
- PortSwigger Web Security Academy – Cross Site Scripting

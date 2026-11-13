# Cross-Site Scripting – HTTP-Header XSS

## Methodology

1. **Request identification**  
   I analyzed the network traffic generated during the logout process and identified a request responsible for saving the user login IP address.

2. **Response analysis**  
   I observed that the IP address provided by the client was reflected in the server response.

3. **Input control identification**  
   I determined that the IP address value could be influenced by client-controlled HTTP headers.

4. **Request interception**  
   Using Burp Suite, I intercepted the logout request before it was sent to the server.

5. **Header manipulation**  
   I injected a persisted Cross-Site Scripting payload into the HTTP header used to determine the client IP address by setting its value to an iframe containing JavaScript code.

6. **Request forwarding**  
   I forwarded the manipulated request to the server.

7. **Payload execution**  
   When the application processed and displayed the stored IP address, the injected payload executed in the browser.

8. **Validation**  
   Successful execution of the JavaScript code validated the challenge.

### Tools used
- Web browser
- Burp Suite

---

## Vulnerabilities

- **Vulnerability name**: Persisted Cross-Site Scripting via HTTP Header
- **Affected components**: Logout mechanism, request header processing, response rendering logic
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to inject malicious scripts through HTTP headers that are later rendered by the application.  
Potential business impacts include:
- Execution of arbitrary JavaScript in user browsers
- Session hijacking and account compromise
- Theft of sensitive information
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Never trust or reflect client-controlled HTTP headers
- Enforce strict input validation for all request headers

### Remediation fixes
- Sanitize and encode header values before processing or storage
- Avoid rendering untrusted header data in responses
- Use server-side mechanisms to determine client IP addresses securely

### Security best practices
- Apply defense-in-depth for all input vectors
- Regularly test applications for header-based injection flaws
- Follow OWASP recommendations for Cross-Site Scripting prevention

---


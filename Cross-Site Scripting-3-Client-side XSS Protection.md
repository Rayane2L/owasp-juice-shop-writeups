# Cross-Site Scripting – Client-side XSS Protection

## Methodology

1. **User registration**  
   I registered a new user account using the application’s registration functionality.

2. **Endpoint identification**  
   After registration, I identified the `/api/users` endpoint responsible for handling user data.

3. **Request interception**  
   Using **Burp Suite**, I intercepted the HTTP request related to user creation and sent it to the Repeater tool.

4. **Request analysis**  
   I analyzed the JSON body of the request and observed parameters such as `email`, `password`, and other user-related fields.

5. **Payload injection**  
   I modified the request by inserting a persisted Cross-Site Scripting payload into the `email` parameter, bypassing any client-side input validation.

6. **Request replay**  
   I sent the manipulated request to the server using Burp Repeater.

7. **Payload execution**  
   When the user data was later rendered by the application, the injected payload executed and triggered a JavaScript alert.

8. **Validation**  
   The successful execution of the persisted XSS payload validated the challenge.

### Tools used
- Burp Suite (Interceptor and Repeater)
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Persisted Cross-Site Scripting (XSS)
- **Affected components**: User management API, client-side input validation
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to store malicious JavaScript payloads by bypassing client-side protections.  
Potential business impacts include:
- Execution of arbitrary scripts in users’ browsers
- Account compromise through session hijacking
- Defacement of application content
- Loss of user trust and reputational damage

---

## Actions

### Mitigation strategies
- Never rely solely on client-side security mechanisms
- Enforce server-side input validation and sanitization

### Remediation fixes
- Implement strict server-side validation for all user inputs
- Encode output before rendering user-controlled data
- Apply allowlists for acceptable input formats
- Sanitize stored data at creation time

### Security best practices
- Follow OWASP Top 10 recommendations for Cross-Site Scripting
- Treat all client input as untrusted
- Perform security testing on APIs independently of the frontend
- Regularly audit and test client-side security controls

---

Allowlist Bypass
Enforce a redirect to a page you are not supposed to redirect to. (Difficulty Level: 4)

## Methodology

1. **Source code analysis**  
   I analyzed the client-side JavaScript file `main.js` and noticed logic related to redirecting users to external resources.

2. **Redirect endpoint identification**  
   I identified a redirection endpoint that accepts a parameter intended to allow only trusted links.

3. **Trusted URL discovery**  
   While inspecting the application behavior, I found a reference to a Bitcoin address page hosted on a well-known blockchain website, which was considered a trusted destination by the application.

4. **Parameter manipulation**  
   I crafted a redirection URL by nesting the trusted destination inside another parameter, effectively bypassing the trusted link validation.

5. **Redirect chaining**  
   By embedding the trusted URL as a query parameter of an internal page, I was able to trick the application into accepting and processing the redirection.

6. **Request execution**  
   I submitted the manipulated redirect request to the application.

7. **Validation**  
   The application successfully redirected to the external Bitcoin address page, validating the challenge.

### Tools used
- Web browser
- Manual URL manipulation

---

## Vulnerabilities

- **Vulnerability name**: Unvalidated Redirect
- **Affected components**: Redirect mechanism, URL validation logic
- **Severity level**: Medium

---

## Risks

This vulnerability allows attackers to redirect users to arbitrary external websites while appearing to originate from a trusted domain.  
Potential business impacts include:
- Phishing attacks using trusted application URLs
- User redirection to malicious or fraudulent websites
- Loss of user trust
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Strictly validate redirect destinations
- Avoid using user-controlled input for redirection logic

### Remediation fixes
- Implement an allowlist of approved redirect destinations
- Reject nested or chained redirect parameters
- Normalize and validate URLs before processing redirects

### Security best practices
- Follow OWASP recommendations for unvalidated redirects
- Avoid open redirection mechanisms whenever possible
- Regularly audit client-side and server-side redirect logic

---

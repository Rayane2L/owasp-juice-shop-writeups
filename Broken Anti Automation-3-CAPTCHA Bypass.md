# Broken Anti Automation – CAPTCHA Bypass

## Methodology

1. **Feedback functionality analysis**  
   I accessed the customer feedback feature of the application, which is supposed to be protected by an anti-automation mechanism.

2. **Request observation**  
   I submitted a feedback normally and observed the HTTP request sent to the backend.

3. **Anti-automation weakness identification**  
   I noticed that no effective server-side validation or CAPTCHA verification was enforced on the feedback submission endpoint.

4. **Rapid request replay**  
   I copied the feedback submission request and repeatedly sent it multiple times in quick succession using the browser console.

5. **Automation simulation**  
   I submitted more than ten feedback requests within a time window of less than twenty seconds.

6. **Validation**  
   All feedback submissions were accepted by the server without any restriction, validating the challenge.

### Tools used
- Web browser
- Browser developer console
- Manual request replay

---

## Vulnerabilities

- **Vulnerability name**: Broken Anti Automation / Missing Rate Limiting
- **Affected components**: Feedback submission system, CAPTCHA enforcement
- **Severity level**: Medium

---

## Risks

This vulnerability allows attackers to automate actions that are meant to be restricted to human users.  
Potential business impacts include:
- Spam and content pollution
- Abuse of feedback or review systems
- Resource exhaustion
- Degraded user experience and reputational damage

---

## Actions

### Mitigation strategies
- Enforce server-side anti-automation controls
- Do not rely solely on client-side protections

### Remediation fixes
- Implement proper CAPTCHA validation on the server side
- Add rate limiting to feedback submission endpoints
- Detect and block abnormal request patterns

### Security best practices
- Apply defense-in-depth for anti-automation mechanisms
- Monitor and log excessive or suspicious request activity
- Regularly test endpoints for automation abuse
- Follow OWASP recommendations for bot and automation protection

---

# Broken Access Control – Forged Feedback

## Methodology

1. **Feature identification**  
   I identified a feedback submission feature allowing authenticated users to post feedback.

2. **Request interception**  
   Using **Burp Suite**, I intercepted the HTTP POST request sent when submitting feedback.

3. **Request analysis**  
   I analyzed the request parameters and noticed a `userId` field was included and controlled by the client.

4. **Parameter tampering**  
   I modified the `userId` value to another existing user's identifier.

5. **Request replay**  
   I forwarded the modified request to the server.

6. **Validation**  
   The feedback was successfully posted under another user's identity, validating the challenge.

### Tools used
- Burp Suite
- Web browser (for normal interaction)

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Insecure Direct Object Reference (IDOR)
- **Affected components**: Feedback system, user identity management
- **Severity level**: High

---

## Risks

This vulnerability allows an attacker to impersonate other users by submitting content in their name.  
Potential impacts include:
- Reputational damage to users or the organization
- Loss of trust in the platform
- Social engineering or harassment using forged identities
- Legal or compliance issues if abused at scale

---

## Actions

### Mitigation strategies
- Enforce server-side access control checks for all user-related actions
- Never trust client-supplied identifiers such as `userId`

### Remediation fixes
- Derive the user identity exclusively from the authenticated session or access token
- Remove any client-controlled user identifier from sensitive requests
- Implement authorization checks to ensure users can only act on their own data

### Security best practices
- Follow the principle of least privilege
- Perform regular access control testing
- Use centralized authorization mechanisms
- Conduct security reviews and penetration testing on user input handling

---

# Broken Access Control – Forged Review

## Methodology

1. **Functionality identification**  
   I identified a product review feature that allows authenticated users to post reviews.

2. **Request interception**  
   Using **Burp Suite**, I intercepted the HTTP request sent when submitting a product review.

3. **Request analysis**  
   I analyzed the request body and observed an `author` field containing the review author's email address, which was controlled by the client.

4. **Parameter manipulation**  
   I modified the `author` field by replacing the email address with the email of another existing user.

5. **Request replay**  
   I forwarded the modified request to the server.

6. **Validation**  
   The review was successfully posted (or edited) under another user's identity, confirming the vulnerability.

### Tools used
- Burp Suite
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Insecure Direct Object Reference (IDOR)
- **Affected components**: Product review system, user identity management
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to impersonate other users by creating or modifying reviews in their name.  
Possible business impacts include:
- Manipulation of product ratings and reviews
- Loss of customer trust
- Reputational damage to the platform
- Potential legal issues related to false or misleading content

---

## Actions

### Mitigation strategies
- Enforce strict server-side authorization checks
- Do not rely on client-supplied identity information

### Remediation fixes
- Determine the review author based solely on the authenticated session or token
- Remove or ignore the `author` field from client requests
- Validate that users can only create or modify their own reviews

### Security best practices
- Apply the principle of least privilege
- Implement centralized access control mechanisms
- Regularly test access control logic during development
- Align with OWASP Top 10 recommendations for Broken Access Control

---

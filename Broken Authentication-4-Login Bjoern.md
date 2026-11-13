# Broken Authentication – Login Bjoern

## Methodology

1. **Client-side code analysis**  
   I inspected the main JavaScript file of the application and searched for authentication-related logic.

2. **Authentication logic discovery**  
   I identified a section handling OAuth-based login where the password value was generated on the client side.

3. **Password generation understanding**  
   The code revealed that the password was constructed by reversing the user’s email address and then encoding the result using Base64 encoding.

4. **Email identification**  
   I identified Bjoern’s Gmail address from previously available information within the application.

5. **Password reconstruction**  
   I reversed the email string character by character and then applied Base64 encoding to the resulting value.

6. **Authentication attempt**  
   I used the reconstructed value as the password while logging in with Bjoern’s Gmail address.

7. **Validation**  
   The authentication was successful without changing the password, using SQL Injection, or compromising the Gmail account, validating the challenge.

### Tools used
- Web browser
- JavaScript code inspection
- Base64 encoding knowledge

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Client-Side Credential Generation
- **Affected components**: OAuth login logic, client-side authentication code
- **Severity level**: High

---

## Risks

This vulnerability exposes predictable authentication credentials derived from public information.  
Potential business impacts include:
- Unauthorized account access
- Full account takeover
- Exposure of personal and sensitive data
- Severe reputational damage

---

## Actions

### Mitigation strategies
- Never generate or transform authentication secrets on the client side
- Avoid deterministic password derivation mechanisms

### Remediation fixes
- Move all authentication logic to the server side
- Use secure, random, and non-predictable credentials
- Enforce proper OAuth token validation flows

### Security best practices
- Treat client-side code as untrusted
- Follow OWASP recommendations for authentication and session management
- Regularly audit authentication flows and client-side logic
- Apply secure coding standards for credential handling

---

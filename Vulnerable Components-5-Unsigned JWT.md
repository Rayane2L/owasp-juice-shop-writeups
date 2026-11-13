# Broken Authentication – Unsigned JWT

## Methodology

1. **Token reconnaissance**  
   I inspected the browser local storage and identified a JSON Web Token used for authentication.  
   I retrieved an existing token associated with an administrator account to understand its structure.

2. **JWT structure analysis**  
   I analyzed the token header and payload to identify the signing algorithm and user attributes such as email, role, and status.

3. **Algorithm misuse identification**  
   I noticed that the application accepted tokens with the algorithm field set to `none`, meaning no cryptographic signature was required.

4. **Token forgery**  
   Using the structure of the original token as a reference, I manually crafted a new JWT with:
   - `alg` set to `none`
   - A payload impersonating a non-existing user with administrative privileges

5. **Payload manipulation**  
   The forged payload included the email `jwtn3d@juice-sh.op` and an elevated role set to `admin`.

6. **Token generation**  
   I generated the unsigned JWT using a JWT editor, ensuring no signature was applied.

7. **Token injection**  
   I replaced the existing authentication token in the browser local storage with the forged token.

8. **Authentication bypass**  
   After refreshing the application, the server accepted the unsigned token and authenticated me as the forged user.

9. **Challenge validation**  
   Successful impersonation of the non-existing user validated the challenge.

### Tools used
- Web browser developer tools
- JWT editor
- Manual token crafting

---

## Vulnerabilities

- **Vulnerability name**: Unsigned JSON Web Token acceptance
- **Affected components**: Authentication system, JWT validation mechanism
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to forge authentication tokens and impersonate any user, including administrators.  
Potential business impacts include:
- Complete authentication bypass
- Privilege escalation
- Unauthorized access to sensitive data
- Full application compromise
- Loss of trust and reputational damage

---

## Actions

### Mitigation strategies
- Enforce strict JWT signature verification
- Reject tokens using the `none` algorithm

### Remediation fixes
- Explicitly disable the `none` algorithm in JWT libraries
- Validate token signatures using a strong asymmetric or symmetric key
- Ensure server-side validation of token claims

### Security best practices
- Follow JWT security best practices from OWASP
- Implement proper key management and rotation
- Apply defense-in-depth for authentication mechanisms
- Regularly test authentication logic for token manipulation issues

---

# Broken Authentication – Forged Signed JWT

## Methodology

1. **Authentication mechanism analysis**  
   I identified that the application uses RSA-signed JSON Web Tokens for authentication.

2. **Key discovery attempt**  
   I searched for exposed or hidden resources that could contain cryptographic material used for JWT signing.

3. **Hidden endpoint identification**  
   A hidden endpoint named `/encryptionkeys` was discovered, which exposed public cryptographic keys.

4. **Key extraction**  
   From this endpoint, I downloaded the RSA public key file (`jwt.pub`) used by the application to verify JWT signatures.

5. **JWT structure preparation**  
   Using a standard JWT structure, I crafted a token payload impersonating a non-existing user with the email `rsa_lord@juice-sh.op`.

6. **Payload manipulation**  
   The forged payload included elevated privileges, mimicking the structure of a legitimate administrative token.

7. **Signature forging**  
   I generated a valid RSA signature for the token using the exposed RSA key material.

8. **Encoding process**  
   The generated signature was encoded using Base64URL encoding, as required by the JWT specification.

9. **Token assembly**  
   I assembled the final JWT by combining the header, payload, and the forged Base64URL-encoded signature.

10. **Token injection**  
    I replaced the existing authentication token in the browser local storage with the forged signed JWT.

11. **Authentication bypass**  
    After refreshing the application, the server accepted the forged token as valid.

12. **Challenge validation**  
    Successful impersonation of the non-existing user validated the challenge.

### Tools used
- Web browser developer tools
- Directory enumeration tool
- JWT editor
- RSA key handling utilities
- Base64URL encoding

---

## Vulnerabilities

- **Vulnerability name**: Improper JWT signature verification
- **Affected components**: Authentication system, cryptographic key management
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to forge cryptographically signed authentication tokens.  
Potential business impacts include:
- Full authentication bypass
- Administrative privilege escalation
- Unauthorized access to sensitive data
- Complete compromise of the application
- Severe reputational and financial damage

---

## Actions

### Mitigation strategies
- Never expose cryptographic keys through public endpoints
- Restrict access to encryption and key management resources

### Remediation fixes
- Rotate and invalidate exposed cryptographic keys immediately
- Store keys securely using a dedicated secrets management solution
- Enforce strict JWT validation using trusted key sources only

### Security best practices
- Apply secure key lifecycle management
- Separate public key distribution from application logic
- Regularly audit authentication mechanisms
- Follow OWASP recommendations for JWT and cryptographic security
- Perform periodic penetration testing focused on authentication and authorization

---

# Cryptographic Issues – Nested Easter Egg

## Methodology

1. **Initial easter egg discovery**  
   After completing the initial Easter Egg challenge, I obtained a hidden message left by the developers.

2. **Encoded message identification**  
   I observed that the message was encoded using Base64.

3. **Base64 decoding**  
   I decoded the Base64 string and obtained a readable output that appeared to resemble a URL, but with characters in an incorrect order.

4. **Cipher analysis**  
   Based on the structure of the decoded text, I suspected an additional layer of encryption rather than random corruption.

5. **Caesar cipher hypothesis**  
   I tested a Caesar cipher rotation on the decoded message to determine if it was a simple substitution cipher.

6. **Successful decryption**  
   The Caesar cipher decryption revealed a valid URL.

7. **URL access**  
   I accessed the decoded URL through the application.

8. **Final easter egg discovery**  
   The URL led to a hidden page displaying a planet image.

9. **Validation**  
   Accessing the hidden page validated the Nested Easter Egg challenge.

### Tools used
- Base64 decoding tools
- Manual cryptanalysis
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Weak Cryptography / Security by Obscurity
- **Affected components**: Hidden content protection mechanism
- **Severity level**: Medium

---

## Risks

This vulnerability demonstrates that sensitive or hidden information is protected only by weak or reversible encoding techniques.  
Potential business impacts include:
- Unauthorized discovery of hidden resources
- Exposure of internal or secret content
- Increased likelihood of further information disclosure
- Undermining of application security controls

---

## Actions

### Mitigation strategies
- Avoid relying on encoding or simple ciphers to protect sensitive data
- Use strong cryptographic mechanisms when confidentiality is required

### Remediation fixes
- Replace reversible encoding with proper access control checks
- Restrict access to hidden resources server-side
- Remove sensitive information from client-accessible locations

### Security best practices
- Follow OWASP recommendations for cryptographic storage
- Do not rely on security by obscurity
- Apply defense-in-depth for hidden or special application features
- Regularly audit client-side content for exposed secrets

---

# Broken Access Control – GDPR Data Theft

## Methodology

1. **Order creation**  
   I placed an order using a legitimate user account.

2. **Network traffic inspection**  
   I analyzed the HTTP requests and responses related to the order using the browser developer tools (Network tab).

3. **Sensitive data exposure**  
   I observed that the response contained personal data related to the account that placed the order.

4. **Email masking analysis**  
   The email address was partially masked. Only vowels were replaced by asterisks, while consonants and the overall structure remained visible.

5. **Account recreation**  
   Based on this masking pattern, I created a new account using the same email structure, replacing the masked characters with arbitrary vowels.

6. **Authorization flaw exploitation**  
   I requested the personal data associated with this newly created account. Since no order existed for the new account, the application incorrectly returned the personal data of the original user.

7. **Validation**  
   Personal data belonging to another user was successfully retrieved without using any injection technique, validating the challenge.

### Tools used
- Web browser
- Browser Developer Tools (Network tab)

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Insecure Object Reference
- **Affected components**: Order management system, user data resolution logic
- **Severity level**: Critical

---

## Risks

This vulnerability leads to unauthorized disclosure of personal user data.  
Potential business impacts include:
- Violation of user privacy
- Non-compliance with GDPR and data protection regulations
- Legal penalties and regulatory fines
- Severe reputational damage and loss of customer trust

---

## Actions

### Mitigation strategies
- Enforce strict authorization checks for all personal data requests
- Avoid using masked identifiers to resolve user identities

### Remediation fixes
- Always retrieve personal data based on the authenticated user context
- Do not rely on partially masked data as lookup keys
- Ensure orders and account data are strictly bound to the correct user
- Implement ownership validation before returning sensitive information

### Security best practices
- Apply privacy-by-design principles
- Minimize exposure of personal data in API responses
- Regularly test access control and data handling logic
- Align application behavior with GDPR requirements

---


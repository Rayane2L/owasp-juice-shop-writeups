# Broken Access Control – Manipulate Basket

## Methodology

1. **Functionality identification**  
   I identified the shopping basket feature that allows authenticated users to add products to their basket.

2. **Request interception**  
   Using **Burp Suite**, I intercepted the HTTP request sent when adding an item to the shopping basket.

3. **Request analysis**  
   I analyzed the request body and observed that the basket identifier was controlled by the client.

4. **Parameter injection**  
   I added a second parameter named `basketId` in the request body and set its value to a different existing basket identifier belonging to another user.

5. **Request replay**  
   I forwarded the modified request to the server.

6. **Validation**  
   The product was successfully added to another user's shopping basket, validating the challenge.

### Tools used
- Burp Suite
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Insecure Direct Object Reference (IDOR)
- **Affected components**: Shopping basket system, order management
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to manipulate other users' shopping baskets without authorization.  
Potential business impacts include:
- Unauthorized modification of user orders
- Financial losses due to fraudulent orders
- Loss of customer trust
- Customer dissatisfaction and reputational damage

---

## Actions

### Mitigation strategies
- Enforce strict server-side authorization checks on basket ownership
- Avoid trusting client-supplied basket identifiers

### Remediation fixes
- Associate the basket exclusively with the authenticated user session
- Ignore or reject any basket identifier provided by the client
- Validate that users can only modify their own shopping basket

### Security best practices
- Implement centralized access control mechanisms
- Apply the principle of least privilege
- Regularly test authorization logic for business-critical features
- Follow OWASP Top 10 guidelines for Broken Access Control

---

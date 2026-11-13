# Broken Access Control – Product Tampering

## Methodology

1. **Endpoint enumeration**  
   I enumerated the available product-related API endpoints and identified `/api/products` as the endpoint returning product information.

2. **Target identification**  
   By reviewing the product list, I identified the OWASP SSL Advanced Forensic Tool (O-Saft) product and confirmed it was associated with product ID `9`.

3. **Request interception**  
   Using **Burp Suite**, I intercepted the HTTP request sent to `/api/products/9`.

4. **Request manipulation**  
   I modified the intercepted request by adding a `href` value inside the `description` field of the request body and set it to `https://owasp.slack.com`.

5. **Request replay**  
   I forwarded the modified request to the server.

6. **Validation**  
   The product description was successfully altered and the challenge was validated.

### Tools used
- Burp Suite
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Unauthorized Data Modification
- **Affected components**: Product management API, product description content
- **Severity level**: High

---

## Risks

This vulnerability allows unauthorized users to modify product data.  
Potential business impacts include:
- Defacement or manipulation of product information
- Redirection of users to malicious or misleading external links
- Loss of customer trust
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Restrict product modification endpoints to authorized administrative roles only
- Enforce strict server-side access control checks

### Remediation fixes
- Implement role-based access control (RBAC) for product update endpoints
- Validate user permissions before allowing any product data modification
- Use separate endpoints for read and write operations with proper authorization

### Security best practices
- Apply the principle of least privilege
- Protect critical API endpoints with strong authorization mechanisms
- Regularly audit API permissions and access logs
- Follow OWASP API Security Top 10 recommendations

---

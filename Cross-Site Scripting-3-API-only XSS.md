# Cross-Site Scripting – API-only XSS

## Methodology

1. **Endpoint discovery**  
   I identified a product-related API endpoint used to search and retrieve product information in JSON format.

2. **HTTP method analysis**  
   While interacting with this endpoint, I noticed that multiple HTTP methods were allowed, including methods that should not normally be permitted for standard users.

3. **API response inspection**  
   I performed a product search request and analyzed the JSON response returned by the API.

4. **Payload injection preparation**  
   I modified the product information in the request body and inserted a persistent Cross-Site Scripting payload into one of the product fields.

5. **Unauthorized resource creation**  
   By assigning a non-existing product ID and sending the modified request to the API, I was able to create a new product containing the injected payload.

6. **Payload execution**  
   I searched for the newly created product using the API. When the product data was rendered, the injected payload executed and triggered a JavaScript alert.

7. **Validation**  
   The successful execution of the persisted XSS payload validated the challenge.

### Tools used
- Web browser
- Manual API request manipulation
- HTTP client (via browser or proxy tool)

---

## Vulnerabilities

- **Vulnerability name**: Persisted Cross-Site Scripting (XSS)
- **Affected components**: Product API, data storage and rendering logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to inject and persist malicious scripts through the API.  
Potential business impacts include:
- Execution of arbitrary JavaScript in users’ browsers
- Session hijacking or credential theft
- Defacement of application content
- Large-scale compromise of user accounts

---

## Actions

### Mitigation strategies
- Restrict allowed HTTP methods on API endpoints
- Validate and sanitize all user-supplied data at the API level

### Remediation fixes
- Implement strict input validation and output encoding
- Apply allowlists for acceptable input formats
- Enforce proper authorization checks on create and update API endpoints
- Sanitize stored data before rendering it in any client

### Security best practices
- Follow OWASP Top 10 recommendations for XSS
- Apply the principle of least privilege to API endpoints
- Regularly audit API method exposure
- Perform security testing on APIs independently of the frontend

---

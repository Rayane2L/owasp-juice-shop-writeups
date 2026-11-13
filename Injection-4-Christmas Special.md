# Injection – Christmas Special

## Methodology

1. **Search feature analysis**  
   I analyzed the product search functionality, which sends a query parameter to the backend when the page loads.

2. **Injection testing**  
   I modified the search parameter to manipulate the database query logic and observed the server response.

3. **Query behavior observation**  
   The response revealed that the results could be reordered, allowing me to infer the structure and column count of the underlying SQL query.

4. **Hidden product discovery**  
   By manipulating the search request, I was able to retrieve and browse products that were not normally visible through the frontend.

5. **Product identification**  
   I searched through the returned product list and identified the Christmas special offer from 2014, including its internal product identifier.

6. **Basket request interception**  
   Using Burp Suite, I intercepted the API request responsible for adding products to the shopping basket.

7. **Product ID manipulation**  
   I modified the intercepted request body and replaced the product identifier with the one corresponding to the Christmas special offer.

8. **Checkout process**  
   The product was successfully added to the basket and I completed the checkout process.

9. **Validation**  
   The order of the Christmas special offer from 2014 was accepted, validating the challenge.

### Tools used
- Web browser
- Burp Suite
- Manual request manipulation
- SQL knowledge

---

## Vulnerabilities

- **Vulnerability name**: SQL Injection
- **Affected components**: Search functionality, product catalog access, basket API
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to access and purchase hidden or discontinued products.  
Potential business impacts include:
- Unauthorized sales of retired or restricted products
- Financial losses
- Inventory inconsistencies
- Loss of control over product lifecycle management

---

## Actions

### Mitigation strategies
- Prevent user input from influencing database queries
- Enforce strict server-side validation of product identifiers

### Remediation fixes
- Use parameterized queries for all database interactions
- Restrict access to discontinued or hidden products at the business logic level
- Validate product availability before allowing checkout

### Security best practices
- Follow OWASP recommendations for Injection prevention
- Implement proper access control on product visibility
- Regularly test search and basket endpoints for injection vulnerabilities
- Apply defense-in-depth across business-critical features

---

# Improper Input Validation – Payback Time

## Methodology

1. **Shopping workflow analysis**  
   I added a product to the shopping basket using the normal application workflow.

2. **Request interception**  
   Using Burp Suite, I intercepted the HTTP request sent to the API endpoint responsible for adding items to the basket.

3. **Request inspection**  
   I analyzed the request body and identified the parameter controlling the quantity of the product.

4. **Input manipulation**  
   I modified the quantity value to a negative number before forwarding the request to the server.

5. **Order completion**  
   I proceeded to checkout and completed the payment process.

6. **Validation**  
   The order resulted in an increase of my account balance, effectively making money from the transaction and validating the challenge.

### Tools used
- Web browser
- Burp Suite

---

## Vulnerabilities

- **Vulnerability name**: Improper Input Validation
- **Affected components**: Shopping basket API, order processing logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to manipulate transaction values to gain financial benefits.  
Potential business impacts include:
- Direct financial loss
- Abuse of the payment system
- Inconsistent or corrupted accounting data
- Loss of trust from customers and partners

---

## Actions

### Mitigation strategies
- Enforce strict validation of numeric input values
- Reject invalid or out-of-range quantities

### Remediation fixes
- Ensure quantities are validated as positive integers on the server side
- Implement business logic checks before order processing
- Add safeguards to prevent negative pricing scenarios

### Security best practices
- Validate all user input on the server side
- Implement sanity checks for financial operations
- Perform regular security testing on business logic flows
- Follow OWASP guidelines for input validation

---

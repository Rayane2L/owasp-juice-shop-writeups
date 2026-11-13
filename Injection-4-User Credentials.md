# Injection – User Credentials

## Methodology

1. **Search endpoint analysis**  
   I analyzed the product search functionality, which sends a request containing a search parameter to the backend when the page loads.

2. **Injection testing**  
   I modified the search parameter to introduce malformed input and observed that the backend database returned error messages and altered responses.

3. **Database schema correlation**  
   Based on information previously obtained from database schema enumeration, I knew that the users table contained sensitive columns such as email addresses, usernames, and password hashes.

4. **Column alignment discovery**  
   I adjusted the injected input to match the number of columns returned by the original query, allowing the database to accept a combined result set.

5. **Union-based data extraction**  
   I crafted a request that merged the original query with a second query targeting the users table in order to retrieve authentication-related data.

6. **Data exfiltration**  
   The response contained a list of user credentials, including emails, usernames, and password hashes.

7. **Validation**  
   The application displayed the extracted user credential data, validating the challenge.

### Tools used
- Web browser
- Manual request manipulation
- SQL knowledge

---

## Vulnerabilities

- **Vulnerability name**: SQL Injection
- **Affected components**: Search functionality, database query layer
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to retrieve sensitive authentication data for all users.  
Potential business impacts include:
- Mass account compromise
- Credential reuse attacks on other platforms
- Exposure of personal data
- Severe reputational damage and legal consequences

---

## Actions

### Mitigation strategies
- Prevent user input from being directly embedded into SQL queries
- Enforce strict server-side input handling

### Remediation fixes
- Use prepared statements or parameterized queries
- Restrict database user privileges to the minimum required
- Mask or avoid returning sensitive data in application responses

### Security best practices
- Follow OWASP recommendations for Injection prevention
- Regularly test all input points for injection vulnerabilities
- Apply secure password storage practices
- Monitor and log suspicious database query behavior

---

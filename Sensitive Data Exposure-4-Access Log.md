# Injection – Access Log

## Methodology

1. **Authentication target identification**  
   I identified the login functionality as a potential entry point to gain unauthorized access.

2. **SQL Injection discovery**  
   I tested the email input field of the login form for SQL injection vulnerabilities.

3. **Injection technique**  
   I used a classic SQL injection payload that closes the email string and comments out the rest of the SQL query, effectively bypassing the password verification logic.

4. **Authentication bypass**  
   The injection was successful, and I was authenticated as the `support@juice-sh.op` user without providing a valid password.

5. **Privilege exploration**  
   After logging in, I navigated through the application and accessed the `/support/logs` endpoint.

6. **Unauthorized access**  
   The server access log files were accessible from this location.

7. **Validation**  
   Gaining access to the server access logs validated the challenge.

### Tools used
- Web browser
- Manual SQL injection testing

---

## Vulnerabilities

- **Vulnerability name**: SQL Injection
- **Affected components**: Authentication system, support interface, log access functionality
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to bypass authentication and access sensitive server log files.  
Potential business impacts include:
- Disclosure of internal server information (IP addresses, endpoints, timestamps)
- Facilitation of further targeted attacks
- Compromise of privileged support accounts
- Severe reputational and legal consequences

---

## Actions

### Mitigation strategies
- Prevent SQL injection vulnerabilities in all authentication mechanisms
- Restrict access to log files to authorized administrative users only

### Remediation fixes
- Use parameterized queries or prepared statements for all database interactions
- Properly validate and sanitize all user inputs
- Implement strict role-based access control (RBAC) on sensitive endpoints
- Avoid exposing server log files through the web interface

### Security best practices
- Follow OWASP Top 10 recommendations for Injection vulnerabilities
- Perform regular code reviews and security testing
- Implement centralized and secured logging solutions
- Monitor authentication attempts for anomalous behavior

---

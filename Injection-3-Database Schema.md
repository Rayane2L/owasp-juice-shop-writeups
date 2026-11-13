# Injection – Database Schema

## Methodology

1. **Search feature analysis**  
   I analyzed the product search functionality, which sends a request containing a search parameter to the backend.

2. **Request manipulation**  
   I copied the search request and manually modified the input parameter to introduce malformed input, intentionally triggering a database error.

3. **SQL error observation**  
   The error message revealed the structure of the SQL query used by the application, including table selection, filtering conditions, and ordering logic.

4. **Query structure understanding**  
   From the error output, I inferred that the query was selecting multiple columns from the products table and was vulnerable to injection.

5. **Order-based injection**  
   I modified the input to alter the query ordering, allowing me to determine the number of columns returned by the original query.

6. **Union-based injection**  
   Once the correct column count was identified, I crafted a request that merged the original query with a second query targeting the database metadata table.

7. **Schema extraction**  
   The injected query retrieved the SQL definitions of all database tables, effectively exfiltrating the entire database schema.

8. **Validation**  
   The database schema information was successfully displayed in the application response, validating the challenge.

### Tools used
- Web browser
- Manual request editing
- SQL knowledge

---

## Vulnerabilities

- **Vulnerability name**: SQL Injection
- **Affected components**: Search functionality, database query layer
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to fully enumerate the database structure.  
Potential business impacts include:
- Exposure of database schema and internal structure
- Facilitation of further attacks such as data extraction or modification
- Compromise of sensitive application data
- Increased risk of complete database takeover

---

## Actions

### Mitigation strategies
- Prevent direct concatenation of user input into SQL queries
- Implement strict input validation

### Remediation fixes
- Use prepared statements or parameterized queries
- Disable verbose database error messages in production
- Restrict database permissions to the minimum required

### Security best practices
- Apply secure coding practices for database interactions
- Regularly test for injection vulnerabilities
- Follow OWASP recommendations for Injection prevention
- Implement proper logging and monitoring of database errors

---

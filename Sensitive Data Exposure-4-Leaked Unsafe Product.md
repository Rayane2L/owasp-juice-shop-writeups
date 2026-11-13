# Sensitive Data Exposure – Leaked Unsafe Product

## Methodology

1. **Data source identification**  
   I reused a database dump obtained during a previous challenge.

2. **Database analysis**  
   I reviewed the product table and searched for suspicious keywords related to product safety.

3. **Keyword discovery**  
   I identified entries containing the keyword "unsafe", indicating products that had been removed from the shop.

4. **Ingredient enumeration**  
   I extracted the list of ingredients associated with the unsafe product.

5. **Open-source research (OSINT)**  
   I searched online for each listed fruit name using a search engine.

6. **External information discovery**  
   The searches led to a Pastebin page containing descriptions of the ingredients, including health hazards associated with some of them.

7. **Hazard identification**  
   Based on the information found, I identified two dangerous ingredients:
   - Hueteroneel  
   - Eurogium Edule

8. **Validation**  
   Identifying the unsafe product and its hazardous ingredients validated the challenge.

### Tools used
- Database dump
- Search engine
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Sensitive Data Exposure
- **Affected components**: Product database, data retention and disclosure mechanisms
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to access internal product information that was not intended to be publicly available.  
Potential business impacts include:
- Disclosure of sensitive internal decisions (product recalls or removals)
- Regulatory and legal consequences related to unsafe products
- Loss of customer trust
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Restrict access to internal databases and backups
- Ensure removed or deprecated products are properly sanitized from exposed data sources

### Remediation fixes
- Implement strict access controls on database dumps and backups
- Avoid storing sensitive or deprecated product information in publicly accessible systems
- Regularly review and clean legacy data

### Security best practices
- Apply the principle of least privilege to data access
- Encrypt sensitive data at rest
- Perform regular audits of stored and exposed data
- Follow OWASP recommendations for sensitive data handling

---

# Improper Input Validation – Poison Null Byte

## Methodology

1. **Directory enumeration**  
   I browsed the publicly accessible FTP directory and identified files that were visible but not downloadable due to server-side restrictions.

2. **Access restriction analysis**  
   I observed that certain files could not be downloaded directly, indicating the presence of a file type or extension validation mechanism.

3. **Poison Null Byte injection**  
   I appended a URL-encoded null byte sequence followed by an allowed file extension to the file name.

4. **Request execution**  
   I submitted the modified request to the server to access the restricted file.

5. **File retrieval**  
   The server returned the content of the file that was originally blocked.

6. **Validation**  
   The restricted file was successfully downloaded, validating the challenge.

### Tools used
- Web browser
- Manual URL manipulation

---

## Vulnerabilities

- **Vulnerability name**: Improper Input Validation / Poison Null Byte
- **Affected components**: File access control, file name validation logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to bypass file access restrictions.  
Potential business impacts include:
- Unauthorized access to sensitive files
- Information disclosure
- Exposure of internal or confidential data
- Increased risk of further attacks

---

## Actions

### Mitigation strategies
- Enforce strict server-side validation of file paths and extensions
- Properly sanitize and normalize user-supplied file names

### Remediation fixes
- Reject null byte sequences in file paths
- Use safe file handling APIs that do not allow string truncation
- Implement strict allowlists for accessible files

### Security best practices
- Treat all user input as untrusted
- Apply secure file handling practices
- Regularly test file access controls
- Follow OWASP recommendations for input validation and file handling security

---

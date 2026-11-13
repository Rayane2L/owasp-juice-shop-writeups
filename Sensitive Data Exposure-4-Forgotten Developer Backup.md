# Broken Access Control – Forgotten Developer Backup

## Methodology

1. **Directory exploration**  
   I explored the publicly accessible `/ftp` directory exposed by the application.

2. **File discovery**  
   Inside this directory, I identified a file named `coupons_2013.md`, which appeared to be a developer backup file.

3. **Access restriction identification**  
   Direct download of the file was restricted by the application.

4. **Bypass technique selection**  
   I attempted to bypass the file access restriction using a null byte poisoning technique.

5. **Payload crafting**  
   I appended a double-encoded null byte followed by a file extension to the requested filename, allowing the backend to incorrectly process the file validation.

6. **Request execution**  
   I sent the crafted request to the server.

7. **Validation**  
   The backup file was successfully downloaded, validating the challenge.

### Tools used
- Web browser
- Manual request manipulation

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Improper Input Validation (Null Byte Poisoning)
- **Affected components**: File download mechanism, FTP directory access
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to access forgotten or sensitive backup files.  
Potential business impacts include:
- Exposure of internal or sensitive data
- Disclosure of business logic or promotional information
- Increased risk of further attacks using leaked information
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Enforce strict server-side file access controls
- Prevent access to backup and development files

### Remediation fixes
- Reject null byte characters and encoded variants in user input
- Store backup files outside publicly accessible directories
- Use allowlists for permitted file names and extensions
- Implement secure file handling routines

### Security best practices
- Apply the principle of least privilege for file access
- Regularly audit public directories for forgotten files
- Follow OWASP guidelines for secure file handling
- Perform periodic security assessments

---

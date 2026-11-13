# Broken Access Control – Forgotten Sales Backup

## Methodology

1. **Directory exploration**  
   I explored the publicly accessible `/ftp` directory exposed by the application.

2. **File discovery**  
   Inside this directory, I identified a file named `package.json.bak`, which appeared to be a forgotten backup file from a sales-related context.

3. **Access restriction identification**  
   Direct download of the file was blocked by server-side validation.

4. **Bypass technique selection**  
   I attempted to bypass file access restrictions using a **null byte poisoning** attack.

5. **Payload crafting**  
   I appended a double-encoded null byte followed by a `.md` extension to the filename, allowing the server to incorrectly process the file and bypass validation.

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
- Exposure of sensitive business information
- Leakage of internal configurations or development artifacts
- Facilitation of further attacks using leaked data
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Enforce strict server-side file access controls
- Prevent access to backup or internal files from public directories

### Remediation fixes
- Reject null byte characters and encoded variants in user input
- Store backup files outside publicly accessible directories
- Use allowlists for permitted file names and extensions
- Implement secure file handling routines

### Security best practices
- Apply the principle of least privilege for file access
- Regularly audit public directories for forgotten or sensitive files
- Follow OWASP guidelines for secure file handling
- Conduct periodic security assessments

---

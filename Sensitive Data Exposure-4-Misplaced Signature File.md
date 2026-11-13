# Broken Access Control – Misplaced Signature File

## Methodology

1. **Directory exploration**  
   I explored the publicly accessible `/ftp` directory exposed by the application.

2. **File discovery**  
   Within this directory, I identified a file named `suspicious_errors.yml`, which appeared to be a SIEM signature or configuration file.

3. **Access restriction identification**  
   Direct download of the file was restricted by server-side validation.

4. **Bypass technique selection**  
   I attempted to bypass the file access restriction using a null byte poisoning technique.

5. **Payload crafting**  
   I appended a double-encoded null byte followed by an allowed file extension to the requested filename, causing improper validation by the backend.

6. **Request execution**  
   I sent the crafted request to the server.

7. **Validation**  
   The SIEM signature file was successfully downloaded, validating the challenge.

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

This vulnerability allows attackers to access internal security configuration files.  
Potential business impacts include:
- Disclosure of SIEM detection rules
- Evasion of monitoring and alerting mechanisms
- Increased likelihood of successful future attacks
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Enforce strict server-side access control for security-related files
- Prevent exposure of SIEM and monitoring configuration files

### Remediation fixes
- Reject null byte characters and encoded variants in user input
- Store security configuration files outside publicly accessible directories
- Implement strict allowlists for downloadable files
- Use secure file handling APIs

### Security best practices
- Apply the principle of least privilege
- Regularly audit public directories for sensitive files
- Protect security configurations with strong access controls
- Follow OWASP guidelines for secure file handling

---

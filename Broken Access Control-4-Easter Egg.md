# Broken Access Control – Easter Egg

## Methodology

1. **Resource discovery**  
   I browsed the application directories and discovered the `/ftp` directory, which exposes downloadable files.

2. **Directory enumeration**  
   Inside the `/ftp` directory, I identified a folder named `easteregg`.

3. **Access restriction identification**  
   Direct download of the `easteregg` file was not allowed due to server-side restrictions.

4. **Bypass technique selection**  
   I attempted a **null byte poisoning attack** to bypass file extension validation mechanisms.

5. **Payload crafting**  
   I appended `%2500.md` to the requested filename. The double-encoded null byte (`%2500`) was interpreted by the backend and truncated the filename validation.

6. **Request execution**  
   I sent the crafted request to the server.

7. **Validation**  
   The file was successfully downloaded, revealing the easter egg content and validating the challenge.

### Tools used
- Web browser
- Manual HTTP request manipulation

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Improper Input Validation (Null Byte Poisoning)
- **Affected components**: File download mechanism, FTP directory access control
- **Severity level**: Medium to High

---

## Risks

This vulnerability allows attackers to bypass file access restrictions and retrieve unauthorized files.  
Potential business impacts include:
- Exposure of sensitive or internal files
- Leakage of configuration or source code
- Increased attack surface for further exploitation
- Reputational damage if sensitive data is exposed

---

## Actions

### Mitigation strategies
- Enforce strict server-side file access controls
- Properly validate and sanitize user-supplied file paths

### Remediation fixes
- Reject null bytes and encoded null byte sequences in user input
- Use allowlists for permitted file names and extensions
- Avoid relying on string-based file extension validation
- Implement secure file handling APIs

### Security best practices
- Apply the principle of least privilege for file access
- Regularly audit file handling and download features
- Follow OWASP recommendations for secure file access
- Conduct security testing against common bypass techniques

---

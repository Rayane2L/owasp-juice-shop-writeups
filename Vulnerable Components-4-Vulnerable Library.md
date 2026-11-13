# Vulnerable Components – Vulnerable Library

## Methodology

1. **File discovery**  
   I explored the `/ftp` directory and identified backup files that were not intended to be publicly accessible.

2. **Bypass of download restriction**  
   I used a Poison Null Byte technique to bypass file extension checks and successfully download the `package.json.bak` file.

3. **Dependency analysis**  
   I analyzed the content of the backup file and reviewed the listed dependencies and their versions.

4. **Vulnerability identification**  
   While inspecting the dependencies, I identified an outdated and vulnerable library used by the application.

5. **Library confirmation**  
   The vulnerable dependency found was:
   - Library name: express-jwt  
   - Version: 0.1.3

6. **Challenge validation**  
   I reported the exact library name and version through the customer feedback feature, which successfully validated the challenge.

### Tools used
- Web browser
- Manual file inspection
- Knowledge of known vulnerable libraries

---

## Vulnerabilities

- **Vulnerability name**: Use of vulnerable third-party library
- **Affected components**: Authentication middleware, dependency management
- **Severity level**: High

---

## Risks

Using outdated and vulnerable libraries exposes the application to known exploits.  
Potential business impacts include:
- Authentication bypass
- Unauthorized access
- Increased attack surface
- Compromise of application security
- Reputational damage

---

## Actions

### Mitigation strategies
- Regularly audit third-party dependencies
- Monitor known vulnerability databases for used libraries

### Remediation fixes
- Upgrade the vulnerable library to a secure and maintained version
- Remove unused or deprecated dependencies

### Security best practices
- Implement automated dependency scanning
- Keep all libraries up to date
- Use dependency lock files
- Apply the principle of minimal dependency usage
- Follow secure software supply chain practices

---

# Improper Input Validation – Upload Type

## Methodology

1. **File preparation**  
   I created a text file larger than 100 kilobytes to exceed the allowed upload size limit.

2. **Client-side restriction bypass**  
   To bypass client-side checks, I compressed the text file into a ZIP archive.

3. **Upload request interception**  
   Using Burp Suite, I intercepted the HTTP request generated during the file upload process.

4. **Request manipulation**  
   I modified the intercepted request by changing the file name and content type, removing the ZIP extension and keeping only the TXT format.

5. **Request forwarding**  
   I forwarded the manipulated request to the server.

6. **Validation**  
   The server accepted the upload of a file larger than 100 kilobytes and not matching the allowed file types, validating the challenge.

### Tools used
- Web browser
- Burp Suite
- Text editor

---

## Vulnerabilities

- **Vulnerability name**: Improper Input Validation
- **Affected components**: File upload mechanism, server-side validation logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to upload oversized and unauthorized file types.  
Potential business impacts include:
- Denial of service due to storage abuse
- Upload of malicious files
- Circumvention of content restrictions
- Increased attack surface on the server

---

## Actions

### Mitigation strategies
- Enforce strict server-side validation for file uploads
- Do not rely on client-side controls for security

### Remediation fixes
- Validate file size on the server before accepting uploads
- Enforce strict allowlists for file types and MIME types
- Recalculate and verify file metadata server-side
- Reject files that exceed defined limits regardless of client input

### Security best practices
- Treat all uploaded files as untrusted
- Implement antivirus or malware scanning for uploaded files
- Apply defense-in-depth to file upload features
- Follow OWASP recommendations for secure file upload handling

---

# Improper Input Validation – Admin Registration

## Methodology

1. **Registration process analysis**  
   I accessed the user registration functionality and initiated the creation of a new account.

2. **Request interception**  
   Using Burp Suite, I intercepted the HTTP request sent to the server during the registration process.

3. **Request body inspection**  
   I analyzed the request body and observed that it contained a parameter defining the user role.

4. **Privilege manipulation**  
   I modified the role parameter in the request body and set its value to an administrative role.

5. **Request forwarding**  
   I forwarded the modified request to the server.

6. **Validation**  
   The account was successfully created with administrator privileges, validating the challenge.

### Tools used
- Web browser
- Burp Suite

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Privilege Escalation
- **Affected components**: User registration system, role assignment logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to create accounts with elevated privileges.  
Potential business impacts include:
- Full compromise of administrative functionalities
- Unauthorized access to sensitive data
- Modification or deletion of critical application resources
- Severe reputational and operational damage

---

## Actions

### Mitigation strategies
- Enforce strict server-side role assignment
- Prevent users from defining their own privilege levels

### Remediation fixes
- Remove role-related parameters from client-controlled requests
- Assign user roles exclusively on the server side
- Implement role validation and authorization checks during registration

### Security best practices
- Apply the principle of least privilege
- Regularly review access control logic
- Perform security testing on authentication and registration flows
- Follow OWASP recommendations for Broken Access Control

---

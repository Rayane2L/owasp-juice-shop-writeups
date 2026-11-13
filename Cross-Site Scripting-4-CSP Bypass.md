# Cross-Site Scripting – CSP Bypass

## Methodology

1. **Legacy page identification**  
   I navigated to the user profile page, which appeared to be an older (legacy) part of the application.

2. **Initial payload injection**  
   I attempted to inject a basic XSS payload into the `name` field:
   <script>alert(xss)</script>  
   The payload did not execute due to Content Security Policy (CSP) restrictions.

3. **CSP analysis**  
   I inspected the CSP applied to the page and confirmed that inline scripts were blocked by default.

4. **CSP bypass technique**  
   I identified that the CSP could be weakened by allowing inline scripts.  
   By abusing a controlled image URL, I was able to extend the policy to allow inline JavaScript execution by adding unsafe directives to the script source configuration.

5. **Payload execution**  
   After bypassing the CSP restrictions, the injected script in the `name` field executed successfully.

6. **Validation**  
   The execution of the JavaScript payload validated the challenge.

### Tools used
- Web browser
- Browser Developer Tools

---

## Vulnerabilities

- **Vulnerability name**: Cross-Site Scripting (XSS) with CSP Bypass
- **Affected components**: Legacy profile page, Content Security Policy configuration
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to bypass CSP protections and execute arbitrary JavaScript.  
Potential business impacts include:
- Session hijacking and account compromise
- Theft of sensitive user data
- Defacement of application content
- Severe reputational damage

---

## Actions

### Mitigation strategies
- Enforce strict and immutable CSP headers
- Avoid unsafe CSP directives such as inline script execution

### Remediation fixes
- Remove unsafe CSP directives from all pages
- Properly sanitize and encode user-controlled input
- Refactor legacy pages to follow modern security standards

### Security best practices
- Follow OWASP recommendations for CSP and XSS prevention
- Regularly audit CSP configurations
- Apply defense-in-depth for client-side security
- Perform security testing on legacy application components

---

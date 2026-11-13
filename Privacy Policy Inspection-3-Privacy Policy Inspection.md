# Security through Obscurity – Privacy Policy Inspection

## Methodology

1. **Policy page access**  
   I accessed the Privacy Policy page available on the application.

2. **Content inspection**  
   I carefully reviewed the displayed text and interacted with the page content.

3. **Hidden behavior discovery**  
   While moving the mouse cursor over the text, I noticed that certain words or sections visually reacted by highlighting.

4. **Hidden message reconstruction**  
   I identified all highlighted words and assembled them in the correct order to form a meaningful sentence.

5. **Challenge response submission**  
   I submitted the reconstructed sentence using the customer feedback feature of the application.

6. **Validation**  
   The application accepted the submitted sentence, validating the challenge.

### Tools used
- Web browser
- Manual interaction with page content

---

## Vulnerabilities

- **Vulnerability name**: Security through Obscurity
- **Affected components**: Privacy Policy page, hidden client-side logic
- **Severity level**: Low

---

## Risks

This vulnerability relies on hiding information rather than enforcing real security controls.  
Potential business impacts include:
- False sense of security
- Exposure of hidden messages or logic
- Encouragement of relying on obscurity instead of proper controls

---

## Actions

### Mitigation strategies
- Avoid hiding sensitive or important logic within client-side content
- Use explicit and documented mechanisms for verification challenges

### Remediation fixes
- Remove hidden interactive elements from static policy pages
- Implement proper challenge validation mechanisms if user verification is required

### Security best practices
- Do not rely on security through obscurity
- Keep policy pages purely informational
- Follow OWASP recommendations for secure design
- Ensure that all security-related mechanisms are explicit and robust

---

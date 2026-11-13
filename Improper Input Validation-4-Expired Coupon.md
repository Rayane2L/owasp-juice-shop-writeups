# Broken Access Control – Expired Coupon

## Methodology

1. **Client-side code analysis**  
   I inspected the JavaScript files of the application and searched for keywords related to discounts and coupons.

2. **Coupon discovery**  
   I identified a discount configuration corresponding to a 75 percent promotion related to International Women’s Day.

3. **Expired coupon identification**  
   Among the discovered coupons, I found one associated with the year 2019.

4. **Date verification**  
   I checked the official date of International Women’s Day in 2019, which occurred on March 8.

5. **Client-side date manipulation**  
   I changed the system date of my computer to match March 8, 2019.

6. **Coupon redemption**  
   I applied the expired coupon code during the checkout process.

7. **Validation**  
   The application accepted the expired coupon and applied the discount, validating the challenge.

### Tools used
- Web browser
- Text editor
- Operating system date settings

---

## Vulnerabilities

- **Vulnerability name**: Broken Access Control / Improper Validation of Time-Based Logic
- **Affected components**: Coupon validation mechanism, discount logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to redeem expired promotional offers.  
Potential business impacts include:
- Financial loss due to unauthorized discounts
- Abuse of promotional campaigns
- Inconsistent or incorrect accounting data
- Loss of trust from partners and customers

---

## Actions

### Mitigation strategies
- Enforce server-side validation of coupon expiration dates
- Never rely on client-side time for security decisions

### Remediation fixes
- Validate coupon validity using server-side timestamps
- Reject expired coupons regardless of client system time
- Centralize and harden discount validation logic

### Security best practices
- Treat client-side data as untrusted
- Implement server-side business logic checks
- Regularly audit promotional and discount mechanisms
- Follow OWASP recommendations for business logic security

---

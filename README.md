# OWASP Juice Shop – Write-ups

Write-ups de **45 challenges** de [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/), une application web volontairement vulnérable qui couvre l'OWASP Top 10 et au-delà.

Réalisé dans le cadre du module de sécurité de 1re année du Bachelor Epitech.

Chaque write-up suit la même structure : **méthodologie et outils**, **vulnérabilité**, **risques**, puis **actions correctives** (stratégies de mitigation, correctifs, bonnes pratiques).

> **Note :** contenu à but pédagogique, réalisé sur une instance locale de Juice Shop. Ne pas reproduire sur des systèmes sans autorisation.

## Sommaire

| Catégorie | Challenges (difficulté) |
|---|---|
| **Broken Access Control** | [Forged Feedback](<Broken Access Control-3-Forged Feedback.md>) ★★★<br>[Forged Review](<Broken Access Control-3-Forged Review.md>) ★★★<br>[Manipulate Basket](<Broken Access Control-3-Manipulate Basket.md>) ★★★<br>[Product Tampering](<Broken Access Control-3-Product Tampering.md>) ★★★<br>[Easter Egg](<Broken Access Control-4-Easter Egg.md>) ★★★★ |
| **Broken Anti Automation** | [CAPTCHA Bypass](<Broken Anti Automation-3-CAPTCHA Bypass.md>) ★★★ |
| **Broken Authentication** | [Bjoerns Favorite Pet](<Broken Authentication-3-Bjoerns Favorite Pet.md>) ★★★<br>[GDPR Data Erasure](<Broken Authentication-3-GDPR Data Erasure.md>) ★★★<br>[Reset Jims Password](<Broken Authentication-3-Reset Jims Password.md>) ★★★<br>[Login Bjoern](<Broken Authentication-4-Login Bjoern.md>) ★★★★<br>[Reset Benders Password](<Broken Authentication-4-Reset Benders Password.md>) ★★★★<br>[Change Benders Password](<Broken Authentication-5-Change Benders Password.md>) ★★★★★<br>[Reset Bjoerns Password](<Broken Authentication-5-Reset Bjoerns Password.md>) ★★★★★ |
| **Cross-Site Scripting** | [API-only XSS](<Cross-Site Scripting-3-API-only XSS.md>) ★★★<br>[Client-side XSS Protection](<Cross-Site Scripting-3-Client-side XSS Protection.md>) ★★★<br>[CSP Bypass](<Cross-Site Scripting-4-CSP Bypass.md>) ★★★★<br>[HTTP Header XSS](<Cross-Site Scripting-4-HTTP Header XSS.md>) ★★★★ |
| **Cryptographic Issues** | [Nested Easter Egg](<Cryptographic Issues-4-Nested Easter Egg.md>) ★★★★ |
| **Improper Input Validation** | [Admin Registration](<Improper Input Validation-3-Admin Registration.md>) ★★★<br>[Deluxe Fraud](<Improper Input Validation-3-Deluxe Fraud.md>) ★★★<br>[Payback Time](<Improper Input Validation-3-Payback Time.md>) ★★★<br>[Upload Size](<Improper Input Validation-3-Upload Size.md>) ★★★<br>[Upload Type](<Improper Input Validation-3-Upload Type.md>) ★★★<br>[Expired Coupon](<Improper Input Validation-4-Expired Coupon.md>) ★★★★<br>[Poison Null Byte](<Improper Input Validation-4-Poison Null Byte.md>) ★★★★ |
| **Injection** | [Database Schema](<Injection-3-Database Schema.md>) ★★★<br>[Login Bender](<Injection-3-Login Bender.md>) ★★★<br>[Login Jim](<Injection-3-Login Jim.md>) ★★★<br>[Christmas Special](<Injection-4-Christmas Special.md>) ★★★★<br>[User Credentials](<Injection-4-User Credentials.md>) ★★★★ |
| **Internationalization** | [Extra Language](<Internationalization-5-Extra Language.md>) ★★★★★ |
| **Privacy Policy Inspection** | [Privacy Policy Inspection](<Privacy Policy Inspection-3-Privacy Policy Inspection.md>) ★★★ |
| **Sensitive Data Exposure** | [Login Amy](<Sensitive Data Exposure-3-Login Amy.md>) ★★★<br>[Access Log](<Sensitive Data Exposure-4-Access Log.md>) ★★★★<br>[Forgotten Developer Backup](<Sensitive Data Exposure-4-Forgotten Developer Backup.md>) ★★★★<br>[Forgotten Sales Backup](<Sensitive Data Exposure-4-Forgotten Sales Backup.md>) ★★★★<br>[GDPR Data Theft](<Sensitive Data Exposure-4-GDPR Data Theft.md>) ★★★★<br>[Leaked Unsafe Product](<Sensitive Data Exposure-4-Leaked Unsafe Product.md>) ★★★★<br>[Misplaced Signature File](<Sensitive Data Exposure-4-Misplaced Signature File.md>) ★★★★<br>[Reset Uvogins Password](<Sensitive Data Exposure-4-Reset Uvogins Password.md>) ★★★★ |
| **Unvalidated Redirects** | [Allowlist Bypass](<Unvalidated Redirects-4-Allowlist Bypass.md>) ★★★★ |
| **Vulnerable Components** | [Vulnerable Library](<Vulnerable Components-4-Vulnerable Library.md>) ★★★★<br>[Unsigned JWT](<Vulnerable Components-5-Unsigned JWT.md>) ★★★★★<br>[Forged Signed JWT](<Vulnerable Components-6-Forged Signed JWT.md>) ★★★★★★ |
| **XXE** | [XXE Data Access](<XXE-3-XXE Data Access.md>) ★★★ |

## Outils

Burp Suite (Proxy, Repeater) · navigateur et console développeur

# Copilot Reviewer Quick Checklist – Studyportals Organisation

### 1. Code Quality

* [ ] Naming is clear, explicit, and uses granular namespaces.
* [ ] No global variables; global scope not polluted.
* [ ] Separation of concerns, cohesion, and SOLID principles applied.
* [ ] Functions follow single responsibility; unnecessary indirection avoided.
* [ ] Polymorphism is used where appropriate.
* [ ] Third-party libraries are encapsulated.
* [ ] Asynchronous calls have proper error handling.

---
### 2. Deprecating Code

* [ ] Deprecated code includes `@deprecated` comment with date, reason, and replacement.
* [ ] SCSS mixins or functions include deprecation warnings.

---
### 3. HTML & CSS/SCSS

* [ ] Semantic HTML5 and accessibility standards followed.
* [ ] No inline styles; classes and SCSS mixins used.
* [ ] SCSS is modular; related styles grouped in partials.
* [ ] Reusable styles use mixins, variables, or functions.
* [ ] Classes are scoped/namespaced.
* [ ] Numeric values, colors, breakpoints use variables/constants; no magic numbers.

---
### 4. Repository Documentation

* [ ] Repository purpose, features, capabilities, and architecture documented.
* [ ] Documentation accessible (README.md, docs/, or inline) and up to date.
* [ ] Setup, usage, and testing instructions are included and accurate.

---
### 5. Testing

* [ ] If core logic, APIs, or infra are modified, ensure appropriate tests exist or are updated.
* [ ] Behavior and regression points covered.
* [ ] Balance of black-box and white-box testing approaches.
* [ ] Infrastructure, SDK, API calls tested with mocks/stubs.
* [ ] Code is testable and maintainable.

---
### 6. Security

* [ ] Follows OWASP guidance and secure coding standards.
* [ ] No SQL Injection, XSS, CSRF vulnerabilities.
* [ ] No hardcoded secrets or credentials.
* [ ] Sensitive data anonymized or tokenized when needed.
* [ ] Data encrypted at rest and in transit.
* [ ] Error handling does not leak sensitive information.
* [ ] Least-privilege access enforced.
* [ ] Automated security scans run; vulnerabilities remediated.
* [ ] SDK/CDK and IAM policies follow least-privilege principles.
* [ ] Duplicated code detected and flagged.
* [ ] If dependency files are modified, ensure dependencies are stable, pinned,
        and reviewed for performance, security, and maintenance.



---
### 7. Performance & Efficiency

* [ ] No unnecessary computations, loops, or redundant operations.
* [ ] Memory usage and network calls minimized.
* [ ] Front-end optimized (avoid reflows/repaints, DOM optimized).
* [ ] Backend queries, caching, async operations efficient.
* [ ] Images, assets, bundles optimized for web performance.

---
### 8. Encryption & Data Handling

* [ ] Sensitive data encrypted in transit and at rest.
* [ ] Proper hashing, salting, and tokenization used.
* [ ] Credentials, API keys, secrets securely stored and accessed.
* [ ] Sensitive logs/error messages do not expose private info.

---
### 9. Maintainability & Documentation

* [ ] Deprecated functions, libraries, APIs not used.
* [ ] Validation, escaping, and security checks centralized.
* [ ] Code modular; follows Knowledge Vault architecture patterns.
* [ ] Inline documentation included where it improves readability and maintainability.

---
### 10. Review Output & Generic Instructions

* Include code snippets or examples for any detected issues.
* Explain reasoning briefly, so developers understand the why, not just the what.

---
## Review Scope (Mandatory)
* Review only files changed in this pull request
* Do NOT perform full-repository audits
* Flag issues only when they are directly observable in the diff

---
### 11. Reviewer Guidelines Preferences
* **Tone:** Professional
* **Response format:** Markdown
* **Level of detail:** High
---

# Copilot Reviewer Quick Checklist – Studyportals Organisation

### 1. Code Quality

* [ ] Naming is clear, explicit, and uses granular namespaces.
* [ ] No global variables; global scope not polluted.
* [ ] Separation of concerns, cohesion, and SOLID principles applied.
* [ ] Functions follow single responsibility; unnecessary indirection avoided.
* [ ] Polymorphism is used where appropriate.
* [ ] Third-party libraries are encapsulated.
* [ ] Asynchronous calls have proper error handling.
* [ ] Duplicated code detected and flagged.

---
### 2. HTML & CSS/SCSS

* [ ] Semantic HTML5 and accessibility standards followed.
* [ ] No inline styles; classes and SCSS mixins used.
* [ ] SCSS is modular; related styles grouped in partials.
* [ ] Reusable styles use mixins, variables, or functions.
* [ ] Classes are scoped/namespaced.
* [ ] Numeric values, colors, breakpoints use variables/constants; no magic numbers.

---
### 3. Repository Documentation

* [ ] Repository purpose, features, capabilities, and architecture documented.
* [ ] Documentation accessible (README.md, docs/, or inline) and up to date.
* [ ] Setup, usage, and testing instructions are included and accurate.

---
### 4. Testing

* [ ] Code covered by unit, integration, and end-to-end tests.
* [ ] Behavior and regression points covered.
* [ ] Balance of black-box and white-box testing approaches.
* [ ] Infrastructure, SDK, API calls tested with mocks/stubs.
* [ ] Code is testable and maintainable.

---
### 5. Security

* [ ] Follows OWASP guidance and secure coding standards.
* [ ] No SQL Injection, XSS, CSRF vulnerabilities.
* [ ] No hardcoded secrets, credentials, or API keys; all sensitive information is securely stored and accessed.
* [ ] Sensitive data anonymized or tokenized when needed.
* [ ] Error handling does not leak sensitive information.
* [ ] Least-privilege access enforced.
* [ ] Automated security scans run; vulnerabilities remediated.
* [ ] SDK/CDK and IAM policies follow least-privilege principles.
* [ ] Dependencies stable, pinned, and reviewed for performance/security/maintenance.

---
### 6. Performance & Efficiency

* [ ] No unnecessary computations, loops, or redundant operations.
* [ ] Memory usage and network calls minimized.
* [ ] Front-end optimized (avoid reflows/repaints, DOM optimized).
* [ ] Backend queries, caching, async operations efficient.
* [ ] Images, assets, bundles optimized for web performance.

---
### 7. Encryption & Data Handling

* [ ] Data encrypted at rest and in transit.
* [ ] Proper hashing, salting, and tokenization used.
* [ ] Sensitive logs/error messages do not expose private info.

---
### 8. Maintainability & Documentation

* [ ] Deprecated functions, libraries, APIs not used.
* [ ] Validation, escaping, and security checks centralized.
* [ ] Code modular.
* [ ] Deprecated code includes `@deprecated` comment with date, reason, and replacement.
* [ ] SCSS mixins or functions include deprecation warnings.

---
**Reviewer Guidelines**: Professional tone, Markdown responses, high level of detail.

---

# GitHub Copilot Guidance for Studyportals

## 1. Code Quality

- Use clear, explicit naming and granular namespaces.
- Apply separation of concerns, cohesion, and SOLID principles.
- Avoid unnecessary indirection and expose only needed interfaces.
- Prefer polymorphism for specialized behavior.
- Encapsulate third-party libraries.
- Restrict functions to a single responsibility.
- Follow **Clean Code** guidelines and refactor as needed.
- Wrap asynchronous calls with proper error handling.

---

## 2. Deprecating Code

- Add a `@deprecated` comment with date, reason, and replacement.

**PHP/JS Example:**
```javascript
/**
 * @deprecated 2025-12-16 - Use `something.someOtherKindOfFunctionality` instead
 */
function someKindOfFunctionality() {}
````

**SCSS Example:**

```scss
@mixin adjust-location($x, $y) {
  @warn "@deprecated `@mixin adjust-location($x, $y)` - Use new-location mixin instead";
}
```

---

## 3. HTML & CSS/SCSS Guidelines

* Follow semantic HTML5 markup and accessibility standards.
* Avoid inline styles; use classes and SCSS mixins.
* Keep SCSS modular; group related styles in partials.
* Use mixins, variables, and functions for reusable styles.
* Use `@warn` in SCSS to deprecate mixins instead of removing them immediately.
* Ensure CSS is responsive and works across supported devices and browsers.
* Minimize global styles; prefer scoped or namespaced classes.
* Avoid magic numbers; use variables or constants for dimensions, colors, and breakpoints.

---

## 4. Microservices & Packages

* Use templates: [Vue Template](https://github.com/studyportals/Template-Vuejs#vuejs-template), [Vue Platform](https://github.com/studyportals/Vue-Platform).
* Create DLL and non-DLL versions; keep object references versioned:

```javascript
entry: { some_package_v1: ["@studyportals/some-package/some-package.js"] }
entry: { some_package_v2: ["@studyportals/some-package/some-package.js"] }
```

* Analyze bundles with Webpack Bundle Analyzer.
* Load common dependencies appropriately per environment.

---

## 5. Testing

* Use unit, integration, and end-to-end tests.
* Cover both behavior and regression points.
* Balance black-box and white-box testing.
* Ensure infrastructure, SDK, and API calls are validated with mocks or stubs.
* Ensure code is testable and maintainable.

---

## 6. Secure Coding & Security Checks

* Follow OWASP guidance and secure programming standards.
* Avoid SQL Injection, XSS, CSRF, and other common vulnerabilities.
* Avoid hardcoding secrets or production credentials.
* Use anonymized or tokenized production data if needed.
* Encrypt sensitive data at rest and in transit.
* Handle errors securely; avoid leaking sensitive information.
* Enforce least-privilege access for systems, APIs, or credentials.
* Run automated security scans in CI/CD; remediate vulnerabilities before release.
* Ensure SDK/CDK resources and IAM policies follow least-privilege principles.
* Peer review all code; promote maintainable and documented coding conventions.
* Detect and refactor duplicated or copy-pasted code.
* Validate dependencies: use stable versions, remove unused packages, and pin versions where appropriate.

---

## 7. Maintainability & Documentation

* Replace deprecated functions, libraries, or APIs.
* Centralize validation, escaping, and security checks.
* Structure code modularly and follow architecture patterns from Knowledge Vault.
* Include inline documentation where it improves readability and maintainability.


# GitHub Copilot Guidance for Studyportals


## 1. Code Quality

* Verify that naming is clear, explicit, and uses granular namespaces.
* Avoid global variables and polluting the global scope; prefer encapsulation, modules, or namespaces.
* Check that separation of concerns, cohesion, and SOLID principles are applied.
* Ensure unnecessary indirection is avoided and only required interfaces are exposed.
* Confirm polymorphism is used appropriately for specialized behavior.
* Ensure third-party libraries are encapsulated.
* Check that functions adhere to a single responsibility.
* Verify adherence to **Clean Code** guidelines and confirm refactoring where necessary.
* Ensure asynchronous calls include proper error handling.

---

## 2. Deprecating Code

* Verify that deprecated code includes a @deprecated comment including date, reason, and replacement.

**PHP/JS**
```javascript
/**
 * @deprecated 2025-12-16 - Use `something.someOtherKindOfFunctionality` instead
 */
function someKindOfFunctionality() {}
```

**SCSS**

```scss
@mixin adjust-location($x, $y) {
  @warn "@deprecated `@mixin adjust-location($x, $y)` - Use new-location mixin instead";
}
```

---

## 3. HTML & CSS/SCSS Guidelines

* Verify semantic HTML5 markup and adherence to accessibility standards.
* Ensure inline styles are avoided; classes and SCSS mixins are used for styling.
* Check that SCSS is modular and related styles are grouped in partials.
* Confirm mixins, variables, and functions are used for reusable styles.
* Ensure classes are scoped or namespaced to prevent style collisions.
* Verify that numeric values, colors, and breakpoints use variables or constants; avoid hardcoded “magic numbers” to ensure maintainability and consistency.

---

## 4. Repository Documentation

* Each repository must include documentation that clearly describes:
    - The repository’s purpose and intended use.
    - Key features and capabilities.
    - Implementation details, architecture, and important design decisions.
* Documentation should be accessible (e.g., in a `README.md`, `docs/` folder, or inline code comments) and kept up to date with changes.
* Include examples or instructions for setup, usage, and testing where applicable.

---

## 5. Testing

* Verify that the code is covered by unit, integration, and end-to-end tests where applicable.
* Check that both behavior and regression points are covered.
* Ensure a balance of black-box and white-box testing approaches.
* Confirm infrastructure, SDK, and API calls are tested using mocks or stubs.
* Verify that the code is testable and maintainable.

---

## 6. Secure Coding & Security Checks

* Verify that code follows OWASP guidance and secure programming standards.
* Check that code avoids common vulnerabilities such as SQL Injection, XSS, and CSRF.
* Confirm that secrets or credentials are not hardcoded.
* Ensure anonymized or tokenized data is used when needed.
* Check that sensitive data is encrypted at rest and in transit.
* Ensure error handling does not leak sensitive information.
* Verify least-privilege access is enforced for systems, APIs, and credentials.
* Confirm that automated security scans are run in CI/CD and vulnerabilities are remediated before release.
* Check that SDK/CDK resources and IAM policies follow least-privilege principles.
* Detect and flag duplicated or copy-pasted code across the repository.
* Validate dependencies: stable versions, no wildcards (`*`), unused packages removed, and versions pinned where appropriate.
* Recommend security-aware dependency updates and patching policies.

---

## 7. Maintainability & Documentation

* Verify that deprecated functions, libraries, or APIs are not used.
* Check that validation, escaping, and security checks are centralized where appropriate.
* Ensure code is modular and follows architecture patterns from the Knowledge Vault.
* Confirm that inline documentation is included where it improves readability and maintainability.


## Reviewer Guidelines Preferences
- **Tone:** Professional
- **Response format:** Markdown
- **Level of detail:** High

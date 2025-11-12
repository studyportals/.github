# Code Review and Security Audit Instructions — Version 1

## Goals

### 1. Enforce Company-Wide Good Practices and Quality Standards
Refer to the [Knowledge-Vault repository](https://github.com/studyportals/Knowledge-Vault/tree/master/good-practices-and-quality-standards).

Include all `.md` files under this path and apply guidance for:
- **Infrastructure:** CDK, cloud resources, IAM
- **Security practices**
- **Testing standards and coverage**
- **Code quality and maintainability**


### 2. Identify Security Issues in Repositories
Focus on detecting and mitigating:
- **SQL Injection** or other injection vulnerabilities
- **Cross-Site Scripting (XSS)** or similar frontend/backend vulnerabilities
- **IAM misconfigurations** and excessive privileges
- **Hardcoded secrets** or sensitive information
- **Debug information leaks** or verbose logging
- **CSRF** or other common web vulnerabilities


### 3. Validate Least-Privilege IAM and SDK/CDK Usage
- Detect overly broad policies (e.g., `"Action": "*"` or `"Resource": "*"`).
- Ensure SDK and CDK resources follow the **principle of least privilege**.
- Ensure environment variables, secrets, and credentials are handled securely.


### 4. Ensure All Repositories Have Adequate Tests
Testing should cover both infrastructure and application logic:
- Infrastructure stack assertions, integration, and unit tests.
- SDK or API calls properly mocked/stubbed in unit tests.
- Adequate **unit** and **integration test coverage** for application code.


### 5. Promote Secure, Maintainable, and Documented Coding Conventions
- Follow naming, modularity, and architecture patterns from **Knowledge-Vault**.
- Replace **deprecated functions, libraries, or APIs**.
- Apply **structured error handling** and logging.
- Centralize validation, escaping, and security checks.
- Detect and refactor **duplicated or copy-pasted code**:
    - Encourage reuse via shared functions, modules, or libraries.
    - Highlight repeated patterns that may indicate missing abstractions.

### 6. Validate Dependencies and Runtime Environments
- Ensure all **packages/dependencies** use **stable versions** (avoid alpha/beta unless justified).
- Identify and flag **unnecessary or unused packages**.
- Validate that **runtime or engine versions** (Node.js, Python, Java, etc.) match the organization’s approved standards.
- Ensure manifest files (`package.json`, `requirements.txt`, `pom.xml`, etc.) follow best practices:
    - Pin versions where appropriate.
    - Avoid wildcard (`*`) version specifications unless required.
    - Detect conflicting versions across dependencies.
- Recommend **security-aware dependency updates** and patching policies.


## Preferences
- **Tone:** Professional
- **Response format:** Markdown
- **Level of detail:** High  

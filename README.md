# Studyportals
## About Studyportals
Studyportals is the global study choice platform. Since its inception,
it was founded to solve student problems, with a strong belief
in the value of international experiences – both for individual students and society at large.

[Come work for us](https://studyportals.com/careers/)

# .github Repository

This repository contains GitHub Actions workflows that automate
key tasks related to security, code quality, and repository maintenance
for the Studyportals organization. The workflows include:

- **CodeQL Analysis**: Automatic security and code quality scanning using CodeQL.
- **Dependency Scanning**: Monitoring project dependencies for vulnerabilities.
- **Goldeneye** A CI/CD pipeline generator.
- **Linting**: Ensuring code quality by running linters for various languages.
- **Stale Bot**: Automatically managing stale issues and pull requests.

## Workflows

### 1. CodeQL Analysis
The **CodeQL Analysis** workflow automatically scans the codebase for security vulnerabilities
and code quality issues using GitHub's CodeQL. It is triggered on `push` and
`pull_request` events, and can also be scheduled for regular analysis.

- **Trigger:** `push`, `pull_request`, and scheduled runs (e.g., every Monday at 7 AM).
- **Languages analyzed:** JavaScript, TypeScript, Python, and others.
- **Custom queries:** Configurable CodeQL queries for additional security checks.

**Configuration:**
The workflow uses a reusable GitHub Actions setup to run CodeQL analysis.
You can customize the analysis by specifying the languages you want to analyze.
Additional configuration options can be defined in the `codeql-config.yml` file, 
placed in the `.github/workflows/` directory of the repository.


### 2. Dependency Scanning
The **Dependency Scanning** workflow ensures that the project's dependencies
are free of known vulnerabilities. 

- **Trigger:** `push` and `pull_request` events.
- **Action:** Automatically checks for outdated dependencies or vulnerabilities in the dependency tree.

### 3. Goldeneye
The **Goldeneye workflow** is a CI/CD pipeline generator that automates the creation of pipelines.

**Trigger**: `push`, `pull_request`, and manual triggers.

**Action**: Automatically creates CI/CD pipelines for deployment or testing.

**Configuration**:
Customize the goldeneye.json configuration in the workflow file for service names, AWS accounts, and regions.


### 3. Linting
The **Linting** workflow ensures the code adheres to predefined coding standards
and best practices. It runs linters for various languages like PHP,JavaScript, TypeScript,
Python, etc., based on the project's needs.

- **Trigger:** `push`, `pull_request`, and manual triggers.
- **Tools used:** ESLint for JavaScript/TypeScript, Flake8 for Python, and more.
- **Action:** Linting is automatically run whenever code is pushed to the
  repository or when a pull request is made.

### 4. Stale Bot
The **Stale Bot** workflow helps keep the repository clean by automatically
marking issues and pull requests as stale if they have not had activity
for a specified period. This helps the team focus on active issues and PRs.

- **Trigger:** On a schedule (e.g., daily or weekly).
- **Action:** Automatically marks issues or PRs as "stale" if no activity has occurred in the last 30 days.
- **Configuration:** Can be customized to change the inactivity period, labels, and more.

## Setup Instructions

This repository is intended to be used as part of a larger project. To use the workflows in your own project:

1. Create the `.github` directory into your repository.
2. Customize any workflows based on your specific needs (e.g., language versions, linting rules, etc.)
   See Portal repository for examples.
    - You can copy the workflow files from this repository to your own repository.
    - Make sure to adjust any paths or configurations as necessary.
3. Modify any settings in the workflows to match the project requirements (e.g., configuring the
   dependency scanning tool to scan your specific dependency manager)
4. Push the changes to your repository, and the workflows will automatically run based on their triggers.
5. Make the GitHub checks required if needed.

## Workflow Overview

| Workflow Name           | Trigger Events                    | Description                                                          |
|-------------------------|-----------------------------------|----------------------------------------------------------------------|
| **CodeQL Analysis**     | `push`, `pull_request`, schedule  | Scans the code for security vulnerabilities and code quality issues. |
| **Dependency Scanning** | `push`, `pull_request`            | Scans dependencies for known vulnerabilities.                        |
| **Goldeneye**           | `push`, `pull_request`, manual    | Creates CI/CD piplines                                               |
| **Linting**             | `push`, `pull_request`, manual    | Runs linters for various languages to ensure code quality.           |
| **Stale Bot**           | Scheduled (e.g., daily, weekly)   | Marks issues/PRs as stale if there has been no activity.             |


## Customizing Workflows

### CodeQL Analysis
You can customize which languages are analyzed by modifying the `languages` input in the workflow file.
You can also customize the CodeQL queries being run.

NOTE: When adding the CodeQL workflow to a repository for the first time, the workflow might not
report results. You may see the following message in the [checks](./images/CodeQLTroubleshooting.png)

To resolve this issue, run the following commands in Git Bash or WSL terminal:
```bash
gh api -H "Accept: application/vnd.github+json" ./repos/<OrganisationName>/<RepositoryName>/code-scanning/analyses --paginate | jq '.[]|select(.category=="/language:actions") | .id ' | sed 's/\r//' | xargs -I {} gh api --method DELETE -H "Accept: application/vnd.github+json" -H "X-GitHub-Api-Version: 2022-11-28" /repos/<OrganisationName>/<RepositoryName>/code-scanning/analyses/{}?confirm_delete

gh api -H "Accept: application/vnd.github+json" ./repos/<OrganisationName>/<RepositoryName>/code-scanning/analyses --paginate | jq '.[]|select(.category=="/language:javascript-typescript") | .id ' | sed 's/\r//' | xargs -I {} gh api --method DELETE -H "Accept: application/vnd.github+json" -H "X-GitHub-Api-Version: 2022-11-28" /repos/<OrganisationName>/<RepositoryName>/code-scanning/analyses/{}?confirm_delete

```
Make sure to replace `<OrganisationName>` and `<RepositoryName>` with the actual names , and adjust the
`category` value to match the one displayed in your repository's checks.

**Important Notes:**
* The CodeQL Analysis workflow itself will typically show as successful, even if vulnerabilities are detected.
* A separate line item—`Code scanning results / CodeQL`—will display the actual results of the CodeQL scan.
* By default, this check will only report a failure if high or critical severity issues are found.
* You can customize this behavior to fail the check on any level of issue, including medium, low severity or warnings.
* CodeQL errors and warnings are displayed directly on the pull request, along with GitHub Copilot suggestions to help fix the issue.

### Goldeneye
You can customize which aws accounts, regions service names in the `goldeneye.json` input in the workflow file.
Check the specific configuration in the workflow file.

### Dependency Scanning
You can enable or configure the **dependency scanning** to use different tools like `npm audit`, `yarn audit`,
or any other security tools. Check the specific configuration in the workflow file.

### Linting
You can add more linters, configure existing ones, or change the linter rules by
modifying the `.github/workflows/lint.yml` file.

### Stale Bot
You can modify the settings in the stale bot workflow to change how often the bot runs
and which labels it should apply when marking issues or PRs as stale.
The bot's inactivity timeout can also be adjusted.

## PULL_REQUEST_TEMPLATE.md
The repository also includes a `PULL_REQUEST_TEMPLATE.md` file that can be used
to standardize pull requests across repositories within the organization. This template
ensures that pull requests are well-structured and provide all necessary information for reviewers.

* **Purpose:** The template helps contributors provide details such as the problem being solved,
  the approach taken, and any additional information that may be relevant.

* **Customization:** You can modify the template to suit your team's specific needs,
  such as including sections for testing instructions, related issues, or feature documentation.

This template ensures that every pull request provides clarity on what changes are
being made and why, helping maintain consistency and improving communication across your team.



## Contributing

Feel free to fork this repository, modify the workflows, and submit pull requests.
If you want to improve or add additional workflows, such as testing, deployment,
or notifications, feel free to open an issue or PR.

NOTE: You can find examples of the custom workflow in the Portal repository
under the `.github/workflows` directory.

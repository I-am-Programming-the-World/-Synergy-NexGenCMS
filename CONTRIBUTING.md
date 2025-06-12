# Contributing to Synergy-NexGenCMS

First and foremost, thank you for considering a contribution to Synergy-NexGenCMS. Open-source projects like this thrive on the collaborative spirit of the community, and every contribution, no matter how small, is deeply valued. Whether you're fixing a typo, reporting a bug, suggesting a feature, or writing a new module, you are helping to make this project better for everyone.

This document provides a comprehensive set of guidelines to ensure that contributing to Synergy-NexGenCMS is a smooth and effective process for everyone involved. These are not rigid rules but rather best practices that help maintain the quality and integrity of the project. Please use your best judgment, and feel free to propose changes to this document in a pull request if you see an opportunity for improvement.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Submitting a Pull Request](#submitting-a-pull-request)
- [Development Setup](#development-setup)
- [Style Guides](#style-guides)
  - [Git Commit Messages](#git-commit-messages)
  - [PHP Style](#php-style)
  - [JavaScript Style](#javascript-style)
  - [Documentation Style](#documentation-style)
- [Pull Request Review Process](#pull-request-review-process)
- [Community & Getting Help](#community--getting-help)

---

## Code of Conduct

This project and everyone participating in it is governed by the [Synergy-NexGenCMS Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code to help foster an open, welcoming, and inclusive environment. Please report any unacceptable behavior to the project maintainers.

---

## How Can I Contribute?

There are many ways to contribute to the project, and all are valuable.

### Reporting Bugs

A well-documented bug report is the first step to fixing a problem. Before submitting a new issue, please take a moment to **search the existing issues** to see if the bug has already been reported.

When creating a bug report, please provide a complete and detailed overview of the problem. A high-quality bug report should include:

- **A clear and descriptive title** that summarizes the issue.
- **A detailed, step-by-step description** of how to reproduce the bug.
- **The exact version of Synergy-NexGenCMS** you are using (e.g., `v1.2.3`).
- **A thorough description of the environment**, including your PHP version, database type and version (e.g., MySQL 8.0), web server, operating system, and browser.
- **Any relevant error messages, stack traces, or logs**, pasted within a code block.
- **Screenshots or GIFs** that visually demonstrate the issue can be incredibly helpful.

### Suggesting Enhancements

If you have an idea for a new feature or an improvement to an existing one, we'd love to hear about it. To ensure your suggestion is effective, please check the [GitHub issues](https://github.com/your-username/Synergy-NexGenCMS/issues) and the project's [Roadmap](#roadmap) in the `README.md` to see if your idea has already been discussed.

When submitting an enhancement suggestion, please:

1.  Create a new issue on GitHub using the "Feature Request" template.
2.  Provide a clear and descriptive title.
3.  Give a detailed description of the proposed enhancement.
4.  Explain the "why" — the use case or problem this enhancement solves. Why would this be useful to most Synergy-NexGenCMS users?
5.  Include any relevant mockups, code examples, or screenshots to help illustrate your idea.

### Submitting a Pull Request

Code contributions are made via Pull Requests (PRs). We welcome PRs for everything from minor typo fixes to major new features.

1.  **Fork the Repository:** Start by forking the `Synergy-NexGenCMS` repository to your own GitHub account.
2.  **Create a Feature Branch:** From the `main` branch of your fork, create a new branch that describes the feature or fix.
    ```sh
    # Branch names should be descriptive, e.g., feat/user-profile-avatars or fix/login-csrf-issue
    git checkout -b your-branch-name
    ```
3.  **Make Your Changes:** Implement your code changes within your feature branch. Ensure your code adheres to the project's style guides.
4.  **Update Documentation:** If you are adding or changing a feature, please update the relevant documentation within the `/docs` directory. Good documentation is as important as the code itself.
5.  **Add Tests:** If applicable, add unit or integration tests to cover your changes. Our goal is to maintain a high level of test coverage.
6.  **Ensure All Tests Pass:** Run the full test suite locally to ensure your changes haven't introduced any regressions.
7.  **Commit Your Changes:** Commit your changes using a descriptive commit message that follows our [commit message style guide](#git-commit-messages).
    ```sh
    git commit -m "feat(profiles): Allow users to upload custom avatars"
    ```
8.  **Push to Your Branch:** Push your feature branch to your forked repository.
    ```sh
    git push origin your-branch-name
    ```
9.  **Open a Pull Request:** From your fork on GitHub, open a pull request to the `main` branch of the original `Synergy-NexGenCMS` repository.
10. **Describe Your PR:** Provide a clear title and a detailed description of your changes. If your PR resolves an existing issue, link it using keywords like `Fixes #123`.

---

## Development Setup

To get your local development environment configured, please follow the detailed instructions in the [Getting Started](#getting-started) section of the `README.md` file. This will guide you through installing all necessary prerequisites, cloning the repository, and setting up your local server and database.

---

## Style Guides

To maintain a consistent and high-quality codebase, we adhere to the following style guides. Automated tools are configured to enforce most of these rules, which simplifies the contribution process.

### Git Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification. This provides a clean, readable history and allows us to automate changelog generation.

-   **Format:** A commit message should be structured as follows:
    ```
    <type>(<scope>): <subject>
    <BLANK LINE>
    <body>
    <BLANK LINE>
    <footer>
    ```
-   **Header:** The header is mandatory and includes:
    -   `type`: Must be one of `feat` (new feature), `fix` (bug fix), `docs` (documentation), `style` (formatting), `refactor` (code restructuring), `perf` (performance improvement), `test` (adding or fixing tests), or `chore` (build tasks, etc.).
    -   `scope` (optional): The part of the codebase affected (e.g., `api`, `auth`, `admin`).
    -   `subject`: A concise description of the change, in the imperative mood (e.g., "add," "fix," not "added," "fixes").
-   **Body** (optional): Provides additional context, explaining the "what" and "why" of the change.
-   **Footer** (optional): Used for referencing issue numbers (e.g., `Fixes #123`) and noting breaking changes (`BREAKING CHANGE:`).

**Example:**

feat(api): add user profile endpoint

The new endpoint at /api/v1/users/{id} allows for fetching
user profile data. This is required for the new frontend profile
page.

Fixes #42


### PHP Style

All PHP code must strictly adhere to the [PSR-12](https://www.php-fig.org/psr/psr-12/) coding style guide. We use `PHP-CS-Fixer` to enforce this.

-   **Formatting:** Before committing, run the following command to automatically format your PHP files:
    ```sh
    ./vendor/bin/php-cs-fixer fix
    ```
-   **Strict Types:** All PHP files should start with `declare(strict_types=1);`.
-   **Type Hinting:** All method/function arguments, return types, and class properties (where supported) must have type hints. Use `mixed` or union types where appropriate.
-   **PHPDoc Blocks:** All classes, methods, and functions must have comprehensive PHPDoc blocks. This includes a short description, long description (if necessary), and annotations like `@param`, `@return`, and `@throws`.

### JavaScript Style

We use a combination of **Prettier** for code formatting and **ESLint** for code quality and analysis.

-   **Formatting:** Prettier is configured to run automatically. You can also trigger it manually:
    ```sh
    npm run format
    ```
-   **Linting:** ESLint helps catch common errors and enforce best practices. Before committing, check your code for any linting issues:
    ```sh
    npm run lint
    ```
-   **Best Practices:** We encourage the use of modern JavaScript (ES6+), such as `const` and `let` over `var`, arrow functions, and async/await for asynchronous operations.

### Documentation Style

Clear and accurate documentation is crucial.

-   **Language:** Write in a clear, concise, and professional tone. Use active voice and write for an international audience (avoid slang or overly colloquial language).
-   **Formatting:** Use standard Markdown. Keep lines reasonably short (80-100 characters) to improve readability in plain text editors.
-   **Code Examples:** All code examples should be complete, runnable, and easy to understand. They should be enclosed in fenced code blocks with the correct language identifier (e.g., ` ```php ` or ` ```js `).

---

## Pull Request Review Process

Once you submit a pull request, a project maintainer will review your changes. The review process typically involves:
1.  **Initial Triage:** A maintainer will assign relevant labels and potentially a reviewer.
2.  **Automated Checks:** GitHub Actions will run automatically to check for linting errors, run the test suite, and ensure code style adherence. Make sure these checks pass.
3.  **Code Review:** A maintainer will review your code for correctness, performance, and adherence to best practices. They may leave comments or request changes. Please be responsive to feedback and be prepared to discuss your implementation.
4.  **Approval and Merge:** Once all feedback has been addressed and the PR is approved, a maintainer will merge your changes into the `main` branch.

Thank you for your patience and collaboration during the review process!

---

## Community & Getting Help

If you have questions about contributing or get stuck on a particular issue, the best place to ask is on our [GitHub Discussions](https://github.com/your-username/Synergy-NexGenCMS/discussions) page. This is the central place for community members to help one another and discuss the project.

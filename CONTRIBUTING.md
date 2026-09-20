# Contributing to GraphQL Security Hub

First of all, thank you for your interest in contributing to **GraphQL Security Hub**.

GraphQL Security Hub is an open-source, community-driven knowledge base focused on **GraphQL security testing, reconnaissance, payloads, vulnerabilities, methodology, labs, and real-world security patterns**.

Anyone can contribute. You do not need to be a security researcher, professional pentester, or GraphQL expert to contribute.

If your contribution is useful, accurate, and properly documented, we would love to have it here.

---

## What Can You Contribute?

You can contribute to almost any part of the project.

### Payloads

Add useful GraphQL security payloads related to:

```text
Introspection
Discovery
Queries
Mutations
Authorization
IDOR
Field-Level Access
Aliases
Batching
CSRF
Injection
Rate Limiting
```

Every payload should explain **why it is useful** and **what a tester should observe**.

---

### Dictionaries

You can improve or expand:

```text
Dictionaries/
├── mutations.md
├── types.md
├── arguments.md
├── fields.md
├── input-types.md
└── identifiers.md
```

Examples:

* New mutation names.
* New type names.
* New argument names.
* New sensitive fields.
* New input types.
* New object identifiers.

Please avoid adding random words just to increase the size of a dictionary.

---

### Methodology

You can contribute testing methodologies for:

* GraphQL reconnaissance.
* Endpoint discovery.
* Schema discovery.
* Authorization testing.
* IDOR testing.
* Field-level authorization testing.
* Input handling.
* Injection testing.
* Alias and batching testing.
* Rate-limit testing.
* Error analysis.

---

### Labs

You can contribute practical GraphQL security labs.

A good lab should contain:

1. Lab objective.
2. Setup/context.
3. Reconnaissance.
4. Attack surface.
5. Vulnerability identification.
6. Exploitation.
7. Why it works.
8. Impact.
9. Verification.
10. Root cause.
11. Takeaway.

Labs should be designed for **legal and educational environments**.

---

### Examples

You can contribute realistic GraphQL examples such as:

```text
E-commerce
Blog
Social platform
SaaS application
Authentication system
Admin panel
Organization / tenant system
```

Examples can demonstrate how GraphQL functionality can introduce security problems when authorization or input validation is implemented incorrectly.

---

### Documentation

You can also improve existing documentation.

Examples:

* Fixing inaccurate information.
* Improving explanations.
* Adding missing security context.
* Fixing grammar or formatting.
* Adding useful examples.
* Improving navigation.
* Adding references.

Small documentation fixes are welcome.

---

# How to Contribute

The basic contribution workflow is:

```text
Fork Repository
      ↓
Clone Repository
      ↓
Create Branch
      ↓
Make Changes
      ↓
Test / Review
      ↓
Commit Changes
      ↓
Push Branch
      ↓
Open Pull Request
      ↓
Review
      ↓
Merge
```

---

# 1. Fork the Repository

Fork this repository to your own GitHub account.

Your fork will become your personal copy of the project where you can make changes safely.

---

# 2. Clone Your Fork

Clone your fork to your local machine.

```bash
git clone https://github.com/<your-username>/graphql-security-hub.git
cd graphql-security-hub
```

---

# 3. Create a Branch

Create a separate branch for your contribution.

Example:

```bash
git checkout -b add-graphql-payloads
```

Other examples:

```bash
git checkout -b improve-idor-methodology
git checkout -b add-mutation-dictionary
git checkout -b add-graphql-lab
git checkout -b fix-documentation
```

Avoid doing your work directly on the `main` branch.

---

# 4. Make Your Changes

Add or modify the relevant files.

For example:

```text
Payloads/
Dictionaries/
Methodology/
Labs/
Examples/
```

Keep changes focused.

If you are adding an IDOR payload, avoid mixing unrelated documentation changes into the same Pull Request.

---

# 5. Review Your Contribution

Before submitting, check:

```text
[ ] Is the information technically accurate?
[ ] Is the payload actually relevant to GraphQL security?
[ ] Is the purpose of the payload explained?
[ ] Is the security impact explained?
[ ] Are examples valid?
[ ] Is the Markdown formatting correct?
[ ] Are there duplicate entries?
[ ] Are links/references working?
[ ] Is the contribution limited to authorized/educational testing?
```

---

# 6. Commit Your Changes

Use a clear commit message.

Example:

```bash
git add .
git commit -m "Add GraphQL authorization payloads"
```

Other examples:

```text
Add mutation dictionary entries
Add GraphQL IDOR methodology
Add batching security examples
Fix introspection documentation
Add authorization lab
```

---

# 7. Push Your Branch

```bash
git push origin add-graphql-payloads
```

Replace the branch name with your own branch name.

---

# 8. Open a Pull Request

Go to your GitHub fork and open a **Pull Request** against the original repository's `main` branch.

Your Pull Request should explain:

### What did you add or change?

Example:

```text
Added a collection of GraphQL authorization-testing
payloads and documented what each payload is intended
to test.
```

### Why is it useful?

Example:

```text
These examples help testers identify potential
object-level and field-level authorization issues.
```

### Testing / Verification

Explain how you verified the contribution.

For example:

```text
Tested against a local GraphQL lab application.
```

---

# Pull Request Guidelines

Please keep Pull Requests:

* Focused.
* Technically accurate.
* Well documented.
* Easy to review.
* Free from unnecessary changes.

One Pull Request should ideally solve one problem or add one logical feature.

---

# Payload Contribution Format

When adding a new security payload, use this structure when appropriate:

````markdown
## Title

### Payload

```graphql
<your payload>
````

### Purpose

Explain what the payload is intended to test.

### What to Observe

Explain what changes in the response may indicate.

### Security Relevance

Explain which security property is being tested.

### Example

Provide a safe example using a local lab or authorized environment.

### Notes

Add limitations, assumptions, or implementation-specific behavior.

### References

Add relevant documentation, research, or lab references.

````

The exact format can be adapted depending on the type of payload.

---

# Dictionary Contribution Guidelines

When adding dictionary entries:

### Do

```text
Use realistic GraphQL terminology.
Group related entries logically.
Remove obvious duplicates.
Add security-relevant terms where appropriate.
````

### Don't

```text
Add random words.
Add thousands of low-quality guesses.
Duplicate existing entries.
Add unrelated application-specific data.
```

The goal is **useful reconnaissance**, not simply creating the largest possible wordlist.

---

# Lab Contribution Guidelines

Labs should be:

* Reproducible.
* Educational.
* Clearly documented.
* Focused on one or more security concepts.
* Safe to run locally or in an authorized environment.

Whenever possible, include:

```text
Setup
Objective
Recon
Attack
Why it works
Impact
Root cause
Fix / mitigation
```

Do not submit labs that require attacking real third-party systems.

---

# Real-World Research

Real-world research can be valuable to the project.

If you document a vulnerability discovered in a real application:

* Only test systems where you have explicit authorization.
* Follow the target's bug bounty / security policy.
* Do not expose sensitive information.
* Do not publish credentials, tokens, personal data, or private source code.
* Follow responsible disclosure practices.
* Prefer sanitized examples when publishing technical details.

GraphQL Security Hub is an educational project and **does not provide authorization to test third-party systems**.

---

# Responsible Disclosure

Do **not** use this repository to publicly disclose an unpatched vulnerability in a real organization without following an appropriate disclosure process.

If you discover a vulnerability:

```text
1. Verify the issue safely.
2. Check the organization's security policy.
3. Report it through the official security channel.
4. Allow reasonable time for remediation.
5. Publish details only when appropriate.
```

Sensitive information should never be committed to the repository.

This includes:

```text
Passwords
API keys
Access tokens
Session tokens
Private keys
Personal information
Internal credentials
Private URLs
Production secrets
```

If accidentally exposed, remove it immediately and notify the maintainers.

---

# Security Testing Rules

Contributions must be intended for:

```text
Local environments
CTF/lab environments
Authorized penetration tests
Bug bounty programs
Systems where you have explicit permission
```

Do not use this repository as a guide to attack systems without authorization.

---

# Quality Standards

A contribution may be reviewed for:

### Accuracy

Does the technical information correctly describe GraphQL behavior?

### Relevance

Is the content useful for GraphQL security testing?

### Reproducibility

Can another researcher understand and reproduce the technique in an authorized environment?

### Documentation

Does the contribution explain the purpose and security implications?

### Safety

Does the contribution avoid exposing sensitive information or facilitating unauthorized targeting?

### Maintainability

Is the content organized consistently with the rest of the repository?

---

# Community Standards

Please keep discussions and Pull Requests respectful and constructive.

We welcome contributors with different levels of experience.

You can:

* Ask questions.
* Suggest improvements.
* Correct mistakes.
* Propose new research.
* Review Pull Requests.
* Improve existing documentation.

You do not need to be an expert to contribute.

---

# Contribution Review

Pull Requests may go through the following process:

```text
Submission
    ↓
Maintainer Review
    ↓
Technical Review
    ↓
Requested Changes (if necessary)
    ↓
Approval
    ↓
Merge
```

Maintainers may request changes before a contribution is accepted.

Not every submission will necessarily be merged.

The goal is to maintain a **high-quality and useful GraphQL security knowledge base**.

---

# Attribution

If your contribution is accepted, you may be credited through the Git history and/or project documentation.

When contributing material based on someone else's research, always provide appropriate attribution and references.

Do not copy copyrighted content without permission.

---

# Getting Help

If you are unsure about something before opening a Pull Request, you can open a GitHub Issue and describe:

```text
What you want to contribute
What security concept it covers
What you have tested
What you are unsure about
```

The community and maintainers can help review the idea.

---

# Thank You

Every contribution helps improve the GraphQL security community.

Whether you contribute:

```text
1 payload
1 dictionary entry
1 bug fix
1 lab
1 methodology
1 research article
```

or a large feature, your contribution can help another security researcher learn something new.

**Thank you for contributing to GraphQL Security Hub.**

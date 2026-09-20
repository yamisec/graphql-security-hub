# graphql-security-hub

An open-source **GraphQL security knowledge base, payload library, reconnaissance dictionary, testing methodology, practical labs, and community-driven research project**.

This project aims to build a centralized resource for security researchers, penetration testers, bug bounty hunters, students, and developers who want to understand and test GraphQL security in authorized environments.

---

## Project Goals

GraphQL introduces a different attack surface compared to traditional REST APIs.

Instead of relying on many predictable endpoints, GraphQL applications often expose functionality through a centralized GraphQL endpoint where queries, mutations, fields, arguments, input objects, and relationships determine what the client can access or modify.

This project aims to document that attack surface in a practical and security-focused way.

### Main goals

* Build a structured GraphQL security knowledge base.
* Collect useful GraphQL security payloads.
* Maintain reconnaissance dictionaries.
* Document practical testing methodologies.
* Create reproducible GraphQL security labs.
* Document common vulnerability patterns.
* Share real-world research and security observations.
* Help researchers understand GraphQL from an offensive-security perspective.
* Build a community-driven resource that anyone can contribute to.

---

# What's Inside?

```text
graphql-security-hub/
│
├── Dictionaries/
│   ├── arguments.md
│   ├── fields.md
│   ├── identifiers.md
│   ├── input-types.md
│   ├── mutations.md
│   └── types.md
│
├── Checklist/
│
├── Examples/
│
├── Labs/
│
├── Methodology/
│
├── Payloads/
│
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

Each section has a different purpose.

---

# Dictionaries

The `Dictionaries/` directory contains common GraphQL names and identifiers useful during reconnaissance.

### Available dictionaries

| Dictionary       | Purpose                           |
| ---------------- | --------------------------------- |
| `arguments.md`   | Common GraphQL argument names     |
| `fields.md`      | Common GraphQL field names        |
| `identifiers.md` | Object/resource identifiers       |
| `input-types.md` | Common GraphQL input object names |
| `mutations.md`   | Common mutation names             |
| `types.md`       | Common GraphQL type/object names  |

These dictionaries are intended to help researchers identify potentially interesting functionality when the complete schema is unavailable, partially exposed, or requires additional discovery.

---

# Payloads

The `Payloads/` directory contains practical GraphQL security testing payloads.

Planned categories include:

```text
Payloads/
├── Introspection/
├── Discovery/
├── Queries/
├── Mutations/
├── Authorization/
├── IDOR/
├── Field-Access/
├── Aliases/
├── Batching/
├── CSRF/
├── Injection/
└── Rate-Limiting/
```

Payloads should not simply be listed without context.

Where appropriate, each payload should explain:

* What it does.
* Why it is useful.
* What part of GraphQL it targets.
* What a tester should observe.
* What security issue it may help identify.
* Any important limitations.
* How it can be reproduced safely.

---

# Reconnaissance

GraphQL security testing starts with understanding the application's exposed functionality.

Recon may include:

```text
Endpoint Discovery
        ↓
GraphQL Confirmation
        ↓
Schema Discovery
        ↓
Query Discovery
        ↓
Mutation Discovery
        ↓
Type Discovery
        ↓
Field Discovery
        ↓
Argument Discovery
        ↓
Identifier Discovery
        ↓
Relationship Mapping
```

The repository aims to provide resources for each stage.

---

# Security Testing Areas

GraphQL Security Hub focuses on security issues and testing patterns such as:

### Schema & Introspection

* Introspection exposure.
* Partial schema exposure.
* Schema discovery.
* Query/mutation discovery.
* Hidden functionality discovery.

### Authentication & Authorization

* Authentication boundaries.
* Query-level authorization.
* Mutation authorization.
* Object-level authorization.
* Field-level authorization.
* Horizontal privilege issues.
* Vertical privilege issues.

### IDOR / Object-Level Access

Testing identifiers such as:

```text
userId
accountId
organizationId
projectId
postId
orderId
documentId
fileId
```

The focus is on determining whether the server properly authorizes access to the object referenced by the identifier.

### Input Handling & Injection

Potentially interesting input locations include:

```text
Arguments
Variables
Input Objects
String values
IDs
Numeric values
Boolean values
Nested objects
```

Testing should be performed against authorized environments.

### Aliases & Batching

GraphQL features that can cause multiple operations or resolver executions to be processed within a single HTTP request.

Security testing may include understanding how applications implement:

* Rate limiting.
* Authorization.
* Request counting.
* Resource consumption controls.

### CSRF

Testing whether state-changing GraphQL operations can be triggered through requests that an attacker could forge from another origin.

### Rate Limiting & Resource Consumption

Testing application controls around:

* Large queries.
* Repeated operations.
* Aliases.
* Batching.
* Query complexity.
* Query depth.
* Expensive resolver execution.

---

# Labs

The `Labs/` directory is intended for practical learning.

Labs should provide reproducible environments where researchers can safely understand GraphQL vulnerabilities without targeting real-world systems.

A typical lab may contain:

```text
Lab Objective
      ↓
Reconnaissance
      ↓
Attack Surface
      ↓
Vulnerability Identification
      ↓
Exploitation
      ↓
Why It Works
      ↓
Impact
      ↓
Verification
      ↓
Root Cause
      ↓
Takeaway
```

The objective is not just to provide the solution, but to explain the reasoning behind the vulnerability.

---

# Examples

The `Examples/` directory contains realistic GraphQL application scenarios.

Examples may cover applications such as:

```text
E-commerce
Blog platforms
Social applications
SaaS applications
Authentication systems
Organization/tenant systems
Admin applications
```

These examples can be used to understand how GraphQL functionality and security controls interact.

---

# Methodology

The `Methodology/` directory documents practical GraphQL security testing workflows.

The goal is to move beyond individual payloads and understand the complete testing process.

A typical workflow:

```text
1. Find the GraphQL endpoint
2. Confirm GraphQL
3. Identify the operation types
4. Attempt schema discovery
5. Enumerate queries
6. Enumerate mutations
7. Map types and fields
8. Identify arguments and input types
9. Identify object identifiers
10. Map object relationships
11. Test authentication
12. Test object-level authorization
13. Test field-level authorization
14. Test hidden functionality
15. Test input handling
16. Test aliases/batching
17. Test CSRF
18. Test rate limiting
19. Analyze errors
20. Verify security impact
```

The exact workflow may vary depending on the target application.

---

# Checklist

The `Checklist/` directory provides a structured checklist for GraphQL security assessments.

The purpose is to reduce the chance of missing important attack surfaces during testing.

It can be used during:

* Learning.
* Lab testing.
* Authorized penetration tests.
* Bug bounty testing.
* Security assessments.
* Research.

---

# Research

GraphQL Security Hub is intended to become a community-driven research resource.

Researchers can contribute:

* New attack patterns.
* New payloads.
* New reconnaissance techniques.
* Interesting GraphQL behaviors.
* Vulnerability write-ups.
* Defensive observations.
* Practical examples.
* Labs.
* Dictionary entries.

Contributions should be technically accurate and properly documented.

---

# Contributing

Everyone is welcome to contribute.

You do not need to be a professional security researcher to contribute.

You can contribute by:

```text
Adding a payload
Adding a dictionary entry
Writing a methodology
Creating a lab
Adding an example
Fixing documentation
Correcting technical mistakes
Adding research
Improving existing content
```

The general workflow is:

```text
Fork
  ↓
Create Branch
  ↓
Make Changes
  ↓
Commit
  ↓
Push
  ↓
Open Pull Request
  ↓
Maintainer Review
  ↓
Changes Requested / Approved
  ↓
Merge
```

All contributions are reviewed before being merged into the main repository.

For detailed contribution guidelines, see:

**[CONTRIBUTING.md](CONTRIBUTING.md)**

---

# Responsible Use

GraphQL Security Hub is an **educational and security research project**.

All techniques, payloads, examples, and methodologies should be used only against:

* Your own applications.
* Local environments.
* CTFs and security labs.
* Authorized penetration-testing targets.
* Bug bounty programs within their stated scope.
* Systems where you have explicit permission to test.

This repository does **not** grant permission to test any third-party system.

Always follow the target application's security policy and applicable laws.

---

# Responsible Disclosure

If you discover a vulnerability in a real application:

1. Verify the issue safely.
2. Check the organization's security policy.
3. Report the vulnerability through the appropriate security channel.
4. Avoid accessing or exposing unnecessary sensitive information.
5. Follow the organization's disclosure process.
6. Do not publish sensitive information such as credentials, tokens, private keys, or personal data.

GraphQL Security Hub should not be used to publicly disclose an unpatched vulnerability without following an appropriate responsible disclosure process.

---

# Useful Resources

This project can be used alongside established GraphQL and web-security resources.

Recommended resources include:

* GraphQL documentation.
* OWASP security resources.
* PortSwigger Web Security Academy.
* GraphQL implementations and framework documentation.
* Security research and responsible disclosure programs.

---

# Project Vision

The long-term goal is to make GraphQL Security Hub more than a collection of payloads.

The project can evolve into a structured ecosystem containing:

```text
GraphQL Security Knowledge Base
            │
            ├── Payload Library
            │
            ├── Recon Dictionaries
            │
            ├── Testing Methodology
            │
            ├── Practical Labs
            │
            ├── Vulnerability Examples
            │
            ├── Research
            │
            └── Community Contributions
```

Future development may include additional tooling, structured datasets, automation, and interactive learning resources.

---

# Contribute & Improve

If you find something incorrect, incomplete, outdated, or missing, feel free to open an Issue or submit a Pull Request.

Every useful contribution helps make the GraphQL security community stronger.

**Research. Test. Document. Share.**

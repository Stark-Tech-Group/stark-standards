# stg-standards

## Why use Source Control?
 - Team approval approach. New standards are done through pull-requests
 - Easily reference coding standards in other GitHub repositories
 - Versions and history tracking of standards
 - Automation of releasing new standards

## Building the Document
To build the document install ```markdown-include``` and then run ``` node .\node_modules\markdown-include\bin\cli.js .\markdown.json ```.


# Guidance
Software development standards and best practices change as the industry develops new technology, discovers new vulnerabilities, and finds better approaches to solving complex problems. Creating standards around an ever-changing world is a task that requires frequent maintenance and communication.

Stark Tech Group also manages several source code repositories, using several languages, and projects range from simple script utilities to full scale production applications. A repository that manages and processes financial transactions for public companies are held to a different standard than a data science workflow repository. Lastly, some repository may handle Personal Identifiable Information (PII) and may be required to adhere to state or federal guideless or may need to conform to a specific SLA or agreement.

With all these variables at play this document has been designed to offer guidance instead of concrete standards. The standards of each project and/or code repository is defined to its contributors by a code-owner.

This document should only serve as the basic or minimum guidance to any source code repository.


## Code-Owners and Contributors
Every repository has code-owners and contributors and the roles of each are important to following these guidelines. A code-owner, also known as a maintainer, can also be a contributor in repository and they must follow the same guidelines and requirements. Roles of each are set by the repository administrator.

**_NOTE:_** The term ‘Code-Owner’ does not imply actual ownership or equity in the underline code. The term is used in accordance with git’s CODEOWNER permissions.

### Code-Owners
Every source code repository is assigned at least one code-owner. Code-owners are employees of Stark Tech Group that are ultimately responsible for the stability, maintenance, and overall work product of the repository.

Code-owners have the flexibility and freedom to apply specific standards as they see fit and are entrusted to balance best practices, maintainability, stability, security, and timeline of a task.

Code-owners are encouraged to provide the following on each repository:

 - **Contributor Guidelines**: Code-owners should outline any specific guidelines in a README located in the root of the project under a section named Contributor Guidelines.
 - **Feedback**: Code-owners should provide descriptive feedback on pull-requests that require updating, refactoring or correction.
 - **Consistency**: Code-owners should be consistent in requirements as best as they can among various repositories, languages, and frameworks.
  - **Coach**: If a pull-request does not meet requirements, a code-owner should help the contributor understand why.

### Contributors
Every source code repository can have one to many contributors. Contributors are responsible for pulling and creating branches, resolving issues, documenting work, and ensuring pull-requests meet the guidelines of the repository. Code-owners can also be contributors their own repositories and must follow the same guidelines.

Contributors must follow the following guidelines on each repository:

- **Follow Code-Owner Requirements**: The code-owner sets the requirements and all contributors must follow them.
- **Communication**: Contributors should document and communicate changes through commit messages and pull-requests using issue numbers.


# General
#include "general/general/README.md"

# Tests
#include "general/tests/README.md"

# Dependencies
#include "general/dependencies/README.md"

# Design
#include "general/design/README.md"

# Security
#include "general/security/README.md"

# Source Control
#include "general/source-control/README.md"
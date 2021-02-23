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

With all these variables at play this document has been designed to offer guidance instead of concrete standards. The standards of each project and/or code repository is defined to its Contributors by a code-owner.

This document should only serve as the basic or minimum guidance to any source code repository.


## Code-Owners and Contributors
Every repository has Code-Owners and Contributors and the roles of each are important to following these guidelines. A code-owner, also known as a maintainer, can also be a Contributor in repository and they must follow the same guidelines and requirements. Roles of each are set by the repository administrator.

**_NOTE:_** The term ‘Code-Owner’ does not imply actual ownership or equity in the underline code. The term is used in accordance with git’s CODEOWNER permissions.

### Code-Owners
Every source code repository is assigned at least one code-owner. Code-Owners are employees of Stark Tech Group that are ultimately responsible for the stability, maintenance, and overall work product of the repository.

Code-Owners have the flexibility and freedom to apply specific standards as they see fit and are entrusted to balance best practices, maintainability, stability, security, and timeline of a task.

Code-Owners are encouraged to provide the following on each repository:

 - **Contributor Guidelines**: Code-Owners should outline any specific guidelines in a README located in the root of the project under a section named Contributor Guidelines.
 - **Feedback**: Code-Owners should provide descriptive feedback on pull-requests that require updating, refactoring or correction.
 - **Consistency**: Code-Owners should be consistent in requirements as best as they can among various repositories, languages, and frameworks.
  - **Coach**: If a pull-request does not meet requirements, a code-owner should help the Contributor understand why.

### Contributors
Every source code repository can have one to many Contributors. Contributors are responsible for pulling and creating branches, resolving issues, documenting work, and ensuring pull-requests meet the guidelines of the repository. Code-Owners can also be Contributors their own repositories and must follow the same guidelines.

Contributors must follow the following guidelines on each repository:

- **Follow Code-Owner Requirements**: The Code-owner sets the requirements and all Contributors must follow them.
- **Communication**: Contributors should document and communicate changes through commit messages and pull-requests using issue numbers.

## Repository Classifications
Code-Owners may enforce special or specific requirements on a repository at any time. These specific requirements should be based on the classification of a repository. Below are some examples of when a Code-owner may require enhanced or specific standards of it's Contributor's.

1.	**Personal Identifiable Information (PII)**: Repositories and\or code blocks that process, handle or store Personal Identifiable Information PII must be classified as such and must adhere to enhanced guidance following state, local and federal laws, and regulations. The Code-Owners of these repositories are responsible for maintaining and enforcing additional standards.
2.	**Federally Classified or Sensitive Data (Fed\Gov)**: Repositories and\or code blocks that process, handle or store classified or sensitive information must be classified as such and must adhere to enhanced guidance following state, local and federal laws, and regulations. The Code-Owners of these repositories are responsible for maintaining and enforcing additional standards.
3.	**Financial Transactions**: Repositories and\or code blocks that process, handle or store financial transactions must be classified as such and must adhere to enhanced guidance established by its Code-Owners. Code owners of these repositories may require additional units, integration tests, specific data type usage and enhanced security among other requirements.
4.	**Trade Secrets**: Repositories and\or code blocks that process, handle or store trade secrets must be classified as such and must adhere to enhanced guidance established by its Code-Owners. Code-Owners of these repositories may require enhanced documentation, storage, and encryption processes among other requirements. 
5.	**Contracts and Agreements (SLAs)**: Repositories and\or code blocks that are associated with a Service Level Agreement (SLA) or specific legally binding agreement must be classified as such. Code-Owners of these repositories may require enhanced guidance that is specific to a binding agreement.
6.	**High Performance**: Repositories and\or code blocks that consist of highly performant code must be classified as such. These types of repositories may be required to not follow best practices in favor of high-performance requirements. Code blocks or functions falling under these requirements should be noted so.
7.	**Tools and Utilities**: Repositories that consist of only tools and utilities that support internal tasks through scripts or documentation must be classified as such. These types of repositories may be held to a higher or lower level of guidance outlined by its code owners. 



# General
#include "general/general/README.md"

# Security
#include "general/security/README.md"

# Tests
#include "general/tests/README.md"

# Dependencies
#include "general/dependencies/README.md"

# Design
#include "general/design/README.md"

# Source Control
#include "general/source-control/README.md"

# Devops
#include "general/devops/README.md"

# Datastore
#include "general/datastore/README.md"

# Resources
#include "general/resources/README.md"

# stg-standards

## Why use GitHub
 - Team approval approach. New standards are done through pull-requests
 - Easily reference coding standards in other GitHub repositories
 - Versions and history tracking of standards
 - Automation of releasing new standards

## Building the Document
To build the document install ```markdown-include``` and then run ``` node .\node_modules\markdown-include\bin\cli.js .\markdown.json ```.


## Guidance
Software development standards and best practices change as the industry develops new technology, discovers new vulnerabilities, and finds better approaches to solving complex problems. Creating standards around an ever-changing world is a task that requires frequent maintenance and communication.

Stark Tech Group also manages several source code repositories, using several languages, and projects range from simple script utilities to full scale production applications. A repository that manages and processes financial transactions for public companies are held to a different standard than a data science workflow repository. Lastly, some repository may handle Personal Identifiable Information (PII) and may be required to adhere to state or federal guideless or may need to conform to a specific SLA or agreement.

With all these variables at play this document has been designed to offer guidance instead of concrete standards. The standards of each project and/or code repository is defined to its contributors by a code-owner.

This document should only serve as the basic or minimum guidance to any source code repository.


# Tests
#include "general/tests/README.md"

# Naming
#include "general/naming/README.md"

# Dependencies
#include "general/dependencies/README.md"

# Design
#include "general/design/README.md"

# Security
#include "general/security/README.md"

# Source Control
#include "general/source-control/README.md"
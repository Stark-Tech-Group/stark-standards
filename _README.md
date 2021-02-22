# stg-standards

## Why use GitHub
 - Team approval approach. New standards are done through pull-requests
 - Easily reference coding standards in other GitHub repositories
 - Versions and history tracking of standards
 - Automation of releasing new standards

## Building the Document
To build the document install ```markdown-include``` and then run ``` node .\node_modules\markdown-include\bin\cli.js .\markdown.json ```.

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
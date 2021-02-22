# stg-standards

## Why use GitHub
 - Team approval approach. New standards are done through pull-requests
 - Easily reference coding standards in other GitHub repositories
 - Versions and history tracking of standards
 - Automation of releasing new standards

## Building the Document
To build the document install ```markdown-include``` and then run ``` node .\node_modules\markdown-include\bin\cli.js .\markdown.json ```.

# Tests
| Code   | Description                                                              |
|--------|--------------------------------------------------------------------------|
| test-1 | Avoid multiple assertions in one unit test.                              |
| test-2 | Keep unit tests small.                                                   |
| test-3 | Keep unit test and integration tests separate.                           |
| test-4 | Avoid flaky test. Use retry frameworks or label flaky test if necessary. |
| test-5 | Embrace mock frameworks when useful.                                     |
| test-6 | Create test, dev and prod test environments.                             |
| test-7 | Use a logger                                                             |




# Naming
| Code    | Description                                                                                    |
|---------|------------------------------------------------------------------------------------------------|
| names-1 | camelCase naming for variables.                                                                |
| names-2 | Uppercase constants and static.                                                                |
| names-3 | Capitalize first word for classes.                                                             |
| names-4 | Avoid global variables, use the least exposure possible.                                       |
| names-5 | Avoid public variables for classes. Enforce the idea of encapsulation with getters and setter. |
| names-6 | Avoid redundant labeling. <br/> ` book.getBookPage(1) //redundant ` vs. `book.getPage(1)`      |
| names-7 | Use meaning full names.  <br/> ` var returnVal = 2; ` vs. `var zoomLevel = 2;`                 |
|         |                                                                                                |





# Dependencies
| Code  | Description                                                    |
|-------|----------------------------------------------------------------|
| dep-1 | Use the latest dependencies.                                   |
| dep-2 | Avoid unsupported or poorly supported dependencies.            |
| dep-3 | Avoid dependencies from foreign nations.                       |
| dep-4 | Keep dependencies in one location.                             |
| dep-5 | Understand dependency licensing.                               |
| dep-6 | Keep test and dev dependencies out of production environments. |




# Design
| Code  | Description                 |
|-------|-----------------------------|
| des-1 | Design for containerization |
| des-2 | Design for localization     |




# Security
| Code  | Description                             |
|-------|-----------------------------------------|
| sec-1 | Do not commit secrets to source control |
| sec-2 | Use a secrets manager                   |
| sec-3 | Do not log secrets                      |




# Source Control
| Code  | Description                             |
|-------|-----------------------------------------|
| scm-1 | |
| scm-2 | |
| scm-3 | |



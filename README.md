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
| Code   | Description                                                                                    |
|--------|------------------------------------------------------------------------------------------------|
| gen-1  | Follow best practices of the language.                                                         |
| gen-2  | camelCase naming for variables.                                                                |
| gen-3  | Uppercase constants and static.                                                                |
| gen-4  | Capitalize first word for classes.                                                             |
| gen-5  | Avoid global variables, use the least exposure possible.                                       |
| gen-6  | Avoid public variables for classes. Enforce the idea of encapsulation with getters and setter. |
| gen-7  | Avoid redundant labeling. <br/> ` book.getBookPage(1) //redundant ` vs. `book.getPage(1)`      |
| gen-8  | Use meaning full names.  <br/> ` var returnVal = 2; ` vs. `var zoomLevel = 2;`                 |
| gen-9  | Avoid constructors with more than 8 arguments, consider a builder or data object.              |
| gen-10 | Consider static factory methods instead of constructors.                                       |
| gen-11 | Enforce singleton property with a private constructor or an enum type.                         |
| gen-12 | Don't comment out code, just remove it.                                                        |
| gen-13 | Obey the general contract when overriding equals and hashCode.                                 |
| gen-14 | Minimize mutability, use `final` or `const` judiciously.                                       |
| gen-15 | Design for inheritance or prohibit it (`final` or `sealed` class).                             |
| gen-16 | Use enums instead of int constants.                                                            |
| gen-17 | Use `static final` for repetitive string constants .                                           |
| gen-18 | Remove unused functions.                                                                       |
| gen-19 | Avoid console output, use a logger                                                             |
| gen-20 | Validate inputs early to avoid unintended consequences.                                        |
| gen-21 | Embrace dependency injection                                                                   |


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
| Code   | Description                                                                                |
|--------|--------------------------------------------------------------------------------------------|
| sec-1  | Do not allow cross-site scripting (XSS) vulnerabilities                                    |
| sec-2  | Do not allow cross-site request forgery (CSRF) vulnerabilities                             |
| sec-3  | Do not allow sql injection vulnerabilities, favor prepared statements and named variables  |
| sec-4  | Do not commit secrets to source control                                                    |
| sec-5  | Use a secrets manager                                                                      |
| sec-6  | Do not log secrets                                                                         |
| sec-7  | Treat Personal Identifiable Information (PII) as secrets                                   |
| sec-8  | Always assume inputs will be malicious                                                     |
| sec-9  | Always assume file uploads will be malicious in content, size and type                     |
| sec-10 | Do not include secrets in error or exception messages                                      |
| sec-11 | Use well known encryption tools. Don't create your own encryption algorithm                |
| sec-12 | Avoid keeping secrets in memory longer than needed                                         |
| sec-13 | Favor char arrays over strings for when storying secrets in memory                         |
| sec-14 | Protect against arithmetic overflow and underflow                                          |
| sec-15 | Limit the count and size a log file can grow to                                            |
| sec-16 | Configure XML parsers to prevent XXE                                                       |
| sec-17 | Never store secrets or PII in plain text                                                   |
| sec-18 | Limit serialization interfaces and protect against unsafe de-serialization vulnerabilities |
| sec-19 | HTTPS only                                                                                 |
| sec-20 | Assume supply chains and vendors are compromised                                           |
| sec-21 | Assume parsers are vulnerabilities (HTML, CSV, XML, JSON, REGEX, etc.)                     |
| sec-22 | Limit the number of chained exceptions                                                     |
| sec-23 | Log failed access and authentication attempts                                              |
| sec-24 | Favor deny all                                                                             |
| sec-25 | Document trusted IP address in net-sec repository                                          |
| sec-26 | Document malicious IP addresses in net-sec repository                                      |
| sec-27 | Limit number of failed access and authentication attempts                                  |
| sec-28 | Use de-bouncing techniques                                                                 |


# Source Control
| Code   | Description                                                                                                     |
|--------|-----------------------------------------------------------------------------------------------------------------|
| scm-1  | Only code-owners can merge into ```main``` branches                                                             |
| scm-2  | No direct commits into ```main``` or ```dev``` branches                                                         |
| scm-3  | Use snake-case for branch names                                                                                 |
| scm-4  | Feature additions must pull from ```dev``` and be prefixed with ```feature/name-of-feature```                   |
| scm-5  | Bug fixes must pull from ```dev``` and be prefixed with ```bug/name-of-bug```                                   |
| scm-6  | Hot fixes must pull from ```main``` or ```dev``` and be prefixed with ```hot-fix/name-of-bug```                 |
| scm-7  | Include ticket number/link in commit when available                                                             |
| scm-8  | Merge into `main` or `dev` requested via Pull Request and must be peer reviewed and passing all required checks |
| scm-9  | Keep Pull Request small and focused for easy review                                                             |
| scm-9  | New Projects are required to have a `main` and `dev` branch                                                      |
| scm-10 | New Projects are required to the `dev` branch set as the base or target branch                                   |
| scm-11 | New Projects setup should limit push to `main` and `dev` to Code-Owners                                          |





# Resources

### Books
| Category   | Description                                                                 | Link                                                                                                                                                                                                                                                                                                                                                          |
|------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Java       | Effective Java 3rd Edition                                                  | [Amazon](https://www.amazon.com/Effective-Java-Joshua-Bloch/dp/0134685997)                                                                                                                                                                                                                                                                                    |
| Java, .Net | Clean Code: A Handbook of Agile Software Craftsmanship                      | [Amazon](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882/ref=sr_1_1?dchild=1&keywords=clean+code&qid=1614013320&s=books&sr=1-1)                                                                                                                                                                                               |
| Java, .Net | Refactoring: Improving the Design of Existing Code (2nd Edition)            | [Amazon]( https://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Signature/dp/0134757599/ref=sr_1_1?crid=6B1L3C0XYODS&dchild=1&keywords=refactoring+martin+fowler&qid=1614013437&s=books&sprefix=refactor%2Cstripbooks%2C171&sr=1-1)                                                                                                            |
| .Net       | Concurrency in .NET: Modern patterns of concurrent and parallel programming | [Amazon](https://www.amazon.com/Concurrency-NET-patterns-concurrent-programming/dp/1617292990/ref=sr_1_16?crid=1JZI6AB7HRQK6&dchild=1&keywords=concurrency&qid=1614013497&s=books&sprefix=concur%2Cstripbooks%2C183&sr=1-16)                                                                                                                                  |
| General    | Design Patterns: Elements of Reusable Object-Oriented Software              | [Amazon](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612/ref=sr_1_2?crid=34AVG7GIWGMCW&dchild=1&keywords=design+patterns&qid=1614013693&s=books&sprefix=design+pa%2Cstripbooks%2C182&sr=1-2)                                                                                                                           |
| General    | Clean Architecture: A Craftsman's Guide to Software Structure and Design    | [Amazon](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164/ref=pd_bxgy_img_3/139-1242530-4776209?_encoding=UTF8&pd_rd_i=0134494164&pd_rd_r=e20d6db4-c2c7-4f47-8d07-986543bc726f&pd_rd_w=60njV&pd_rd_wg=uTchM&pf_rd_p=f325d01c-4658-4593-be83-3e12ca663f0e&pf_rd_r=YY21Q43S05F5NQXNEQS8&psc=1&refRID=YY21Q43S05F5NQXNEQS8) |
| Go         | Go Programming Language                                                     | [Amazon](https://www.amazon.com/Programming-Language-Addison-Wesley-Professional-Computing/dp/0134190440/ref=sr_1_3?dchild=1&keywords=Golang&qid=1614015187&sr=8-3)                                                                                                                                                                                           |

### Online 
| Category            | Description                                             | Link                                                                                               |
|---------------------|---------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Angular             | Angular - The Complete Guide                            | [udemy](https://www.udemy.com/course/the-complete-guide-to-angular-2/)                             |
| Git                 | The Complete GitHub Actions & Workflows Guide           | [udemy](https://www.udemy.com/course/github-actions/)                                              |
| Git                 | Git Complete: The definitive, step-by-step guide to Git | [udemy](https://www.udemy.com/course/git-complete/)                                                |
| Yaml                | YAML Essentials                                         | [udemy](https://www.udemy.com/course/yaml-essentials/)                                             |
| Agile               | Basics of Scrum, Agile and Project Delivery             | [udemy](https://www.udemy.com/course/scrum-methodology/)                                           |
| NodeJs              | Introduction to TypeScript                              | [udemy](https://www.udemy.com/course/typescript/)                                                  |
| Docker/Kubernetes   | Docker and Kubernetes: The Complete Guide               | [udemy](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/)                    |


### Tools 
The following tools are available to Stark Tech Group employees for software development.
 - CLion
 - DataGroup
 - dotCover
 - dotMemory
 - dotTrace
 - GoLand
 - IntelliJ IDEA
 - ReShapper C++
 - Rider
 - RubyMine
 - WebStorm
 - Visual Studio
 - Visual Studio Code
 - Sql Server Management Studio
 - Postman



# Devops
| Code     | Description                                                                                                                          |
|----------|--------------------------------------------------------------------------------------------------------------------------------------|
| devop-1  | All projects are required to have a Continuous Integration pipeline                                                                  |
| devop-2  | All projects are required to have a Continuous Deployment pipeline                                                                   |
| devop-3  | CI should execute test, run lint checks, build production and test images, build artifacts(.jar, .war, exe), and run security checks |
| devop-4  | CD should deploy artifacts and images to registries(maven/gradle, docker) and production or staging environments                     |
| devop-5  | CI pipeline should be designed as logical steps( pull->lint->unit-test->integration test->build/compile                              |
| devop-6  | All generated documents, reports, and artifacts will be stored with the pipeline execution                                           |
| devop-7  | CI will be triggered on push and on PR                                                                                               |
| devop-8  | CD will be triggered after PR into base/production branch                                                                            |


# Datastore
| Code | Description                                                    |
|------|----------------------------------------------------------------|
| ds-1 | Database changes should never be made directly on a database server.  Use database change management solutions (like liquibase) to track changesets and apply those changesets.                                   |



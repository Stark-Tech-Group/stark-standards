# Software Development and Programming Guidance

## Why use Source Control?
 - Team approval approach with pull-requests comments and branching
 - Easily reference coding standards in other GitHub repositories
 - Automation of releases and updates
 - History and version tracking

## Building the Document
This document is built automatically using workflow actions and nodejs. Once a change has been approved using a pull-request and merged into ```dev``` a new version will be published.


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
<table>
<thead>
<tr><th> Code </th><th>Description</th></tr>
</thead>
<tbody>
<tr><td> gen-1  </td><td> Follow best practices of the language</td></tr>
<tr><td> gen-2  </td><td> camelCase naming for variables</td></tr>
<tr><td> gen-3  </td><td> Uppercase constants and static</td></tr>
<tr><td> gen-4  </td><td> Capitalize first word for classes</td></tr>
<tr><td> gen-5  </td><td> Avoid global variables, use the least exposure possible</td></tr>
<tr><td> gen-6  </td><td> Avoid public variables for classes. Enforce the idea of encapsulation with getters and setter</td></tr>
<tr><td> gen-7  </td><td> Avoid redundant labeling

```javascript
//avoid:
const bookPage = book.getBookPage(1)
```
 
```javascript
//embrace:
const page = book.getPage(1)
```

</td></tr>
<tr><td> gen-8  </td><td> Use meaning full names 

```javascript
//avoid:
function calculate(a, b, c) {
    return (a * b) * c;
}
```
 
```javascript
//embrace:
function calculate(speed, distance, time) {
    return (speed * distance) * time;
}
```

<tr><td> gen-9  </td><td> Avoid constructors with more than 4 arguments, consider a builder or data object
    
```javascript
//avoid:
const book = new Book("Design Patterns Explained", "Alan Shalloway", 
                        "978-0321247148", 4.9, 480, "October 12, 2004", "English")
```
 
```javascript
//embrace:
const book = new BookBuilder.setTitle("Design Patterns Explained")
                .setAuthor("Alan Shalloway")
                .setISBN("978-0321247148")
                .setRating(4.9)
                .setPageCount(480)
                .setPublishDate("October 12, 2004")
                .setLanguange("English")
                .build()
```
    
</td></tr>
<tr><td> gen-10 </td><td> Consider static factory methods instead of constructors

```javascript
const location = Location.from("Buffalo", "NY")
const prime = Lists.of(2, 3, 5)
```

</td></tr>
<tr><td> gen-11 </td><td> Enforce singleton property with a private constructor or an enum type</td></tr>
<tr><td> gen-12 </td><td> Don't comment out code, just remove it</td></tr>
<tr><td> gen-13 </td><td> Obey the general contract when overriding equals and hashCode</td></tr>
<tr><td> gen-14 </td><td> Minimize mutability, use `final` or `const` judiciously</td></tr>
<tr><td> gen-15 </td><td> Design for inheritance or prohibit it (`final` or `sealed` class)</td></tr>
<tr><td> gen-16 </td><td> Replace anonymous constants with descriptive constants <br/>

```javascript
//avoid:
function isOk(response) {
    if ( anyNulls(response, response.get('code') ) return false;
    return response.get('code') === 1 // anonymous constant
}
```

```javascript
//embrace:
const OK_RESPONSE_CODE = 1 
function isOk(response) {
    if ( anyNulls(response, response.get('code') ) return false;
    return response.get('code') === OK_RESPONSE_CODE // descriptive constant
}
```

</td></tr>
<tr><td> gen-17 </td><td> Use `static final` for repetitive string constants</td></tr>
<tr><td> gen-18 </td><td> Remove unused functions</td></tr>
<tr><td> gen-19 </td><td> Avoid console output, use a logger
 
```javascript
//avoid:
function calculate(speed, distance, time) {
    console.log("calling calculate")
    /* debugger
    console.log("speed", speed)
    console.log("distance", distance)
    console.log("time", time)
    */
    // console.log("done")
    return (speed * distance) * time;
}
```
 
```javascript
//embrace:
function calculate(speed, distance, time) {
    Logger.debug("calling calculate speed:%s, distance:%s, time:%s", speed, distance, time)
    return (speed * distance) * time;
}
``` 
 
</td></tr>
<tr><td> gen-20 </td><td> Validate inputs early to avoid unintended consequences
 
 
```javascript
//avoid:
function search(user, query, limit) {
   if ( limit > MAX_RESULT ) throw new Error('limit too large')
   
   const results = searchService.query(query, limit)
   
   if ( user == null ) throw new Error('no user provided')
   else results.set('user', user)
  
   return results
}
```

```javascript
//embrace:
function search(user, query, limit) {
   if ( limit > MAX_RESULT ) throw new Error('limit too large')
   if ( user == null ) throw new Error('no user provided')
   
   const results = searchService.query(query, limit)   
   results.set('user', user)
  
   return results
}
```

 
 
 
 </td></tr>
<tr><td> gen-21 </td><td> Embrace dependency injection when available</td></tr>
<tr><td> gen-22 </td><td> Favor iterators when dealing with large collections</td></tr>
<tr><td> gen-23 </td><td> Avoid loading unnecessary items into collections for later filtering <br/>

```javascript
//avoid:
function getUser(username) {
   const allUsers = sql.getRows("SELECT id, username FORM users")
   return allUsers.find( (i) => i.username === username )
}
```

```javascript
//embrace:
function getUser(username) {
   return sql.getRows("SELECT id, username FORM users WHERE username = :username", username)
}
```

</td></tr>
<tr><td> gen-24 </td><td> Don't ignore exceptions <br/>

```javascript
//avoid:
function print(a) {
   try { return Printer.print(a) } 
   catch (e) { 
    /* something bad happend */ 
    return; 
   }
}
```

```javascript
//embrace:
function print(a) {
   try { return Printer.print(a) } 
   catch (e) { 
    handleError(e);
   }
}
```

</td></tr>
<tr><td> gen-23 </td><td> Limit number of conditionals in one function to no more than 10 (if and switch)</td></tr>
</tbody>
</table>


# Security
<table>
  <thead>
    <tr>
      <th>Code</th><th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td> sec-1  </td><td> Do not allow cross-site scripting (XSS) vulnerabilities</td></tr>
<tr><td> sec-2  </td><td> Do not allow cross-site request forgery (CSRF) vulnerabilities</td></tr>
<tr><td> sec-3  </td><td> Do not allow sql injection vulnerabilities, favor prepared statements and named variables

```javascript
//avoid:
function getUser(username) {
   return sql.getRows("SELECT id, username FORM users WHERE = '" + username + "'")
}
```

```javascript
//embrace:
function getUser(username) {
   return sql.getRows("SELECT id, username FORM users WHERE username = :username", {'username':username})
}
```
</td></tr>
<tr><td> sec-4  </td><td> Do not commit secrets to source control</td></tr>
<tr><td> sec-5  </td><td> Use a secrets manager</td></tr>
<tr><td> sec-6  </td><td> Do not log secrets
  
```javascript
//avoid:
function call(url, apiKey) {
  Logger.info("call with apiKey:" + apiKey)
  return url.setHeader("auth", apiKey).get(url)
}
```
  
</td></tr>
<tr><td> sec-7  </td><td> Treat Personal Identifiable Information (PII) as secrets</td></tr>
<tr><td> sec-8  </td><td> Always assume inputs will be malicious</td></tr>
<tr><td> sec-9  </td><td> Always assume file uploads will be malicious in content, size and type</td></tr>
<tr><td> sec-10 </td><td> Do not include secrets in error or exception messages</td></tr>
<tr><td> sec-11 </td><td> Use well known encryption tools. Don't create your own encryption algorithm</td></tr>
<tr><td> sec-12 </td><td> Avoid keeping secrets in memory longer than needed</td></tr>
<tr><td> sec-13 </td><td> Favor char arrays over strings for when storying secrets in memory</td></tr>
<tr><td> sec-14 </td><td> Protect against arithmetic overflow and underflow</td></tr>
<tr><td> sec-15 </td><td> Limit the count and size a log file can grow to</td></tr>
<tr><td> sec-16 </td><td> Configure XML parsers to prevent XXE</td></tr>
<tr><td> sec-17 </td><td> Never store secrets or PII in plain text</td></tr>
<tr><td> sec-18 </td><td> Limit serialization interfaces and protect against unsafe de-serialization vulnerabilities</td></tr>
<tr><td> sec-19 </td><td> HTTPS by default</td></tr>
<tr><td> sec-20 </td><td> Assume supply chains and vendors are compromised</td></tr>
<tr><td> sec-21 </td><td> Assume parsers are vulnerabilities (HTML, CSV, XML, JSON, REGEX, etc.)</td></tr>
<tr><td> sec-22 </td><td> Limit the number of chained exceptions</td></tr>
<tr><td> sec-23 </td><td> Log failed access and authentication attempts</td></tr>
<tr><td> sec-24 </td><td> Favor deny all</td></tr>
<tr><td> sec-25 </td><td> Document trusted IP address in net-sec repository</td></tr>
<tr><td> sec-26 </td><td> Document malicious IP addresses in net-sec repository</td></tr>
<tr><td> sec-27 </td><td> Limit number of failed access and authentication attempts</td></tr>
<tr><td> sec-28 </td><td> Throttle login to help prevent brute force</td></tr>
<tr><td> sec-29 </td><td> Do not store secrets in containers</td></tr>
<tr><td> sec-30 </td><td> Avoid putting security controls on client side

```javascript
//avoid:
<input class="button" disabled="canDelete()" onclick="delete(e)"> Delete </input>
...

//client-side
func canDelete() { return user.hasRole("DELETE"); }
func delete(e) { db.delete(e); }
```

```javascript
//embrace:
<input class="button" disabled="canDelete()" onclick="delete(e)"> Delete </input>

//client-side
func canDelete() { return user.hasRole("DELETE"); }
func delete(e) { db.delete(user, e); /* server checks permissions, not client */ }

```
  
</td></tr>
<td> sec-31 </td><td> Always prefer whitelisting over blacklisting</td></tr>

<tr><td> sec-32  </td><td> Use id objects and typing to enforce your intention

```javascript
//avoid:
function getUserById(id) {
   return db.get('user', id)
}
```

```javascript
//embrace:

class PersonId {
  private constructor( private readonly id: number ) { }
  getId() { return this.id; }
  public static of(id: number): PersonId {
    if (id < 0) { return null; }
    return new PersonId(id);
  }
}

function getUserById(personId PersonId) {
   return db.get('user', personId.getId() )
}
```
</td></tr>

</tbody>
</table>


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
| test-8 | Test edge cases thoroughly(null, empty, missing, out of range)           |




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




# Source Control
| Code     | Description                                                                                                     |
|----------|-----------------------------------------------------------------------------------------------------------------|
| scm-1    | Only code-owners can merge into ```main``` branches                                                             |
| scm-2    | No direct commits into ```main``` or ```dev``` branches                                                         |
| scm-3    | Use snake-case for branch names                                                                                 |
| scm-4    | Feature additions must pull from ```dev``` and be prefixed with ```feature/name-of-feature```                   |
| scm-5    | Bug fixes must pull from ```dev``` and be prefixed with ```bug/name-of-bug```                                   |
| scm-6    | Hot fixes must pull from ```main``` or ```dev``` and be prefixed with ```hot-fix/name-of-bug```                 |
| scm-7    | Include ticket number/link in commit when available                                                             |
| scm-8    | Merge into `main` or `dev` requested via Pull Request and must be peer reviewed and passing all required checks |
| scm-9    | Keep Pull Request small and focused for easy review                                                             |
| scm-9    | New Projects are required to have a `main` and `dev` branch                                                     |
| scm-10   | New Projects are required to have the `dev` branch set as the base or target branch                             |
| scm-11   | New Projects will restrict push to `main` and `dev` to Code-Owners                                              |





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



# Additional Guidance & Resources

## Code Smells
In computer programming, a code smell is any characteristic in the source code of a program that possibly indicates a deeper problem. Determining what is and is not a code smell is subjective, and varies by language, developer, and development methodology. Code-owners may identify code smells in pull-requests or in commits and should be refactored and or cataloged as technical debt.

For more information regarding code smell you may refer to: https://en.wikipedia.org/wiki/Code_smell

### Application-level smells:
1.	**Mysterious Name**: functions, modules, variables or classes are named so that they don't communicate what they do or how to use them.
2.	**Duplicated code**: identical or very similar code exists in more than one location.
3.	**Contrived complexity**: forced usage of overcomplicated design patterns were simpler design would suffice.
4.	**Shotgun surgery**: a single change needs to be applied to multiple classes at the same time.
5.	**Uncontrolled side effects**: very easy to cause runtime exceptions and unit tests can't capture it.
6.	**Variable mutations**: very hard to refactor code since the actual value is unpredictable and hard to reason about.
7.	**Boolean blindness**: easy to assert on the opposite value and still type checks.

### Class-level smells:
1.	**Large class**: a class that has grown too large. See God object.
2.	**Feature envy**: a class that uses methods of another class excessively.
3.	**Inappropriate intimacy**: a class that has dependencies on implementation details of another class. See Object orgy.
4.	**Refused bequest**: a class that overrides a method of a base class in such a way that the contract of the base class is not honored by the derived class. See Liskov substitution principle.
5.	**Lazy class / freeloader**: a class that does too little.
6.	**Excessive use of literals**: these should be coded as named constants, to improve readability and to avoid programming errors. Additionally, literals can and should be externalized into resource files/scripts, or other data stores such as databases where possible, to facilitate localization of software if it is intended to be deployed in different regions.
7.	**Cyclomatic complexity**: too many branches or loops; this may indicate a function needs to be broken up into smaller functions, or that it has potential for simplification/Refactoring.
8.	**Downcasting**: a type cast which breaks the abstraction model; the abstraction may have to be refactored or eliminated.
9.	**Orphan variable or constant class**: a class that typically has a collection of constants which belong elsewhere where those constants should be owned by one of the other member classes.
10.	**Data clump**: Occurs when a group of variables are passed around together in various parts of the program. In general, this suggests that it would be more appropriate to formally group the different variables together into a single object, and pass around only the new object instead.

### Method-level smells:
1.	**Too many parameters**: a long list of parameters is hard to read, and makes calling and testing the function complicated. It may indicate that the purpose of the function is ill-conceived and that the code should be refactored so responsibility is assigned in a more clean-cut way.
2.	**Long method**: a method, function, or procedure that has grown too large.
3.	**Excessively long identifiers**: in particular, the use of naming conventions to provide disambiguation that should be implicit in the software architecture.
4.	**Excessively short identifiers**: the name of a variable should reflect its function unless the function is obvious.
5.	**Excessive return of data**: a function or method that returns more than what each of its callers needs.
6.	**Excessive comments**: a class, function or method has irrelevant or trivial comments. A comment on an attribute setter/getter is a good example.
7.	**God Objects**: a class that has lots of responsibilities and is low cohesive.
8.	**Excessively long line of code (or God Line)**: A line of code which is too long, making the code difficult to read, understand, debug, refactor, or even identify possibilities of software reuse. Example


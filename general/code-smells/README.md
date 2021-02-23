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

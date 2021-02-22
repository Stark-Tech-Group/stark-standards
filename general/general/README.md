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
| gen-21 | Embrace dependency injection when available                                                    |
| gen-22 | Favor iterators when dealing with large collections                                            |
| gen-23 | Avoid loading unnecessary items into collections for later filtering                           |


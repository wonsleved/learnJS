# Variables

Variables are used to store this information.

## A variable

To create a variable in JavaScript, use the `let` keyword.

***`var` instead of `let`***

***Declaring twice triggers an error.***
A variable should be declared only once.

## Variable naming

There are two limitations on variable names in JavaScript:

1. The name must contain only letters, digits, or the symbols `$` and `_`.
2. The first character must not be a digit.

**Case matters**

**Non-Latin letters are allowed, but not recommended**

***Reserved names***

There is a [list of reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords), which cannot be used as variable names because they are used by the language itself.

For example: `let`, `class`, `return`, and `function` are reserved.

***An assignment without `use strict`***
```
// note: no "use strict" in this example

num = 5; // the variable "num" is created if it didn't exist

alert(num); // 5
```
This is a bad practice and would cause an error in strict mode:
```
"use strict";

num = 5; // error: num is not defined
```

## Constants

To declare a constant (unchanging) variable, use `const` instead of `let`.

### Uppercase constants

There is a widespread practice to use constants as aliases for difficult-to-remember values that are known _prior to execution_.
Such constants are named using capital letters and underscores.

## Name things right

- Use human-readable names like `userName` or `shoppingCart`.
- Stay away from abbreviations or short names like `a`, `b`, `c`, unless you really know what you’re doing.
- Make names maximally descriptive and concise. Examples of bad names are `data` and `value`. Such names say nothing. It’s only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
- Agree on terms within your team and in your own mind. If a site visitor is called a “user” then we should name related variables `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.
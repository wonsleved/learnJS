# Eval: run a code string

The built-in `eval` function allows to execute a string of code.

```
let result = eval(code);
```

The result of `eval` is the result of the last statement.

It can change outer variables.

In strict mode, `eval` has its own lexical environment. So functions and variables, declared inside eval, are not visible outside.

Without `use strict`, `eval` doesn’t have its own lexical environment.

## Using “eval”

It’s often said that “eval is evil”.

**If eval’ed code doesn’t use outer variables, please call `eval` as `window.eval(...)`**

**If eval’ed code needs local variables, change `eval` to `new Function` and pass them as arguments:**

***`new Function` creates a function from a string, also in the global scope. So it can’t see local variables.***
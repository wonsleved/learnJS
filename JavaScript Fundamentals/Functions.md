# Functions

## Function Declaration

```
function name(parameter1, parameter2, ... parameterN) {
  ...body...
}
```

## Local variables

A variable declared inside a function is only visible inside that function.

## Outer variables

A function can access an outer variable as well, for example.

If a same-named variable is declared inside the function then it *shadows* the outer one.

## Parameters

- A parameter is the variable listed inside the parentheses in the function declaration (it’s a declaration time term)
- An argument is the value that is passed to the function when it is called (it’s a call time term).

## Default values

If a function is called, but an argument is not provided, then the corresponding value becomes `undefined`.

We can specify the so-called “default” (to use if omitted) value for a parameter in the function declaration, using `=`.

## Returning a value

A function can return a value back into the calling code as the result.

***A function with an empty `return` or without it returns `undefined`***

***Never add a newline between `return` and the value.***
Javascript will add a semicolon after `return`.

## Naming a function

- A name should clearly describe what the function does. When we see a function call in the code, a good name instantly gives us an understanding what it does and returns.
- A function is an action, so function names are usually verbal.
- There exist many well-known function prefixes like `create…`, `show…`, `get…`, `check…` and so on. Use them to hint what a function does.
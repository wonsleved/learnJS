# Object methods, "this"

- Functions that are stored in object properties are called “methods”.
- Methods allow objects to “act” like `object.doSomething()`.
- Methods can reference the object as `this`.

The value of `this` is defined at run-time.

- When a function is declared, it may use `this`, but that `this` has no value until the function is called.
A function can be copied between objects.
When a function is called in the “method” syntax: `object.method()`, the value of `this` during the call is `object`.

## “this” in methods

To access the object, a method can use the `this` keyword.

## “this” is not bound

In JavaScript, keyword `this` behaves unlike most other programming languages. It can be used in any function, even if it’s not a method of an object.

The value of `this` is evaluated during the run-time, depending on the context.

Calling without an object: `this == undefined`

## Arrow functions have no “this”

Arrow functions are special: they don’t have their “own” `this`. If we reference `this` from such a function, it’s taken from the outer “normal” function.



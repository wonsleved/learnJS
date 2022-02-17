# Reference Type

A dynamically evaluated method call can lose `this`.

## Reference type explained

Looking closely, we may notice two operations in `obj.method()` statement:

1. First, the dot `'.'` retrieves the property `obj.method`. 
2. Then parentheses `()` execute it.

**To make `user.hi()` calls work, JavaScript uses a trick – the dot `'.'` returns not a function, but a value of the special [Reference Type](https://tc39.github.io/ecma262/#sec-reference-specification-type).**

The Reference Type is a “specification type”. We can’t explicitly use it, but it is used internally by the language.

The value of Reference Type is a three-value combination `(base, name, strict)`, where:

- `base` is the object.
- `name` is the property name.
- `strict` is true if use strict is in effect.

Reference type is a special “intermediary” internal type, with the purpose to pass information from dot `.` to calling parentheses `()`.

So, as the result, the value of `this` is only passed the right way if the function is called directly using a dot `obj.method()` or square brackets `obj['method']()` syntax (they do the same here).
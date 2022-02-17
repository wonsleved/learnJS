# Function expressions

```
let sayHi = function() {
  alert( "Hello" );
};
```

As the function creation happens in the context of the assignment expression (to the right side of `=`), this is a *Function Expression*.

## Function is a value

## Callback functions

It is possible to pass function expression as argument into another function.

## Function Expression vs Function Declaration

- *Function Declaration*: a function, declared as a separate statement, in the main code flow.
- *Function Expression*: a function, created inside an expression or inside another syntax construct. Here, the function is created at the right side of the “assignment expression” `=`:

**A Function Expression is created when the execution reaches it and is usable only from that moment.**

**A Function Declaration can be called earlier than it is defined.**

**In strict mode, when a Function Declaration is within a code block, it’s visible everywhere inside that block. But not outside of it.**

***Prefer function declaration to function expression***




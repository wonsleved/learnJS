# Optional chaining '?.'

The optional chaining `?.` is a safe way to access nested object properties, even if an intermediate property doesn’t exist.

## The “non-existing property” problem

If property doesn't exist in object, and we try to access property of previous one, we'll get an error.

## Optional chaining

The optional chaining `?.` stops the evaluation if the value before `?.` is `undefined` or `null` and returns `undefined`.

***Don’t overuse the optional chaining***

We should use `?.` only where it’s ok that something doesn’t exist.

***The variable before `?.` must be declared***

## Short-circuiting

`?.` immediately stops (“short-circuits”) the evaluation if the left part doesn’t exist.

```
let user = null;
let x = 0;

user?.sayHi(x++); // no "sayHi", so the execution doesn't reach x++

alert(x); // 0, value not incremented
```

## Other variants: ?.(), ?.[]

- `obj?.prop` – returns `obj.prop` if `obj` exists, otherwise `undefined`.
- `obj?.[prop]` – returns `obj[prop]` if `obj` exists, otherwise `undefined`.
- `obj.method?.()` – calls `obj.method()` if `obj.method` exists, otherwise returns `undefined`.


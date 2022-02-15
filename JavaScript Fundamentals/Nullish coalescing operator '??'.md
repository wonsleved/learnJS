# Nullish coalescing operator '??'

The result of `a` ?? `b` is:

- if `a` is defined, then `a`,
- if `a` isn’t defined, then `b`.

## Using ?? with && or ||

Due to safety reasons, JavaScript forbids using `??` together with `&&` and `||` operators, unless the precedence is explicitly specified with parentheses.

```
let x = 1 && 2 ?? 3; // Syntax error
```
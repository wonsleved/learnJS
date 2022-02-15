# The "switch" statement

A `switch` statement can replace multiple `if` checks.

```
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```

***If there is no `break` then the execution continues with the next `case` without any checks.***

***Any expression can be a `switch/case` argument***

## Type matters

Let’s emphasize that the equality check is always **strict**. The values must be of the same type to match.


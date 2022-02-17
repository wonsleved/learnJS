# Conditional branching: if, '?'

## The “if” statement

The `if(...)` statement evaluates a condition in parentheses and, if the result is `true`, executes a block of code.

## Boolean conversion

The `if (…)` statement evaluates the expression in its parentheses and converts the result to a boolean.

## The “else” clause

The `if` statement may contain an optional “else” block. It executes when the condition is falsy.

## Several conditions: “else if”

Sometimes, we’d like to test several variants of a condition. The `else if` clause lets us do that.

## Conditional operator ‘?’

The operator is represented by a question mark `?`. Sometimes it’s called “ternary”, because the operator has three operands.

```
let result = condition ? value1 : value2;
```

The `condition` is evaluated: if it’s truthy then `value1` is returned, otherwise – `value2`.




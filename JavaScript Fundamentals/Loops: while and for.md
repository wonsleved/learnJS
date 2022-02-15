# Loops: while and for

## The “while” loop

```
while (condition) {
  // code
  // so-called "loop body"
}
```

***Curly braces are not required for a single-line body***

## The “do…while” loop

```
do {
  // loop body
} while (condition);
```

## The “for” loop

```
for (begin; condition; step) {
  // ... loop body ...
}
```

### Skipping parts

```
for (;;) {
  // repeats without limits
}
```

## Breaking the loop

We can force the exit at any time using the special `break` directive.

## Continue to the next iteration

The `continue` directive is a “lighter version” of `break`. It doesn’t stop the whole loop. Instead, it stops the current iteration and forces the loop to start a new one (if the condition allows).

***The `continue` directive helps decrease nesting***

***No `break/continue` to the right side of ‘?’***

## Labels for break/continue

Sometimes we need to break out from multiple nested loops at once.

A *label* is an identifier with a colon before a loop:
```
labelName: for (...) {
  ...
}
```

The `break <labelName>` statement in the loop breaks out to the label.




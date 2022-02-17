# BigInt

A bigint is created by appending `n` to the end of an integer literal or by calling the function `BigInt` that creates bigints from strings, numbers etc.

```
const bigint = 1234567890123456789012345678901234567890n;

const sameBigint = BigInt("1234567890123456789012345678901234567890");

const bigintFromNumber = BigInt(10); // same as 10n
```

All operations on bigints return bigints.

```
alert(5n / 2n); // 2
```

***The unary plus is not supported on bigints***

## Comparisons

Comparisons, such as `<`, `>` work with bigints and numbers just fine.

Numbers and bigints belong to different types, they can be equal `==,` but not strictly equal `===`.

```
alert( 1 == 1n ); // true

alert( 1 === 1n ); // false
```

## Boolean operations

When inside `if` or other boolean operations, bigints behave like numbers.
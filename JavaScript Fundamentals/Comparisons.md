# Comparisons

## Boolean is the result

All comparison operators return a boolean value.

## String comparison

To see whether a string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.

1. Compare the first character of both strings.
2. If the first character from the first string is greater (or less) than the other string’s, then the first string is greater (or less) than the second. We’re done.
3. Otherwise, if both strings’ first characters are the same, compare the second characters the same way.
4. Repeat until the end of either string.
5. If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.

## Comparison of different types

When comparing values of different types, JavaScript converts the values to numbers.

**A strict equality operator `===` checks the equality without type conversion.**

There is also a “strict non-equality” operator `!==` analogous to `!=`.

## Comparison with null and undefined

**For a strict equality check `===`**

These values are different, because each of them is a different type.

**For a non-strict check `==`**
```
alert( null == undefined ); // true
```

**For maths and other comparisons `< > <= >=`**

`null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

## Strange result: null vs 0

```
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true
```

The reason is that an equality check `==` and comparisons `> < >= <=` work differently. Comparisons convert null to a number, treating it as `0`. That’s why (3) `null >= 0` is true and (1) `null > 0` is false.

On the other hand, the equality check `==` for `undefined` and `null` is defined such that, without any conversions, they equal each other and don’t equal anything else. That’s why (2) `null == 0` is false.

## An incomparable undefined

The value `undefined` shouldn’t be compared to other values.

```
alert( undefined > 0 ); // false
alert( undefined < 0 ); // false
alert( undefined == 0 ); // false
```


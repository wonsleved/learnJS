# Type Conversions

For example, `alert` automatically converts any value to a string to show it. Mathematical operations convert values to numbers.

***Not talking about objects yet.***
For now we’ll just be talking about primitives.

## String Conversion

String conversion happens when we need the string form of a value.

Call the `String(value)` function to convert a `value` to a string.

A `false` becomes `"false"`, `null` becomes `"null"`, etc.

## Numeric Conversion

Numeric conversion happens in mathematical functions and expressions automatically.

Use `Number(value)` function to explicitly convert a `value` to a number.

If the string is not a valid number, the result of such a conversion is `NaN`.

`undefined`	=> `NaN`,
`null` => `0`,
`true` and `false` => `1` and `0`

## Boolean Conversion

It happens in logical operations (later we’ll meet condition tests and other similar things) but can also be performed explicitly with a call to `Boolean(value)`.

The conversion rule:

- Values that are intuitively “empty”, like `0`, an empty string, `null`, `undefined`, and `NaN`, become `false`.
- Other values become `true`.

***The string with zero "0" is true***


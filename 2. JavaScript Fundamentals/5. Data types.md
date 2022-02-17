# Data types

There are 8 basic data types in JavaScript.

- number
- bigint
- string
- boolean
- null
- undefined
- object
- symbol

## Number

The number type represents both integer and floating point numbers.

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: `Infinity`, `-Infinity` and `NaN`.
```
alert( 1 / 0 ); // Infinity
```
`NaN` represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance:
```
alert( "not a number" / 2 ); // NaN, such division is erroneous
```

## BigInt

The “number” type cannot represent integer values larger than (253-1), or less than -(253-1) for negatives.

A `BigInt` value is created by appending `n` to the end of an integer:
```
const bigInt = 1234567890123456789012345678901234567890n;
```

## String

A string in JavaScript must be surrounded by quotes.

***There is no character type.***

## Boolean (logical type)

The boolean type has only two values: true and false.

## The “null” value

The special `null` value does not belong to any of the types described above.

It’s just a special value which represents “nothing”, “empty” or “value unknown”.

## The “undefined” value

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.

The meaning of `undefined` is “value is not assigned”.

If a variable is declared, but not assigned, then its value is `undefined`.

## Objects and Symbols

The `object` type is special.

All other types are called “primitive” because their values can contain only a single thing (be it a string or a number or whatever). In contrast, objects are used to store collections of data and more complex entities.

The `symbol` type is used to create unique identifiers for objects.

## The typeof operator

A call to `typeof x` returns a string with the type name.

***The `typeof(x)` syntax***
It’s the same as `typeof x`.
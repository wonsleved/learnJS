# Symbol type

By specification, object property keys may be either of string type, or of symbol type.\

## Symbols

A “symbol” represents a unique identifier.

```
let id = Symbol();
```

```
// id is a symbol with the description "id"
let id = Symbol("id");
alert(id.description); // id
```

Two symbols with the same description are not equal.

Symbols don’t auto-convert to a string, but we can use `symbol.toString()`;

## “Hidden” properties

Symbols allow us to create “hidden” properties of an object, that no other part of code can accidentally access or overwrite.

## Symbols in an object literal

If we want to use a symbol in an object literal `{...}`, we need square brackets around it.

## Symbols are skipped by for…in

## Global symbols

There exists a global symbol registry. We can create symbols in it and access them later, and it guarantees that repeated accesses by the same name return exactly the same symbol.

In order to read (create if absent) a symbol from the registry, use `Symbol.for(key)`.

Symbols inside the registry are called global symbols.

### Symbol.keyFor

`Symbol.keyFor(symbol)` returns a name by a global symbol.

## System symbols

- `Symbol.hasInstance`
- `Symbol.isConcatSpreadable`
- `Symbol.iterator`
- `Symbol.toPrimitive`
- …and so on.

`Symbol.toPrimitive` allows us to describe object to primitive conversion.

***These methods must return a primitive, not an object.***

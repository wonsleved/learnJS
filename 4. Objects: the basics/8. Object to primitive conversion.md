# Object to primitive conversion

## Conversion rules

1. All objects are true in a boolean context. There are only numeric and string conversions.
2. The numeric conversion happens when we subtract objects or apply mathematical functions.
3. As for the string conversion – it usually happens when we output an object like alert(obj) and in similar contexts.

There are three variants(hints) of type conversion.

- `"string"`
- `"number"`
- `"default"` (Occurs in rare cases when the operator is “not sure” what type to expect)

***No `"boolean"` hint***

**To do the conversion, JavaScript tries to find and call three object methods:**

1. Call `obj[Symbol.toPrimitive](hint)` – the method with the symbolic key `Symbol.toPrimitive` if such method exists,
2. Otherwise if hint is `"string"`
   - try `obj.toString()` and `obj.valueOf()`, whatever exists.
3. Otherwise if hint is `"number"` or `"default"`
   - try `obj.valueOf()` and `obj.toString()`, whatever exists.

## Symbol.toPrimitive

```
let user = {
  name: "John",
  money: 1000,

  [Symbol.toPrimitive](hint) {
    alert(`hint: ${hint}`);
    return hint == "string" ? `{name: "${this.name}"}` : this.money;
  }
};
```

## toString/valueOf

- If conversation to string then toString if exists, else valueOf
- If conversation to number then valueOf if exists, else toString

By default, a plain object has following `toString` and `valueOf` methods:

- The `toString` method returns a string `"[object Object]"`.
- The `valueOf` method returns the object itself.

```
let user = {
  name: "John",
  money: 1000,

  // for hint="string"
  toString() {
    return `{name: "${this.name}"}`;
  },

  // for hint="number" or "default"
  valueOf() {
    return this.money;
  }

};
```

### A conversion can return any primitive type

There is no control whether `toString` returns exactly a string, or whether `Symbol.toPrimitive` method returns a number for a hint `"number"`.
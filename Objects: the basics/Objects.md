# Objects

## Literals and properties

We can immediately put some properties into `{...}` as “key: value” pairs.

To remove a property, we can use `delete` operator:

```
delete user.age;
```

## Square brackets

If property is a multiword or a variable, use `Object[prop]`.

```
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

## Property value shorthand

```
function makeUser(name, age) {
  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };
}
```

## Property names limitations

For an object property, there’s no such restriction.

A special property named `__proto__`. We can’t set it to a non-object value.

## Property existence test, “in” operator

```
"key" in object
```

## The “for…in” loop

```
for (key in object) {
  // executes the body for each key among object properties
}
```



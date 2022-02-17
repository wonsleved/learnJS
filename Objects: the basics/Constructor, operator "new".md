# Constructor, operator "new"

## Constructor function

Constructor functions technically are regular functions. There are two conventions though:

1. They are named with capital letter first.
2. They should be executed only with `"new"` operator.

When a function is executed with `new`, it does the following steps:

1. A new empty object is created and assigned to `this`.
2. The function body executes. Usually it modifies `this`, adds new properties to it.
3. The value of `this` is returned.

## Constructor mode test: new.target

Inside a function, we can check whether it was called with `new` or without it, using a special `new.target` property.

It is `undefined` for regular calls and equals the function if called with `new`.

```
function User(name) {
  if (!new.target) { // if you run me without new
    return new User(name); // ...I will add new for you
  }
  this.name = name;
}

let john = User("John"); // redirects call to new User
alert(john.name); // John
```

## Return from constructors

Usually constructors don’t have a `return` statement.

If there is a `return` statement, then the rule is simple:

- If `return` is called with an object, then the object is returned instead of this.
- If `return` is called with a primitive, it’s ignored.

***Omitting parentheses***

```
let user = new User; // <-- no parentheses
// same as
let user = new User();
```

It is not a “good style”.

## Methods in constructor

We can add to `this` not only properties, but methods as well.







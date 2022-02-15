# Currying

Currying is a transformation of functions that translates a function from callable as `f(a, b, c)` into callable as `f(a)(b)(c)`

Currying doesn’t call a function. It just transforms it.

```
function curry(f) {
  return function(a) {
    return function(b) {
      return f(a, b);
    };
  };
}
```

***Currying allows us to easily get partials.***

## Advanced curry implementation

```
function curry(func) {

  return function curried(...args) {
    if (args.length >= func.length) {
      return func.apply(this, args);
    } else {
      return function(...args2) {
        return curried.apply(this, args.concat(args2));
      }
    }
  };
  
}
```

***Fixed-length functions only.***
The currying requires the function to have a fixed number of arguments.



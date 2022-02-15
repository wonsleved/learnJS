# Proxy and Reflect

A Proxy `object` wraps another object and intercepts operations, like reading/writing properties and others, optionally handling them on its own, or transparently allowing the object to handle them.

## Proxy

```
let proxy = new Proxy(target, handler)
```

- `target` – is an object to wrap, can be anything, including functions.

- `handler` – proxy configuration: an object with “traps”, methods that intercept operations. – e.g. get trap for reading a property of target, set trap for writing a property into target, and so on.

`Proxy` is a special “exotic object”. It doesn’t have own properties. With an empty `handler` it transparently forwards operations to `target`.

## Default value with “get” trap

To intercept reading, the `handler` should have a method `get(target, property, receiver)`.

It triggers when a property is read, with following arguments:

- `target` – is the target object, the one passed as the first argument to new Proxy, 
- `property` – property name,
- `receiver` – if the target property is a getter, then `receiver` is the object that’s going to be used as `this` in its call. Usually that’s the `proxy` object itself (or an object that inherits from it, if we inherit from proxy).

## Validation with “set” trap

The `set` trap triggers when a property is written.

`set(target, property, value, receiver)`:

- `target` – is the target object, the one passed as the first argument to new Proxy,
- `property` – property name,
- `value` – property value,
- `receiver` – similar to `get` trap, matters only for setter properties.

The `set` trap should return `true` if setting is successful, and `false` otherwise (triggers `TypeError`).

## Iteration with “ownKeys” and “getOwnPropertyDescriptor”

`Object.keys`, `for..in` loop and most other methods that iterate over object properties use `[[OwnPropertyKeys]]` internal method (intercepted by `ownKeys` trap) to get a list of properties.

Use `ownKeys` trap to make `for..in` loop over `user`, and also `Object.keys` and `Object.values`.

***If we return a key that doesn’t exist in the object, Object.keys won’t list.***

**It can be used to filter actions on protected properties**

## “In range” with “has” trap

The `has` trap intercepts `in` calls.

`has(target, property)`

- `target` – is the target object, passed as the first argument to `new Proxy`,
- `property` – property name

## Wrapping functions: "apply"

The `apply(target, thisArg, args)` trap handles calling a proxy as function:

- `target` is the target object (function is an object in JavaScript),
- `thisArg` is the value of `this`.
- `args` is a list of arguments.

## Reflect

`Reflect` is a built-in object that simplifies creation of `Proxy`.

We can use `Reflect` to forward an operation to the original object.

```
Reflect.set(user, 'name', 'John');
```

## Proxy limitations

Proxies provide a unique way to alter or tweak the behavior of the existing objects at the lowest level. Still, it’s not perfect. There are limitations.

### Built-in objects: Internal slots

Many built-in objects, for example `Map`, `Set`, `Date`, `Promise` and others make use of so-called “internal slots”.

`Map` stores items in the internal slot `[[MapData]]`. Built-in methods access them directly, not via `[[Get]]/[[Set]]` internal methods. So `Proxy` can’t intercept that.

***`Array` has no internal slots***

### Private fields

A similar thing happens with private class fields.

Private fields are implemented using internal slots. JavaScript does not use `[[Get]]/[[Set]]` when accessing them.

### Proxy != target

The proxy and the original object are different objects.

***Proxies can’t intercept a strict equality test `===`***

## Revocable proxies

A *revocable* proxy is a proxy that can be disabled.

```
let {proxy, revoke} = Proxy.revocable(target, handler)
```

The call returns an object with the `proxy` and `revoke` function to disable it.




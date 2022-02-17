# Object references and copying

***A variable assigned to an object stores not the object itself, but its “address in memory” – in other words “a reference” to it.***

***When an object variable is copied, the reference is copied, but the object itself is not duplicated.***

## Comparison by reference

Two objects are equal only if they are the same object.

## Cloning and merging, Object.assign

So, copying an object variable creates one more reference to the same object.

```
Object.assign(dest, [src1, src2, src3...])
```

- The first argument `dest` is a target object.
- Further arguments `src1, ..., srcN` (can be as many as needed) are source objects.
- It copies the properties of all source objects `src1, ..., srcN` into the target `dest`. In other words, properties of all arguments starting from the second are copied into the first object.
- The call returns `dest`.

```
let clone = Object.assign({}, user);
```

## Nested cloning

Properties can be references to other objects.

We can use recursion to implement it. Or, to not reinvent the wheel, take an existing implementation, for instance [_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep) from the JavaScript library [lodash](https://lodash.com/).

***Const objects can be modified***


# Garbage collection

## Reachability

The main concept of memory management in JavaScript is *reachability*.

There’s a base set of inherently reachable values, that cannot be deleted for obvious reasons.

For instance:

1. The currently executing function, its local variables and parameters.
   - Other functions on the current chain of nested calls, their local variables and parameters.
   - Global variables.
   - (there are some other, internal ones as well)
   These values are called roots.

2. Any other value is considered reachable if it’s reachable from a root by a reference or by a chain of references.

## Unreachable island

It is possible that the whole island of interlinked objects becomes unreachable and is removed from the memory.

## Internal algorithms

The basic garbage collection algorithm is called “mark-and-sweep”.

The following “garbage collection” steps are regularly performed:

- The garbage collector takes roots and “marks” (remembers) them.
- Then it visits and “marks” all references from them.
- Then it visits marked objects and marks their references. All visited objects are remembered, so as not to visit the same object twice in the future.
- …And so on until every reachable (from the roots) references are visited.
- All objects except marked ones are removed.

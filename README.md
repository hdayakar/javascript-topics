# Destructing assignment
The *destructing assignment* syntax is a javascript expression that makes it possible to unpack
values from arrays, or properties from objects, into distinct variables.

~~~~js
var a, b, rest;
[a, b] = [10, 20];

console.log(a);
// expected output: 10

console.log(b);
// expected output: 20

[a, b, ...rest] = [10, 20, 30, 40, 50];

console.log(rest);
// expected output: [30,40,50]
~~~~

## Object destructuring
~~~~js
var o = {p: 42, q: true};
var {p, q} = o;

console.log(p); // 42
console.log(q); // true
~~~~

## Array destructuring
~~~~js
var foo = ['one', 'two', 'three'];

var [one, two, three] = foo;
console.log(one); // "one"
console.log(two); // "two"
console.log(three); // "three"
~~~~

### Default values
A variable can be assigned a default, in the case that the value unpacked from the object is undefined.
~~~~js
var {a = 10, b = 5} = {a: 3};

console.log(a); // 3
console.log(b); // 5
~~~~

### Swapping variables
Two variables values can be swapped in one destructuring expression.

Without destructuring assignment, swapping two values requires a temporary variable (or, in some low-level languages, the XOR-swap trick).

~~~~js
var a = 1;
var b = 3;

[a, b] = [b, a];
console.log(a); // 3
console.log(b); // 1
~~~~

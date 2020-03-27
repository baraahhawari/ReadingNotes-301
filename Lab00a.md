# ES6 let and const

### ES6 ECMAScript 2015

[ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/)
**Overview: Variable declarations**
_let_
[MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
[caniuse.com](https://caniuse.com/#feat=let)

_const_
[MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
[caniuse.com](https://caniuse.com/#feat=const)

**Additional resources**

1. [Video from Fun Fun Function titled: “var, let and const - What, why and how](https://www.youtube.com/watch?v=sjyJBL5fkp8)
1. [“JavaScript ES6+: var, let, or const?” by Eric Elliott](https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75)
1. [“ES6 let vs. const variables” by Wes Bos](https://wesbos.com/let-vs-const/)

## ECMAScript is object-based:

- **basic language and host facilities are provided by objects**.
- **an object** in ECMAScript: is a collection of zero or more **properties** each with **attributes** that determine how each property can be used.
- when **attribute for a property** is set to **false**, any attempt by executed ECMAScript code to assign a different value to the property **fails**.

(Properties : are containers that hold other objects, **primitive values**, or **functions**).

**primitive values** is a member of one of the following built-in types:

1. Undefined
1. Null
1. Boolean
1. Number
1. String
1. Symbol

_ECMAScript_ defines a collection of **built-in objects**

- Global Objects
  - Object, Function, Boolean, Symbol, and various Error objects **objects that represent and manipulate numeric values** including:
    - Math
    - Number
    - Date
  - the text processing objects
    - String
    - RegExp
  - objects that are **indexed** collections of values including _Array_ and nine different kinds of Typed Arrays whose elements all have a specific numeric data representation.
  - keyed collections including:
    - Map
    - Set objects
  - objects supporting structured data including:
    - JSON object
    - ArrayBuffer
    - DataView
  - objects supporting control abstractions including:
    - generator functions
    - Promise objects
  - reflection objects including:
    - Proxy
    - Reflect.

_ECMAScript_ also defines a set of built-in **operators**:

- various unary operations
- multiplicative operators
- additive operators
- bitwise shift operators
- relational operators
- equality operators
- binary bitwise operators
- binary logical operators
- assignment operators
- the comma operator.

Large **ECMAScript** programs are supported by **modules** which:

1. allow a program to be divided into multiple sequences of **statements** and **declarations**.
1. Each module explicitly identifies declarations it uses that need to be provided by other modules and which of its declarations are available for use by other modules.

**features**

- let
- const

## The let statement

**declares a block scope local variable, optionally initializing it to a value**

_let_ vs _var_
**let** allows you to declare variables that are limited to a scope of a block statement, or expression on which it is used
**var** which defines a variable globally, or locally to an entire function regardless of block scope.

let, unlike var, **does not create a property on the global object**

```function varTest() {
  var x = 1;
  {
    var x = 2;  // same variable!
    console.log(x);  // 2
  }
  console.log(x);  // 2
}

function letTest() {
  let x = 1;
  {
    let x = 2;  // different variable
    console.log(x);  // 2
  }
  console.log(x);  // 1
}

var x = 'global';
let y = 'global';
console.log(this.x); // "global"
console.log(this.y); // undefined
```

## The const statement

**The value of a constant can't be changed through reassignment, and it can't be redeclared.**

_const_ declaration:

1. creates a constant whose scope can be either **global** or **local** to the block in which it is declared.
1. **Global** constants do **not** become **properties of the window object**, unlike var variables.
1. creates a read-only reference to a value.
1. variable identifier cannot be reassigned.

**A constant cannot share its name with a function or a variable in the same scope.**

#### Summary

You are familiar with the process of declaring a variable using **var**, and how that **variable receives global or local scope depending on the context in which it was declared**. If the variable is declared outside of any functions, it has global scope, but if it is declared inside a function, the variable is scoped to that function and not accessible globally.

**let**

1. a variable declaration can be scoped to a code block { code }, such as we commonly see with **for, if, or while** constructions. As with variables declared with var, the **values assigned to them can be reassigned** to any type of value at any time, so long as the reassignment occurs within the same scope in which the variable was declared.

**const** is a little more complicated:

- Like let, **const** is also **block-scoped**.
- Variables initialized with const must be assigned a value at the time they are declared.
- Unlike variables declared with var, variables declared with const **do not become properties of the window object**.
- When const is used to assign to a variable one of the five primitive values in JavaScript (number, string, Boolean, null, undefined), the variable **cannot be reassigned and attempting to do so will throw an error:** “Uncaught TypeError: Assignment to constant variable.”
- However, when a const variable is used to hold an object (and by extension arrays and functions, which are both objects in JavaScript), new properties can be assigned to the object and their values reassigned at will.

:green_heart:
@bara'ah_hawari.

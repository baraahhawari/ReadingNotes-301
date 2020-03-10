# ES6 let and const
### ES6 ECMAScript 2015

## ECMAScript is object-based: 
- __basic language and host facilities are provided by objects__.
- **an object** in ECMAScript: is a collection of zero or more **properties** each with **attributes** that determine how each property can be used.
- when **attribute for a property** is set to __false__, any attempt by executed ECMAScript code to assign a different value to the property __fails__.

(Properties : are containers that hold other objects, __primitive values__, or __functions__).

__primitive values__ is a member of one of the following built-in types:
1. Undefined
1. Null
1. Boolean
1. Number
1. String
1. Symbol

_ECMAScript_ defines a collection of **built-in objects**
- Global Objects
    - Object, Function, Boolean, Symbol, and various Error objects __objects that represent and manipulate numeric values__ including:
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
__declares a block scope local variable, optionally initializing it to a value__

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
console.log(this.y); // undefined```

## The const statement 
__The value of a constant can't be changed through reassignment, and it can't be redeclared.__

_const_ declaration:
1. creates a constant whose scope can be either **global** or **local** to the block in which it is declared. 
1. **Global** constants do **not** become **properties of the window object**, unlike var variables.
1. creates a read-only reference to a value. 
1. variable identifier cannot be reassigned.

__A constant cannot share its name with a function or a variable in the same scope.__

#### Summary
**const** is a little more complicated:

- Like let, const is also block-scoped.
- Variables initialized with const must be assigned a value at the time they are declared.
- Unlike variables declared with var, variables declared with const do not become properties of the window object.
- When const is used to assign to a variable one of the five primitive values in JavaScript (number, string, Boolean, null, undefined), the variable cannot be reassigned and attempting to do so will throw an error: “Uncaught TypeError: Assignment to constant variable.”
- However, when a const variable is used to hold an object (and by extension arrays and functions, which are both objects in JavaScript), new properties can be assigned to the object and their values reassigned at will.


:green_heart:
@bara'ah_hawari.

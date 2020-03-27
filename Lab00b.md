# ES6 Arrow Functions

[ES6 ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/)

**Arrow Functions**

1. [MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
1. [caniuse.com](https://caniuse.com/#search=arrow%20functions)

**Additional resources**
[“JavaScript Arrow Functions” by Wes Bos](https://wesbos.com/arrow-functions/)

**Arrow function expressions**

1. syntactically compact alternative to a **regular function expression**
   **although without its own bindings to the this, arguments, super, or new.target keywords.**
1. Arrow function expressions are ill suited as methods
1. they cannot be used as constructors.

_Two factors_ influenced the introduction of arrow functions:

- the need for shorter functions
- the behavior of the this keyword.

**_Syntax_**:
`() => { statements }`

**No separate this**
Before arrow functions, every new function defined its own **this** value based on how the function was called:

1. A new object in the case of a constructor.
1. undefined in strict mode function calls.
1. The base object if the function was called as an "object method".

**An arrow function** does **not** have its own **this**. The **this** value of the enclosing lexical scope is used
**arrow functions** follow the normal variable lookup rules. So while searching for **this** which is not present in current scope, an arrow function ends up finding the **this** from _its enclosing scope_.

**Invoked through call or apply**
b/c arrow functions do not have their own this: - the methods **call()** and **apply()** can only pass in parameters. - Any this argument is ignored.
**example**:

```var adder = {
  base: 1,

  add: function(a) {
    var f = v => v + this.base;
    return f(a);
  },

  addThruCall: function(a) {
    var f = v => v + this.base;
    var b = {
      base: 2
    };

    return f.call(b, a);
  }
};

console.log(adder.add(1));         // This would log 2
console.log(adder.addThruCall(1)); // This would log 2 still
```

**No binding of arguments**

1. **arguments** is an **Array**-like object accessible inside functions that **contains** the values of the arguments **passed** to that function.
1. The **arguments object** is a **local** variable available within all **non-arrow functions**.

**Arrow functions used as methods**
**arrow function expressions are best suited for non-method functions**
if its used as method the output will be undefined and the object will be return the window object.

**Arrow functions cannot be used as constructors and will throw an error when used with new.**
**Arrow functions do not have a prototype property.**
**An arrow function cannot contain a line break between its parameters and its arrow.**

1. line break after the arrow
1. using parentheses/braces
1. line breaks between arguments.

```var func = (a, b, c) =>
  1;

var func = (a, b, c) => (
  1
);

var func = (a, b, c) => {
  return 1
};

var func = (
  a,
  b,
  c
) => 1;
```

_Arrow Function_ **Implicit**(Implied indirectly, without being directly expressed) Return.
**explicit** return (Very specific, clear, or detailed.)

### Function expression

[function expressions](https://developer.mozilla.org/en-US/docs/web/JavaScript/Reference/Operators/function)

- The **function** keyword can be used to define a function inside an expression.
- You can also define functions using the **Function constructor** and a **function declaration**.

### function declaration

[function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)

- The function declaration (function statement) **defines** a function with the **specified parameters**.

**Summary**
There are a few **caveats(limitations)** with arrow functions.

1. Most importantly, arrow functions **affect function scope**.
1. **code block** the scope of a function is within its opening and closing curly braces.
1. when an arrow function is used, the **scope** of the function bubbles up to the **next-nearest scope**. This can be an **enclosing function**, or if it is a **deeply-nested function**, the closest function that does not use an arrow function.
1. If arrow functions are used exclusively(only) in a file, the **scope of the function** will become the _global window object_.

**Why does this happen? Arrow functions do not bind “this”, so the context of “this” bubbles up to the global window object, which is the next-nearest enclosing scope. Therefore, you will want to avoid using an arrow function in a constructor or any method that needs to use “this” to behave properly.**

:green_heart:
@bara'ah_hawari.

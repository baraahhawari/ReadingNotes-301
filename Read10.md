# The Call Stack and Debugging :computer:

**Reading**

1. [The Call Stack defined on MDN](https://developer.mozilla.org/en-US/docs/Glossary/Call_stack)
1. [Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)
1. [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

**Additional Resources**

1. [JavaScript errors reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)

## Call stack

_a mechanism :nut_and_bolt: for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions_

1. When a **script calls** a function, the **interpreter** adds it to the call stack and then starts carrying out the function.
1. Any functions that are called by that function are added to the **call stack further** up, and run where their calls are reached.
1. When the current function is finished, the **interpreter** takes it off the stack and resumes execution where it left off in the last code listing.
1. If the stack takes up more space than it had assigned to it, it results in a "stack overflow" **error**.

### Understanding the JavaScript call stack :pager:

_The JavaScript **engine** :gear: (which is found in a hosting environment like the browser), is a **single-threaded interpreter** comprising of a heap and a single call stack. The **browser provides** **web APIs** like the **DOM**, **AJAX, and Timers**._

`call stack_ is a data structure that uses the _Last In, First Out (LIFO)_ principle to temporarily store and manage function invocation (call).`

The key takeaways from the **call stack** are:

1. It is **single-threaded**. Meaning it can only do one thing at a time.
2. Code execution is **synchronous**.
3. A function invocation creates a **stack** frame that occupies a **temporary** memory.
4. It works as a **LIFO** — Last In, First Out data structure.

## JavaScript error messages && debugging :no_entry_sign:

**Types of error messages**

1. **Reference errors**: use a variable that is not yet declared
1. **Syntax errors**: something that cannot be parsed in terms of syntax
1. **Range errors**: manipulate an object with some kind of length and give it an invalid length
1. **Type errors**: undefined type of variable

**Debugging** :link:

- Using Node.js with Visual Studio Code

**Tools to avoid runtime errors** :shield:

- **quokka** to evaluate your code as you type
- **eslint** to make sure your style guide is **consistency** and it will grab you an error or two along the way and
- to make JS a more **strong** typed experience you can check out stuff like **TypeScript**.

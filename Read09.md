# Refactoring

**Reading**

1. [Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)
1. [Refactoring Javascript for Readability](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec)

### Functional programming

- a programming paradigm _a style of building the structure and elements of computer programs_

  1. **Pure functions**
     - It returns the same result if given the same arguments (it is also referred as deterministic)
     - It does not cause any observable side effects
  1. **Pure functions benefits**
     - easier to test codes
  1. **impure functions**
     - with global var
     - readings external files
     - random number generator
  1. **Immutability**
     - Unchanging over time or unable to be changed.
  1. **referential transparency**
     - pure functions + immutable data = referential transparency
  1. **Functions as first-class entities** CAN:

     - refer to it from constants and variables
     - pass it as a parameter to other functions
     - return it as result from other functions

  1. **Higher-order functions**
     - takes one or more functions as arguments, or
     - returns a function as its result

## Refactoring JavaScript for Performance and Readability (with Examples!)

**Strategies**
_There are no absolutes when it comes to clean code — there's always an edge case!_

1. Return early from functions
1. Cache variables so functions can be read like sentences
1. Check for Web APIs before implementing your own functionality

```function cacheBust(url) {
  return url.includes('?') === true ?
    `${url}&time=${Date.now()}` :
    `${url}?time=${Date.now()}`
}

// Refactor into ->

function cacheBust(url) {
  // This throws an error on invalid URL which stops undefined behaviour
  const urlObj = new URL(url);
  urlObj.searchParams.append('time', Date.now); // Easier to skim read
  return url.toString();
}
```

## modules :

1. seperate the js files to make the codes eaiser to read
1. at the second file **module.exports=_the function you need to use on the other file_** (at the end of the file)
1. at the bigging of the first file **const variable name to be used(pointer to the file) = require('./filename.js')**
1. use the pointer as constructor function **(basic())**...
   **run js files on the terminal using node (file.js)**
1. make helper js file that contain another thing can be used in the 1st file and **module.exports= function**
1. put the require in the file used in
   **make an empty object in the helper file and store all the functions in it and export the object it is much easiear**

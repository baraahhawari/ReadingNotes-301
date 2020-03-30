# Code Challenge: 01 - forEach

- [forEach](https://codefellows.github.io/code-301-guide/curriculum/class-01/challenges/)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-01/challenges/DEMO.html)

**code challenge** ::
**Array.forEach**

1. Applies the callback to each element
1. You cannot “Return” a value
1. You cannot “break” or “continue” as you can with a for loop
1. By default, forEach does not mutate the array
1. If you mutate it in process, you will have interesting issues

[forEach](https://codeburst.io/javascript-the-difference-between-foreach-and-for-in-992db038e4c2)

**Array.forEach** allows you to iterate through an array. Where a normal for loop is “iterative”, forEach is more declarative or functional in nature.

It is implemented as a method on your array instance.

```let myArray = ['a', 'b', 'c'];
myArray.forEach( ... )
It takes a callback as a parameter, which in turn receives the value and the iterator, and runs it on every element.

let myArray = ['a','b','c'];

myArray.forEach( function(value, i) {
  console.log(i);       // 0, 1, 2
  console.log(value);   // a, b, c
})
```

`// For loops let us "break" away given a condition`
`// For loops let us "continue" (skip over an iteration) given a condition`
`// In a function, you can return from a for loop...`
`// In a function, you can return from a for loop...`
`// Array.forEach is a method on an array that processes every element in the array with a callback`
`// The callback is always given the current element's value and index in the array as args`
`// It cannot "break", "continue" or "return"`

# Code Challenge: 02 - Pass by value, pass by reference

- [Pass by value, pass by reference](https://codefellows.github.io/code-301-guide/curriculum/class-02/challenges/)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)

# Code Challenge: 03 - Sort

- [sort](https://codefellows.github.io/code-301-guide/curriculum/class-03/challenges/)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-03/challenges/DEMO.html)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)

**sort function** through an array

1. sort function will take a call back function(compare function)

- will compare the 2 values (a, b)
  - a, b the values from the array
    `[1,2,6,7,3,44,6]` the normal will be a=1, b=2 \ a=2, b=6 etc..
    - if the function returns **true** will reverse the array
    - if it returns **false** a=1 b=2\ a=1 b=6 (the first number stay where it is) will return the array with no changes
    - if it return a **zero** will return the array with no changes

# Code Challenge: 04 - Regular expressions, part 1

- [Regular expressions](https://codefellows.github.io/code-301-guide/curriculum/class-04/challenges/)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-04/challenges/DEMO.html)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)

  `'use strict';

    <!-- the string that we search in -->

  let string = 'The rain is spain falls mainly in june 45 times';

  // validator

    <!-- the variable that hold the value of what we are searching for -->

  let validator = /[0-2]/g;

  <!-- test it the output will be true or false depending on the number in the string var-->

  // console.log(validator.test(string));

let regex= /in\b/g;

<!-- the output will be an array of ['in', 'in', 'in'] the words that ends of in -->

// console.log(string.match(regex));

let wordsEnding=/\W/g;

<!-- output is array of empty spaces ['',''] spaces btween the words -->

console.log(string.match(wordsEnding));

<!-- the output will be The_rain_is_spain_falls_mainly_in_june_45_times -->

console.log(string.replace(wordsEnding,'\_'));

let firstLetter= /\b(\w)/g;

<!-- output is an array of the first letter of each word -->

console.log(string.match(firstLetter));

let firstLetter= /\b(\w)/g;
console.log(string.match(firstLetter));

let camelCase=string.replace(firstLetter,(rawMatch, machedThing, idx)=>{
return idx===0? machedThing.toLowerCase() : machedThing.toUpperCase();
});

<!-- the output will be the same string each first letter will be capitalized except 't' in The word will be small letter  -->

console.log(camelCase);

let camelCase=string.replace(firstLetter,(rawMatch, machedThing, idx)=>{
return idx===0? machedThing.toLowerCase() : machedThing.toUpperCase();
}).replace(/\W/g, '');

<!-- the result above but with no spaces between the words -->

console.log(camelCase);

`

# Code Challenge: 05 - Split, join, slice, splice

## Array and String Methods

- [Array and String Methods](https://codefellows.github.io/code-301-guide/curriculum/class-05/challenges/).
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-05/challenges/DEMO.html)

`
let str="bebo is awsom";
word=str.split('');

<!-- will split by letter -->

console.log(word);

let str="bebo is awsom";
word=str.split(' ');

<!-- will split by word -->

console.log(word);

let letter='B';

<!-- the code (numeric value) for the letter -->

console.log(letter.charCodeAt(0));

let str="bebo is awsom";

<!-- the 3rd letter -->

console.log(str.charAt(3));

let str="bebo is awsom";

<!-- incleds true not includes false -->

console.log(str.includes('be'));

<!-- true false -->

console.log(str.startsWith('b'));
console.log(str.endsWith('b'));

<!-- start and end of letter in the string (space is counted as index) -->

console.log(str.substring(2,3));
`

# Code Challenge: 06 - Object.keys, Object.values, Object.entries

- [Object Iteration](https://codefellows.github.io/code-301-guide/curriculum/class-06/challenges/).
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-06/challenges/DEMO.html)

_**for … in** … a looping method for objects that acts much like an old fashioned “for” loop._
`for( let property in person ) { console.log(property, person[property]); }`
_**Object.keys** … this is an Object constructor prototype method, which takes in an object as an argument and returns an array of keys (properties)_
`let properties = Object.keys(person); properties.forEach( property => { console.log(property, person[property]); })`
_**Object.values** - Returns an iterable array of just the values from the object._
_**Object.entries** - Returns an array of each “Entry” as an an array with a key and value_

**Caveats(warnings) and Notes**

1. Applies the **callback** to each element
1. You **cannot “Return”** a value
1. You **cannot “break”** or **“continue”** as you can with a for loop
1. By default, forEach does not mutate the array
1. If you mutate it in process, you will have interesting issues

## Object Iteration

- object is a data type
- use methode to get its value

```const person={
firstName:'bebo',
lastName:'3asal',
age:22,
what:['aha', 'aywa']
};
<!-- the output will be the object as it is -->
// console.log(person);
// **Object.values** is a constructor function to iterate the value of an object as an array
<!-- the output will be ['bebo', '3asal', 22, ['aha', 'aywa']] -->
console.log(Object.values(person));
```

```// the keys of the object
<!-- the output will be ['firstName', 'lastName', 'age', 'what'] -->
console.log(Object.keys(person));

// this will print the values of the object keys
Object.keys(person).forEach((value)=>{
<!-- this will print firstName    lastName   age   what -->
  console.log(value);
<!-- the output will be the values of the keys -->
<!-- bebo   3asal   22  ['aha', 'aywa']-->
console.log(person[value]);
});
```

<// the output will be array of array
console.log(Object.entries(person));>

### map for array

- forEach will return array
  **so if I did that**_the output will be undefiend_
  <b/c forEach runs for every element in the array and dose not return >

```let names=['bebo', 'nma2', '2ns'];
let allNames=names.forEach((name)=>{
<b/c forEach runs for every element in the array and doesnt return>
<!-- undefiened -->
  return name;
})
<!-- the output will be Undefiend -->
console.log(allNames);

```

_so_ **map** it runs through each element in the array and does return a new array that the exact same size of the origion one and filled with value that it return.

**map used to change the shape of data from strings to opject ot to bollean ..etc**

1. map dosent change the origion array
1. its called functional programming

- immutable (cant be change)
- no side effects (the function only works inside the braces)

<!-- the difference btw map and for each that
map whatever U return it will became an element of the array
 -->

```let allNames=names.map((name)=>{
return name;
})
<!-- the map output is always an array -->
console.log( allNames);
<!-- the output will be ['bebo', 'nma2', '2ns'] -->
```

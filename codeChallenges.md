# Code Challenge: 01 - forEach

- [forEach](https://codefellows.github.io/code-301-guide/curriculum/class-01/challenges/)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-01/challenges/DEMO.html)

# Code Challenge: 02 - Pass by value, pass by reference

- [Pass by value, pass by reference](https://codefellows.github.io/code-301-guide/curriculum/class-02/challenges/)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)

# Code Challenge: 03 - Sort

- [sort](https://codefellows.github.io/code-301-guide/curriculum/class-03/challenges/)
- [try](https://codefellows.github.io/code-301-guide/curriculum/class-03/challenges/DEMO.html)
- [video](https://www.youtube.com/playlist?list=PLVngfM2hsbi-L6G8qlWd8RyRbuTamHt3k)

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

- [ Split, join, slice, splice](https://codefellows.github.io/code-301-guide/curriculum/class-05/challenges/).
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

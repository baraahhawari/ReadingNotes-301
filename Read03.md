# Flexbox and Templating

### Learn Handlebars in 10 Minutes or Less

- popular **templating engine**.
- based on the **Mustache template** language.
- Handlebars, able you to separate the generation of **HTML** from the rest of your **JavaScript** and write cleaner code.

1. (Adding it to your project)[http://handlebarsjs.com/] or

```<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/2.0.0/handlebars.js"></script>

```

1. **Templates**

- They can contain HTML and text, mixed with Handlebars expressions.
- Expressions are wrapped in double or triple curly braces `{{}}`
- Templates need to be **compiled** to a JavaScript function before use.

1. **Expressions**

- any data that you print out in an `{{ }}` expression, will automatically get `HTML escaped` by handlebars

1. **Context**

- the object where properties you include in curly braces are looked up
- **JavaScript object** that pass to the compiled template.
  `<script id="example-template" type="text/x-handlebars-template">`

1. **Helpers**

- **JavaScript functions** that you can call from your templates, and help you **reuse code** and **create complex templates**.
- To call a helper, just use it as an expression - **{{helpername}}**.
- [registerHelper function](http://handlebarsjs.com/)

1. **Block helpers**

- have an opening and a closing tag (like the **#if** and **#each** built-ins)

## A Complete Guide to Flexbox

[open here](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
[try](https://flexboxfroggy.com/)



**code challenge** ::
**Array.forEach**

1. Applies the callback to each element
1. You cannot “Return” a value
1. You cannot “break” or “continue” as you can with a for loop
1. By default, forEach does not mutate the array
1. If you mutate it in process, you will have interesting issues

[forEach](https://codeburst.io/javascript-the-difference-between-foreach-and-for-in-992db038e4c2)

__Array.forEach__ allows you to iterate through an array. Where a normal for loop is “iterative”, forEach is more declarative or functional in nature.

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
`// Array.forEach is a method on an array that processes every element in the array with a callback
// The callback is always given the current element's value and index in the array as args
// It cannot "break", "continue" or "return"`
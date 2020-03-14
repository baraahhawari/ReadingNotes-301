# Flexbox and Templating

### Learn Handlebars in 10 Minutes or Less
### What is Handlebars?

_Handlebars is a simple templating language_
- A handlebars expression is a `{{`, some contents, followed by a `}}`. When the template is executed, these expressions are replaced with values from an input object.
- popular **templating engine**.
- based on the **Mustache template** language.
- Handlebars, able you to separate the generation of **HTML** from the rest of your **JavaScript** and write cleaner code.

1. (Adding it to your project)[http://handlebarsjs.com/] (__try it__)

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

[A Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
[Flexbox Froggy](https://flexboxfroggy.com/)

*  __display: flex;__ then the following will be written:
-  _justify-content_ property, which aligns items **horizontally** and accepts the following values:

  1. **flex-start**: Items align to the left side of the container.
  1. **flex-end**: Items align to the right side of the container.
  1. **center**: Items align at the center of the container.
  1. **space-between**: Items display with equal spacing between them.
  1. **space-around**: Items display with equal spacing around them.

  ```#pond {
    display: flex;
  justify-content:center;
  }```

- __align-items__ CSS property aligns items **vertically** and accepts the following values:
  1. **flex-start**: Items align to the top of the container.
  1. **flex-end**: Items align to the bottom of the container.
  1. **center**: Items align at the vertical center of the container.
  1. **baseline**: Items display at the baseline of the container.
  1. **stretch**: Items are stretched to fit the container.


- __flex-direction__ This CSS property defines the direction items are placed in the container, and accepts the following values:
  1. **row**: Items are placed the same as the text direction.
  1. **row-reverse**: Items are placed opposite to the text direction.
  1. **column**: Items are placed top to bottom.
  1. **column-reverse**: Items are placed bottom to top.


**Notice that when the flex direction is a column, justify-content changes to the vertical and align-items to the horizontal.**

- __order__  Sometimes reversing the row or column order of a container is not enough. In these cases, we can apply the __order__ property to individual items. By default, items have a value of 0, but we can use this property to also set it to a positive or negative integer value (-2, -1, 0, 1, 2).
-  __align-self__ Another property you can apply to **individual** items is **align-self**. This property accepts the same values as align-items and its value for the specific item.

- __flex-wrap__ property, which accepts the following values:
  1. **nowrap**: Every item is fit to a single line.
  1. **wrap**: Items wrap around to additional lines.
  1. **wrap-reverse**: Items wrap around to additional lines in reverse.

- __flex-flow__ The two properties flex-direction and flex-wrap are used so often together that the shorthand property flex-flow.
- __align-content__ to set how multiple lines are spaced apart from each other. This property takes the following values:

  1. **flex-start** : Lines are packed at the top of the container.
  1. **flex-end** : Lines are packed at the bottom of the container.
  1. **center** : Lines are packed at the vertical center of the container.
  1. **space-between** : Lines display with equal spacing between them.
  1. **space-around** : Lines display with equal spacing around them.
  1. **stretch** : Lines are stretched to fit the container.
This can be **confusing**, but **align-content** determines the **spacing between lines**, while **align-items** determines how the **items as a whole are aligned within the container**. When there is only one line, align-content has no effect.

`#pond {
  display: flex;
  flex-wrap: wrap;
align-content:flex-start;
}`


`#pond {
  display: flex;
flex-direction:column-reverse;
flex-wrap:wrap-reverse;
justify-content:center;
align-content:space-between;
}`

[trythis](https://codepip.com/games/)
=============================================================================
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
`// Array.forEach is a method on an array that processes every element in the array with a callback`
`// The callback is always given the current element's value and index in the array as args`
`// It cannot "break", "continue" or "return"`
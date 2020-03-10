# Flexbox and Templating

### Learn Handlebars in 10 Minutes or Less
- popular **templating engine**.
- based on the **Mustache template** language.
- Handlebars, able you to separate the generation of **HTML** from the rest of your **JavaScript** and write cleaner code.

1. (Adding it to your project)[http://handlebarsjs.com/] or
```<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/2.0.0/handlebars.js"></script>
```
1. **Templates**
-  They can contain HTML and text, mixed with Handlebars expressions.
- Expressions are wrapped in double or triple curly braces `{{}}`
- Templates need to be **compiled** to a JavaScript function before use.

1. **Expressions**
- any data that you print out in an `{{ }}` expression, will automatically get `HTML escaped` by handlebars

1. **Context**
-  the object where properties you include in curly braces are looked up
- **JavaScript object** that pass to the compiled template. 
```<script id="example-template" type="text/x-handlebars-template">```

1. **Helpers**
-  **JavaScript functions** that you can call from your templates, and help you __reuse code__ and __create complex templates__.
- To call a helper, just use it as an expression - __{{helpername}}__.
- (registerHelper function)[http://handlebarsjs.com/]

1. **Block helpers**
- have an opening and a closing tag (like the __#if__ and __#each__ built-ins)

## A Complete Guide to Flexbox
(open here)[https://css-tricks.com/snippets/css/a-guide-to-flexbox/]
(try)[https://flexboxfroggy.com/]
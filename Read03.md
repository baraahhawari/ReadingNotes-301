# Flexbox and Templating

[Templating with Mustache](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)

[Reference: Mustache.js Official Documentation](https://github.com/janl/mustache.js)

[Getting started with Mustache.js](https://www.youtube.com/watch?v=mguNnJP5drw)

## Mustache.js

1. js templetting library
1. ease to seperate data from presentation
1. allow to write code easier to **understand**, **maintain** and **extend**

**Code Examples**

1. snippits.js => small pieces of javaScript code
1. index.html => an example of a webpage
1. style.css => for presentatoin only
1. mustache-logo.png => for presentatoin only

`to use it, it should be included to the webpage`

**Install**
`$ npm install mustache --save`

**Usage**

```var view = {
  title: "Joe",
  calc: function () {
    return 2 + 4;
  }
};

var output = Mustache.render("{{title}} spends {{calc}}", view);
```

**Templates**
`There are several techniques that can be used to load templates and hand them to mustache.js:`

```<html>
  <body onload="renderHello()">
    <div id="target">Loading...</div>
    <script id="template" type="x-tmpl-mustache">
      Hello {{ name }}!
    </script>

    <script src="https://unpkg.com/mustache@latest"></script>
    <script src="render.js"></script>
  </body>
</html>
```

1. _Include Templates_

```function renderHello() {
  var template = document.getElementById('template').innerHTML;
  var rendered = Mustache.render(template, { name: 'Luke' });
  document.getElementById('target').innerHTML = rendered;
}
```

1. _Load External Templates_
   using [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) :

   ```function renderHello() {
   fetch('template.mustache')
    .then((response) => response.text())
    .then((template) => {
      var rendered = Mustache.render(template, { name: 'Luke' });
      document.getElementById('target').innerHTML = rendered;
    });
   }
   ```

### Learn Handlebars in 10 Minutes or Less

### What is Handlebars?

_Handlebars is a simple templating language_

- A handlebars expression is a `{{`, some contents, followed by a `}}`. When the template is executed, these expressions are replaced with values from an input object.
- popular **templating engine**.
- based on the **Mustache template** language.
- Handlebars, able you to separate the generation of **HTML** from the rest of your **JavaScript** and write cleaner code.

1. [TryHandlebars](http://tryhandlebarsjs.com/) (**try it**)
1. [Adding it to your project](http://handlebarsjs.com/) (**try it**)
1. [CDN's](https://cdnjs.com/libraries/handlebars.js) (**try it**)

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

## Handlebars.js vs Mustache

[Handlebars.js vs Mustache](https://stackshare.io/stackups/handlebars-vs-mustache)

**Handlebars.js vs Mustache: What are the differences?**

**Handlebars.js**:

1. Minimal Templating on Steroids.
1. Handlebars.js is an **extension** to the **Mustache** templating language created by Chris Wanstrath.
1. Handlebars.js and Mustache are **both** **logicless** **templating** **languages** that keep the view and the code separated like we all know they should be;

**Mustache: Logic-less templates.**

1. Mustache is a logic-less template **syntax**.
1. It can be used for **HTML**, **config files**, **source code - anything**.
1. It works by **expanding tags** in a template using **values provided in a hash or object**.
1. We call it "**logic-less**" because there are **no if statements**, **else clauses**, or** for loops**.
1. Instead there are only **tags**. Some tags are replaced with a **value**, some **nothing**, and others a **series of values**.

`Handlebars.js and Mustache belong to "Templating Languages & Extensions" category of the tech stack.`

"Simple" is the top reason why over 102 developers like _Handlebars.js_, while over 29 developers mention "Dead simple templating" as the leading cause for choosing Mustache.

Handlebars.js and Mustache are **both** **open source tools**. **Handlebars.js** with 14.5K GitHub stars and 1.86K forks on GitHub appears to be **more popular** than Mustache with 13.1K GitHub stars and 2.3K GitHub forks.

![Handlebars.js vs Mustache](img/handel-vs-mustach.png)

![Handlebars.js vs Mustache](img/handlebarsvsmustache.png)

## A Complete Guide to Flexbox

[A Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
[Flexbox Froggy](https://flexboxfroggy.com/)

- **display: flex;** then the following will be written:

* _justify-content_ property, which aligns items **horizontally** and accepts the following values:

1. **flex-start**: Items align to the left side of the container.
1. **flex-end**: Items align to the right side of the container.
1. **center**: Items align at the center of the container.
1. **space-between**: Items display with equal spacing between them.
1. **space-around**: Items display with equal spacing around them.

```#pond {
  display: flex;
justify-content:center;
}
```

- **align-items** CSS property aligns items **vertically** and accepts the following values:

1. **flex-start**: Items align to the top of the container.
1. **flex-end**: Items align to the bottom of the container.
1. **center**: Items align at the vertical center of the container.
1. **baseline**: Items display at the baseline of the container.
1. **stretch**: Items are stretched to fit the container.

- **flex-direction** This CSS property defines the direction items are placed in the container, and accepts the following values:

1. **row**: Items are placed the same as the text direction.
1. **row-reverse**: Items are placed opposite to the text direction.
1. **column**: Items are placed top to bottom.
1. **column-reverse**: Items are placed bottom to top.

**Notice that when the flex direction is a column, justify-content changes to the vertical and align-items to the horizontal.**

- **order** Sometimes reversing the row or column order of a container is not enough. In these cases, we can apply the **order** property to individual items. By default, items have a value of 0, but we can use this property to also set it to a positive or negative integer value (-2, -1, 0, 1, 2).
- **align-self** Another property you can apply to **individual** items is **align-self**. This property accepts the same values as align-items and its value for the specific item.

- **flex-wrap** property, which accepts the following values:

1. **nowrap**: Every item is fit to a single line.
1. **wrap**: Items wrap around to additional lines.
1. **wrap-reverse**: Items wrap around to additional lines in reverse.

- **flex-flow** The two properties flex-direction and flex-wrap are used so often together that the shorthand property flex-flow.
- **align-content** to set how multiple lines are spaced apart from each other. This property takes the following values:

1. **flex-start** : Lines are packed at the top of the container.
1. **flex-end** : Lines are packed at the bottom of the container.
1. **center** : Lines are packed at the vertical center of the container.
1. **space-between** : Lines display with equal spacing between them.
1. **space-around** : Lines display with equal spacing around them.
1. **stretch** : Lines are stretched to fit the container.
   This can be **confusing**, but **align-content** determines the **spacing between lines**, while **align-items** determines how the **items as a whole are aligned within the container**. When there is only one line, align-content has no effect.

`#pond { display: flex; flex-wrap: wrap; align-content:flex-start; }`

`#pond { display: flex; flex-direction:column-reverse; flex-wrap:wrap-reverse; justify-content:center; align-content:space-between; }`

# [GAMES](https://codepip.com/games/)

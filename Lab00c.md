# Intro to SMACSS
### Scalable and Modular Architecture for CSS A flexible guide to developing sites small and large.

**SMACSS** `(pronounced “smacks”)` is more style guide than rigid framework. 
1. **no library** within here for you to **download** or **install**.
1. **no git repository** for you to clone. 
**SMACSS** is a _way_ to examine your design process **and** as a way to fit those **rigid frameworks** into a **flexible** thought process. 
1. It is **an attempt** to document a consistent approach to site development when using **CSS**.

__techniques that can keep CSS more organized and more structured, leading to code that is easier to build and easier to maintain.__

### CSS Tools: Reset CSS
- to reduce browser **inconsistencies** in things like default line heights, margins and font sizes of headings, and so on. 

### Don’t Overthink It Grids

1. **Context**
`` <div class="grid">
  <!-- 100% wide -->
</div>```

1. **Columns**
```class="col-2-3"``` 
```.col-2-3 { width: 66.66%; }```
1. **Clearing Context**
_The parent element will collapse to zero height since it has only floated children. Let's fix that by clearing it._
```.grid:after {
  content: "";
  display: table;
  clear: both;
}
```
1. **Gutters**
_fixed pixel size gutters_

- The first step: __box-sizing:border-box;__
using it on absolutely everything.
```*, *:after, *:before {
  box-sizing: border-box;
}
```
**Now when set a width, that element stays that width, despite padding or borders being applied.**

- The second step: __applying a fixed padding to the right side of all columns except the last one.__

```[class*='col-'] {
  padding-right: 20px;
}
[class*='col-']:last-of-type {
  padding-right: 0;
}
```

1. **Outside Gutters**
1. **More Column Choices**
```
.col-1-2 {
  width: 50%;
}
.col-1-4 {
  width: 25%;
}
.col-1-8 {
  width: 12.5%;
}
```
1. **Sass**
1. **Modules**

## What is "Float":
**Float is a CSS positioning property**
- What are floats used for!
    - used to create entire web layouts.
- Clearing the Float

**Techniques for Clearing Floats**
1. The Empty Div Method
``` <div style="clear: both;"></div> ```
1. The Overflow Method
1. The Easy Clearing Method

**Problems with Floats**
1. Pushdown __Quick fix__: Make sure you don't have any images that do this, use **overflow: hidden** to cut off excess.
1. Double Margin Bug: Another thing to remember when dealing with IE6 is that if you apply a **margin** in the **same direction as the float**, it will **double the margin**. Quick fix: __set display: inline on the float__, and don't worry it will remain a block-level element.
1. 3px Jog:  is when text that is up next to a floated element is mysteriously kicked away by **3px** like a weird forcefield around the float. __Quick fix__: set a width or height on the affected text.
1. Bottom Margin Bug : is when if a floated parent has floated children inside it, bottom margin on those children is ignored by the parent. __Quick fix__: using bottom padding on the parent instead.


__Summary__
- Styling should progress from broadest to most specific
- **base.css** should contain any general styling on top of what is provided by a **reset.css** or **normalize.css** file.
    - Apply to elements such as body and main
    - Examples include styling of overall font and background color
- **layout.css** should contain general positioning on the page
    - Apply to elements such as header, footer, nav, aside
    - Classes and IDs can be included here
- **modules.css** should contain smaller components on the page
    - Apply to elements such as list items, individual images, specific paragraphs
    - Classes and descendant selectors should primarily be included here
- **state.css** should contain any styling that changes upon user interaction or state change
    - Apply to hover state, before or after clicking on a link, focus and blur effects
    - Pseudo-classes and pseudo-elements should be included here
- **theme.css** should contain small changes on top of all other normal styling
    - Applying temporary changes, such as a holiday theme
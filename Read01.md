# SMACSS and Responsive Web Design

**Reading**
- [Shay Howe’s intro to RWD](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)
- [All About Floats](https://css-tricks.com/all-about-floats/)

**Bookmark/Skim**
- [Don’t Overthink It Grids](https://css-tricks.com/dont-overthink-it-grids/)
- [CSS Floats Explained By Riding An Escalator](https://www.freecodecamp.org/news/css-floats-explained-by-riding-an-escalator-57fa55232333/) 
- [SMACSS Official Documentation](http://smacss.com/)

### Responsive Web Design

**Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop.**

[Ethan Marcotte book](https://abookapart.com/products/responsive-web-design)

**Responsive** vs. **Adaptive** vs. **Mobile**

- _Responsive_ generally means to react quickly and positively to any change.
  - websites **continually** and **fluidly** change based on different factors, such as :
    - **viewport**.
    - **width**.
- _adaptive_ means to be easily modified for a new purpose or situation.
  - built to a group of preset factors.
- _Mobile_ means to build a separate website commonly on a new domain solely for mobile users.

Currently the most popular **technique** lies within **responsive web design**, favoring design that dynamically adapts to different browser and device viewports, changing layout and content along the way. This solution has the benefits of being all three, **responsive**, **adaptive**, and **mobile**.

### Responsive web design is broken down into three main components:

1. Flexible Layouts

   - the practice of building the layout of a website with a **flexible grid**
   - capable of dynamically resizing to any width.
     - **Flexible grids** are built using relative length units(percentages **%** or **em**). These relative lengths are then used to declare common grid property values such as **width**, **margin**, or **padding**.

1. media queries

   - an **extension** to media types commonly found when targeting and including styles.
   - `@media all and (min-width: 800px) and (max-width: 1024px) {...}`
   - **mobile first**
   - **Viewport**
     - Viewport Height & Width `<meta name="viewport" content="width=device-width">`
     - Viewport Scale `<meta name="viewport" content="initial-scale=2">`

1. flexible media

   - Images, videos, and other media types need to be scalable, changing their size as the size of the viewport changes.
   - using the **max-width** property.

**Flexible Embedded Media**

- the embedded element needs to be **absolutely** positioned within **a parent element**.
- The **parent** element needs to have a **width of 100%** so that it may scale based on the width of the viewport.
- the parent element also needs to have a **height of 0** to trigger the hasLayout mechanism within Internet Explorer.

[Responsive Web Design](https://alistapart.com/article/responsive-web-design/)

# Intro to SMACSS

### Scalable and Modular Architecture for CSS A flexible guide to developing sites small and large.

**SMACSS** `(pronounced “smacks”)` is more style guide than rigid framework.

1. **no library** within here for you to **download** or **install**.
1. **no git repository** for you to clone.
   **SMACSS** is a _way_ to examine your design process **and** as a way to fit those **rigid frameworks** into a **flexible** thought process.
1. It is **an attempt** to document a consistent approach to site development when using **CSS**.

**techniques that can keep CSS more organized and more structured, leading to code that is easier to build and easier to maintain.**

### CSS Tools: Reset CSS

- to reduce browser **inconsistencies** in things like default line heights, margins and font sizes of headings, and so on.

### Don’t Overthink It Grids

1. **Context**
   `` <div class="grid">

     <!-- 100% wide -->
   </div>```

1. **Columns**
   `class="col-2-3"`
   `.col-2-3 { width: 66.66%; }`
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

- The first step: **box-sizing:border-box;**
  using it on absolutely everything.

```*, *:after, *:before {
  box-sizing: border-box;
}
```

**Now when set a width, that element stays that width, despite padding or borders being applied.**

- The second step: **applying a fixed padding to the right side of all columns except the last one.**

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
  - **used to create entire web layouts.**
  - Clearing the Float

**Techniques for Clearing Floats**

1. The Empty Div Method
   `<div style="clear: both;"></div>`
1. The Overflow Method
1. The Easy Clearing Method

**Problems with Floats**

1. Pushdown **Quick fix**: Make sure you don't have any images that do this, use **overflow: hidden** to cut off excess.
1. Double Margin Bug: Another thing to remember when dealing with IE6 is that if you apply a **margin** in the **same direction as the float**, it will **double the margin**. Quick fix: **set display: inline on the float**, and don't worry it will remain a block-level element.
1. 3px Jog: is when text that is up next to a floated element is mysteriously kicked away by **3px** like a weird forcefield around the float. **Quick fix**: set a width or height on the affected text.
1. Bottom Margin Bug : is when if a floated parent has floated children inside it, bottom margin on those children is ignored by the parent. **Quick fix**: using bottom padding on the parent instead.

**Summary**

- Styling should progress from broadest to most specific
- **base.css** should contain any general styling on top of what is provided by a **reset.css** or **normalize.css** file.
  - Apply to elements such as body and main
  - Examples include styling of overall font and background color
- **layout.css** should contain general positioning on the page
  - Apply to elements such as header, footer, nav, aside
  - Classes and IDs can be included here
- **modules.css** should contain smaller components on the page
  - Apply to elements such as list items, individual images, specific paragraphs
  - Classes and descendant selectors should primarily be included here **colors**
- **state.css** should contain any styling that changes upon user interaction or state change
  - Apply to hover state, before or after clicking on a link, focus and blur effects
  - Pseudo-classes and pseudo-elements should be included here
- **theme.css** should contain small changes on top of all other normal styling
  - Applying temporary changes, such as a holiday theme.

```Reham Told me :
1. base (reset tags like  margin badding ..)
2. layout(grid float position display width ..)
3. theme (color background ..  )
4. modules(navbar list collabsing .. )
```

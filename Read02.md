# jQuery, Events, and The DOM
**"Write less, do more,"**

__Readings__
- JavaScript and jQuery book by Jon Duckett **pages 293-301** __306-331 and 354-357__
- [6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)

__Skim__
- JavaScript and jQuery book by Jon Duckett **pages 332-335**

- JavaScript and jQuery book by Jon Duckett **pages 302-305**

### jQuery
**javascript file**
[jQuery Cheat Sheet](https://oscarotero.com/jquery/)
1. include the jQuery script in your page. it is included before the closing </body> tag.
1. $ () shortcut for the jQuery () function.
1. it makes coding simpler
    - SIMPLE SELECTORS
    - COMMON TASKS IN LESS CODE
        jQuery has methods that offer web developers simpler ways to perform common tasks, such as:
        • loop through elements
        • Add I remove elements from the DOM tree
        • Handle events
        • Fade elements into I out of view
        • Handle Ajax requests
1. chaining of methods __Once you have selected· some elements, this allows you to apply multiple methods to the same selection__

![jQuery select elements](img/jQueryselectelements.png)

![Conten Filter](img/contentFilter.png)

DOING THINGS WITH YOUR SELECTION
![Do with selection](img/doing.png)

Once you have selected the elements you want to work with (and they are in a jQuery object), the jQuery methods listed on these two pages perform tasks on those elements.
![Methods](img/methods.png)

**matched set/ jquery selection**
_when one or more than one elements is selected_
**jquery methods that get and set data**
`$('li').html('update');`
**jquery opjects store references to elements**
**caching jquery selections in variables**

### LOOPING
The ability to update all of the elements in the jQuery selection is known as **implicit iteration**.
When you want to get information from a series of elements, you can use the
**. each () method**rather than writing a loop.

### CHAINING
The process of placing several methods in the same selector is referred to as chaining.
`$( 'l i [i d!="one"] ') . hide() .delay(SOO) . fadeln(1400);`

jQuery `.ready()` checks that the page is ready for your code to work with.
![Ready](img/ready.png)

_GETTING ELEMENT CONTENT_
The • **html ()** and • **text ()** methods both retrieve and update the content
of elements.
1. html(): it retrieves only the HTML inside **the first element** in the matched set, along with any of its descendants.
1. text(): it returns the content from **every element** in the jQuery selection, along with the text from any descendants.

__UPDATING ELEMENTS__
1. **. html()**
This method gives every element in the matched set the same new content. The new content may include HTML.
1. **.replaceWith()**
This method replaces every element in a matched set with new content. It also returns the replaced elements.
1. **. text()**
This method gives every element in the matched set the same new text content. Any markup would be shown as text.
1. **. remove()**
This method removes all of the elements in the matched set.

__INSERTING ELEMENTS__
**Inserting new elements involves two steps:**
1. Create the new elements in a jQuery object
`var $newltem = $('<li class="new">item</ li>');`
2. Use a method to insert the content into the page
    - **.before()**
        This method inserts content before the selected element(s) .
    - **.prepend()**
        This method inserts content inside the selected element(s), after the opening tag.
    - **.after()**
        This method inserts content after the selected element (s).
    - **.append()**
        This method inserts content inside the selected element(s), before the closing tag.

__GETTING AND SETTING ATTRIBUTE VALUES__

1. **.attr()**
    This method can get or set a specified attribute and its value.
    `$( ' li#one').attr('id');` To update the value of an attribute, you specify both the attribute name and its new value. `$('li#one').attr('id' , 'hot ' );`
1. **. addCl ass()**
    This method adds a new value to the existing value of the class attribute. It does not overwrite existing values.
1. **. removeAttr()**
    This method removes a specified attribute (and its value). You just specify the name of the attribute that you want to remove from the element in the parentheses.
    `$('1 i #one') . removeAttr (' i d' };`
1. **.removeClass()**
    This method removes a value from the cl ass attribute, leaving any other class names within that attribute intact.

__GETTING & SETTING CSS PROPERTIES__
The **.css ()** method lets you retrieve and set the values of CSS properties.

__WORKING WITH EACH ELEMENT IN A SELECTION__
jQuery allows you to recreate the functionality of a loop on a selection of elements, using the **each () method**.
1. **each()**
It takes one parameter: a function containing the statements you want to run on each element.

1. **this or $(this)**
You also often see $ (this), which uses the this keyword to create a new jQuery selection containing the current element.
It allows you to use jQuery methods on the current element.

___EVENT METHODS__
**.on ()** method is used to handle all events.

![EventObject](img/eventobject.png)

__EFFECTS__
![effects methods](img/effects.png)

__ANIMATING CSS PROPERTIES__ **.animate()**

### Ways to include jQuery in your page
1. LOADING JQUERY FROM A CDN

__WHERE TO PLACE YOUR SCRIPTS__
The position of <scri pt> elements can affect how quickly a web page seems to load.
1. **in the Head** avoid it b/c the pages will seems slower DOM content is not loaded.
1. **in the page** will slow the rest of the page.
1. ideal location **before the closing </body>** the DOM has already loaded by the time the script is excuted and the script is not blocking other things from downloading.

### 6 Reasons for Pair Programming
1. Greater efficiency
1. Engaged collaboration
1. Learning from fellow students
1. Social skills
1. Job interview readiness
1. Work environment readiness


- Iterative loops
- Code reviews
- Fast feedback

**The Driver** is the programmer who is typing and the only one whose hands are on the keyboard.
**Navigator** uses their words to guide the Driver but does not provide any direct input to the computer

__Why pair program__
 **four** fundamental skills that help anyone learn a new language: 
 1. Listening: hearing and interpreting the vocabulary 
 1. Speaking: using the correct words to communicate an idea 
 1. Reading: understanding what written language intends to convey 
 1. Writing: producing from scratch a meaningful
 **Pair programming touches on all four skills**

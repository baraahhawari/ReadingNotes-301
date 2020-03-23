# jQuery

```dom manipulatuon js
val element = document.getElementById("start");
element.innerHTML="Go";
```

# overview

**dom manipulation jQuery**
\$("#start").html("Go");

**CDN for jQurey library**
wil be added to the head of the HTML document in script tag.
It is a good practice to wait for the HTML document to be fully loaded and ready before working with it.
For that we use the ready event of the document object:

\$(document).ready(function (){
//jQuery code....
})

**The \$ is used to access jQuery.**

From here, the code accesses the document object and defines a function to be called when the document's ready event is fired.
This prevents any jQuery code from running before the document is finished loading.
there is a handy shortcut for writing it:

```$(function (){
//code here...
})
```

1. the CDN of the jQuery in the head
2. defines the document ready event
3. start the manibulation ...
   if I want tocahnge the div content from strat to Go
   where the div has id of start
   jQuery:

$(function (){
$("#start").html("Go");
})

---

**(attribute and content)**

##jQuery is used to select (query) HTML elements and perform "actions" on them.
Basic syntax is: \$("selector").action()

Attributes (get set remove)

We can manipulate attributes assigned to HTML elements easily through jQuery.
href, src, id, class, style are all examples of HTML attributes.

in HTML
<a href="www.bebo.com"></a>
in jQuery
$(function (){
var val =$("a").attr("href");
alet(val);
});
alert will be www.bebo.com

===========
another thing :
where the <a href="www.nma2.com"></a>
we can use attr() method to set values
$(function(){
$("a").attr("href","www.bebo.com");
});

////////////////////////////
We can also use jQuery for DOM manupulation and remove the attributes
.removeAttr()

##Get Content

There are several methods for manipulating the content of HTML elements via jQuery.
The html() method is used to get the content of the selected element, including the HTML markup.

1. .html() method
2. .text() method

$(function(){
var val = $("p").html();
alert(val);
})
the alert will be (everything inside the p tag eventhough if it contain another tag)

$(function(){
var val=$("p").text();
alert(val);
})
the alert will be only the text contant of the p tag

##Set Content
also by using the .html() and .text() methods
another method can be used is the val() which used to get and set the values of
**form fields, such as **textboxes, **dropdowns, and **similar inputs.

=========

## Summary

The following jQuery methods are available to get and set content and attributes of selected HTML elements:
text() sets or returns the text content of selected elements.
html() sets or returns the content of selected elements (including HTML markup).
val() sets or returns the value of form fields.
attr() sets or returns the value of attributes.
removeAttr() removes the specified attribute.

---

when we set content the existing g=content get lost
so jQuery has methods to add content without deleting the existing content:
append()
prepend()
after()
before()
append() inserts content at the end of the selected elements.
prepend() inserts content at the beginning of the selected elements.
after() inserts content after the selected elements.
before() inserts content before the selected elements.
we can use the html() markup for the after() method
####also they can be used to add newly created element
which can be done:
var txt=$("<p></p>").text("hi bebo");// creat element and assign its value in variable
use the variable:
$(function(){
var txt=$("<p></p>").text("hi bebo");
$("#demo").after(txt);
});
I can use it by seperating them using coma:
\$("#demo").after(txt, txt1, txt2);// extera can be done only once

---

(manipulating CSS)
Manipulating CSS
##adding removing classes
1).addClass() method adding one or more cclass to the element
\$("div").addClass("header");

2. .removeClass() method
3. toggleClass(), The toggleClass() method toggles between adding/removing classes from the selected elements,
   meaning that if the specified class exists for the element, it is removed, and if it does not exist, it is added.

##css properties
Similar to the html() method, the css() method can be used to get and set CSS property values.

##Multiple Properties
to set multiple CSS properties the css methods use JSOn syntax:
css({'property':'value', 'property':'value'.....etc})
\$('p').css({'background-color':'blue', 'font-size':'20px', 'color':'white'});

##Dimentions
The width() and height(numbers only no px) methods can be used to get and set the width and height of HTML elements.

The width() and height() methods get and set the dimensions without the padding, borders and margins.
The innerWidth() and innerHeight() methods also include the padding.
The outerWidth() and outerHeight() methods include the padding and borders.
padding margin border(outer padding 2 sides + border)(inner padding 2 sides)

===========================================
manipulate DOM
The DOM

When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
To accomplish this, the browser builds the Document Object Model (DOM) of that page, which is an object oriented model of its logical structure.
The DOM of an HTML document can be represented as a nested set of boxes:

the DOM structure is tree

The <html> element is the parent of <body> and an ancestor of everything below it.
The <body> element is the parent of the <h1> and <a> elements.
The <h1> and <a> elements are child elements of the <body> element and descendants of <html>.
The <h1> and <a> elements are siblings (they share the same parent).

Summary
An ancestor is a parent, grandparent, great-grandparent, and so on.
A descendant is a child, grandchild, great-grandchild, and so on.
Siblings share the same parent.

##DOM Traversal
parent() method
The parent() method can only traverse a single level up the DOM tree.
To get all ancestors of the selected element you can use the parents() method. For example:
The eq() method can be used to select a specific element from multiple selected elements.

##Remove Elements
remove() method
\$("p").eq(1).remove();
##Removing Content
The empty() method is used to remove the child elements of the selected element(s).

////////////
Events
Handling Events(event handler is a function)
JQuery provides an efficient way to handle events.
Events occur when the user performs an action, such as **clicking an element, **moving the mouse,
or **submitting a form.
When an event occurs on a **target element, a \*\*handler function is _executed_.
// using th js pure
window.onload=function(){
var a =document.getElementById('demo');
a.onclick=function(){
document.body.innerHTML=Date();
}
};

// the same event handling using jQuery
$(function(){
    $("#demo").click(function(){
\$('body').html(Date());
});
});

##Handling Events
Another way to handle events in jQuery is by using the ##on() method.
You can remove event handlers using the ##off() method.

--The Event Object
Every event handling function can receive an event object,
which contains **properties and **methods related to the event:
pageX, pageY the mouse position (X & Y coordinates) at the time the event occurred, relative to the top left of the page.
type the type of the event (e.g. "click").
##which the button or key that was pressed.
data any data that was passed in when the event was bound.
target the DOM element that initiated the event.
preventDefault() prevent the default action of the event (e.g., following a link).
stopPropagation() Stop the event from bubbling up to other elements.

##Trigger Events
trigger() method.
trigger

---

$$
this Html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
        <script src="https://code.jquery.com/jquery-3.1.1.js"></script>
    </head>
    <body>
        <div>Click me</div>
        <h1>My To-Do List</h1>
        <input type="text" placeholder="New item" />
        <button id="add">Add</button>
        <ol id="mylist"></ol>
    </body>
</html>

the jQurey will be:
$(function(){
    //function on click
    $('#add').on('click', function(){
        //creat list and put the value of the input appended to the OL
    var element= $("<li></li>").text('input');
    // putting the values of the inputs after each li cretaed
    $('#mylist').append(element);
    });
});

another thing can be done:
removing the element from the list :
$(function (){
    // function on click
   $('#add').on('click', function(){
    //   storing the value of the input in var
      var value=$('input').val();
      if (value !==''){
        //   if statment to deal with the empty input
        // creat li element on each click
          var element=$('<li></li>').text(value);
        //   adding button with class styleing it to remove
          $(element).append("<button class='remove'>X</button>");
        //   putting the values from the input in the list
        $('#mylist').append(element);
        // another function to remove the item on click
        $('.remove').on('click', function(){
            $(this).parent().remove();
        })
      }
   }) ;
});


========================================
jQuery effects
:::
animation :
1.The hide() and show() methods are used to hide and show the selected elements.
2.The toggle() method is used to 3.toggle between hiding and showing elements.

I can put time inside the toggle(1000) in millesecond

4. fade in fade out
Similar to the hide/show methods, jQuery provides the fadeIn/fadeOut methods, which fade an element in and out of visibility.
Just like the toggle() method switches between hiding and showing, the fadeToggle() method fades in and out.

5. slideup/slidedown
The slideUp() and slideDown() methods are used to create a sliding effect on elements.
//////////////////////////////
Animate::
animate()

The animate() method lets you animate to a set value, or to a value relative to the current value.
You need to define the CSS properties to be animated as its parameter in JSON format ("key":"value" pairs).
The second parameter defines the speed of the animation.
$("div").click(function() {
  $("div").animate({width: '250px'}, 1000);
});

Multiple properties can be animated at the same time by separating them with commas.
$(function() {
    $("div").click(function() {
        $("div").animate({
            width: '+=250px',
            height: '+=250px'
        }, 1000);
    });
});
on each click will increase the values
paddingLeft no -dashes


$("div").animate({
  width: '250px',
  height: '250px'
}, 1000);

works only one time on he first click.

##Animation Queue
Animation Queue

By default, jQuery comes with queue functionality for animations.
This means that if you write multiple animate() calls one after another, jQuery creates an "internal" queue for these method calls.
 Then it runs the animate calls one-by-one.

Each animate() method call will run one after another.
Remember, to manipulate the position of elements, you need to set the CSS position property of the element to relative, fixed, or absolute.
//////////////////////////
Drop-Down Menu

$(function() {
    $("#item").click(function() {
        $("#submenu").slideToggle(500);
    });
});
$$

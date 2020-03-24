# Components

**Reading**
[EJS Partials](https://medium.com/@henslejoseph/ejs-partials-f6f102cb7433)

**Videos**
[Watch EJS tutorial from WalkThroughCode on YouTube, Video 7, Partials](https://www.youtube.com/watch?v=3_xEEH4fTEk&t=0s&index=7&list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)

### EJS Partials

**Partials** come in handy, to **reuse the same HTML across multiple views**.
<you define that reusable bundle of code in a file andinclude it wherever you need it>

_create partials_

1. inside the **veiws directory** create a **file called **navbar.ejs\*\*

```<!-- views/partials/navbar.ejs -->
    <div class="header clearfix">
        <nav>
            <ul class="nav nav-pills pull-right">
                <li role="presentation"><a href="/">Home</a></li>
            </ul>
            <h3 class="text-muted">Node.js Blog</h3>
        </nav>
    </div>
```

1. inside the **veiws directory** create a **file called **footer.ejs\*\*

```<!-- views/partials/footer.ejs -->
    <footer class="footer">
        <p>© 90210 Lawyer Stuff.</p>
    </footer>
```

**Now that we have our partials defined, we can use them in our home.ejs and post.ejs templates! In EJS, any JavaScript or non-HTML syntax you include in your templates is always surrounded by <% %> delimiters (you could change these delimiters if you really wanted to).**

_in the home.ejs file_

```<!-- views/home.ejs -->
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Node.js Blog</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
        <style>
            body {
                padding-top: 20px;
                padding-bottom: 20px;
            }
            .jumbotron {
              margin-top: 10px;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <%- include('partials/navbar') %>
            <div class="jumbotron">
                <h1>All about Node</h1>
                <p class="lead">Check out our articles below!</p>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <div class="list-group">
                      <!-- loop over blog posts and render them -->
                      LIST_OF_POSTS
                    </div>
                </div>
            </div>
            <%- include('partials/footer') %>
        </div>
    </body>
    </html>
```

**video**
_Intro to EJS - Layouts_

1. **layouts** not native to **ejs** **express**
1. are useful while switching views between **url**
1. `npm i --save express-ejs-layouts`
1. server.js file
   - `var expressLayout=require('express-ejs-layouts')`
   - `app.use(expressLayout);`
1. thats will give us the apportunity to use the **body** as a **placeholder** for the views inside the layout
1. the **layout file (the wrapper)**
   `<%- body %> //the place for the particular view`
1. so modify all the ejs files you have to see the action
1. on server.js

```app.get('/about',(req,res)=>{
res.render('about');
})
```

**layout file stays on the file during swiching btw urls**

_Intro to EJS - Partials_

1. **partials** unlike layout are **native to ejs**
1. navbar footer (static)
1. on server.js (check that everything is ok)
1. on the **views folder** create **partials folder** and inside it **onepartial.ejs** file
1. on layout.ejs file :

```
<%- body %>
<%- include('partials/onepartial') %>
```

# Read: 14b - Project Ideas & APIs

[public-apis](https://github.com/public-apis/public-apis)

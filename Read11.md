# EJS Embedded JavaScript templating.

a simple **templating language** that lets you **generate HTML markup** with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.

**Reading**

1. [Watch EJS tutorial from WalkThroughCode on YouTube, Videos 1-5](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)
   Note that this series of videos should take approximately 20 minutes to watch

**Additional Resources**

1. Reference: [Google Books API Docs](https://developers.google.com/books/docs/v1/using#WorkingVolumes)
   Specifically the section about working with Volumes. Review the sample request and response. Practice making requests using Postman and consider the possible properties of the response that you may want to include in your book application.
1. Reference: [EJS Docs](https://ejs.co/)

**Bookmark/Skim**

1. Skim: [EJS Tutorial](https://scotch.io/tutorials/use-ejs-to-template-your-node-application)
1. Skim: [Source Code for the EJS Tutorial](https://github.com/scotch-io/node-ejs)

1) npm init -y
2) npm install --save express body-parser cors ejs
3) file server.js
4) on the js file

```var express=require('express');
var bodyParser=require('body-parser');
var cors=require('cors');
<!-- built in moduels(core moduale for node) -->
var path= require('path');

var app= express();

app.use(bodyParser());
app.use(cors());

<!-- it takes 2 path and joins them -->
app.set('views', path.join(__dirname, 'views'));

app.set('view engine', 'ejs');


<!-- create new folder (views) inside it a file (index.ejs) -->
<!-- inside index.ejs <h1>Hello bebo</h1> -->

app.get('/', function(req, res){
    res.render('index');
});

app.listen(8000, function (){
    console.log('hello port 8000');
})
```

- on the terminal node server.js
- localhost:8000 it will show U hello bebo

**Intro to EJS - Injecting values into the views**
in the above code the rendering takes 3 parameters:

1. _view_
1. _object_
1. _callback_
   contuned on the a bove code :

```
<!-- replace the app.get('/') -->
app.get('/', function(req,res){
res.render('index', {
foo:'bar'
});
});
<!-- on the index file make <%=foo %> -->
<!-- on the terminal nodemon -->
```

**Intro to EJS - For Loops and Arrays**

contuned on the a bove code :

```
<!-- replace the app.get('/') -->
app.get('/', function(req,res){
res.render('index', {
people:[
    {name:'brbr'},
    {name:'nma2'},
    {name:'nrnrn'}
]
});
});
<!-- on the index file make unordered list
<ul>
<% for (var person of people) %>
<li><% = person.name %></li>
<% }%>
</ul> -->
<!-- on the terminal nodemon -->
```

**Intro to EJS - If_Else Statement**
<contunue on the abve code on the index file>

```<ul>
<% for (var person of people) %>
<% if(person.name ==='dave'){ %>
<li>This is <% = person.name %></li>
<% } else { %>
<li>This is not <% = person.name %></li>
<% } %>
<% } %>
</ul> -->
```

## Working with volumes

**Performing a search**

1. _You can perform a volumes search by sending an HTTP GET request to the following URI:_ `https://www.googleapis.com/books/v1/volumes?q=search+terms`

![volumes](img/volumes.png)

1. Request
   - `GET https://www.googleapis.com/books/v1/volumes?q=flowers+inauthor:keyes&key=yourAPIKey`
1. Response
   - `the formated results`

**Optional query parameters**

1. Download Format: to restrict the returned results to volumes that have an available download
   `GET https://www.googleapis.com/books/v1/volumes?q=pride+prejudice&download=epub&key=yourAPIKey`
1. Filtering
   ![filter](img/filter.png)
1. Pagination
1. Projection
1. Sorting

**GET STARTED**
![options](img/options.png)
![tags](img/tags.png)

======================================================================================================================================================================================================================================================

## CRUD _is the reason for internet_

_used by JS .Net PHP Java Python_
_related to database_
**C Create** POST
**R Read** GET
**U update** PUT, PATCH
**D delete** DELETE

THE RESPONSE is json or html markup (using handlebar)
the **json** will **render** the data on the **browser** using **handlebar**
**REST** (setting data from here to here)_turning the data into json and move it_
**Representational State Transfer** (how people communicate on the web)

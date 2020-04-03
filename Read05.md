# Heroku Deployment :sunglasses:

**Reading**
[Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs): Getting Started with Node.

**Bookmark/Skim**
[Deploying a Simple Blog to Heroku](https://howtonode.org/deploy-blog-to-heroku)

### Defining an application

- Heroku lets you **deploy**, **run** and **manage** applications written in Ruby, **Node.js**, Java, Python, Clojure, Scala, Go and PHP.
- **Dependency mechanism**s vary across languages: in Ruby you use a Gemfile, in Python a requirements.txt, in **Node.js a package.json**, in Java a pom.xml and so on.

### Knowing what to execute

**One requirement** is **informing the platform** as to <which parts of your application are runnable>.

- Heroku is a **polyglot[speaking, many languages.]** platform it lets you:
  - **build**
  - **run**
  - **scale** applications in a similar manner across all the languages
  - utilizing the **dependencies** and Procfile.
    - The Procfile exposes an architectural aspect of your application

### Deploying applications :alien:

1. The Heroku platform uses **Git** as the primary means for deploying applications (there are other ways to transport your source code to Heroku, including via an **API**).
1. When you create an application on Heroku, it associates a **new Git remote**, typically named heroku, with the local Git repository for your application. `$ git push heroku master`

### Build

### Running applications on dynos

Heroku executes applications by running a command you specified in the Procfile, on a dyno that’s been preloaded with your prepared slug (in fact, with your release, which extends your **slug** and a few items not yet defined: **config vars** and **add-ons**).

`$ heroku ps:scale web=3 queue=2`

# Node.js For Beginners.

## Deploy Your Blog to Heroku

### How can I?

1. We will use **Node.js** for our project.
   1. is an **open source**
   1. **cross-platform runtime environment**
   1. allows you to **build server-side**
   1. **networking applications**.

### Pretty simple, but it's a server!

First of all, we need to **create a JavaScript file**. Let's name it **server.js**:

```var http = require("http");

http.createServer( function( request, response) {

response.writeHead( 200, {"Content-Type": "text/plain"} );

response.write( "It's alive!" );

response.end();

}).listen(3000);

```

- **make sure it's working**. Run at your terminal: `node server.js`

- Let's look more closely at our first **Node server**.
  This is an example of how Node provides you with **non-blocking** and **event-driven behavior**. Let me explain:

`$.post('/some_requested_resource', function(data) { console.log(data); });`

- This code performs a **request** for some resource
  - When the response comes back, an **anonymous function is called**. It contains the **argument data**, which is the data received from that request.
  - **Node** allows you to use the **so-called event loop**, which works **faster** because of **non-blocking behavior**.

## Make it worldwide :earth_asia:

Use **Heroku** cloud application platform for this

- First step after Heroku installation is to log in to the system from your computer:

  `heroku login`.

**Create your project directory**. And then **create the server.js** file **inside of it**.

- First of all, let's declare some variables:

  - `var http = require("http");` will give the **key to Node's HTTP functionality**
  - `var fs = require("fs");` for possibility to **interact with the file system**
  - `var path = require("path");` allows you to **handle file paths**
  - `var mime = require("mime");` allows you to **determine a file's MIME-type it's not a part of Node.js**`

_so_ we need to _install_ **third-party dependencies** before using it. We need to create the package.json file for that purpose.
It will contain project related **information**:

1. name
1. version
1. description, and so on.

For our project we will use **MIME-types recognition**, because it's not enough to just **send** the contents of a file when you use HTTP. You also need to **set** the Content-Type header with proper MIME-type. That's why we need this plug-in.

- Create the **package.json** file and fill it with proper information. Here's mine:

```{
   "name" : "blog",
   "version" : "0.0.1",
   "description" : "My minimalistic blog",
    "dependencies" : { "mime" : "~1.2.7" }
}
```

- run `npm install` **It will create node_modules folder and place all the files inside of it**

We will now create **send 404() function**. It will handle the sending of 404 error, which usually appears when requested file doesn't exist:

```function send404(response) {
   response.writeHead(404, {"Content-type" : "text/plain"});
   response.write("Error 404: resource not found");
   response.end(); }
```

Now we will define **sendPage() function.** It first writes the header and then sends the contents of the file:

```
function sendPage(response, filePath, fileContents) {
   response.writeHead(200, {"Content-type" : mime.lookup(path.basename(filePath))});
   response.end(fileContents); }
```

Now we'll define how our **server** will **handle responses**. This function will return the **content of the requested** file or the 404 error otherwise:

```
function serverWorking(response, absPath) {
   fs.exists(absPath, function(exists) {
      if (exists) {
      fs.readFile(absPath, function(err, data) {
         if (err) { send404(response) }
         else { sendPage(response, absPath, data); } }); }
         else { send404(response); } });
         }
```

And now it's time to create the **HTTP server**:

```var server = http.createServer(function(request, response) {
var filePath = false;
if (request.url == '/') {
   filePath = "public/index.html";
   } else {
   filePath = "public" + request.url;
   }

var absPath = "./" + filePath;
serverWorking(response, absPath);
});
```

Now we need to **start our server. And here's the tricky part.** :nerd_face:
`http.createServer(<some code here>).listen(3000)`
**But Heroku sets a dynamically assigned port number to your app. That's why we need to handle all this mess with ports as it’s shown below:**
`var port_number = server.listen(process.env.PORT || 3000);`

We need to create the **index.html** file. It will determine our **blog's exterior**. Here's the code:

```
<!DOCTYPE html>
<html>
    <head>
        <title>Blog</title>
        <link rel="stylesheet" type="text/css" href="stylesheets/style.css">
    </head>
    <body>
        <div id="header">
            <span>My Simple Blog</span>
            <ul id="menu">
                <li>ABOUT</li>
                <li>ARTICLES</li>
                <li>VIDEOS</li>
                <li>SUBSCRIBE</li>
            </ul>
        </div>
        <div id="content">
            <h2><a href="ui_libraries_comparison.html">JavaScript UI libraries comparison</a></h2>
            <p>It seems to be pretty easy to create a good-looking web page. Even your neighbor has one or two of them. It's for sure! For approximately two decades of World Wide Web existence hordes of web developers are trying to improve the way of how you interact with the Global Network. And how it interacts with you through different technologies such as JavaScript, for example... <a class="article" href="ui_libraries_comparison.html">Read more</a></p>
            <h2><a href="">Node.js for beginners. Building your own web server</a></h2>
            <p>We will use Node.js for our project. Node.js is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications. It's written in JavaScript and can be run within the Node.js runtime on any platform. First of all, of course, you need to install it... <a class="article" href="hode.html">Read more</a></p>
        </div>
    </body>
</html>
```

**To start your server locally run:** `node server.js`
We tested our simple server locally and now is time to deploy it.

## It's Heroku time!

1. Open your terminal within your project folder. For my Linux it's:
   `cd/path/to/my/project`
1. Then run: `git init` Empty Git repository will be initialized in .git/ folder.
1. Then run: `git add .` This command allows Git to track your files changes.
1. Now commit your files to the initialized Git repo: `git commit -m "Simple server functionality added"`
1. **We'll create our first Heroku application now:**
   `heroku create`
   Heroku will **generate a random name** for your application.
1. Now we can deploy our project. Every **Heroku app starts with no branches and no code**. So, the first time we deploy our project, we need to specify a remote branch to push to:
   `git push heroku master`
1. The application is now deployed. Ensure that at least one instance of the app is running:
   `heroku ps:scale web=1`
1. And now, before we open it, it's time to choose a proper name for our first creation. I called it myfirstserver:
   `heroku apps:rename myfirstserver`
1. Everything is done. You can try it now:
   `heroku open`
   ##### This command will open your Heroku project in your web browser. In this particular case, server address is https://myfirstserver.herokuapp.com/. Now you can share your first web application with any person you want.

<!-- ---------------------------------------------------------------------------------------------------------- -->
<!-- -----------------------------------IMPORTANT-------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------------------------------------------------- -->

## live server very cool fast and its on the cloud and you can make as many branches as you can:

:innocent:
"use strict";
first server

1. create repo on github clone it to the pc
2. deploy and test the server from my machine (data rout send json data/ static files*index.html* served from public )
3. open repo on pc and create file server.js
4. on the terminal run :
   1. **npm init -y (it will create a file called package.json)**
   2. **npm install express (its like jQuery to help server my app depends on express)**
   3. **cat package.json (your server details)**
   4. **ls -al (list of files in the folder)**

**to get express in its going to be required**
`const express = require("express");`

**express is actually a function**
server has alot of methods to help us
`const server = express();`

**local host (tell express which port to use)**
PORT writen capitalized b/c whe we will go to herouku it will have many ports (just to know it)
process.env.PORT special thing in node(given by heroku for free)
the next line means (use what heruku gives U or use 3000)
`const PORT = process.env.PORT || 3000;`

**make rout (which is look like jQuery get(event listener) )**

```server.get("/test", (Request, Response) => {
Response.send("your test worked");
});
```

**build another Rout called Data**

```server.get("/data", (Request, Response) => {
let family = [{ name: "bebo" }, { name: "nma2" }, { name: "mum" }];
Response.json(family);
});
```

**static file from public jordan.html**
`server.use(express.static("./public"));`

to test it go to terminal and stop the server (clt+c) and start it again npm start
**go to browser and type http://localhost:3000/test**
**go to browser and type http://localhost:3000/data**
**go to browser and type http://localhost:3000/jordan.html**

**server has listen**

```server.listen(PORT, () =>
console.log("listining to the port or on port", PORT)
);
```

on terminal typ `npm start` (the msg shown will be the msg inside the console)

```http//localhost:3000/data(its called path or rout)
 /data (its called path or rout)
```

:fleur_de_lis:

- create an account on heroku.com
- create an app
- deploy the app from github

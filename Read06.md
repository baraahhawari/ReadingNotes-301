# Node, Express, and APIs

**Reading**
[An Introduction to Node.js on sitepoint.com](https://www.sitepoint.com/an-introduction-to-node-js/)

### What Is Node and When Should I Use It?

_What Is Node.js?_
**Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.**

1. “event-based”??
1. “non-blocking”??
1. “asynchronous I/O”??

**Node Is Built on Google Chrome’s V8 JavaScript Engine**

- The **V8 engine** is the open-source JavaScript engine
  - runs in Google Chrome and other Chromium-based web browsers.
  - responsible for compiling JavaScript directly to native machine code that your computer can execute.

Node is built on the V8 engine **dosen't mean that Node programs are executed in a browser**
**They aren’t**.

_V8 engine_ enhanced with various features, such as :

1. a file system API
1. an HTTP library
1. a number of operating system–related utility methods.

<**Node.js is a _program_ we can use to _execute_ JavaScript on our computers** _it’s a JavaScript runtime._>

**npm** _package manager that comes bundled(To tie or wrap together.) with Node._

**use a version manager** => This is a _program_ that allows you to install **multiple versions** of Node and **switch between them** at will.
_advantages to using a version manager_:

1. it negates potential permission issues when using Node with npm
1. lets you set a Node version on a per-project basis.

check that Node is installed on your system => `node -v`

**Node.js Has Excellent Support for Modern JavaScript**
**Node** has excellent support for

- **ECMAScript 2015 (ES6)** and beyond.

  - this means that you can write your JavaScript using the **latest and most modern syntax**.
  - It also means that you don’t generally have to worry about _compatibility_ issues — as you would if you were writing JavaScript that would run in different browsers.

  **Introducing npm, the JavaScript Package Manager**
  check which version you have installed on your system, type `npm -v`.

  **npm**

  1. the package manager for JavaScript
  1. the world’s largest software registry

  **how we would use npm to install a package.**

  - _Installing a Package Globally_ `npm install -g jshint`
    - This will install the **jshint package globally** on your system. We can use it to lint the index.js file

- _Installing a Package Locally_ `npm init -y`

  - This will create and **auto-populate a package.json** file in the same folder.
  - install the **lodash package** and save it as a project dependency
    `npm install lodash --save`

- Working with the _package.json_ File

1. **node_modules** folder => This is where npm has saved lodash and any libraries that lodash depends on.

## What Is Node.js Used For?

1. **Node.js Lets Us Run JavaScript on the Server**

   - The Node.js Execution Model
     - Node.js is an **event-driven**
       <example when a new request comes in (one kind of event) the server will start processing it. If it then encounters a blocking I/O operation, instead of waiting for this to complete, it will register a callback before continuing to process the next event. When the I/O operation has finished (another kind of event), the server will execute the callback and continue working on the original request. Under the hood, Node uses the libuv library to implement this asynchronous (that is, non-blocking) behavior.>
     - Node.js capable of handling a large number of **simultaneous connections**
     - The traditional approach to _scaling a Node app_ is to **clone** it and have the cloned instances share the workload.
     - Node.js even has a **built-in module** to help you implement a cloning strategy on a single server.

**Are There Any Downsides?**
_The fact that Node runs in a single thread does impose some limitations. For example, blocking I/O calls should be avoided, CPU-intensive operations should be handed off to a worker thread, and errors should always be handled correctly **for fear of crashing the entire process**._

### What Kind of Apps Is Node.js Suited To?

Node is particularly suited to building applications that require some form of **real-time interaction** or collaboration

1. chat sites
1. apps such as CodeShare, where you can watch a document being edited live by someone else.
1. building APIs where you’re handling lots of requests that are I/O driven (such as those needing to perform operations on a database).
1. sites involving data streaming, as Node makes it possible to process files while they’re still being uploaded.

### What Are the Advantages of Node.js?

1. _speed and scalability_
1. _it speaks JSON._
   - JSON is probably the most important data exchange format on the Web, and the lingua franca for interacting with object databases (such as MongoDB). JSON is ideally suited for consumption by a JavaScript program, meaning that when you’re working with Node, data can flow neatly between layers without the need for reformatting. You can have one syntax from browser to server to database.
1. _ubiquitous_

**Other Uses of Node**
**And it doesn’t stop at the server. There are many other exciting and varied uses of Node.js! For example it can be used as a scripting language to automate repetitive or error prone tasks on your PC. It can also be used to write your own command line tool, such as this Yeoman-Style generator to scaffold out new projects. Node.js can also can be used to build cross-platform desktop apps and even to create your own robots**







## Trello :: way of working as professional 



<!-- Express:







 -->

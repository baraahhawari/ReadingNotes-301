# APIs continued :incoming_envelope:

**Reading**

- [What Google Learned From Its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

- [How I explained REST to my brother](https://gist.github.com/brookr/5977550)

**Bookmark/Skim**

- [Documentation for SuperAgent](https://visionmedia.github.io/superagent/)

## How I explained REST to my brother :pencil2:

From what I understand of this article **polymorphism** applies to **REST** by saying that we can have **multiple** nouns, ie things to be **selected** that have the same **verb** applied to them I.E.

1. **POST**
1. **GET**
1. **PUT**
1. **DELETE**.

Which relate to **SQL** with :slot_machine:

1. **INSERT**
1. **SELECT**
1. **UPDATE**
1. **DELETE**.

## API Keys :old_key:

Request a personal API key from the following APIs. You should receive these in your email within a few hours, often within minutes. Please request these keys prior to lecture to allow adequate time because you will need them in order to complete your lab assignment.

- [Geocoding API Docs](https://locationiq.com/) :world_map:
- [Dark Sky API Docs](https://darksky.net/dev/docs) :cloud_with_rain:
- [Yelp API Docs](https://www.yelp.com/developers/documentation/v3/business_search) :atom:
- [The Movie DB API Docs](https://developers.themoviedb.org/3/getting-started/introduction) :performing_arts:

#### live API's

- [Developer accounts](https://console.developers.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project)

- go to this wesite and create project (_this will make me google developer_ **it will allow me to do work for google with thier data**)
- activate enable apis and services
  - search for the api that U need (mab and geo)
    - Maps Static API (that will draw the maps for us)
    - Maps JavaScript API
    - Geocoding API
- create credentials to allow U to use the api
  - api key (it will creat an api key for U) _api key_**AIzaSyAjgY6orhQxdVuxkJ-cWF81hdwassjAbkg** :old_key:

**if some one is using chrome**

- _the chrome will be a client b/c its asking for information_
- _the server will send back jason data_
- _behind the server to get info_
  - if I search for weather :cloud_with_lightning: the **server** will get the API from darksky api **(cloud)**
  - writting the code (to make the api getting the data) **superagent**(will take the **api url** to the **cloud** and **.then** will get back with the data (**promise**))
    - **data.body** data object
    - process it using **forEach day** and made **instance** and from that a constructor function
    - **mapped** it or **push** to get an array of info (weather)

### **make express server to deal with the above work**

1. get Repo
1. clone it down with (**.gitignore(node)** and README)
1. touch the server.js
1. npm init

   - package.json

1. ACP to Master
1. woking branch
   - start the work :
     - npm install (**cors express dotenv superagent**)
1. touch .env file

   - PORT=8000

1. edit the server.js file

   - proof of life

     ```
     'use strict';

     requier('dotenv').config();

     const express=require('express');

     const PORT= process.env.PORT;

     const server = express();

     server.get('/hi',(req,res)=>{
       res.status(200).send('hi');
     });

     // started up
     server.listen(PORT, ()=>{
       console.log('hello');
       });

     ```

- _npm start or nodemon_
- _then go to the local host and test it_
- _ACP and merge_

### DEPLOY :star2:

1. **Heroku**

- create an app
- connect to get
- pick the repo
- auto deploy

_the diffecult things are_: :zap:
**API DOCS**
**BIG OBJECTS**
event.event.day....[]

## SuperAgent :robot:

SuperAgent is **light-weight progressive ajax API crafted** for:

1. flexibility
1. readability
1. low learning curve after being frustrated with many of the existing request APIs.
1. It also works with Node.js!

### Request basics :envelope_with_arrow:

A request can be **initiated** by

1. **invoking** the appropriate **method** on the **request object**
1. then **calling** .then() (or .end() or await) to **send** the request.

**DELETE, HEAD, PATCH, POST, and PUT requests can also be used, simply change the method name:**

### Setting header fields :crayon:

**Setting header fields is simple, invoke .set() with a field name and value:**
You may also pass an object to set several fields in a single call :telephone_receiver: :

```
 request
   .get('/search')
   .set({ 'API-Key': 'foobar', Accept: 'application/json' })
   .then(callback);
```

### GET requests

The **.query()** method accepts **objects**, which when used with the **GET** method will form a **query-string**. The following will produce the path `/search?query=Manny&range=1..5&order=desc`.

```
 request
   .get('/search')
   .query({ query: 'Manny' })
   .query({ range: '1..5' })
   .query({ order: 'desc' })
   .then(res => {

   });
```

**The .query() method accepts strings as well:**

```
  request
    .get('/querystring')
    .query('search=Manny&range=1..5')
    .then(res => {

    });
```

### Setting the Content-Type :battery:

**The obvious solution is to use the .set() method** (contiunue the reads from the same page :) )

## What Google Learned From Its Quest to Build the Perfect Team :family_man_woman_boy_boy:

**THE WORK ISSUE: REIMAGINING THE OFFICE** :men_wrestling:

1. How to Build a Perfect Team
2. The War on Meetings
3. The Case for Blind Hiring
4. Failure to Lunch
5. The 'Good Jobs' Gamble
6. Rethinking the Work-Life Equation
7. The Rise of White-Collar Automation
8. The Post-Cubicle Office
9. The New Dream Jobs

# APIs continued

## Reading

[What Google Learned From Its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

[How I explained REST to my brother](https://gist.github.com/brookr/5977550)

`From what I understand of this article polymorphism applies to REST by saying that we can have multiple nouns, ie things to be selected that have the same verb applied to them I.E. POST GET PUT DELETE. Which relate to SQL with INSERT, SELECT, UPDATE, DELETE.`

## Bookmark/Skim

[Documentation for SuperAgent](https://visionmedia.github.io/superagent/)

## API Keys

Request a personal API key from the following APIs. You should receive these in your email within a few hours, often within minutes. Please request these keys prior to lecture to allow adequate time because you will need them in order to complete your lab assignment.

[Geocoding API Docs](https://locationiq.com/)
[Dark Sky API Docs](https://darksky.net/dev/docs)
[Yelp API Docs](https://www.yelp.com/developers/documentation/v3/business_search)
[The Movie DB API Docs](https://developers.themoviedb.org/3/getting-started/introduction)

#### live API's

[Developer accounts](https://console.developers.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project)

- go to this wesite and create project (_this will make me google developer_ **it will allow me to do work for google with thier data**)
- activate enable apis and services
  - search for the api that U need (mab and geo)
    - Maps Static API (that will draw the maps for us)
    - Maps JavaScript API
    - Geocoding API
- create credentials to allow U to use the api
  - api key (it will creat an api key for U) _api key_**AIzaSyAjgY6orhQxdVuxkJ-cWF81hdwassjAbkg**

<!-- if some one is using chrome -->

- _the chrome will be a client b/c its asking for information_
- _the server will send back jason data_
- _behind the server to get info_
  - if I search for weather the **server** will get the API from darksky api **(cloud)**
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
    <!-- 
    'use strict';
    requier('dotenv').config();
    const express=require('express');
    const PORT= process.env.PORT;
    const server=express;
    server.get('/hi',(req,res)=>{
      res.status(200).send('hi');
    });
    **started up**
    server.listen(PORT, ()=>{
      console.log('hello');
      })
      -->
  _npm start or nodemon_
  _then go to the local host and test it_
  _ACP and merge_

### DEPLOY

1. **Heroku**

- create an app
- connect to get
- pick the repo
- auto deploy

_the diffecult things are_:
**API DOCS**
**BIG OBJECTS**
event.event.day....[]


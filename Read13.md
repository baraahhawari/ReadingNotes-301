# Update/Delete

**Reading** :memo:
[Sending Form Data](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)

**Additional Resources** :pen:
[HTML5 Forms Reference](https://htmlreference.io/forms/)

- Pay special attention to the **“action”** and **“method”** **attributes**.

**Videos** :film_projector:
[Video Series on Styling HTML5 Forms](https://www.youtube.com/playlist?list=PL4cUxeGkcC9g5_p_BVUGWykHfqx6bb7qK)
Note that this video series is approximately **40 minutes** long. You do not need to watch every video from the series, but should keep it handy for **reference as you style your book app during lab time**.

## This article looks at what happens when a user submits a form :notebook:

1. **where** does the data go
1. **how** do we handle it when it gets there?
1. **security** concerns associated with sending form data.

### Client/server architecture

- a **client** (usually a **web browser**) sends a **request** to a **server** (most of the time a web server like **Apache**, **Nginx**, **IIS**, **Tomcat**, etc.)
  - using the **HTTP protocol**. The server **answers** the **request** using the **same protocol**.

![client-server](img/client-server.png)

#### On the client side: defining how to send the data

- The <form> element defines how the data will be sent.
  - All of its **attributes** are **designed** to let you **configure** the **request** to be sent when a user hits a submit button.
  - The two most important attributes are:
    - **action**
    - **method**.

##### The action attribute:

1. defines **where** the data gets **sent**.
1. Its value must be a **valid** relative or **absolute URL**.
1. If this attribute **isn't provided**, the **data** will be **sent** to the **URL** of the page containing the form — the current page
1. The **action** **value** should be a **file** **on** the **server** that can handle the incoming data, including ensuring **server-side validation**
1. The **server** then **responds**, causing a **new page load** (or a **refresh** of the existing page, if the action points to the same page).
   `if the form is hosted on a secure page but you specify an insecure HTTP URL with the action attribute, all browsers display a security warning to the user each time they try to send data because the data will not be encrypted.`

##### The method attribute

**How the data is sent depends on the method attribute.**
HTML form data can be transmitted via a number of different methods:

1. **GET** method
1. **POST** method

To understand the **difference** between those two methods, let's examine how **HTTP** works.
`Each time you want to reach a resource on the Web, the browser sends a request to a URL. An HTTP request consists of two parts: a header that contains a set of global metadata about the browser's capabilities, and a body that can contain information necessary for the server to process the specific request.`

1. **The GET method** :newspaper_roll: : used by the browser `Hey server, I want to get this resource.`
   - the **browser** sends an **empty body**. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the **URL**.

Consider the following form:

```
<form action="http://www.foo.com" method="GET">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

`you'll see the URL www.foo.com/?say=Hi&to=Mom`

**The HTTP request looks like this:**

```
GET /?say=Hi&to=Mom HTTP/2.0
Host: foo.com
```

1. **The POST method** :newspaper_roll: : **browser** uses to talk to the **server** when **asking** for a response that takes into account the data provided in the body of the **HTTP request**:
   `"Hey server, take a look at this data and send me back an appropriate result." If a form is sent using this method, the data is appended to the body of the HTTP request.`

**Using the Get Example and changing the first line by:**
`<form action="https://www.foo.com" method="POST">`
When the **form** is **submitted** using the **POST** method, you get **no data appended to the URL**, and the HTTP request looks like so, with the data included in the request body instead:

```
POST / HTTP/2.0
Host: foo.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 13

say=Hi&to=Mom
```

- The **Content-Length** header: indicates the **size** of the **body**.
- Thee **Content-Type** header: indicates the **type** of **resource** sent to the **server**.

1. **Viewing HTTP requests** :page_facing_up: : HTTP requests displayed to the user by useing tools [Chrome Developer Tools](https://developers.google.com/web/tools/chrome-devtools?utm_source=dcc&utm_medium=redirect&utm_campaign=2018Q2)

**After submitting the form:** :performing_arts:

- Open the developer tools.
- Select "Network"
- Select "All"
- Select "foo.com" in the "Name" tab
- Select "Headers"
  ![network-monitor](img/network-monitor.png)

**The only thing displayed to the user is the URL called. with a GET request the user will see the data in their URL bar, but with a POST request they won't. This can be very important for two reasons:**

1. If you need to send a **password** (or any other sensitive piece of data), **never use the GET method** or you risk displaying it in the URL bar, which would be very insecure.
1. If you need to send a **large amount of data**, the **POST** method is **preferred** because some browsers limit the sizes of URLs. In addition, many **servers limit the length of URLs they accept**.

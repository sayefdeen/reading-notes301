# SENDING FORM DATA

[Home](https://sayefdeen.github.io/reading-notes301/)

At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.

An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server. This enables the user to provide information to be delivered in the HTTP request.

## On the Client Side.

The `<form>` element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are `action` and `method`.

```html
<form action="http://www.foo.com" method="GET">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi" />
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom" />
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

```javascript
// The Previous data will be sent like this
{
//  name:value
    say:Hi,
    to:Mom
}
```

The names and values of the non-file form controls are sent to the server as **name=value** pairs joined with ampersands. The action value should be a file on the server that can handle the incoming data, including ensuring server-side validation. The server then responds, generally handling the data and loading the URL defined by the action attribute, causing a new page load (or a refresh of the existing page, if the action points to the same page).

---

## How the data is sent?

The `method` attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the `GET method` and the `POST method`, by default the from has a GET method.

1. The GET method : is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource." In this case, the browser sends an empty body. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.

```http
<!-- The Previous example URL -->
        www.foo.com/?say=Hi&to=Mom
```

The HTTP request looks like this :

    GET /?say=Hi&to=Mom HTTP/2.0

    Host: foo.com

2. The POST method : is a little different. It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." If a form is sent using this method, the data is appended to the body of the HTTP request.

The HTTP request looks like this :

    POST / HTTP/2.0
    Host: foo.com
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 13
    say=Hi&to=Mom

The Content-Length header indicates the size of the body, and the Content-Type header indicates the type of resource sent to the server. We'll discuss these headers later on.

## Viewing HTTP requests.

HTTP requests are never displayed to the user (if you want to see them, you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools)

- If you need to send a password (or any other sensitive piece of data), never use the GET method or you risk displaying it in the URL bar, which would be very insecure.

- If you need to send a large amount of data, the POST method is preferred because some browsers limit the sizes of URLs. In addition, many servers limit the length of URLs they accept.

---

## Security issues

Each time you send data to a server, you need to consider security. HTML forms are by far the most common server attack vectors (places where attacks can occur). The problems never come from the HTML forms themselves — they come from how the server handles data.

<p style="color:red; background-color:black; text-align: center; text-transform:uppercase  "> Be paranoid: Never trust your users.

All data that comes to your server must be checked and sanitized. Always. No exception.

- **Escape potentially dangerous characters**. The specific characters you should be cautious with vary depending on the context in which the data is used and the server platform you employ, but all server-side languages have functions for this. Things to watch out for are character sequences that look like executable code (such as JavaScript or SQL commands).

- Limit the incoming amount of data to allow only what's necessary.

- **Sandbox uploaded files**. Store them on a different server and allow access to the file only through a different subdomain or even better through a completely different domain.

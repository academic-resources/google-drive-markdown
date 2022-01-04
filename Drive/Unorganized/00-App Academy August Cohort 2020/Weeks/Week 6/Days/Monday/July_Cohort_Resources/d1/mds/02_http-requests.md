# HTTP Requests

Without a query, there wouldn't be a need for a response! Let's take a look at
the _request_: the client-initiated portion of an HTTP exchange.

We'll cover:

- what an HTTP request looks like,
- fields that make up a request,
- and how to send a request of your own!

## Retrieving hypertext

Years ago, daily shopping looked very different. Instead of walking the aisles
and picking up what they wanted, customers would approach a counter and ask a
clerk to retrieve the items on their list. The clerk was responsible for knowing
where those items were located and how best to get them to the customer.

While the retail industry has changed dramatically since that time, the Web
follows that old tried-and-true pattern. You tell your browser which website you
would like to access, and your browser hands that request off to a server that
can get you what you've asked for. At the simplest level, the Web is just made
up of computers asking each other for things!

Your browser's part in this transaction is called the _request_. Since the
browser is acting on your behalf, we sometimes refer to it as the _user-agent_
(you being the _user_). You might also hear this referred to more generically as
the _client_ in the exchange.

## Structure of an HTTP request

Your browser is designed to be compliant with the HTTP specification, so it
knows how to translate your instructions into a well-formatted HTTP request. An
important part of the HTTP spec is that it's simple to read, so let's take a
look at an example.

Here's what the HTTP request looks like for visiting `appacademy.io`:

```text
GET / HTTP/1.1
Host: appacademy.io
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
```

Let's break it down!

### Request-line & HTTP verbs

The first line of an HTTP request is called the **request-line**, and it sets
the stage for everything to come. It's made up of three parts, separated by
spaces:

- the _method_, indicated by an _HTTP verb_,
- the _URI (Uniform Resource Indicator)_ that identifies what we've requested,
- and the _HTTP version_ we expect to use (usually `HTTP/1.1` or `HTTP/2`).

In our `appacademy.io` example, we can see that our version matches the most
common HTTP version (`1.1`) and that our URI is `/`, or the _root_ resource of
our target. That first word, `GET` is the HTTP verb we're using for this
request.

HTTP verbs are a simple way of declaring our intention to the server. We do the
same thing with English verbs when asking for help: "Can you **get** me that?",
"Should I **remove** this?", etc. HTTP has a small handful of verbs available,
but we're going to look at the five most common: `GET`, `POST`, `PUT`, `PATCH`,
and `DELETE`.

- `GET` is used for direct requests. A `GET` request is generally how websites
  are retrieved, and they only require that the server return a resource. These
  types of requests will never have a body. Any data you need to send in a `GET`
  request must be shared via the URI.

- `POST` is typically used for creating new resources on the server. Most of the
  time, when you submit a form a `POST` request is generated. These types of
  requests can have a _body_ containing any data the server might need to
  complete your request, like your username & password or the contents of your
  shopping cart.

- `PUT` requests are used to update a resource on the server. These will contain
  the whole resource you'd like to update. For example: when updating your name
  on a website, a `PUT` request will be generated containing not just your new
  name but also your user ID, email, etc.

- `PATCH` requests are very similar to `PUT` requests, but do not require the
  whole resource to perform the update. Keeping with our example of updating
  your name: a `PATCH` request would only require your new name, not the rest of
  your account details, to succeed.

- `DELETE` requests destroy resources on the server. These might be saved
  database records, like removing a product that's sold out, or more ephemeral
  resources, like logging a user out of their current session.

Ultimately, how these verbs get acted upon is up to the server. You could write
an application that totally ignores these rules and uses a `DELETE` request to
log in, but that's only going to confuse your teammates and frustrate you in the
future! It's best to use them as the spec intends.

### Headers

The _request-line_ sets the table, but it's the headers that describe the menu!
_Headers_ are key/value pairs that come after the _request-line_. They each
appear on separate lines and define metadata needed to process the request. Here
are some common request headers you'll see:

- `Host`: The root path for our URI. This is typically the _domain_ we'd like to
  request our resource from. As you can see above, our `Host` header for
  `appacademy.io` is, appropriately, `appacademy.io`.!

- `User-Agent`: This header displays information about which browser the request
  originated from. It's generally formatted as `name/version`. You can see in
  the `User-Agent` header above that we're using `Chrome/76.0`
  > Our `User-Agent` has much more content, including references to Mozilla,
  >makers of the popular Firefox browser, and Safari, Apple's default browser of
  >choice. What gives?
  >
  >There is some [interesting history][1] behind those additional references,
  >and you can use [www.useragentstring.com][2] for additional details about
  >your current browser's `user-agent`.

- `Referer`: This defines the URL you're coming from. There's none in our
  example since we navigated directly to the App Academy website, but if we
  click any link on the page, the resulting HTTP request will have `Referer:
  https://appacademy.io/` in its headers. Also, you're not reading it wrong -
  this header is misspelled! It should be "referrer", but it was written
  incorrectly in the original specification and the typo stuck. Let this be a
  lesson: your poorly-written code might still be around in 20 years, too!

- `Accept`: "Accept-" headers indicate what the client can receive. When we go
  to most websites, our `Accept` header will be long to ensure we get all the
  various types of content that site might include. However, we can modify this
  header in our requests to only get back certain types of data. One common use
  is setting `Accept: application/json` to get a response in JSON format instead
  of HTML. You may see variations of this header like `Accept-Language` for
  internationalized websites or `Accept-Encoding` for sites that support
  alternative compression formats.

- `Content-*`: Content headers define details about the body of the request. The
  most common content header is `Content-Type`, which lets the server know what
  format we're sending our body data as. This might be `application/json` from a
  JavaScript app or `application/x-www-form-urlencoded` for info submitted from
  a web form. Content headers will only show up on requests that support content
  in the body, so `GET` requests should never have this!

There are LOTS of other header keys! [MDN][3] has an exhaustive reference list
with examples.

### Body

When we need to send data that doesn't fit in a header & is too complex for the
URI, we can place it in the _body_ of our HTTP request. The body comes right
after the headers and can be formatted a few different ways.

The most common way form data is formatted is _URL encoding_. This is the
default for data from web forms and looks a little like this:

```html
name=claire&age=29&iceCream=vanilla
```

Alternatively, you might format your request body using JSON or XML or some
other standard. What's most important is that you remember to set the
appropriate `Content-Type` header so the server knows how to interpret your
body.

## Sending an HTTP request from the command line

We've discussed HTTP requests mostly in the context of your web browser, but
that's not the only way. There are lots of HTTP clients out there you can use to
send requests.

Let's stay close to the exchange itself with a lightweight tool that requires us
to do most of the work ourselves. We'll use `netcat` (also known as `nc`), a
utility that comes as part of Unix-like environments such as Ubuntu and macOS.

`netcat` allows you to open a direct connection with a URL and manually send
HTTP requests. Let's see how this works with a quick `GET` request to App
Academy's homepage.

From your command line, type `nc -v appacademy.io 80`. This will open a
connection to `appacademy.io` on port 80 (the port most-often used for web
connections). Once the connection is established, you'll be able to type out a
simple HTTP request by hand! Let's copy the _request-line_ and `Host:` header
from our request above:

```sh
GET / HTTP/1.1
Host: appacademy.io
```

Now hit "Return" on your keyboard twice. This will send the request and display
the server's response. You should see something similar to this:

```sh
HTTP/1.1 301 Moved Permanently
Date: Thu, 03 Oct 2019 04:17:23 GMT
Transfer-Encoding: chunked
Connection: keep-alive
Cache-Control: max-age=3600
Expires: Thu, 03 Oct 2019 05:17:23 GMT
Location: https://www.appacademy.io/
Server: cloudflare
CF-RAY: 51fc1b0f8b98d304-ATL
```

Congratulations! You've sent your first manual HTTP request. We'll discuss the
parts of the HTTP response you received in an upcoming lesson.

Try it one more time, this time typing `nc -v neverssl.com 80` and making the
same HTTP request with the command `GET / HTTP/1.1` and the header `Host:
neverssl.com`. Don't forget to hit Enter twice. Look! That's the HTML coming
back from the server! Neat-o!

You can read much more about `netcat` by invoking the manual: `man nc`. We'll
also use it in an upcoming project for extra practice.

## What we've learned

HTTP requests are the first step to getting what you want on the web. Having
completed this lesson, you should be able to recount:

- what an HTTP request is,
- some common HTTP request verbs,
- a rough outline of the HTTP request format,
- and how to use `netcat` to send HTTP requests from your command line.

[1]: https://security.stackexchange.com/questions/126407/why-does-chrome-send-four-browsers-in-the-user-agent-header
[2]: http://www.useragentstring.com/
[3]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

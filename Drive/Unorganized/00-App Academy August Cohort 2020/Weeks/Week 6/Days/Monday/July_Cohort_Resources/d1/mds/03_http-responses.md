# HTTP Responses

A web server delivers content via _responses_, the second part of the HTTP's
request/response cycle. Let's dive into how a response is structured and what
your client can expect from the server.

We'll cover:

- HTTP response structure,
- differentiating errors & successful transfers,
- and how to use a server to generate your own responses.

## Hypertext delivered

An HTTP response contains either the content we requested or an explanation of
why that content couldn't be delivered. It's just like ordering at a restaurant:
you place your order and receive either a plate of delicious food or an apology
from the chef. In a good restaurant, the apology will include some extra help:
"I'm sorry, we're out of broccoli. Can we get you something else? How can we
make this right?".

When designing your own HTTP responses, remember that restaurant example. It's
important to note that there's a problem, but it's equally important to provide
reliable, helpful details. We'll look at some examples of this when we build our
own HTTP server in a later lesson.

## Structure of a Response

Responses are formatted similarly to requests: we'll have a _status-line_
(instead of a request-line), headers that provide helpful metadata about the
response, and the response body: a representation of the requested resource.

Here's what the HTTP response looks like when visiting `appacademy.io`:

```text
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Transfer-Encoding: chunked
Connection: close
X-Frame-Options: SAMEORIGIN
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
Cache-Control: max-age=0, private, must-revalidate
Set-Cookie: _rails-class-site_session=BAh7CEkiD3Nlc3Npb25faWQGOgZFVEkiJTM5NWM5YTVlNTEyZDFmNTNlN; path=/; secure; HttpOnly
X-Request-Id: cf5f30dd-99d0-46d7-86d7-6fe57753b20d
X-Runtime: 0.006894
Strict-Transport-Security: max-age=31536000
Vary: Origin
Via: 1.1 vegur
Expect-CT: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
Server: cloudflare
CF-RAY: 51d641d1ca7d2d45-TXL

<!DOCTYPE html>
<html>
...
...
</html>
```

Oof! That's a lot of unfamiliar stuff. Let's walk through the important bits
together.

### Status

Like the request, an HTTP response's first line gives you a high-level overview
of the server's intention. For the response, we refer to this as the
_status-line_.

Here's the status line from our `appacademy.io` response:

```text
HTTP/1.1 200 OK
```

We open with the HTTP version the server is responding with. `1.1` is still the
most commonly used, though you may occasionally see `2` or even `1.0`. We follow
this with a `Status-Code` and `Reason-Phrase`. These give us a quick way of
understanding if our request was successful or not.

_HTTP status codes_ are a numeric way of representing a server's response. Each
code is a three-digit number accompanied by a short description. They're grouped
by the first digit (so, for example, all "Informational" codes begin with a `1`:
`100` - `199`).

Let's take a look at the most common codes in each group.

#### Status codes 100 - 199: Informational

Informational codes let the client know that a request was received, and provide
extra info from the server. There are very few informational codes defined by
the HTTP specification and you're unlikely to see them, but it's good to know
that they exist!

#### Status codes 200 - 299: Successful

Successful response codes indicate that the request has succeeded and the server
is handling it. Here are a couple common examples:

- **200 OK**: Request received and fulfilled. These usually come with a `body`
  that contains the resource you requested.

- **201 Created**: Your request was received and a new record was created as a
  result. You'll often see this response to `POST` requests.

#### Status codes 300 - 399: Redirection

These responses let the client know that there has been a change. There are a
few different ways for a server to note a redirect, but the two most common are
also the most important:

- **301 Moved Permanently**: The resource you requested is in a totally new
  location. This might be used if a webpage has changed domains, or if resources
  were reorganized on the server. Most clients will automatically process this
  redirect and send you to the new location, so you may not notice this response
  at all.

- **302 Found**: Similarly, to _301 Moved Permanently_, this indicates that a
  resource has moved. However, this code is used to indicate a temporary move.
  It's not often that you see temporary moves online, but this code may be used
  to indicate a permanent move where the old domain should still be valid too.
  Clients will usually follow this redirect automatically as well, but you
  shouldn't necessarily update your links until the server returns a `301`.

> _301 Moved Permanently_ and _302 Found_ often get confused. When might we want
> to use a _302 Found_`_? The most common use case today is for the transition
> from HTTP to HTTPS. _HTTPS_ is secure HTTP messaging, where requests &
> responses are _encrypted_ so they can't be read by prying eyes while en route
> to their destinations.
>
> This is a much safer way of communicating online, so most websites require
> access via `https://` before the domain. However, we don't want to ignore folks
> still trying to access our content from the older `http://` approach!
>
> In this case, we'll return a _302 Found_ response to the client, letting them
> know that it's okay to keep navigating to `http://our-website.com`, but we're
> going to redirect them to `https://our-website.com` for their protection.

#### Status codes 400 - 499: Client Error

The status codes from 400 to 499, inclusive, indicate that there is a problem
with the client's request. Maybe there was a typo, or maybe the resource we
requested is no longer available. You'll see lots of these as you're learning to
format HTTP requests. Here are the most common ones:

- **400 Bad Request**: Whoops! The server received your request, but couldn't
  understand it. You might see a _400 Bad Request_ in response to a typo or
  accidentally truncated request. We often refer to these as _malformed_
  requests.

- **401 Unauthorized**: The resource you requested may exist, but you're not
  allowed to see it without authentication. These type of responses might mean
  one of two things: either you didn't log in yet, or you tried to log in but
  your credentials aren't being accepted.

- **403 Forbidden**: The resource you requested may exist, but you're not
  allowed to see it _at all_. This response code means this resource isn't
  accessible to you, even if you're logged in. You just don't have the correct
  permission to see it.

- **404 Not Found**: The resource you requested doesn't exist. You may see this
  response if you have a typo in your request (for example: going to
  `appaccccademy.io`), or if you're looking for something that has been removed.

> _403 Forbidden_ requests let the client know that a valid resource was
> requested. This can be a security risk! For example: if I guess that you have
> _passwords.html_ on your website because you just _want_ to be hacked, a _403
> Forbidden_ response tells me I'm correct. For this reason, some sites will
> return a _404 Not Found_ for resources that exist but aren't accessible.
>
> A well-known example is GitHub. If you try to open a repository you don't have
> permission to access, GitHub will return a _404 Not Found_ even if your URL is
> correct! This protects you from random users guessing the names of your
> projects.

#### Status codes 500 - 599: Server Error

This range of response codes are the Web's way of saying "It's not you, it's
me." These indicate that your request was formatted correctly, but that the
server couldn't do what you asked due to an internal problem.

There are two common codes in this range you'll see while getting started:

- **500 Internal Server Error**: Your request was received, and the server tried
  to process it, but something went awry! As you're learning to write your own
  servers, you'll often see a _500 Internal Server Error_ as your code fails
  unexpectedly.

- **504 Gateway Timeout**: Your request was received but the server didn't
  respond in a reasonable amount of time. Timeout errors can be tricky: your
  first instinct may be that your own connection is bad, but this code means the
  problem is likely on the server's side. You'll often see these when a server
  is no longer reachable (maybe due to an unexpected outage or power failure).

### Headers

Headers on HTTP responses work identically to those on requests. They establish
metadata that the receiving client might need to process the response. Here are
a few common response headers you'll see:

- **Location**: Used by the client for redirection responses. This contains the
  URL the client should redirect to.

- **Content-Type**: Lets the client know what format the body is in. Your client
  will display different types of response content in different ways, to setting
  the _Content-Type_ is important! Notice that this header can be present on
  responses **and** requests. It's a generic header for any HTTP interaction
  involving content.

- **Expires**: When the response should be considered _stale_, or no longer valid.
  The _Expires_ header lets your client _cache_ responses (that is: save them
  locally to prevent having to repeatedly re-download them). The client may
  ignore requests to that same resource until after the date set in the
  _Expires_ header.

- **Content-Disposition**: This header lets the client know how to display the
  response, and is specifically devoted to whether the response should be
  visible to the client or delivered as a download. Think about your own
  experience online: sometimes you click a button and get an immediate download,
  while in other cases you click a button and get to "preview" the content
  before you download it. This is controlled by the _Content-Disposition_
  header.

- **Set-Cookie**: This header sends data back to the client to set on the
  _cookie_, a set of key/value pairs associated with the server's domain.
  Remember how HTTP is _stateless_? Cookies are one way to get around that!
  _Set-Cookie_ may send back information like a unique ID for the user you've
  logged in as or details about other resources you've requested on this domain.

Remember - this isn't an exhaustive list of headers! Sites and intermediate
gateways/proxies can define their own custom headers, so you'll see many more
than these. If you're unsure what a header does, the [MDN HTTP Header
documentation][1] is a great place to start searching.

### Body

Assuming a successful request, the _body_ of the response contains the resource
you've requested. For a website, this means the HTML of the page you're
accessing.

The format of the body is dictated by the _Content-Type_ header. This is an
important detail! If you accidentally configure your server to send
"Content-Type: application/json" along with a body containing HTML, your HTML
won't be rendered properly and your users will see plain text instead of
beautifully-rendered elements. In the same way, API responses should be clearly
marked so that other applications know how to manage them.

We can see in our `appacademy.io` response above that the body begins with
`!<DOCTYPE html>` and ends with `</html>`. If you inspect the source of the page
in your browser, you'll see that this is exactly what's being rendered. Headers
may change **how** the browser handles the body, but they won't **modify** the
body's content.

## Using a custom server to generate responses

At its most basic, a web server is just a tool to generate HTTP responses.
Therefore, the best way to practice is to build your own webserver!

We'll walk through building our own server from scratch using Node.js in an
upcoming video lesson.

## What we've learned

Like HTTP requests, HTTP responses involve lots of new lingo and details. Hang
in there - we'll start doing practical work with this new vocabulary in the
projects & video demos coming up.

After this reading, you should:

- Understand the parts of an HTTP response,
- be able to identify common status codes & their meanings,
- recognize common response headers,
- and be prepared to build your own server!

[1]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

# HTTP: From Zero To Server

We've been knee-deep in everyone else's HTTP workflow; let's build one of our
own! Together we're going to build an HTTP server from scratch. We'll cover:

- Node's `http` module & `createServer` method,
- Routing requests based on multiple factors,
- Returning content and headers in your response,
- and testing your server locally using command line tools.

**DO NOT GIVE INTO COPY & PASTE!** In the following instructions, you will see
code samples. Do _not_ copy and paste them. Type them in or watch someone type
them in. Do this so that you _feel_ the syntax. If you just copy and paste, when
it comes to typing the code yourself, you will be at a loss.

## Phase 1: Proof of concept

Your goal is to go from "zero to server" in this project, so let's get "zero"
ready. Clone this project's starter repo:

```
git clone https://github.com/appacademy-starters/http-from-zero-to-server-starter.git
```

You'll notice that this starter project only has a `test` directory. In the
project directory, outside of the `test` folder, create an empty file named
`server.js`.

You'll be basing your server on the `http` module that's built into Node.js. You
can't use this module until we include it in your application! Use the `require`
directive to import Node's `http` module right away and assign it to a variable
named `http`.

Next, time to get a bare bones server up and running. Drop down a line and call
the `createServer` method on `http`. This method accepts a single argument that
is a function. The function should have two parameters. By convention, we name
the parameters `req` (short for "*req*uest") and `res` (short for "*res*ponse").
Within the body of that function argument, call the `end` method on `response`.
This will generate a simple `200 OK` response to any request at all, regardless
of what's asking for.

Remember that you can't run your server without letting it know where to expect
requests from! Chain the `listen` method on to the end of the `createServer`
call we just made. `listen` accepts two parameters: a port number and a
function. The port number indicates where the server will be accessible from,
and the function argument is meant for any initialization code you'd like to run
when the server starts. Use port `3000` and, within your function argument,
`console.log` a helpful startup message. Make sure you include the port number
in your message in case your users forget!

By now you should have a dead-simple HTTP server. This app will accept requests
and respond with `http`'s default response: `200 OK`, no custom headers, no body
content. You can confirm this by running the server in your terminal and
visiting `http://localhost:3000` in your browser. You won't see any content in
the browser, but check the "Network" tab in your dev tools to confirm that the
server response matches what you expect. You may need to refresh the page to see
the request/response.

Save and commit your changes to version control! This completes your first unit
of work and results in a runnable server that's all your own. We know we can do
better, though! Let's look into routing.

To see what this should look like, have a peek at [About Node.js®].

## Phase 2: Status code all the things!

When discussing Web servers, _routing_ generally refers to controlling which
part of your application processes each request. For example, you may route
emails differently than website requests. There are lots of complex, high
throughput routing libraries available for Node, but you'll keep it as simple as
possible here and rely on your hard work.

You need something to control how we route each request. For your server, the
best bet is the request's `url` property. This is a key provided by `http`
that's present on every `request` our server processes. You can check the `url`
of each inbound request and decide what we want to return for that particular
resource.

### Phase 2a: Start small

Build out your routing like so: when someone requests a particular
`Reason-Phrase`, you should respond with the matching HTTP `Status-Code`. For
example:

- `http://localhost:300/OK` should return `HTTP/1.1 200 OK`

You can use the [`writeHead`] method on the `response` object to control which
status code gets returned.

```js
if (req.url === "/OK") {
  console.log("Inbound 'OK' request being processed...");
  res.writeHead(200);
  res.end();
}
```

There are a couple important details to note in this condition:

- Your `url` property includes a leading slash.
- You still have to `end()` each response to send it back to the client. If you
  don't do this, the browser will wait and wait and wait and, eventually, tell
  you that the request timed out.

This code should go in the function argument of `createServer`, where your `req`
and `res` params are accessible.

You're only controlling for one `url` option here. What about all the other
possibilities? Before you save this portion of our work as done, you should add
an `else` to this condition that returns a appropriate status code. A perfect
choice would be status code 404! Don't forget to include a relevant
`console.log` in your else condition as well.

Before saving & committing, make sure you can run your server, and that visiting
`http://localhost:3000/OK` returns a `200`, while visiting any other URL returns
a `404`. You should see a new line in your terminal, consistent with the
messages in your `console.log`s, for each request that's made.

### Phase 2b: Rinse, repeat

You've read about many more codes than `200` and `404`. Extend your server to
respond to each reason phrase we discussed in our readings. You can omit `OK`
and `Not Found` because we've already handled those cases.

Here's an alphabetical list of each `url` your server should respond to:

```text
- /Bad-Request
- /Created
- /Forbidden
- /Found
- /Gateway-Timeout
- /Internal-Server-Error
- /Moved-Permanently
- /Unauthorized
```

It's up to you to look up the matching HTTP status codes each will need to
return. Use [DuckDuckGo] (or your favorite search engine) to search for HTTP
status codes. You can bet there's at least a Wikipedia entry on it!

Follow the pattern you used with `/OK` and don't forget the details. This may
feel a little repetitive, but it's a great opportunity to practice matching
status codes to reasons. This is the sort of minutiae that technical
interviewers will want to quiz you on during your job hunt - try to lock it down
now!

Save, commit, and test your new server out.

## Phase 3: Confirming functionality

The tricky thing about the HTTP specification that most clients are configured
to respond to certain codes in certain ways. Browsers, for example, will try to
follow redirection codes and will show special pages for server errors unless
directed otherwise. This means that browser testing can be a little flaky.

Try using one of a couple tools you already know how to use to test our server,
instead of hoping the browser will keep working the way you'd like.

## Phase 3a: A command line client

The lowest-friction approach you can take is using a native command line tool to
test our HTTP server like `netcat`.

Run your server in one terminal, and in another terminal run `nc -v localhost
3000`. This will run `netcat` in "verbose" mode, so you get a little extra info
with each request. Now you can manually craft HTTP requests to your server.

Try typing (or copying/pasting) `GET /OK HTTP/1.1` first. Remember to press the
"Return" key twice after entering that request line. You should receive a `200
OK` response immediately. If your response is taking more than a couple seconds
to process, try restarting `netcat` by pressing `Ctrl` + `C` on your keyboard
and starting over.

Now test your other routes - do they all return what you expect?

## Phase 3b: Double-check your work

Automated testing can be a little more work, but don't worry: we've put some
tests together for you!

With your server running on port 3000 and run `mocha` on your command line to
watch the tests fly!

Your tests will confirm that your routes are all returning the expected status
codes, and will let you know of any that might have been missed. If you get
confused, don't be afraid to read the test file for extra details. The code &
comments within may be clearer than mocha's error messaging.

## Bonus phase: Take it up a notch

Ready to go beyond the basics? Here are some improvements to explore:

- The [`writeHead`] on _response_ accepts a second argument: an object
  containing custom headers. Knowing this, try to update your responses with
  redirection codes to _actually_ redirect. Is there a custom header you can use
  to tell your browser where the request should be directed to? Try searching
  for more information about the status code that redirects the browser to
  another resource.

- This project didn't discuss the [`write`] method on the _response_ object, but
  it adds content to the body of your response. Using both the correct
  `Content-Type` header and the `write` method, try sending some HTML back with
  responses. Can you render a very simple webpage from your server?

- Certain codes (like _201_, for example) are often only seen in response to
  `POST` requests. You've only been using `GET` requests so far, but you could
  improve your server by having it check the `request.method` before responding
  to some URLs. Try limiting the `Created` response to `POST` requests only.
  Otherwise, it should respond with a _405 Method Not Allowed_, a status code
  created for just the purpose of telling clients that they've used an HTTP
  method (GET, POST, PUT, PATCH, or DELETE) that the URL doesn't support.

## What you've learned

You've mastered the art of the HTTP server - congratulations! You'll soon grow
into larger, more fully-featured frameworks, but don't forget your basics. Every
server out there is based on these same simple principles.

After completing this project, you should be able to:

- write up a basic server for Node,
- respond to requests of all types with appropriate status codes & data,
- and test servers (both your own and others') using reliable command line
  tools.

[1]:
https://nodejs.org/api/http.html#http_response_writehead_statuscode_statusmessage_headers
[`write`]:
https://nodejs.org/api/http.html#http_response_write_chunk_encoding_callback
[About Node.js®]: https://nodejs.org/en/about/#about-node-js [`writeHead`]:
https://nodejs.org/api/http.html#http_response_writehead_statuscode_statusmessage_headers
[DuckDuckGo]: https://www.duckduckgo.com

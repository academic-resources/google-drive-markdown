This website stores cookies on your computer. These cookies are used to
collect information about how you interact with our website and allow us
to remember you. We use this information in order to improve and
customize your browsing experience and for analytics and metrics about
our visitors both on this website and other media. To find out more
about the cookies we use, see our Privacy Policy.

If you decline, your information won’t be tracked when you visit this
website. A single cookie will be used in your browser to remember your
preference not to be tracked.

[Accept](https://www.npmjs.com/package/node-fetch#)
[Decline](https://www.npmjs.com/package/node-fetch#)

[](https://github.blog/2020-04-15-npm-has-joined-github/)

**npm** is now a part of **GitHub**

❤Navel Piercing Madness

-   [Products](https://www.npmjs.com/products)
    -   [Pro](https://www.npmjs.com/products/pro)
    -   [Teams](https://www.npmjs.com/products/teams)
-   [Pricing](https://www.npmjs.com/products)
-   [Documentation](https://docs.npmjs.com/)
-   [Community](https://npm.community/)

npm {._657f443d}
===

[](https://www.npmjs.com/)

Search

[Sign Up](https://www.npmjs.com/signup)[Sign
In](https://www.npmjs.com/login)

Learn about our RFC process, Open RFC meetings & more.[Join in the
discussion! »](https://github.com/npm/rfcs)

node-fetch {.cd6ce1fd .flex .flex-column .w-100 .fw6 .mt3 .black .dib .ma0 .tracked-tight .no-underline .hover-black .f3-ns}
----------

2.6.1 • Public • Published 10 days ago

-   [](https://www.npmjs.com/package/node-fetch?activeTab=readme)
    Readme
-   [](https://www.npmjs.com/package/node-fetch?activeTab=explore)
    ExploreBETA
-   [](https://www.npmjs.com/package/node-fetch?activeTab=dependencies)
    0Dependencies
-   [](https://www.npmjs.com/package/node-fetch?activeTab=dependents)
    14,384Dependents
-   [](https://www.npmjs.com/package/node-fetch?activeTab=versions)
    61Versions

[](https://www.npmjs.com/package/node-fetch#node-fetch)

node-fetch

[![npm
version](./node-fetch%20-%20npm_files/node-fetch)](https://www.npmjs.com/package/node-fetch)
[![build
status](./node-fetch%20-%20npm_files/node-fetch(1))](https://travis-ci.org/bitinn/node-fetch)
[![coverage
status](./node-fetch%20-%20npm_files/master)](https://codecov.io/gh/bitinn/node-fetch)
[![install
size](./node-fetch%20-%20npm_files/node-fetch(2))](https://packagephobia.now.sh/result?p=node-fetch)
[![Discord](./node-fetch%20-%20npm_files/619915844268326952)](https://discord.gg/Zxbndcm)

A light-weight module that brings `window.fetch` to Node.js

(We are looking for [v2 maintainers and
collaborators](https://github.com/bitinn/node-fetch/issues/567))

[![Backers](./node-fetch%20-%20npm_files/backers.svg)](https://opencollective.com/node-fetch)

-   [Motivation](https://www.npmjs.com/package/node-fetch#motivation)
-   [Features](https://www.npmjs.com/package/node-fetch#features)
-   [Difference from client-side
    fetch](https://www.npmjs.com/package/node-fetch#difference-from-client-side-fetch)
-   [Installation](https://www.npmjs.com/package/node-fetch#installation)
-   [Loading and configuring the
    module](https://www.npmjs.com/package/node-fetch#loading-and-configuring-the-module)
-   [Common
    Usage](https://www.npmjs.com/package/node-fetch#common-usage)
    -   [Plain text or
        HTML](https://www.npmjs.com/package/node-fetch#plain-text-or-html)
    -   [JSON](https://www.npmjs.com/package/node-fetch#json)
    -   [Simple
        Post](https://www.npmjs.com/package/node-fetch#simple-post)
    -   [Post with
        JSON](https://www.npmjs.com/package/node-fetch#post-with-json)
    -   [Post with form
        parameters](https://www.npmjs.com/package/node-fetch#post-with-form-parameters)
    -   [Handling
        exceptions](https://www.npmjs.com/package/node-fetch#handling-exceptions)
    -   [Handling client and server
        errors](https://www.npmjs.com/package/node-fetch#handling-client-and-server-errors)
-   [Advanced
    Usage](https://www.npmjs.com/package/node-fetch#advanced-usage)
    -   [Streams](https://www.npmjs.com/package/node-fetch#streams)
    -   [Buffer](https://www.npmjs.com/package/node-fetch#buffer)
    -   [Accessing Headers and other Meta
        data](https://www.npmjs.com/package/node-fetch#accessing-headers-and-other-meta-data)
    -   [Extract Set-Cookie
        Header](https://www.npmjs.com/package/node-fetch#extract-set-cookie-header)
    -   [Post data using a file
        stream](https://www.npmjs.com/package/node-fetch#post-data-using-a-file-stream)
    -   [Post with form-data (detect
        multipart)](https://www.npmjs.com/package/node-fetch#post-with-form-data-detect-multipart)
    -   [Request cancellation with
        AbortSignal](https://www.npmjs.com/package/node-fetch#request-cancellation-with-abortsignal)
-   [API](https://www.npmjs.com/package/node-fetch#api)
    -   [fetch(url[,
        options])](https://www.npmjs.com/package/node-fetch#fetchurl-options)
    -   [Options](https://www.npmjs.com/package/node-fetch#options)
    -   [Class:
        Request](https://www.npmjs.com/package/node-fetch#class-request)
    -   [Class:
        Response](https://www.npmjs.com/package/node-fetch#class-response)
    -   [Class:
        Headers](https://www.npmjs.com/package/node-fetch#class-headers)
    -   [Interface:
        Body](https://www.npmjs.com/package/node-fetch#interface-body)
    -   [Class:
        FetchError](https://www.npmjs.com/package/node-fetch#class-fetcherror)
-   [License](https://www.npmjs.com/package/node-fetch#license)
-   [Acknowledgement](https://www.npmjs.com/package/node-fetch#acknowledgement)

[](https://www.npmjs.com/package/node-fetch#motivation)

Motivation

Instead of implementing `XMLHttpRequest` in Node.js to run
browser-specific [Fetch polyfill](https://github.com/github/fetch), why
not go from native `http` to `fetch` API directly? Hence, `node-fetch`,
minimal code for a `window.fetch` compatible API on Node.js runtime.

See Matt Andrews'
[isomorphic-fetch](https://github.com/matthew-andrews/isomorphic-fetch)
or Leonardo Quixada's
[cross-fetch](https://github.com/lquixada/cross-fetch) for isomorphic
usage (exports `node-fetch` for server-side, `whatwg-fetch` for
client-side).

[](https://www.npmjs.com/package/node-fetch#features)

Features

-   Stay consistent with `window.fetch` API.
-   Make conscious trade-off when following [WHATWG fetch
    spec](https://fetch.spec.whatwg.org/) and [stream
    spec](https://streams.spec.whatwg.org/) implementation details,
    document known differences.
-   Use native promise but allow substituting it with [insert your
    favorite promise library].
-   Use native Node streams for body on both request and response.
-   Decode content encoding (gzip/deflate) properly and convert string
    output (such as `res.text()` and `res.json()`) to UTF-8
    automatically.
-   Useful extensions such as timeout, redirect limit, response size
    limit, [explicit
    errors](https://github.com/bitinn/node-fetch/blob/HEAD/ERROR-HANDLING.md)
    for troubleshooting.

[](https://www.npmjs.com/package/node-fetch#difference-from-client-side-fetch)

Difference from client-side fetch

-   See [Known
    Differences](https://github.com/bitinn/node-fetch/blob/HEAD/LIMITS.md)
    for details.
-   If you happen to use a missing feature that `window.fetch` offers,
    feel free to open an issue.
-   Pull requests are welcomed too!

[](https://www.npmjs.com/package/node-fetch#installation)

Installation

Current stable release (`2.x`)

``` {.editor .editor-colors}
$ npm install node-fetch
```

[](https://www.npmjs.com/package/node-fetch#loading-and-configuring-the-module)

Loading and configuring the module

We suggest you load the module via `require` until the stabilization of
ES modules in node:

``` {.editor .editor-colors}
const fetch = require('node-fetch');
```

If you are using a Promise library other than native, set it through
`fetch.Promise`:

``` {.editor .editor-colors}
const Bluebird = require('bluebird'); fetch.Promise = Bluebird;
```

[](https://www.npmjs.com/package/node-fetch#common-usage)

Common Usage

NOTE: The documentation below is up-to-date with `2.x` releases; see the
[`1.x` readme](https://github.com/bitinn/node-fetch/blob/1.x/README.md),
[changelog](https://github.com/bitinn/node-fetch/blob/1.x/CHANGELOG.md)
and [2.x upgrade
guide](https://github.com/bitinn/node-fetch/blob/HEAD/UPGRADE-GUIDE.md)
for the differences.

[](https://www.npmjs.com/package/node-fetch#plain-text-or-html)

Plain text or HTML

``` {.editor .editor-colors}
fetch('https://github.com/')    .then(res => res.text())    .then(body => console.log(body));
```

[](https://www.npmjs.com/package/node-fetch#json)

JSON

``` {.editor .editor-colors}
 fetch('https://api.github.com/users/github')    .then(res => res.json())    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#simple-post)

Simple Post

``` {.editor .editor-colors}
fetch('https://httpbin.org/post', { method: 'POST', body: 'a=1' })    .then(res => res.json()) // expecting a json response    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#post-with-json)

Post with JSON

``` {.editor .editor-colors}
const body = { a: 1 }; fetch('https://httpbin.org/post', {        method: 'post',        body:    JSON.stringify(body),        headers: { 'Content-Type': 'application/json' },    })    .then(res => res.json())    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#post-with-form-parameters)

Post with form parameters

`URLSearchParams` is available in Node.js as of v7.5.0. See [official
documentation](https://nodejs.org/api/url.html#url_class_urlsearchparams)
for more usage methods.

NOTE: The `Content-Type` header is only set automatically to
`x-www-form-urlencoded` when an instance of `URLSearchParams` is given
as such:

``` {.editor .editor-colors}
const { URLSearchParams } = require('url'); const params = new URLSearchParams();params.append('a', 1); fetch('https://httpbin.org/post', { method: 'POST', body: params })    .then(res => res.json())    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#handling-exceptions)

Handling exceptions

NOTE: 3xx-5xx responses are *NOT* exceptions and should be handled in
`then()`; see the next section for more information.

Adding a catch to the fetch promise chain will catch *all* exceptions,
such as errors originating from node core libraries, network errors and
operational errors, which are instances of FetchError. See the [error
handling
document](https://github.com/bitinn/node-fetch/blob/HEAD/ERROR-HANDLING.md)
for more details.

``` {.editor .editor-colors}
fetch('https://domain.invalid/')    .catch(err => console.error(err));
```

[](https://www.npmjs.com/package/node-fetch#handling-client-and-server-errors)

Handling client and server errors

It is common to create a helper function to check that the response
contains no client (4xx) or server (5xx) error responses:

``` {.editor .editor-colors}
function checkStatus(res) {    if (res.ok) { // res.status >= 200 && res.status < 300        return res;    } else {        throw MyCustomError(res.statusText);    }} fetch('https://httpbin.org/status/400')    .then(checkStatus)    .then(res => console.log('will not get here...'))
```

[](https://www.npmjs.com/package/node-fetch#advanced-usage)

Advanced Usage

[](https://www.npmjs.com/package/node-fetch#streams)

Streams

The "Node.js way" is to use streams when possible:

``` {.editor .editor-colors}
fetch('https://assets-cdn.github.com/images/modules/logos_page/Octocat.png')    .then(res => {        const dest = fs.createWriteStream('./octocat.png');        res.body.pipe(dest);    });
```

[](https://www.npmjs.com/package/node-fetch#buffer)

Buffer

If you prefer to cache binary data in full, use buffer(). (NOTE:
`buffer()` is a `node-fetch`-only API)

``` {.editor .editor-colors}
const fileType = require('file-type'); fetch('https://assets-cdn.github.com/images/modules/logos_page/Octocat.png')    .then(res => res.buffer())    .then(buffer => fileType(buffer))    .then(type => { /* ... */ });
```

[](https://www.npmjs.com/package/node-fetch#accessing-headers-and-other-meta-data)

Accessing Headers and other Meta data

``` {.editor .editor-colors}
fetch('https://github.com/')    .then(res => {        console.log(res.ok);        console.log(res.status);        console.log(res.statusText);        console.log(res.headers.raw());        console.log(res.headers.get('content-type'));    });
```

[](https://www.npmjs.com/package/node-fetch#extract-set-cookie-header)

Extract Set-Cookie Header

Unlike browsers, you can access raw `Set-Cookie` headers manually using
`Headers.raw()`. This is a `node-fetch` only API.

``` {.editor .editor-colors}
fetch(url).then(res => {    // returns an array of values, instead of a string of comma-separated values    console.log(res.headers.raw()['set-cookie']);});
```

[](https://www.npmjs.com/package/node-fetch#post-data-using-a-file-stream)

Post data using a file stream

``` {.editor .editor-colors}
const { createReadStream } = require('fs'); const stream = createReadStream('input.txt'); fetch('https://httpbin.org/post', { method: 'POST', body: stream })    .then(res => res.json())    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#post-with-form-data-detect-multipart)

Post with form-data (detect multipart)

``` {.editor .editor-colors}
const FormData = require('form-data'); const form = new FormData();form.append('a', 1); fetch('https://httpbin.org/post', { method: 'POST', body: form })    .then(res => res.json())    .then(json => console.log(json)); // OR, using custom headers// NOTE: getHeaders() is non-standard API const form = new FormData();form.append('a', 1); const options = {    method: 'POST',    body: form,    headers: form.getHeaders()} fetch('https://httpbin.org/post', options)    .then(res => res.json())    .then(json => console.log(json));
```

[](https://www.npmjs.com/package/node-fetch#request-cancellation-with-abortsignal)

Request cancellation with AbortSignal

> NOTE: You may cancel streamed requests only on Node \>= v8.0.0

You may cancel requests with `AbortController`. A suggested
implementation is
[`abort-controller`](https://www.npmjs.com/package/abort-controller).

An example of timing out a request after 150ms could be achieved as the
following:

``` {.editor .editor-colors}
import AbortController from 'abort-controller'; const controller = new AbortController();const timeout = setTimeout(  () => { controller.abort(); },  150,); fetch(url, { signal: controller.signal })  .then(res => res.json())  .then(    data => {      useData(data)    },    err => {      if (err.name === 'AbortError') {        // request was aborted      }    },  )  .finally(() => {    clearTimeout(timeout);  });
```

See [test
cases](https://github.com/bitinn/node-fetch/blob/master/test/test.js)
for more examples.

[](https://www.npmjs.com/package/node-fetch#api)

API

[](https://www.npmjs.com/package/node-fetch#fetchurl-options)

fetch(url[, options])

-   `url` A string representing the URL for fetching
-   `options`
    [Options](https://www.npmjs.com/package/node-fetch#fetch-options)
    for the HTTP(S) request
-   Returns: `Promise<Response>`

Perform an HTTP(S) fetch.

`url` should be an absolute url, such as `https://example.com/`. A
path-relative URL (`/file/under/root`) or protocol-relative URL
(`//can-be-http-or-https.com/`) will result in a rejected `Promise`.

[](https://www.npmjs.com/package/node-fetch#options)

Options

The default values are shown after each option key.

``` {.editor .editor-colors}
{    // These properties are part of the Fetch Standard    method: 'GET',    headers: {},        // request headers. format is the identical to that accepted by the Headers constructor (see below)    body: null,         // request body. can be null, a string, a Buffer, a Blob, or a Node.js Readable stream    redirect: 'follow', // set to `manual` to extract redirect headers, `error` to reject redirect    signal: null,       // pass an instance of AbortSignal to optionally abort requests     // The following properties are node-fetch extensions    follow: 20,         // maximum redirect count. 0 to not follow redirect    timeout: 0,         // req/res timeout in ms, it resets on redirect. 0 to disable (OS limit applies). Signal is recommended instead.    compress: true,     // support gzip/deflate content encoding. false to disable    size: 0,            // maximum response body size in bytes. 0 to disable    agent: null         // http(s).Agent instance or function that returns an instance (see below)}
```

[](https://www.npmjs.com/package/node-fetch#default-headers)

Default Headers

If no values are set, the following request headers will be sent
automatically:

  Header                Value
  --------------------- ----------------------------------------------------------
  `Accept-Encoding`     `gzip,deflate` *(when `options.compress === true`)*
  `Accept`              `*/*`
  `Connection`          `close` *(when no `options.agent` is present)*
  `Content-Length`      *(automatically calculated, if possible)*
  `Transfer-Encoding`   `chunked` *(when `req.body` is a stream)*
  `User-Agent`          `node-fetch/1.0 (+https://github.com/bitinn/node-fetch)`

Note: when `body` is a `Stream`, `Content-Length` is not set
automatically.

[](https://www.npmjs.com/package/node-fetch#custom-agent)

Custom Agent

The `agent` option allows you to specify networking related options
which are out of the scope of Fetch, including and not limited to the
following:

-   Support self-signed certificate
-   Use only IPv4 or IPv6
-   Custom DNS Lookup

See
[`http.Agent`](https://nodejs.org/api/http.html#http_new_agent_options)
for more information.

In addition, the `agent` option accepts a function that returns
`http`(s)`.Agent` instance given current
[URL](https://nodejs.org/api/url.html), this is useful during a
redirection chain across HTTP and HTTPS protocol.

``` {.editor .editor-colors}
const httpAgent = new http.Agent({    keepAlive: true});const httpsAgent = new https.Agent({    keepAlive: true}); const options = {    agent: function (_parsedURL) {        if (_parsedURL.protocol == 'http:') {            return httpAgent;        } else {            return httpsAgent;        }    }}
```

[](https://www.npmjs.com/package/node-fetch#class-request)

Class: Request

An HTTP(S) request containing information about URL, method, headers,
and the body. This class implements the
[Body](https://www.npmjs.com/package/node-fetch#iface-body) interface.

Due to the nature of Node.js, the following properties are not
implemented at this moment:

-   `type`
-   `destination`
-   `referrer`
-   `referrerPolicy`
-   `mode`
-   `credentials`
-   `cache`
-   `integrity`
-   `keepalive`

The following node-fetch extension properties are provided:

-   `follow`
-   `compress`
-   `counter`
-   `agent`

See [options](https://www.npmjs.com/package/node-fetch#fetch-options)
for exact meaning of these extensions.

[](https://www.npmjs.com/package/node-fetch#new-requestinput-options)

new Request(input[, options])

*(spec-compliant)*

-   `input` A string representing a URL, or another `Request` (which
    will be cloned)
-   `options` [Options][\#fetch-options] for the HTTP(S) request

Constructs a new `Request` object. The constructor is identical to that
in the
[browser](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request).

In most cases, directly `fetch(url, options)` is simpler than creating a
`Request` object.

[](https://www.npmjs.com/package/node-fetch#class-response)

Class: Response

An HTTP(S) response. This class implements the
[Body](https://www.npmjs.com/package/node-fetch#iface-body) interface.

The following properties are not implemented in node-fetch at this
moment:

-   `Response.error()`
-   `Response.redirect()`
-   `type`
-   `trailer`

[](https://www.npmjs.com/package/node-fetch#new-responsebody-options)

new Response([body[, options]])

*(spec-compliant)*

-   `body` A `String` or [`Readable`
    stream](https://nodejs.org/api/stream.html#stream_readable_streams)
-   `options` A
    [`ResponseInit`](https://fetch.spec.whatwg.org/#responseinit)
    options dictionary

Constructs a new `Response` object. The constructor is identical to that
in the
[browser](https://developer.mozilla.org/en-US/docs/Web/API/Response/Response).

Because Node.js does not implement service workers (for which this class
was designed), one rarely has to construct a `Response` directly.

[](https://www.npmjs.com/package/node-fetch#responseok)

response.ok

*(spec-compliant)*

Convenience property representing if the request ended normally. Will
evaluate to true if the response status was greater than or equal to 200
but smaller than 300.

[](https://www.npmjs.com/package/node-fetch#responseredirected)

response.redirected

*(spec-compliant)*

Convenience property representing if the request has been redirected at
least once. Will evaluate to true if the internal redirect counter is
greater than 0.

[](https://www.npmjs.com/package/node-fetch#class-headers)

Class: Headers

This class allows manipulating and iterating over a set of HTTP headers.
All methods specified in the [Fetch
Standard](https://fetch.spec.whatwg.org/) are implemented.

[](https://www.npmjs.com/package/node-fetch#new-headersinit)

new Headers([init])

*(spec-compliant)*

-   `init` Optional argument to pre-fill the `Headers` object

Construct a new `Headers` object. `init` can be either `null`, a
`Headers` object, an key-value map object or any iterable object.

``` {.editor .editor-colors}
// Example adapted from https://fetch.spec.whatwg.org/#example-headers-class const meta = {  'Content-Type': 'text/xml',  'Breaking-Bad': '<3'};const headers = new Headers(meta); // The above is equivalent toconst meta = [  [ 'Content-Type', 'text/xml' ],  [ 'Breaking-Bad', '<3' ]];const headers = new Headers(meta); // You can in fact use any iterable objects, like a Map or even another Headersconst meta = new Map();meta.set('Content-Type', 'text/xml');meta.set('Breaking-Bad', '<3');const headers = new Headers(meta);const copyOfHeaders = new Headers(headers);
```

[](https://www.npmjs.com/package/node-fetch#interface-body)

Interface: Body

`Body` is an abstract interface with methods that are applicable to both
`Request` and `Response` classes.

The following methods are not yet implemented in node-fetch at this
moment:

-   `formData()`

[](https://www.npmjs.com/package/node-fetch#bodybody)

body.body

*(deviation from spec)*

-   Node.js [`Readable`
    stream](https://nodejs.org/api/stream.html#stream_readable_streams)

Data are encapsulated in the `Body` object. Note that while the [Fetch
Standard](https://fetch.spec.whatwg.org/) requires the property to
always be a WHATWG `ReadableStream`, in node-fetch it is a Node.js
[`Readable`
stream](https://nodejs.org/api/stream.html#stream_readable_streams).

[](https://www.npmjs.com/package/node-fetch#bodybodyused)

body.bodyUsed

*(spec-compliant)*

-   `Boolean`

A boolean property for if this body has been consumed. Per the specs, a
consumed body cannot be used again.

[](https://www.npmjs.com/package/node-fetch#bodyarraybuffer)

body.arrayBuffer()

[](https://www.npmjs.com/package/node-fetch#bodyblob)

body.blob()

[](https://www.npmjs.com/package/node-fetch#bodyjson)

body.json()

[](https://www.npmjs.com/package/node-fetch#bodytext)

body.text()

*(spec-compliant)*

-   Returns: `Promise`

Consume the body and return a promise that will resolve to one of these
formats.

[](https://www.npmjs.com/package/node-fetch#bodybuffer)

body.buffer()

*(node-fetch extension)*

-   Returns: `Promise<Buffer>`

Consume the body and return a promise that will resolve to a Buffer.

[](https://www.npmjs.com/package/node-fetch#bodytextconverted)

body.textConverted()

*(node-fetch extension)*

-   Returns: `Promise<String>`

Identical to `body.text()`, except instead of always converting to
UTF-8, encoding sniffing will be performed and text converted to UTF-8
if possible.

(This API requires an optional dependency of the npm package
[encoding](https://www.npmjs.com/package/encoding), which you need to
install manually. `webpack` users may see [a warning
message](https://github.com/bitinn/node-fetch/issues/412#issuecomment-379007792)
due to this optional dependency.)

[](https://www.npmjs.com/package/node-fetch#class-fetcherror)

Class: FetchError

*(node-fetch extension)*

An operational error in the fetching process. See
[ERROR-HANDLING.md](https://github.com/bitinn/node-fetch/blob/master/ERROR-HANDLING.md)
for more info.

[](https://www.npmjs.com/package/node-fetch#class-aborterror)

Class: AbortError

*(node-fetch extension)*

An Error thrown when the request is aborted in response to an
`AbortSignal`'s `abort` event. It has a `name` property of `AbortError`.
See
[ERROR-HANDLING.MD](https://github.com/bitinn/node-fetch/blob/master/ERROR-HANDLING.md)
for more info.

[](https://www.npmjs.com/package/node-fetch#acknowledgement)

Acknowledgement

Thanks to [github/fetch](https://github.com/github/fetch) for providing
a solid implementation reference.

`node-fetch` v1 was maintained by [@bitinn](https://github.com/bitinn);
v2 was maintained by [@TimothyGu](https://github.com/timothygu),
[@bitinn](https://github.com/bitinn) and
[@jimmywarting](https://github.com/jimmywarting); v2 readme is written
by [@jkantr](https://github.com/jkantr).

[](https://www.npmjs.com/package/node-fetch#license)

License

MIT

Keywords {#user-content-keywords .a0dff0b1 .mt2 .pt2 .mb3 .pb3 .f4 .fw6 .b--black-10}
--------

-   [fetch](https://www.npmjs.com/search?q=keywords:fetch)
-   [http](https://www.npmjs.com/search?q=keywords:http)
-   [promise](https://www.npmjs.com/search?q=keywords:promise)

### Install {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

`npm i node-fetch`{.flex-auto .truncate .db
title="Copy Command to Clipboard"}

Downloads

Weekly Downloads

18,202,437

### Version {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

2.6.1

### License {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

MIT

### Unpacked Size {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

158 kB

### Total Files {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

8

### Issues {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

[59](https://github.com/bitinn/node-fetch/issues)

### Pull Requests {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

[11](https://github.com/bitinn/node-fetch/pulls)

### Homepage {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

[](https://github.com/bitinn/node-fetch)

github.com/bitinn/node-fetch

### Repository {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

[](https://github.com/bitinn/node-fetch)

Git

github.com/bitinn/node-fetch

### Last publish {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

10 days ago

### Collaborators {.c84e15be .f5 .mt2 .pt2 .mb0 .black-50}

-   [![avatar](./node-fetch%20-%20npm_files/39bb5a0f30fc2bcfd5c2b14866a4291b.jpeg "akepinski")](https://www.npmjs.com/~akepinski)
-   [![avatar](./node-fetch%20-%20npm_files/9a8104ac432b50b9f01f0d75be493699.png "bitinn")](https://www.npmjs.com/~bitinn)
-   [![avatar](./node-fetch%20-%20npm_files/02f476ed950384700afba952f6efaa28.jpeg "endless")](https://www.npmjs.com/~endless)
-   [![avatar](./node-fetch%20-%20npm_files/219b77f9d21de75e81851b6b886057c7.jpeg "timothygu")](https://www.npmjs.com/~timothygu)

[](https://runkit.com/npm/node-fetch)

**Try** on RunKit

[](https://www.npmjs.com/advisories/report?package=node-fetch)

**Report** a vulnerability

### Support {._1b8c0a9f}

-   [Help](https://docs.npmjs.com/)
-   [Community](https://npm.community/)
-   [Advisories](https://www.npmjs.com/advisories)
-   [Status](http://status.npmjs.org/)
-   [Contact npm](https://www.npmjs.com/support)

### Company {._1b8c0a9f}

-   [About](https://www.npmjs.com/about)
-   [Blog](https://blog.npmjs.org/)
-   [Press](https://www.npmjs.com/press)

### Terms & Policies {._1b8c0a9f}

-   [Policies](https://www.npmjs.com/policies/)
-   [Terms of Use](https://www.npmjs.com/policies/terms)
-   [Code of Conduct](https://www.npmjs.com/policies/conduct)
-   [Privacy](https://www.npmjs.com/policies/privacy)


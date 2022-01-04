# HTTP Basics

In the late 1980s, a computer scientist named Tim Berners-Lee proposed the
concept of the "WorldWideWeb", laying the foundation for our modern Internet. A
critical part of this concept was _HTTP_, the _Hypertext Transfer Protocol_.

We're going to to dive into what makes HTTP such an important part of Web
browsing and learn how to leverage it in our applications.

We'll cover:

- the vocabulary of the Web,
- how stateless connections work,
- and HTTP request & response types.

## First, some context

> "If you want to build a ship, don’t drum up the men and women to gather wood,
>divide the work, and give orders. Instead, teach them to yearn for the vast and
>endless sea."
>
>-- _Antoine de Saint-Exupéry (paraphrased)_

So far, you've written code that runs in isolation on your own system. Now it's
time to set sail into the "vast and endless" Internet! Before we can do so, we
need to review the fundamentals: what makes the Web a "web"?

We're going to share a lot of vocabulary here, and it may be a little dry at
times, but remember that these are the principles upon which the rest of your
journey will be built! You'll find these concepts missing from most programming
tutorials, so you'll be ahead of the game if you lay a strong foundation now.

## Breaking it down...

Like many disciplines, computer science is built around a shared vocabulary.
Let's demystify the acronym "HTTP" to understand it better.

### **HT-**: HyperText

_Hypertext_ is simply "content with references to other content". This term is
used specifically to refer to content in computing, and may include text,
images, video, or any other digital content. If "hypertext" sounds familiar,
that's because you've heard it before: _HTML_ stands for "**H**yper**T**ext
**M**arkup **L**anguage".

Hypertext is what makes the Web a "web", and it's the most fundamental part of
how we interact online. We refer to references between hypertext resources as
_hyperlinks_, though you're probably used to hearing them referred to as
_links_. Without links, the Internet would resemble a massive collection of
separate books: each blog, news report, and social media site would exist in
total isolation from each other. The ability to link these pages is what makes
the kind of interactivity you're learning to build possible, and it was a
revolutionary concept when it was introduced!

### **-TP**: Transfer Protocol

A _protocol_ in computer science is a set of guidelines surrounding the
transmission of data. Protocols define the process of exchanging data, but don't
define exactly what that data must be. Think of it like a multi-course meal: we
expect the appetizer, then the entree, then the dessert, but we could have any
type of food for each of those courses! As long as the plates arrive in the
particular order we expect, protocol is being followed.

HTTP acts as a _transfer protocol_. It defines the expectations for both ends of
the transfer, and it defines some ways the transfer might fail. More
specifically, HTTP is defined as a _request/response_ protocol. An HTTP exchange
is more like a series of distinct questions & answers than a conversation
between two systems.

## ...and bringing it back together

HTTP defines the process of exchanging hypertext between systems. Specifically,
HTTP works between _clients_ and _servers_. A _client_ (sometimes called the
_user agent_) is the data consumer. This is usually your web browser. A _server_
(sometimes referred to as the _origin_) is the data provider, often where an
application is running. In a typical HTTP exchange, the client sends a _request_
to the server for a particular _resource_: a webpage, image, or application
data. The server provides a _response_ containing either the resource that the
client requested or an explanation of why it can't provide the resource.

Here's a high-level overview of the exchange:

![HTTP Exchange](https://assets.aaonline.io/Module-Web/http/image-http-exchange.svg)

We'll look more closely at the _request_ and _response_ in separate lessons.

## Properties of HTTP

There are a few important properties of HTTP that we need to understand in order
to use it effectively.

### Reliable connections

Let's consider the example of two friends passing a note. If the note contains
important information, the sender will want to make sure that it gets to its
destination. They'll likely take a little extra time to deliver it carefully,
and they'll expect confirmation once it's been received. In computing, we'd
refer to this as a _reliable connection_: messages passed between a client &
server sacrifice a little speed for the sake of trust, and we can rest assured
that each message will be confirmed.

HTTP doesn't work well if messages aren't received in the correct order, so it's
critical that the connection your hypertext is crossing is reliable! Tim
Berners-Lee chose _TCP_, another transmission protocol, as HTTP's preferred
connection type. We'll discuss TCP in greater detail when we get into network
models in a future lesson.

### Stateless transfer

HTTP is considered a _stateless_ protocol, meaning it doesn't store any
information. Each request you send across an HTTP connection should contain all
its own context. This is unlike a _stateful_ protocol, that might include
specifications for storing data between requests.

This can be nice because we only ever need to read a single HTTP request to
understand its intent, but it can cause headaches when it comes to things like
maintaining your login status or the contents of your shopping cart!

To help us with this, HTTP supports _cookies_, bits of data that a client sends
in with their request. The server can examine this data and look up a _session_
for your account, or it can act on the info in the cookie directly. Note that
neither the cookie nor the session are part of HTTP. They're just workarounds
we've created due to the protocol's stateless nature.

### Intermediaries

The Web is a big place, and it's unlikely that your request will go directly to
its destination! Instead, it will pass through a series of _intermediaries_:
other servers or devices that pass your request along. These intermediaries come
in three types:

- _proxies_, which may modify your request so it appears to come from a
  different source,
- _gateways_, which pretend to be the resource server you requested,
- and _tunnels_, which simply pass your request along.

Here's an idea of how these intermediaries might be laid out:

<p>
  <img src="https://assets.aaonline.io/Module-Web/http/image-http-proxy-tunnel-gateway.svg" style="width: 100%; height: auto;">
</p>

Notice that these are interchangeable depending on the flow of data. When the
response is sent back, "Their Router" is acting as a proxy and "Your Router" is
acting as a gateway! This is an important part of HTTP: a single server may act
as any of the intermediary types, depending on the needs of the HTTP message
it's transmitting.

We'll discuss some of these intermediaries more in later lessons. For now, the
takeaway is that HTTP isn't limited to your browser & application server. Lots
of devices support HTTP in their own special way.

## Digging deeper with the HTTP spec

We're just scratching the surface of how HTTP works. If you're interested in
learning more, you can go straight to the source: [the HTTP spec][1]. A _spec_
(short for _specification_) describes a protocol in great detail. It's the
document generated by an idea's founders, and it's reviewed and carefully edited
before being adopted by the [IETF][2] (_Internet Engineering Task Force_).

Specs are intended to be exhaustive, so they can be overwhelming at first! This
is definitely not light reading but any question you have about a particular
protocol can likely be answered from its spec.

## What we've learned

Whew, that's a lot of jargon! Hopefully the fundamental aspects of HTTP are
clearer to you now. Next up, we'll look at an HTTP request & response, and we'll
cover how to generate each.

After completing this lesson, you should have a clear understanding of:

- HTTP's origin & purpose,
- special properties of HTTP,
- and how to learn more from the HTTP spec.

[1]: https://tools.ietf.org/html/rfc2616#section-1.4
[2]: https://www.ietf.org/

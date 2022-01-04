- [Skip to main
  content](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#content)
- [Select
  language](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#language)
- [Skip to
  search](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#main-q)

[](https://developer.mozilla.org/en-US/)

- Technologies
  - [Technologies
    Overview](https://developer.mozilla.org/en-US/docs/Web)
  - [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
  - [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
  - [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  - [Graphics](https://developer.mozilla.org/en-US/docs/Web/Guide/Graphics)
  - [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
  - [APIs / DOM](https://developer.mozilla.org/en-US/docs/Web/API)
  - [Browser
    Extensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions)
  - [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML)
- References & Guides
  - [Learn web
    development](https://developer.mozilla.org/en-US/docs/Learn)
  - [Tutorials](https://developer.mozilla.org/en-US/docs/Web/Tutorials)
  - [References](https://developer.mozilla.org/en-US/docs/Web/Reference)
  - [Developer
    Guides](https://developer.mozilla.org/en-US/docs/Web/Guide)
  - [Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
  - [Game
    development](https://developer.mozilla.org/en-US/docs/Games)
  - [...more docs](https://developer.mozilla.org/en-US/docs/Web)
- Feedback
  - [Send
    Feedback](https://developer.mozilla.org/en-US/docs/MDN/Feedback)
  - [Get Firefox help 🌐](https://support.mozilla.org/)
  - [Get web development help 🌐](https://stackoverflow.com/)
  - [Join the MDN
    community](https://developer.mozilla.org/en-US/docs/MDN/Community)
  - [Report a content problem
    🌐](https://github.com/mdn/sprints/issues/new?template=issue-template.md&projects=mdn/sprints/2&labels=user-report&title=https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
  - [Report an issue
    🌐](https://github.com/mdn/kuma/issues/new/choose)

Search MDN

Open search

[Sign
in](https://developer.mozilla.org/en-US/users/account/signup-landing?next=/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

1.  [See Web technology for
    developers](https://developer.mozilla.org/en-US/docs/Web)
2.  [See JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
3.  [See JavaScript
    reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
4.  [See Statements and
    declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
5.  [for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

English▼

- [Català](https://developer.mozilla.org/ca/docs/Web/JavaScript/Referencia/Sentencies/for...of "Catalan")
- [Deutsch](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/for...of "German")
- [Español](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Sentencias/for...of "Spanish")
- [Français](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/for...of "French")
- [עברית](https://developer.mozilla.org/he/docs/Web/JavaScript/Reference/Statements/for...of "Hebrew")
- [Italiano](https://developer.mozilla.org/it/docs/Web/JavaScript/Reference/Statements/for...of "Italian")
- [日本語](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Statements/for...of "Japanese")
- [한국어](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/for...of "Korean")
- [Português
  (do Brasil)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for...of "Portuguese (Brazilian)")
- [Русский](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Statements/for...of "Russian")
- [Українська](https://developer.mozilla.org/uk/docs/Web/JavaScript/Reference/Statements/for...of "Ukrainian")
- [Tiếng
  Việt](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Statements/for...of "Vietnamese")
- [中文
  (简体)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of "Chinese (Simplified)")
- [Add a
  translation](https://wiki.developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of$locales)

## On this Page

Jump to section

- [Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#Syntax)
- [Examples](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#Examples)
- [Specifications](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#Specifications)
- [Browser
  compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#Browser_compatibility)
- [See
  also](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#See_also)
- [Related
  topics](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#sidebar-quicklinks)

The **`for...of` statement** creates a loop iterating over [iterable
objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#The_iterable_protocol),
including: built-in
[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String),
[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array),
array-like objects (e.g.,
[`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
or [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)),
[`TypedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray),
[`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map),
[`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set),
and user-defined iterables. It invokes a custom iteration hook with
statements to be executed for the value of each distinct property of the
object.

The source for this interactive example is stored in a GitHub
repository. If you'd like to contribute to the interactive examples
project, please clone
[https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)
and send us a pull request.

## Syntax {#Syntax}

```{.syntaxbox .notranslate}
for (variable of iterable) {
  statement
}
```

`variable`
: On each iteration a value of a different property is assigned to
`variable`. `variable` may be declared with `const`, `let`, or
`var`.
`iterable`
: Object whose iterable properties are iterated.

## Examples {#Examples}

### Iterating over an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) {#Iterating_over_an_Array}

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = [10, 20, 30];

for (const value of iterable) {
  console.log(value);
}
// 10
// 20
// 30
```

You can use
[`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
instead of
[`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
too, if you reassign the variable inside the block.

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = [10, 20, 30];

for (let value of iterable) {
  value += 1;
  console.log(value);
}
// 11
// 21
// 31
```

### Iterating over a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) {#Iterating_over_a_String}

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = 'boo';

for (const value of iterable) {
  console.log(value);
}
// "b"
// "o"
// "o"
```

### Iterating over a [`TypedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray) {#Iterating_over_a_TypedArray}

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = new Uint8Array([0x00, 0xff]);

for (const value of iterable) {
  console.log(value);
}
// 0
// 255
```

### Iterating over a [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) {#Iterating_over_a_Map}

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = new Map([['a', 1], ['b', 2], ['c', 3]]);

for (const entry of iterable) {
  console.log(entry);
}
// ['a', 1]
// ['b', 2]
// ['c', 3]

for (const [key, value] of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```

### Iterating over a [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) {#Iterating_over_a_Set}

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = new Set([1, 1, 2, 2, 3, 3]);

for (const value of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```

### Iterating over the arguments object {#Iterating_over_the_arguments_object}

You can iterate over the
[`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
object to examine all of the parameters passed into a JavaScript
function:

```{.brush: .js .notranslate .line-numbers .language-js}
(function() {
  for (const argument of arguments) {
    console.log(argument);
  }
})(1, 2, 3);

// 1
// 2
// 3
```

### Iterating over a DOM collection {#Iterating_over_a_DOM_collection}

Iterating over DOM collections like
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList "NodeList objects are collections of nodes, usually returned by properties such as Node.childNodes and methods such as document.querySelectorAll()."):
the following example adds a `read` class to paragraphs that are direct
descendants of an article:

```{.brush:js .notranslate .line-numbers .language-js}
// Note: This will only work in platforms that have
// implemented NodeList.prototype[Symbol.iterator]
const articleParagraphs = document.querySelectorAll('article > p');

for (const paragraph of articleParagraphs) {
  paragraph.classList.add('read');
}
```

### Closing iterators {#Closing_iterators}

In `for...of` loops, abrupt iteration termination can be caused by
`break`, `throw` or `return`. In these cases, the iterator is closed.

```{.brush: .js .notranslate .line-numbers .language-js}
function* foo(){
  yield 1;
  yield 2;
  yield 3;
};

for (const o of foo()) {
  console.log(o);
  break; // closes iterator, execution continues outside of the loop
}
console.log('done');
```

### Iterating over generators {#Iterating_over_generators}

You can also iterate over
[generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*),
i.e. functions generating an iterable object:

```{.brush:js .notranslate .line-numbers .language-js}
function* fibonacci() { // a generator function
  let [prev, curr] = [0, 1];
  while (true) {
    [prev, curr] = [curr, prev + curr];
    yield curr;
  }
}

for (const n of fibonacci()) {
  console.log(n);
  // truncate the sequence at 1000
  if (n >= 1000) {
    break;
  }
}
```

#### Do not reuse generators {#Do_not_reuse_generators}

Generators should not be re-used, even if the `for...of` loop is
terminated early, for example via the
[`break`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break)
keyword. Upon exiting a loop, the generator is closed and trying to
iterate over it again does not yield any further results.

```{.brush: .js .example-bad .notranslate .line-numbers .language-js}
const gen = (function *(){
  yield 1;
  yield 2;
  yield 3;
})();
for (const o of gen) {
  console.log(o);
  break;  // Closes iterator
}

// The generator should not be re-used, the following does not make sense!
for (const o of gen) {
  console.log(o); // Never called.
}
```

### Iterating over other iterable objects {#Iterating_over_other_iterable_objects}

You can also iterate over an object that explicitly implements
the [iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#iterable)
protocol:

```{.brush:js .notranslate .line-numbers .language-js}
const iterable = {
  [Symbol.iterator]() {
    return {
      i: 0,
      next() {
        if (this.i < 3) {
          return { value: this.i++, done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

for (const value of iterable) {
  console.log(value);
}
// 0
// 1
// 2
```

### Difference between `for...of` and `for...in` {#Difference_between_for...of_and_for...in}

Both `for...in` and `for...of` statements iterate over something. The
main difference between them is in what they iterate over.

The
[`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
statement iterates over the [enumerable
properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
of an object, in an arbitrary order.

The `for...of` statement iterates over values that the [iterable
object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterables)
defines to be iterated over.

The following example shows the difference between a `for...of` loop and
a `for...in` loop when used with an
[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

```{.brush:js .notranslate .line-numbers .language-js}
Object.prototype.objCustom = function() {};
Array.prototype.arrCustom = function() {};

const iterable = [3, 5, 7];
iterable.foo = 'hello';

for (const i in iterable) {
  console.log(i); // logs 0, 1, 2, "foo", "arrCustom", "objCustom"
}

for (const i in iterable) {
  if (iterable.hasOwnProperty(i)) {
    console.log(i); // logs 0, 1, 2, "foo"
  }
}

for (const i of iterable) {
  console.log(i); // logs 3, 5, 7
}
```

Let us look into the above code step by step.

```{.brush: .js .notranslate .line-numbers .language-js}
Object.prototype.objCustom = function() {};
Array.prototype.arrCustom = function() {};

const iterable = [3, 5, 7];
iterable.foo = 'hello';
```

Every object will inherit the `objCustom` property and every object that
is an
[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
will inherit the `arrCustom` property since these properties have been
added to
[`Object.prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype)
and `Array.prototype`, respectively. The object `iterable` inherits the
properties `objCustom` and `arrCustom` because of [inheritance and the
prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

```{.brush: .js .notranslate .line-numbers .language-js}
for (const i in iterable) {
  console.log(i); // logs 0, 1, 2, "foo", "arrCustom", "objCustom"
}
```

This loop logs only [enumerable
properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
of the `iterable` object, in arbitrary order. It doesn't log array
**elements** `3`, `5`, `7` or `hello` because those are **not**
enumerable properties, in fact they are not properties at all, they are
**values**. It logs array **indexes** as well as `arrCustom` and
`objCustom`, which are. If you're not sure why these properties are
iterated over, there's a more thorough explanation of how
[`array iteration and for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in#Array_iteration_and_for...in)
work.

```{.brush: .js .notranslate .line-numbers .language-js}
for (const i in iterable) {
  if (iterable.hasOwnProperty(i)) {
    console.log(i); // logs 0, 1, 2, "foo"
  }
}
```

This loop is similar to the first one, but it uses
[`hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
to check if the found enumerable property is the object's own, i.e. not
inherited. If it is, the property is logged. Properties `0`, `1`, `2`
and `foo` are logged because they are own properties (**not
inherited**). Properties `arrCustom` and `objCustom` are not logged
because they **are inherited**.

```{.brush: .js .notranslate .line-numbers .language-js}
for (const i of iterable) {
  console.log(i); // logs 3, 5, 7
}
```

This loop iterates and logs **values** that `iterable`, as an [iterable
object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterables),
defines to be iterated over. The object's **elements** `3`, `5`, `7` are
shown, but none of the object's **properties**.

## Specifications {#Specifications}

---

Specification

---

[ECMAScript (ECMA-262)\
 The definition of 'for...of statement' in that specification.](https://tc39.es/ecma262/#sec-for-in-and-for-of-statements)

---

## Browser compatibility {#Browser_compatibility}

The compatibility table on this page is generated from structured data.
If you'd like to contribute to the data, please check out
[https://github.com/mdn/browser-compat-data](https://github.com/mdn/browser-compat-data)
and send us a pull request.

[Update compatibility data on
GitHub](https://github.com/mdn/browser-compat-data)

Desktop

Mobile

Server

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

Android webview

Chrome for Android

Firefox for Android

Opera for Android

Safari on iOS

Samsung Internet

Node.js

`for...of`

Chrome Full support 38

Edge Full support 12

Firefox Full support 13

Notes\*\*

Open\*\*

Full support 13

Notes\*\*

Notes\*\* Prior to Firefox 51, using the `for...of` loop construct with
the `const` keyword threw a `SyntaxError` ("missing = in const
declaration").

IE No support No

Opera Full support 25

Safari Full support 7

WebView Android Full support 38

Chrome Android Full support 38

Firefox Android Full support 14

Notes\*\*

Open\*\*

Full support 14

Notes\*\*

Notes\*\* Prior to Firefox 51, using the `for...of` loop construct with
the `const` keyword threw a `SyntaxError` ("missing = in const
declaration").

Opera Android Full support 25

Safari iOS Full support 7

Samsung Internet Android Full support 3.0

nodejs Full support 0.12

async iterators

Chrome Full support 63

Edge Full support 12

Firefox Full support 57

IE No support No

Opera Full support 50

Safari Full support 7

WebView Android Full support 63

Chrome Android Full support 63

Firefox Android Full support 57

Opera Android Full support 46

Safari iOS Full support 7

Samsung Internet Android Full support 8.0

nodejs Full support 10.0.0

Closing iterators

Chrome Full support 51

Edge Full support 14

Firefox Full support 53

IE No support No

Opera Full support 38

Safari Full support 7

WebView Android Full support 51

Chrome Android Full support 51

Firefox Android Full support 53

Opera Android Full support 41

Safari iOS Full support 7

Samsung Internet Android Full support 5.0

nodejs Full support 6.5.0

## Thank you! {.complete-left-block-header}

### Report sent {.right-block-header}

#### What happens next?

Our team will review your report. Once we verify the information you
have supplied we will update this browser compatability table
accordingly.

#### Can I keep track of my report?

You can join the GitHub repository to see updates and commits for this
table data:

[https://github.com/mdn/browser-compat-data](https://github.com/mdn/browser-compat-data)

Finish

## Tell us what’s wrong with this table {.left-block-header}

Our goal is to provide accurate, real values for all our compatibility
data tables. Notifying MDN of inaccurate data or supplying new data
pushes us further towards our goal of providing 100% real values to the
developer community.\
Thank you for helping.

### {.highlight-spanned}

1Which browsers are affected?

Please select the browser or browsers which are affected.

![Chrome](./for...of%20-%20JavaScript%20_%20MDN_files/chrome.b49946f7739f.svg)

Chrome

![Edge](./for...of%20-%20JavaScript%20_%20MDN_files/edge.17e0c684cea1.svg)

Edge

![Firefox](./for...of%20-%20JavaScript%20_%20MDN_files/firefox.1c9f202ae696.svg)

Firefox

![Internet
Explorer](./for...of%20-%20JavaScript%20_%20MDN_files/internet-explorer.4bb2b5f99e82.svg)

Internet Explorer

![Opera](./for...of%20-%20JavaScript%20_%20MDN_files/opera.da441711d2f6.svg)

Opera

![Safari](./for...of%20-%20JavaScript%20_%20MDN_files/safari.aca6ae03b671.svg)

Safari

![Android
webview](./for...of%20-%20JavaScript%20_%20MDN_files/android.201ce5d041f7.svg)

Android webview

![Chrome for
Android](./for...of%20-%20JavaScript%20_%20MDN_files/chrome.b49946f7739f.svg)

Chrome for Android

![Firefox for
Android](./for...of%20-%20JavaScript%20_%20MDN_files/firefox.1c9f202ae696.svg)

Firefox for Android

![Opera for
Android](./for...of%20-%20JavaScript%20_%20MDN_files/opera.da441711d2f6.svg)

Opera for Android

![Safari on
iOS](./for...of%20-%20JavaScript%20_%20MDN_files/safari.aca6ae03b671.svg)

Safari on iOS

![Samsung
Internet](./for...of%20-%20JavaScript%20_%20MDN_files/samsung-internet.8faa2ee1b8a1.svg)

Samsung Internet

![Node.js](./for...of%20-%20JavaScript%20_%20MDN_files/nodejs.33dfe169dc5c.svg)

Node.js

2Which table row is affected?

for...ofasync iteratorsClosing iterators

Next step (2 of 2)

3Can you provide a brief explanation?

Briefly outline the issue you are highlighting. Minimum 10 and maximum
1,000 characters.

4Do you have any supporting material?

Optional

Browser documentation and release notes are good supporting items to
accompany your message. A demo hosted on services like Codepen or JSBin
are perfect for providing real examples of your findings.

Connection error:Sorry, we can’t seem to reach the server. We are
working to fix the problem. Please try again later.

Send report

Previous step

---

[What are we
missing?](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of#)

### Legend {#Legend .offscreen}

Full support  
: Full support
No support  
: No support
See implementation notes.\*\*
: See implementation notes.

## See also {#See_also}

- [`Array.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- [`Map.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach)
- [`Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)
  – Useful when using **`for...of`** over an object.

#### Metadata

- **Last modified:** Apr 20, 2020, [by MDN
  contributors](https://wiki.developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of$history)

Related Topics

1.  [**_JavaScript_**](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
2.  [**Tutorials:**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Tutorials)
3.  Complete beginners

    1.  [JavaScript
        basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
    2.  [JavaScript first
        steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)
    3.  [JavaScript building
        blocks](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks)
    4.  [Introducing JavaScript
        objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)

4.  JavaScript Guide

    1.  [Introduction](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Introduction)
    2.  [Grammar and
        types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types)
    3.  [Control flow and error
        handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
    4.  [Loops and
        iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
    5.  [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    6.  [Expressions and
        operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
    7.  [Numbers and
        dates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Numbers_and_dates)
    8.  [Text
        formatting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Text_formatting)
    9.  [Regular
        expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
    10. [Indexed
        collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    11. [Keyed
        collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections)
    12. [Working with
        objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
    13. [Details of the object
        model](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model)
    14. [Using
        promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
    15. [Iterators and
        generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    16. [Meta
        programming](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Meta_programming)
    17. [JavaScript
        modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)

5.  Intermediate

    1.  [Client-side JavaScript
        frameworks](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks)
    2.  [Client-side web
        APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs)
    3.  [A re-introduction to
        JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
    4.  [JavaScript data
        structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
    5.  [Equality comparisons and
        sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
    6.  [Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

6.  Advanced

    1.  [Inheritance and the prototype
        chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
    2.  [Strict
        mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
    3.  [JavaScript typed
        arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
    4.  [Memory
        Management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)
    5.  [Concurrency model and Event
        Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)

7.  **[References:](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)**
8.  Built-in objects

    1.  \*\*[AggregateError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError "The AggregateError object represents an error when several errors need to be wrapped in a single error. It is thrown when multiple errors need to be reported by an operation, for example by Promise.any(), when all promises passed to it reject.")
    2.  [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array "The JavaScript Array class is a global object that is used in the construction of arrays; which are high-level, list-like objects.")
    3.  [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer "The ArrayBuffer object is used to represent a generic, fixed-length raw binary data buffer.")
    4.  [AsyncFunction](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction "The AsyncFunction constructor creates a new async function object. In JavaScript, every asynchronous function is actually an AsyncFunction object.")
    5.  [Atomics](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics "The Atomics object provides atomic operations as static methods. They are used with SharedArrayBuffer and ArrayBuffer objects.")
    6.  [BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt "BigInt is a built-in object that provides a way to represent whole numbers larger than 253 - 1, which is the largest number JavaScript can reliably represent with the Number primitive and represented by the Number.MAX_SAFE_INTEGER constant. BigInt can be used for arbitrarily large integers.")
    7.  [BigInt64Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt64Array "The BigInt64Array typed array represents an array of 64-bit signed integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0n. Once established, you can reference elements in the array using the object's methods, or by using standard array index syntax (that is, using bracket notation).")
    8.  [BigUint64Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigUint64Array "The BigUint64Array typed array represents an array of 64-bit unsigned integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0n. Once established, you can reference elements in the array using the object's methods, or by using standard array index syntax (that is, using bracket notation).")
    9.  [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean "The Boolean object is an object wrapper for a boolean value.")
    10. [DataView](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView "The DataView view provides a low-level interface for reading and writing multiple number types in a binary ArrayBuffer, without having to care about the platform's endianness.")
    11. [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date "JavaScript Date objects represent a single moment in time in a platform-independent format.")
    12. [Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error "Error objects are thrown when runtime errors occur. The Error object can also be used as a base object for user-defined exceptions. See below for standard built-in error types.")
    13. [EvalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError "The EvalError object indicates an error regarding the global eval() function. This exception is not thrown by JavaScript anymore, however the EvalError object remains for compatibility.")
    14. [FinalizationRegistry](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry "A FinalizationRegistry object lets you request a callback when an object is garbage-collected.")
    15. [Float32Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array "The Float32Array typed array represents an array of 32-bit floating point numbers (corresponding to the C float data type) in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    16. [Float64Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float64Array "The Float64Array typed array represents an array of 64-bit floating point numbers (corresponding to the C double data type) in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    17. [Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function "Every JavaScript function is actually a Function object. This can be seen with the code (function(){}).constructor === Function, which returns true.")
    18. [Generator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator "The Generator object is returned by a generator function and it conforms to both the iterable protocol and the iterator protocol.")
    19. [GeneratorFunction](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction "The GeneratorFunction constructor creates a new generator function object. In JavaScript, every generator function is actually a GeneratorFunction object.")
    20. [Infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity "The global property Infinity is a numeric value representing infinity.")
    21. [Int16Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int16Array "The Int16Array typed array represents an array of twos-complement 16-bit signed integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    22. [Int32Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "The Int32Array typed array represents an array of twos-complement 32-bit signed integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    23. [Int8Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int8Array "The Int8Array typed array represents an array of twos-complement 8-bit signed integers. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    24. [InternalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError "The InternalError object indicates an error that occurred internally in the JavaScript engine.")
    25. [Intl](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl "The Intl object is the namespace for the ECMAScript Internationalization API, which provides language sensitive string comparison, number formatting, and date and time formatting. The Intl object provides access to several constructors as well as functionality common to the internationalization constructors and other language sensitive functions.")
    26. [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON "The JSON object contains methods for parsing JavaScript Object Notation (JSON) and converting values to JSON. It can't be called or constructed, and aside from its two method properties, it has no interesting functionality of its own.")
    27. [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map "The Map object holds key-value pairs and remembers the original insertion order of the keys.")
    28. [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math "Math is a built-in object that has properties and methods for mathematical constants and functions. It’s not a function object.")
    29. [NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN "The global NaN property is a value representing Not-A-Number.")
    30. [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number "The Number constructor contains constants and methods for working with numbers. Values of other types can be converted to numbers using the Number() function.")
    31. [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object "The Object class represents one of JavaScript's data types. It is used to store various keyed collections and more complex entities. Objects can be created using the Object() constructor or the object initializer / literal syntax.")
    32. [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.")
    33. [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy "The Proxy object enables you to create a proxy for another object, which can intercept and redefine fundamental operations for that object.")
    34. [RangeError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError "The RangeError object indicates an error when a value is not in the set or range of allowed values.")
    35. [ReferenceError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError "The ReferenceError object represents an error when a non-existent variable is referenced.")
    36. [Reflect](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect "Reflect is a built-in object that provides methods for interceptable JavaScript operations. The methods are the same as those of proxy handlers. Reflect is not a function object, so it's not constructible.")
    37. [RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp "The RegExp object is used for matching text with a pattern.")
    38. [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set "The Set object lets you store unique values of any type, whether primitive values or object references.")
    39. [SharedArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer "The SharedArrayBuffer object is used to represent a generic, fixed-length raw binary data buffer, similar to the ArrayBuffer object, but in a way that they can be used to create views on shared memory. Unlike an ArrayBuffer, a SharedArrayBuffer cannot become detached.")
    40. [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String "The String object is used to represent and manipulate a sequence of characters.")
    41. [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol "The data type symbol is a primitive data type. The Symbol() function returns a value of type symbol, has static properties that expose several members of built-in objects, has static methods that expose the global symbol registry, and resembles a built-in object class, but is incomplete as a constructor because it does not support the syntax "new Symbol()".")
    42. [SyntaxError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError "The SyntaxError object represents an error when trying to interpret syntactically invalid code. It is thrown when the JavaScript engine encounters tokens or token order that does not conform to the syntax of the language when parsing code.")
    43. [TypeError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError "The TypeError object represents an error when an operation could not be performed, typically (but not exclusively) when a value is not of the expected type.")
    44. [TypedArray](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray "A TypedArray object describes an array-like view of an underlying binary data buffer. There is no global property named TypedArray, nor is there a directly visible TypedArray constructor.  Instead, there are a number of different global properties, whose values are typed array constructors for specific element types, listed below. On the following pages you will find common properties and methods that can be used with any typed array containing elements of any type.")
    45. [URIError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/URIError "The URIError object represents an error when a global URI handling function was used in a wrong way.")
    46. [Uint16Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array "The Uint16Array typed array represents an array of 16-bit unsigned integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    47. [Uint32Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array "The Uint32Array typed array represents an array of 32-bit unsigned integers in the platform byte order. If control over byte order is needed, use DataView instead. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    48. [Uint8Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array "The Uint8Array typed array represents an array of 8-bit unsigned integers. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    49. [Uint8ClampedArray](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray "The Uint8ClampedArray typed array represents an array of 8-bit unsigned integers clamped to 0-255; if you specified a value that is out of the range of [0,255], 0 or 255 will be set instead; if you specify a non-integer, the nearest integer will be set. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).")
    50. [WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap "The WeakMap object is a collection of key/value pairs in which the keys are weakly referenced. The keys must be objects and the values can be arbitrary values.")
    51. [WeakRef](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakRef "A WeakRef object lets you hold a weak reference to another object, without preventing that object from getting garbage-collected.")
    52. [WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet "The WeakSet object lets you store weakly held objects in a collection.")
    53. [WebAssembly](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly "The WebAssembly JavaScript object acts as the namespace for all WebAssembly-related functionality.")
    54. [decodeURI()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURI "The decodeURI() function decodes a Uniform Resource Identifier (URI) previously created by encodeURI() or by a similar routine.")
    55. [decodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent "The decodeURIComponent() function decodes a Uniform Resource Identifier (URI) component previously created by encodeURIComponent or by a similar routine.")
    56. [encodeURI()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI "The encodeURI() function encodes a URI by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).")
    57. [encodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent "The encodeURIComponent() function encodes a URI by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).")
    58. \*\*[escape()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape "The escape() function computes a new string in which certain characters have been replaced by a hexadecimal escape sequence.")
    59. [eval()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval "The eval() function evaluates JavaScript code represented as a string.")
    60. [globalThis](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis "The global globalThis property contains the global this value, which is akin to the global object.")
    61. [isFinite()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite "The global isFinite() function determines whether the passed value is a finite number. If  needed, the parameter is first converted to a number.")
    62. [isNaN()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN "The isNaN() function determines whether a value is NaN or not. Note, coercion inside the isNaN function has interesting rules; you may alternatively want to use Number.isNaN(), as defined in ECMAScript 2015.")
    63. [null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null "The value null represents the intentional absence of any object value. It is one of JavaScript's primitive values and is treated as falsy for boolean operations.")
    64. [parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat "The parseFloat() function parses an argument (converting it to a string first if needed) and returns a floating point number.")
    65. [parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt "The parseInt() function parses a string argument and returns an integer of the specified radix (the base in mathematical numeral systems).")
    66. [undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined "The global undefined property represents the primitive value <undefined. It is one of JavaScript's primitive types.")
    67. \*\*[unescape()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape "The unescape() function computes a new string in which hexadecimal escape sequences are replaced with the character that it represents. The escape sequences might be introduced by a function like escape. Usually, decodeURI or decodeURIComponent are preferred over unescape.")
    68. \*\*[uneval()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/uneval "The uneval() function creates a string representation of the source code of an Object.")

9.  Expressions & operators

    1.  [Addition
        (+)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition "The addition operator (+) produces the sum of numeric operands or string concatenation.")
    2.  [Addition assignment
        (+=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition_assignment "The addition assignment operator (+=) adds the value of the right operand to a variable and assigns the result to the variable. The types of the two operands determine the behavior of the addition assignment operator. Addition or concatenation is possible.")
    3.  [Assignment
        (=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment "The simple assignment operator (=) is used to assign a value to a variable. The assignment operation evaluates to the assigned value. Chaining the assignment operator is possible in order to assign a single value to multiple variables")
    4.  [Bitwise AND
        (&)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_AND "The bitwise AND operator (&) returns a 1 in each bit position for which the corresponding bits of both operands are 1s.")
    5.  [Bitwise AND assignment
        (&=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_AND_assignment "The bitwise AND assignment operator (&=) uses the binary representation of both operands, does a bitwise AND operation on them and assigns the result to the variable.")
    6.  [Bitwise NOT
        (\~)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_NOT "The bitwise NOT operator (~) inverts the bits of its operand.")
    7.  [Bitwise OR
        (|)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR "The bitwise OR operator (|) returns a 1 in each bit position for which the corresponding bits of either or both operands are 1s.")
    8.  [Bitwise OR assignment
        (|=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR_assignment "The bitwise OR assignment operator (|=) uses the binary representation of both operands, does a bitwise OR operation on them and assigns the result to the variable.")
    9.  [Bitwise XOR
        (\^)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR "The bitwise XOR operator (^) returns a 1 in each bit position for which the corresponding bits of either but not both operands are 1s.")
    10. [Bitwise XOR assignment
        (\^=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR_assignment "The bitwise XOR assignment operator (^=) uses the binary representation of both operands, does a bitwise XOR operation on them and assigns the result to the variable.")
    11. [Comma operator
        (,)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator "The comma operator (,) evaluates each of its operands (from left to right) and returns the value of the last operand. This lets you create a compound expression in which multiple expressions are evaluated, with the compound expression's final value being the value of the rightmost of its member expressions. This is commonly used to provide multiple parameters to a for loop.")
    12. [Conditional (ternary)
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator "The conditional (ternary) operator is the only JavaScript operator that takes three operands: a condition followed by a question mark (?), then an expression to execute if the condition is truthy followed by a colon (:), and finally the expression to execute if the condition is falsy.")
    13. [Decrement
        (--)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement "The decrement operator (--) decrements (subtracts one from) its operand and returns a value.")
    14. [Destructuring
        assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment "The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.")
    15. [Division
        (/)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division "The division operator (/) produces the quotient of its operands where the left operand is the dividend and the right operand is the divisor.")
    16. [Division assignment
        (/=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division_assignment "The division assignment operator (/=) divides a variable by the value of the right operand and assigns the result to the variable.")
    17. [Equality
        (==)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality "The equality operator (==) checks whether its two operands are equal, returning a Boolean result. Unlike the strict equality operator, it attempts to convert and compare operands that are of different types.")
    18. [Exponentiation
        (\*\*)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation "The exponentiation operator (**) returns the result of raising the first operand to the power of the second operand.")
    19. [Exponentiation assignment
        (\*\*=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation_assignment "The exponentiation assignment operator (**=) raises the value of a variable to the power of the right operand.")
    20. [Function
        expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function "The function keyword can be used to define a function inside an expression.")
    21. [Greater than
        (\>)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than "The greater than operator (>) returns true if the left operand is greater than the right operand, and false otherwise.")
    22. [Greater than or equal
        (\>=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal "The greater than or equal operator (>=) returns true if the left operand is greater than or equal to the right operand, and false otherwise.")
    23. [Grouping operator (
        )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Grouping "The grouping operator ( ) controls the precedence of evaluation in expressions.")
    24. [Increment
        (++)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment "The increment operator (++) increments (adds one to) its operand and returns a value.")
    25. [Inequality
        (!=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality "The inequality operator (!=) checks whether its two operands are not equal, returning a Boolean result. Unlike the strict inequality operator, it attempts to convert and compare operands that are of different types.")
    26. [Left shift
        (\<\<)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Left_shift "The left shift operator (<<) shifts the first operand the specified number of bits to the left. Excess bits shifted off to the left are discarded. Zero bits are shifted in from the right.")
    27. [Left shift assignment
        (\<\<=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Left_shift_assignment "The left shift assignment operator (<<=) moves the specified amount of bits to the left and assigns the result to the variable.")
    28. [Less than
        (\<)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than "The less than operator (<) returns true if the left operand is less than the right operand, and false otherwise.")
    29. [Less than or equal
        (\<=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than_or_equal "The less than or equal operator (<=) returns true if the left operand is less than or equal to the right operand, and false otherwise.")
    30. [Logical AND
        (&&)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND "The logical AND (&&) operator (logical conjunction) for a set of operands is true if and only if all of its operands are true. It is typically used with Boolean (logical) values. When it is, it returns a Boolean value. However, the && operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value.")
    31. [Logical AND assignment
        (&&=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND_assignment "The logical AND assignment (x &&= y) operator only assigns if x is truthy.")
    32. [Logical NOT
        (!)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT "The logical NOT (!) operator (logical complement, negation) takes truth to falsity and vice versa. It is typically used with Boolean (logical) values. When used with non-Boolean values, it returns false if its single operand can be converted to true; otherwise, returns true.")
    33. [Logical OR
        (||)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR "The logical OR (||) operator (logical disjunction) for a set of operands is true if and only if one or more of its operands is true. It is typically used with Boolean (logical) values. When it is, it returns a Boolean value. However, the || operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value.")
    34. [Logical OR assignment
        (||=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment "The logical OR assignment (x ||= y) operator only assigns if x is falsy.")
    35. [Logical nullish assignment
        (??=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_nullish_assignment "The logical nullish assignment (x ??= y) operator only assigns if x is nullish (null or undefined).")
    36. [Multiplication
        (\*)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication "The multiplication operator (*) produces the product of the operands.")
    37. [Multiplication assignment
        (\*=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication_assignment "The multiplication assignment operator (*=) multiplies a variable by the value of the right operand and assigns the result to the variable.")
    38. [Nullish coalescing operator
        (??)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator "The nullish coalescing operator (??) is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.")
    39. [Object
        initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer "Objects can be initialized using new Object(), Object.create(), or using the literal notation (initializer notation). An object initializer is a comma-delimited list of zero or more pairs of property names and associated values of an object, enclosed in curly braces ({}).")
    40. [Operator
        precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence "Operator precedence determines how operators are parsed concerning each other. Operators with higher precedence become the operands of operators with lower precedence.")
    41. [Optional chaining
        (?.)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining "The ?. operator functions similarly to the . chaining operator, except that instead of causing an error if a reference is nullish (null or undefined), the expression short-circuits with a return value of undefined.")
    42. \*\*[Pipeline operator
        (|\>)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Pipeline_operator "The experimental pipeline operator |> (currently at stage 1) pipes the value of an expression into a function. This allows the creation of chained function calls in a readable manner. The result is syntactic sugar in which a function call with a single argument can be written like this:")
    43. [Property
        accessors](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors "Property accessors provide access to an object's properties by using the dot notation or the bracket notation.")
    44. [Remainder
        (%)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder "The remainder operator (%) returns the remainder left over when one operand is divided by a second operand. It always takes the sign of the dividend.")
    45. [Remainder assignment
        (%=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder_assignment "The remainder assignment operator (%=) divides a variable by the value of the right operand and assigns the remainder to the variable.")
    46. [Right shift
        (\>\>)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift "The right shift operator (>>) shifts the first operand the specified number of bits to the right. Excess bits shifted off to the right are discarded. Copies of the leftmost bit are shifted in from the left. Since the new leftmost bit has the same value as the previous leftmost bit, the sign bit (the leftmost bit) does not change. Hence the name "sign-propagating".")
    47. [Right shift assignment
        (\>\>=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift_assignment "The right shift assignment operator (>>=) moves the specified amount of bits to the right and assigns the result to the variable.")
    48. [Spread syntax
        (...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax "Spread syntax (...) allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.")
    49. [Strict equality
        (===)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality "The strict equality operator (===) checks whether its two operands are equal, returning a Boolean result. Unlike the equality operator, the strict equality operator always considers operands of different types to be different.")
    50. [Strict inequality
        (!==)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality "The strict inequality operator (!==) checks whether its two operands are not equal, returning a Boolean result. Unlike the inequality operator, the strict inequality operator always considers operands of different types to be different.")
    51. [Subtraction
        (-)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction "The subtraction operator (-) subtracts the two operands, producing their difference.")
    52. [Subtraction assignment
        (-=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction_assignment "The subtraction assignment operator (-=) subtracts the value of the right operand from a variable and assigns the result to the variable.")
    53. [Unary negation
        (-)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_negation "The unary negation operator (-) precedes its operand and negates it.")
    54. [Unary plus
        (+)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus "The unary plus operator (+) precedes its operand and evaluates to its operand but attempts to convert it into a number, if it isn't already.")
    55. [Unsigned right shift
        (\>\>\>)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift "The unsigned right shift operator (>>>) (zero-fill right shift) shifts the first operand the specified number of bits to the right. Excess bits shifted off to the right are discarded. Zero bits are shifted in from the left. The sign bit becomes 0, so the result is always non-negative. Unlike the other bitwise operators, zero-fill right shift returns an unsigned 32-bit integer.")
    56. [Unsigned right shift assignment
        (\>\>\>=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift_assignment "The unsigned right shift assignment operator (>>>=) moves the specified amount of bits to the right and assigns the result to the variable.")
    57. [async function
        expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function "The async function keyword can be used to define async functions inside expressions.")
    58. [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await "The await operator is used to wait for a Promise. It can only be used inside an async function.")
    59. [class
        expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/class "The class expression is one way to define a class in ECMAScript 2015. Similar to function expressions, class expressions can be named or unnamed. If named, the name of the class is local to the class body only. ")
    60. [delete
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete "The JavaScript delete operator removes a property from an object; if no more references to the same property are held, it is eventually released automatically.")
    61. [function\*
        expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function* "The function* keyword can be used to define a generator function inside an expression.")
    62. [in
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in "The in operator returns true if the specified property is in the specified object or its prototype chain.")
    63. [instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof "The instanceof operator tests whether the prototype property of a constructor appears anywhere in the prototype chain of an object.")
    64. [new
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new "The new operator lets developers create an instance of a user-defined object type or of one of the built-in object types that has a constructor function.")
    65. [new.target](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target "The new.target pseudo-property lets you detect whether a function or constructor was called using the new operator. In constructors and functions invoked using the new operator, new.target returns a reference to the constructor or function. In normal function calls, new.target is undefined.")
    66. [super](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super "The super keyword is used to access and call functions on an object's parent.")
    67. [this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this "A function's this keyword behaves a little differently in JavaScript compared to other languages. It also has some differences between strict mode and non-strict mode.")
    68. [typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof "The typeof operator returns a string indicating the type of the unevaluated operand.")
    69. [void
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void "The void operator evaluates the given expression and then returns undefined.")
    70. [yield](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield "The yield keyword is used to pause and resume a generator function (function* or legacy generator function).")
    71. [yield\*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield* "The yield* expression is used to delegate to another generator or iterable object.")

10. Statements & declarations

    1.  [async
        function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function "An async function is a function declared with the async keyword. Async functions are instances of the AsyncFunction constructor, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.")
    2.  [block](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block "A block statement (or compound statement in other languages) is used to group zero or more statements. The block is delimited by a pair of braces ("curly brackets") and may optionally be labelled:")
    3.  [break](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break "The break statement terminates the current loop, switch, or label statement and transfers program control to the statement following the terminated statement.")
    4.  [class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class "The class declaration creates a new class with a given name using prototype-based inheritance.")
    5.  [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const "Constants are block-scoped, much like variables defined using the let keyword. The value of a constant can't be changed through reassignment, and it can't be redeclared.")
    6.  [continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue "The continue statement terminates execution of the statements in the current iteration of the current or labeled loop, and continues execution of the loop with the next iteration.")
    7.  [debugger](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/debugger "The debugger statement invokes any available debugging functionality, such as setting a breakpoint. If no debugging functionality is available, this statement has no effect.")
    8.  [do...while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while "The do...while statement creates a loop that executes a specified statement until the test condition evaluates to false. The condition is evaluated after executing the statement, resulting in the specified statement executing at least once.")
    9.  [empty](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Empty "An empty statement is used to provide no statement, although the JavaScript syntax would expect one.")
    10. [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export "The export statement is used when creating JavaScript modules to export live bindings to functions, objects, or primitive values from the module so they can be used by other programs with the import statement. Bindings that are exported can still be modified locally; when imported, although they can only be read by the importing module the value updates whenever it is updated by the exporting module.")
    11. [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for "The for statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement (usually a block statement) to be executed in the loop.")
    12. [for
        await...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for-await...of "The for await...of statement creates a loop iterating over async iterable objects as well as on sync iterables, including: built-in String, Array, Array-like objects (e.g., arguments or NodeList), TypedArray, Map, Set, and user-defined async/sync iterables. It invokes a custom iteration hook with statements to be executed for the value of each distinct property of the object. Like await operator, the statement can only be used inside an async function.")
    13. [for...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in "The for...in statement iterates over all enumerable properties of an object that are keyed by strings (ignoring ones keyed by Symbols), including inherited enumerable properties.")
    14. [for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of "The for...of statement creates a loop iterating over iterable objects, including: built-in String, Array, array-like objects (e.g., arguments or NodeList), TypedArray, Map, Set, and user-defined iterables. It invokes a custom iteration hook with statements to be executed for the value of each distinct property of the object.")
    15. [function
        declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function "The function declaration (function statement) defines a function with the specified parameters.")
    16. [function\*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function* "The function* declaration (function keyword followed by an asterisk) defines a generator function, which returns a Generator object.")
    17. [if...else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else "The if statement executes a statement if a specified condition is truthy. If the condition is falsy, another statement can be executed.")
    18. [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import "The static import statement is used to import read only live bindings which are exported by another module. ")
    19. [import.meta](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import.meta "The import.meta object exposes context-specific metadata to a JavaScript module. It contains information about the module, like the module's URL.")
    20. [label](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label "The labeled statement can be used with break or continue statements. It is prefixing a statement with an identifier which you can refer to.")
    21. [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let "The let statement declares a block-scoped local variable, optionally initializing it to a value.")
    22. [return](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return "The return statement ends function execution and specifies a value to be returned to the function caller.")
    23. [switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch "The switch statement evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case, as well as statements in cases that follow the matching case.")
    24. [throw](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw "The throw statement throws a user-defined exception. Execution of the current function will stop (the statements after throw won't be executed), and control will be passed to the first catch block in the call stack. If no catch block exists among caller functions, the program will terminate.")
    25. [try...catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch "The try...catch statement marks a block of statements to try and specifies a response should an exception be thrown.")
    26. [var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var "The var statement declares a function-scoped or globally-scoped variable, optionally initializing it to a value.")
    27. [while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while "The while statement creates a loop that executes a specified statement as long as the test condition evaluates to true. The condition is evaluated before executing the statement.")
    28. \*\*[with](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/with "The with statement extends the scope chain for a statement.")

11. Functions

    1.  [Arrow function
        expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions "An arrow function expression is a syntactically compact alternative to a regular function expression, although without its own bindings to the this, arguments, super, or new.target keywords. Arrow function expressions are all suited as methods, and they cannot be used as constructors.")
    2.  [Default
        parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters "Default function parameters allow named parameters to be initialized with default values if no value or undefined is passed.")
    3.  [Method
        definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions "Starting with ECMAScript 2015, a shorter syntax for method definitions on objects initializers is introduced. It is a shorthand for a function assigned to the method's name.")
    4.  [Rest
        parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters "The rest parameter syntax allows us to represent an indefinite number of arguments as an array.")
    5.  [The arguments
        object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments "arguments is an Array-like object accessible inside functions that contains the values of the arguments passed to that function.")
    6.  [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get "The get syntax binds an object property to a function that will be called when that property is looked up.")
    7.  [setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set "The set syntax binds an object property to a function to be called when there is an attempt to set that property.")

12. Classes

    1.  [Private class
        fields](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_class_fields "Class properties are public by default and can be examined or modified outside the class. In ES2019, the ability to define private class fields using a hash # prefix is added.")
    2.  [Public class
        fields](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Public_class_fields "Both static and instance public fields are writable, enumerable, and configurable properties. As such, unlike their private counterparts, they participate in prototype inheritance.")
    3.  [constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor "The constructor method is a special method for creating and initializing an object created within a class.")
    4.  [extends](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends "The extends keyword is used in class declarations or class expressions to create a class that is a child of another class.")
    5.  [static](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static "The static keyword defines a static method for a class. Static methods aren't called on instances of the class. Instead, they're called on the class itself.")

13. Errors

    1.  [Error: Permission denied to access property
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Property_access_denied "The JavaScript exception "Permission denied to access property" occurs when there was an attempt to access an object for which you have no permission.")
    2.  [InternalError: too much
        recursion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Too_much_recursion "The JavaScript exception "too much recursion" or "Maximum call stack size exceeded" occurs when there are too many function calls, or a function is missing a base case.")
    3.  [RangeError: argument is not a valid code
        point](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_codepoint "The JavaScript exception "Invalid code point" occurs when NaN values, negative Integers (-1), non-Integers (5.4), or values larger than 0x10FFFF (1114111) are used with String.fromCodePoint().")
    4.  [RangeError: invalid array
        length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_array_length "The JavaScript exception "Invalid array length" occurs when creating an Array or an ArrayBuffer which has a length which is either negative or larger or equal to 232, or when setting the Array.length property to a value which is either negative or larger or equal to 232.")
    5.  [RangeError: invalid
        date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_date "The JavaScript exception "invalid date" occurs when a string leading to an invalid date has been provided to Date or Date.parse().")
    6.  [RangeError: precision is out of
        range](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Precision_range "The JavaScript exception "precision is out of range" occurs when a number that's outside of the range of 0 and 20 (or 21) was passed into toFixed or toPrecision.")
    7.  [RangeError: radix must be an
        integer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_radix "The JavaScript exception "radix must be an integer at least 2 and no greater than 36" occurs when the optional radix parameter of the Number.prototype.toString() or the BigInt.prototype.toString() method was specified and is not between 2 and 36.")
    8.  [RangeError: repeat count must be less than
        infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Resulting_string_too_large "The JavaScript exception "repeat count must be less than infinity" occurs when the String.prototype.repeat() method is used with a count argument that is infinity.")
    9.  [RangeError: repeat count must be
        non-negative](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Negative_repetition_count "The JavaScript exception "repeat count must be non-negative" occurs when the String.prototype.repeat() method is used with a count argument that is a negative number.")
    10. [ReferenceError: "x" is not
        defined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_defined "The JavaScript exception "variable is not defined" occurs when there is a non-existent variable referenced somewhere.")
    11. [ReferenceError: assignment to undeclared variable
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Undeclared_var "The JavaScript strict mode-only exception "Assignment to undeclated variable" occurs when the value has been assigned to an undeclared variable.")
    12. [ReferenceError: can't access lexical declaration\`X' before
        initialization](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_access_lexical_declaration_before_init "The JavaScript exception "can't access lexical declaration `variable' before initialization" occurs when a lexical variable was accessed before it was initialized. This happens within any block statement, when let or const declarations are accessed before they are defined.")
    13. [ReferenceError: deprecated caller or arguments
        usage](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_caller_or_arguments_usage "The JavaScript strict mode-only exception "deprecated caller or arguments usage" occurs when the deprecated Function.caller or Function.arguments properties are used.")
    14. [ReferenceError: invalid assignment left-hand
        side](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_assignment_left-hand_side "The JavaScript exception "invalid assignment left-hand side" occurs when there was an unexpected assignment somewhere. For example, a single "=" sign was used instead of "==" or "===".")
    15. [ReferenceError: reference to undefined property
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Undefined_prop "The JavaScript warning "reference to undefined property" occurs when a script attempted to access an object property which doesn't exist.")
    16. [SyntaxError: "0"-prefixed octal literals and octal escape seq.
        are
        deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_octal "The JavaScript strict mode-only exception "0-prefixed octal literals and octal escape sequences are deprecated; for octal literals use the "0o" prefix instead" occurs when deprecated octal literals and octal escape sequences are used.")
    17. [SyntaxError: "use strict" not allowed in function with
        non-simple
        parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Strict_Non_Simple_Params "The JavaScript exception "'use strict' not allowed in function" occurs when a "use strict" directive is used at the top of a function with default parameters, rest parameters, or destructuring parameters.")
    18. [SyntaxError: "x" is a reserved
        identifier](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reserved_identifier "The JavaScript exception "variable is a reserved identifier" occurs when reserved keywords are used as identifiers.")
    19. [SyntaxError: JSON.parse: bad
        parsing](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/JSON_bad_parse "The JavaScript exceptions thrown by JSON.parse() occur when string failed to be parsed as JSON.")
    20. [SyntaxError: Malformed formal
        parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Malformed_formal_parameter "The JavaScript exception "malformed formal parameter" occurs when the argument list of a Function() constructor call is invalid somehow.")
    21. [SyntaxError: Unexpected
        token](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_token "The JavaScript exceptions "unexpected token" occur when a specific language construct was expected, but something else was provided. This might be a simple typo.")
    22. [SyntaxError: Using //@ to indicate sourceURL pragmas is
        deprecated. Use //\#
        instead](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_source_map_pragma "The JavaScript warning "Using //@ to indicate sourceURL pragmas is deprecated. Use //# instead" occurs when there is a deprecated source map syntax in a JavaScript source.")
    23. [SyntaxError: a declaration in the head of a for-of loop can't
        have an
        initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-of_initializer "The JavaScript exception "a declaration in the head of a for-of loop can't have an initializer" occurs when the head of a for...of loop contains an initializer expression such as |for (var i = 0 of iterable)|. This is not allowed in for-of loops.")
    24. [SyntaxError: applying the 'delete' operator to an unqualified
        name is
        deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Delete_in_strict_mode "The JavaScript strict mode-only exception "applying the 'delete' operator to an unqualified name is deprecated" occurs when variables are attempted to be deleted using the delete operator.")
    25. [SyntaxError: for-in loop head declarations may not have
        initializers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-in_initializer "The JavaScript strict mode-only exception "for-in loop head declarations may not have initializers" occurs when the head of a for...in contains an initializer expression, such as |for (var i = 0 in obj)|. This is not allowed in for-of loops in strict mode.")
    26. [SyntaxError: function statement requires a
        name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unnamed_function_statement "The JavaScript exception "function statement requires a name" occurs when there is a function statement in the code that requires a name.")
    27. [SyntaxError: identifier starts immediately after numeric
        literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Identifier_after_number "The JavaScript exception "identifier starts immediately after numeric literal" occurs when an identifier started with a digit. Identifiers can only start with a letter, underscore (\_), or dollar sign ($).")
    28. [SyntaxError: illegal
        character](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Illegal_character "The JavaScript exception "illegal character" occurs when there is an invalid or unexpected token that doesn't belong at this position in the code.")
    29. [SyntaxError: invalid regular expression flag
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_regexp_flag "The JavaScript exception "invalid regular expression flag" occurs when the flags, defined after the second slash in regular expression literal, are not one of g, i, m, s, u, or y.")
    30. [SyntaxError: missing ) after argument
        list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_parenthesis_after_argument_list "The JavaScript exception "missing ) after argument list" occurs when there is an error with how a function is called. This might be a typo, a missing operator, or an unescaped string.")
    31. [SyntaxError: missing ) after
        condition](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_parenthesis_after_condition "The JavaScript exception "missing ) after condition" occurs when there is an error with how an if condition is written. It must appear in parenthesis after the if keyword.")
    32. [SyntaxError: missing : after property
        id](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_colon_after_property_id "The JavaScript exception "missing : after property id" occurs when objects are created using the object initializer syntax. A colon (:) separates keys and values for the object's properties. Somehow, this colon is missing or misplaced.")
    33. [SyntaxError: missing ; before
        statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_semicolon_before_statement "The JavaScript exception "missing ; before statement" occurs when there is a semicolon (;) missing somewhere and can't be added by automatic semicolon insertion (ASI). You need to provide a semicolon, so that JavaScript can parse the source code correctly.")
    34. [SyntaxError: missing = in const
        declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_initializer_in_const "The JavaScript exception "missing = in const declaration" occurs when a const declaration was not given a value in the same statement (like const RED_FLAG;). You need to provide one (const RED_FLAG = '#ff0').")
    35. [SyntaxError: missing ] after element
        list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_bracket_after_list "The JavaScript exception "missing ] after element list" occurs when there is an error with the array initializer syntax somewhere. Likely there is a closing bracket ("]") or a comma (",") missing.")
    36. [SyntaxError: missing formal
        parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_formal_parameter "The JavaScript exception "missing formal parameter" occurs when your function declaration is missing valid parameters.")
    37. [SyntaxError: missing name after .
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_name_after_dot_operator "The JavaScript exception "missing name after . operator" occurs when there is a problem with how the dot operator (.) is used for property access.")
    38. [SyntaxError: missing variable
        name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_variable_name "The JavaScript exception "missing variable name" occurs way too often as naming things is so hard. Or maybe a comma is wrong. Check for typos!")
    39. [SyntaxError: missing } after function
        body](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_curly_after_function_body "The JavaScript exception "missing } after function body" occurs when there is a syntax mistake when creating a function somewhere. Check if any closing curly brackets or parenthesis are in the correct order.")
    40. [SyntaxError: missing } after property
        list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_curly_after_property_list "The JavaScript exception "missing } after property list" occurs when there is a mistake in the object initializer syntax somewhere. Might be in fact a missing curly bracket, but could also be a missing comma.")
    41. [SyntaxError: redeclaration of formal parameter
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Redeclared_parameter "The JavaScript exception "redeclaration of formal parameter" occurs when the same variable name occurs as a function parameter and is then redeclared using a let assignment in a function body again.")
    42. [SyntaxError: return not in
        function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_return_or_yield "The JavaScript exception "return (or yield) not in function" occurs when a return or yield statement is called outside of a function.")
    43. [SyntaxError: test for equality (==) mistyped as assignment
        (=)?](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Equal_as_assign "The JavaScript warning "test for equality (==) mistyped as assignment (=)?" occurs when there was an assignment (=) when you would normally expect a test for equality (==).")
    44. [SyntaxError: unterminated string
        literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unterminated_string_literal "The JavaScript error "unterminated string literal" occurs when there is an unterminated String somewhere. String literals must be enclosed by single (') or double (") quotes.")
    45. [TypeError: "x" has no
        properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_properties "The JavaScript exception "null (or undefined) has no properties" occurs when you attempt to access properties of null and undefined. They don't have any.")
    46. [TypeError: "x" is (not)
        "y"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_type "The JavaScript exception "x is (not) y" occurs when there was an unexpected type. Oftentimes, unexpected undefined or null values.")
    47. [TypeError: "x" is not a
        constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_constructor "The JavaScript exception "is not a constructor" occurs when there was an attempt to use an object or a variable as a constructor, but that object or variable is not a constructor.")
    48. [TypeError: "x" is not a
        function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_function "The JavaScript exception "is not a function" occurs when there was an attempt to call a value from a function, but the value is not actually a function.")
    49. [TypeError: "x" is not a non-null
        object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_non-null_object "The JavaScript exception "is not a non-null object" occurs when an object is expected somewhere and wasn't provided. null is not an object and won't work.")
    50. [TypeError: "x" is
        read-only](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Read-only "The JavaScript strict mode-only exception "is read-only" occurs when a global variable or object property that was assigned to is a read-only property.")
    51. [TypeError: 'x' is not
        iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/is_not_iterable "The JavaScript exception "is not iterable" occurs when the value which is given as the right hand-side of for…of or as argument of a function such as Promise.all or TypedArray.from, is not an iterable object.")
    52. [TypeError: More arguments
        needed](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/More_arguments_needed "The JavaScript exception "more arguments needed" occurs when there is an error with how a function is called. More arguments need to be provided.")
    53. [TypeError: Reduce of empty array with no initial
        value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reduce_of_empty_array_with_no_initial_value "The JavaScript exception "reduce of empty array with no initial value" occurs when a reduce function is used.")
    54. [TypeError: X.prototype.y called on incompatible
        type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Called_on_incompatible_type "The JavaScript exception "called on incompatible target (or object)" occurs when a function (on a given object), is called with a this not corresponding to the type expected by the function.")
    55. [TypeError: can't access dead
        object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Dead_object "The JavaScript exception "can't access dead object" occurs when Firefox disallows add-ons to keep strong references to DOM objects after their parent document has been destroyed to improve in memory usage and to prevent memory leaks.")
    56. [TypeError: can't access property "x" of
        "y"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_access_property "The JavaScript exception "can't access property" occurs when property access was operated on undefined or null values.")
    57. [TypeError: can't assign to property "x" on "y": not an
        object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_assign_to_property "The JavaScript strict mode exception "can't assign to property" occurs when attempting to create a property on primitive value such as a symbol, a string, a number or a boolean. Primitive values cannot hold any property.")
    58. [TypeError: can't define property "x": "obj" is not
        extensible](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_define_property_object_not_extensible "The JavaScript exception "can't define property "x": "obj" is not extensible" occurs when Object.preventExtensions() marked an object as no longer extensible, so that it will never have properties beyond the ones it had at the time it was marked as non-extensible.")
    59. [TypeError: can't delete non-configurable array
        element](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Non_configurable_array_element "The JavaScript exception "can't delete non-configurable array element" occurs when it was attempted to shorten the length of an array, but one of the array's elements is non-configurable.")
    60. [TypeError: can't redefine non-configurable property
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_redefine_property "The JavaScript exception "can't redefine non-configurable property" occurs when it was attempted to redefine a property, but that property is non-configurable.")
    61. [TypeError: cannot use 'in' operator to search for 'x' in
        'y'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/in_operator_no_object "The JavaScript exception "right-hand side of 'in' should be an object" occurs when the in operator was used to search in strings, or in numbers, or other primitive types. It can only be used to check if a property is in an object.")
    62. [TypeError: cyclic object
        value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cyclic_object_value "The JavaScript exception "cyclic object value" occurs when object references were found in JSON. JSON.stringify() doesn't try to solve them and fails accordingly.")
    63. [TypeError: invalid 'instanceof' operand
        'x'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/invalid_right_hand_side_instanceof_operand "The JavaScript exception "invalid 'instanceof' operand" occurs when the right hand side operands of the instanceof operator isn't used with a constructor object, i.e. an object which has a prototype property and is callable.")
    64. [TypeError: invalid Array.prototype.sort
        argument](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Array_sort_argument "The JavaScript exception "invalid Array.prototype.sort argument" occurs when the argument of Array.prototype.sort() isn't either undefined or a function which compares its operands.")
    65. [TypeError: invalid
        arguments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Typed_array_invalid_arguments "The JavaScript exception "invalid arguments" occurs when typed array constructors are provided with a wrong argument.")
    66. [TypeError: invalid assignment to const
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_const_assignment "The JavaScript exception "invalid assignment to const" occurs when it was attempted to alter a constant value. JavaScript const declarations can't be re-assigned or redeclared.")
    67. [TypeError: property "x" is non-configurable and can't be
        deleted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_delete "The JavaScript exception "property is non-configurable and can't be deleted" occurs when it was attempted to delete a property, but that property is non-configurable.")
    68. [TypeError: setting getter-only property
        "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Getter_only "The JavaScript strict mode-only exception "setting getter-only property" occurs when there is an attempt to set a new value to a property for which only a getter is specified.")
    69. [TypeError: variable "x" redeclares
        argument](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Var_hides_argument "The JavaScript strict mode-only exception "variable redeclares argument" occurs when the same variable name occurs as a function parameter and is then redeclared using a var assignment in a function body again.")
    70. [URIError: malformed URI
        sequence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Malformed_URI "The JavaScript exception "malformed URI sequence" occurs when URI encoding or decoding wasn't successful.")
    71. [Warning: -file- is being assigned a //\# sourceMappingURL, but
        already has
        one](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Already_has_pragma "The JavaScript warning "-file- is being assigned a //# sourceMappingURL, but already has one." occurs when a source map has been specified more than once for a given JavaScript source.")
    72. [Warning: 08/09 is not a legal ECMA-262 octal
        constant](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_octal "The JavaScript warning "08 (or 09) is not a legal ECMA-262 octal constant" occurs when 08 or 09 number literals are used. They can't be interpreted as an octal number.")
    73. [Warning: Date.prototype.toLocaleFormat is
        deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_toLocaleFormat "The JavaScript warning "Date.prototype.toLocaleFormat is deprecated; consider using Intl.DateTimeFormat instead" occurs when the non-standard Date.prototype.toLocaleFormat method is used.")
    74. [Warning: JavaScript 1.6's for-each-in loops are
        deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/For-each-in_loops_are_deprecated "The JavaScript warning "JavaScript 1.6's for-each-in loops are deprecated; consider using ES6 for-of instead" occurs when a for each (variable in obj) statement is used.")
    75. [Warning: String.x is deprecated; use String.prototype.x
        instead](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_String_generics "The JavaScript warning about string generics occurs in Firefox versions prior to 68. String generics have been removed starting with Firefox 68.")
    76. [Warning: expression closures are
        deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_expression_closures "The JavaScript warning "expression closures are deprecated" occurs when the non-standard expression closure syntax (shorthand function syntax) is used.")
    77. [Warning: unreachable code after return
        statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Stmt_after_return "The JavaScript warning "unreachable code after return statement" occurs when using an expression after a return statement, or when using a semicolon-less return statement but including an expression directly after.")

14. Misc
    1.  [JavaScript technologies
        overview](https://developer.mozilla.org/en-US/docs/Web/JavaScript/JavaScript_technologies_overview)
    2.  [Lexical
        grammar](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar)
    3.  [JavaScript data
        structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
    4.  [Enumerability and ownership of
        properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
    5.  [Iteration
        protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
    6.  [Strict
        mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
    7.  [Transitioning to strict
        mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode/Transitioning_to_strict_mode)
    8.  [Template
        literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
    9.  [Deprecated
        features](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features)

## Learn the best of web development {.newsletter-teaser}

Get the latest and greatest from MDN delivered straight to your inbox.

The newsletter is offered in English only at the moment.

E-mail

I’m okay with Mozilla handling my info as explained in this [Privacy
Policy](https://www.mozilla.org/privacy/).

Sign up now

Hide Newsletter Sign-up

[MDN Web Docs](https://developer.mozilla.org/en-US/)

- [Web Technologies](https://developer.mozilla.org/en-US/docs/Web)
- [Learn Web
  Development](https://developer.mozilla.org/en-US/docs/Learn)
- [About MDN](https://developer.mozilla.org/en-US/docs/MDN/About)
- [Feedback](https://developer.mozilla.org/en-US/docs/MDN/Feedback)

- [About](https://www.mozilla.org/about/)
- [MDN Web Docs Store](https://shop.spreadshirt.com/mdn-store/)
- [Contact Us](https://www.mozilla.org/contact/)
- [Firefox](https://www.mozilla.org/firefox/?utm_source=developer.mozilla.org&utm_campaign=footer&utm_medium=referral)

#### MDN

- [](https://twitter.com/mozdevnet)
- [](https://github.com/mdn/)

#### Mozilla

- [](https://twitter.com/mozilla)
- [](https://www.instagram.com/mozillagram/)

© 2005-2020 Mozilla and individual contributors. Content is available
under [these
licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

- [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
- [Privacy](https://www.mozilla.org/privacy/websites/)
- [Cookies](https://www.mozilla.org/privacy/websites/#cookies)

## Sign In {#modal-main-heading}

Sign in to enjoy the benefits of an MDN account. If you haven’t already
created an account, you will be prompted to do so after signing in.

[Sign in with
Github](https://developer.mozilla.org/users/github/login/?next=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FStatements%2Ffor...of)
[Sign in with
Google](https://developer.mozilla.org/users/google/login/?next=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FStatements%2Ffor...of)

Close modal

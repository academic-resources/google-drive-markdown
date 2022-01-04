``` {aria-hidden="true" style="position: absolute; visibility: hidden; white-space: pre; font-family: Lato, sans-serif; font-size: 18px; font-style: normal; font-variant: normal; font-weight: 400; word-spacing: 0px; letter-spacing: normal; text-indent: 0px; text-rendering: auto; text-transform: none;"}
```

[![freeCodeCamp.org](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/fcc_primary_large_24X210.svg)](https://www.freecodecamp.org/news)

[Donate](https://www.freecodecamp.org/donate/)

Stay safe, friends. Learn to code from home. [Use our free 2,000 hour curriculum.](https://www.freecodecamp.org/) {.donation-banner}
-----------------------------------------------------------------------------------------------------------------

8 June 2020 /
[\#JavaScript](https://www.freecodecamp.org/news/tag/javascript/)

JavaScript Promise Tutorial: Resolve, Reject, and Chaining in JS and ES6 {.post-full-title}
========================================================================

![Cem
Eygi](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/Ekran-Resmi-2019-08-01-12.13.08.png)

#### [Cem Eygi](https://www.freecodecamp.org/news/author/cemeygi/) {.author-card-name}

![JavaScript Promise Tutorial: Resolve, Reject, and Chaining in JS and
ES6](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/photo-1571171637578-41bc2dd41cd2)

Promises are one of the ways we can deal with asynchronous operations in
JavaScript. Many people struggle with understanding how Promises work,
so in this post I will try to explain them as simply as I can.

Promises are a broad topic so I can't go into every detail in this
article. But you'll find an overall introduction to what Promises are,
explanations of terms like resolve, reject, and chaining, and a code
example for creating and using Promises.

**Prerequisite:**To understand this article better, check out my other
post about [JavaScript
Callbacks](https://www.freecodecamp.org/news/javascript-callback-functions-what-are-callbacks-in-js-and-how-to-use-them/).

What is a Promise?
------------------

A promise in JavaScript is similar to a promise in real life. When we
make a promise in real life, it is a guarantee that we are going to do
something in the future. Because promises can only be made for the
future.

A promise has 2 possible outcomes: it will either be kept when the time
comes, or it won’t.

This is also the same for promises in JavaScript. When we define a
promise in JavaScript, it will be resolved when the time comes, or it
will get rejected.

### Promises in JavaScript

First of all, a Promise is an object. There are 3 states of the Promise
object:

-   **Pending:** Initial State, before the Promise succeeds or fails
-   **Resolved:** Completed Promise
-   **Rejected:** Failed Promise

![](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/Ekran-Resmi-2020-06-06-12.21.27.png)

**Representation of the process of Promises**

For example, when we request data from the server by using a Promise, it
will be in pending mode until we receive our data.

If we achieve to get the information from the server, the Promise will
be resolved successfully. But if we don’t get the information, then the
Promise will be in the rejected state.

Additionally, if there are multiple requests, then after the first
Promise is resolved (or rejected), a new process will start to which we
can attach it directly by a method called chaining.

If you prefer, you can also watch the video version below:

### What is the difference between Callbacks and Promises?

The main difference between Callback Functions and Promises is that we
attach a callback to a Promise rather than passing it. So we still use
callback functions with Promises, but in a different way (chaining).

This is one of the greatest advantages of using Promises, but why?

### What is Chaining?

Callback functions have been used alone for asynchronous operations in
JavaScript for many years. But in some cases, using Promises can be a
better option.

If there are multiple async operations to be done and if we try to use
good-old Callbacks for them, we’ll find ourselves quickly inside a
situation called [Callback hell](http://callbackhell.com/):

``` {.language-javascript}
firstRequest(function(response) {  
    secondRequest(response, function(nextResponse) {    
        thirdRequest(nextResponse, function(finalResponse) {     
            console.log('Final response: ' + finalResponse);    
        }, failureCallback);  
    }, failureCallback);
}, failureCallback);
```

However if we handle the same operation with Promises, since we can
attach Callbacks rather than passing them, this time the same code above
looks much cleaner and easier to read:

``` {.language-javascript}
firstRequest()
  .then(function(response) {
    return secondRequest(response);
}).then(function(nextResponse) {  
    return thirdRequest(nextResponse);
}).then(function(finalResponse) {  
    console.log('Final response: ' + finalResponse);
}).catch(failureCallback);
```

The code just above shows how multiple callbacks can be chained one
after another. Chaining is one of the best features of Promises.

### Creating and Using A Promise Step by Step

Firstly, we use a constructor to create a Promise object:

``` {.language-javascript}
const myPromise = new Promise();
```

It takes two parameters, one for success (resolve) and one for fail
(reject):

``` {.language-javascript}
const myPromise = new Promise((resolve, reject) => {  
    // condition
});
```

Finally, there will be a condition. If the condition is met, the Promise
will be resolved, otherwise it will be rejected:

``` {.language-javascript}
const myPromise = new Promise((resolve, reject) => {  
    let condition;  
    
    if(condition is met) {    
        resolve('Promise is resolved successfully.');  
    } else {    
        reject('Promise is rejected');  
    }
});
```

So we have created our first Promise. Now let's use it.

### then( ) for resolved Promises: {#then-for-resolved-promises-}

If you revisit the picture at the beginning of this post, you'll see
that there are 2 cases: One for resolved promises and one for rejected.
If the Promise gets resolved (success case), then something will happen
next (depends on what we do with the successful Promise).

``` {.language-javascript}
myPromise.then();
```

The then( ) method is called after the Promise is resolved. Then we can
decide what to do with the resolved Promise.

For example, let’s log the message to the console that we got from the
Promise:

``` {.language-javascript}
myPromise.then((message) => {  
    console.log(message);
});
```

### catch( ) for rejected Promises: {#catch-for-rejected-promises-}

However, the then( ) method is only for resolved Promises. What if the
Promise fails? Then, we need to use the catch( ) method.

Likewise we attach the then( ) method. We can also directly attach the
catch( ) method right after then( ):

``` {.language-javascript}
myPromise.then((message) => { 
    console.log(message);
}).catch((message) => { 
    console.log(message);
});
```

So if the promise gets rejected, it will jump to the catch( ) method and
this time we will see a different message on the console.

Wrap Up
-------

So this is how we create a Promise in JavaScript and use it for resolved
and rejected cases. Promises are a broader topic, and there are many
more things to learn about them. So understanding how they work takes
time.

This post is just an introduction to Promises, and I hope you found it
helpful for getting an idea about what JavaScript Promises are and how
to use them.

If you want to learn more about Web Development, feel free to visit my
[Youtube
Channel](https://www.youtube.com/channel/UC1EgYPCvKCXFn8HlpoJwY3Q?view_as=subscriber)
for more.

Thank you for reading!

* * * * *

![Cem
Eygi](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/Ekran-Resmi-2019-08-01-12.13.08.png)

#### [Cem Eygi](https://www.freecodecamp.org/news/author/cemeygi/) {.author-card-name}

Front-end Developer // Follow Me on Youtube: https://bit.ly/3dBiTUT

* * * * *

If you read this far, tweet to the author to show them you care. Tweet a
thanks

Learn to code for free. freeCodeCamp's open source curriculum has helped
more than 40,000 people get jobs as developers. [Get
started](https://www.freecodecamp.org/learn)

Countinue reading about

### [JavaScript](https://www.freecodecamp.org/news/tag/javascript/) {.read-next-card-header-title}

-   [How to Build and Validate Beautiful Forms with Vanilla HTML, CSS, &
    JS](https://www.freecodecamp.org/news/build-and-validate-beautiful-forms-with-vanilla-html-css-js/)
-   [How to Build a Responsive and Dynamic Progress Bar with HTML, CSS,
    and
    JavaScript](https://www.freecodecamp.org/news/how-to-build-a-responsive-and-dynamic-progress-bar/)
-   [How to Understand Recursion in
    JavaScript](https://www.freecodecamp.org/news/understanding-recursion-in-javascript/)

[See all 1668 posts
→](https://www.freecodecamp.org/news/tag/javascript/)

[![Learn Svelte in 5
Minutes](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/Screenshot-2020-06-06-at-16.10.39.png)](https://www.freecodecamp.org/news/learn-svelte-in-5-minutes/)

[\#svelte](https://www.freecodecamp.org/news/tag/svelte/)

[Learn Svelte in 5 Minutes](https://www.freecodecamp.org/news/learn-svelte-in-5-minutes/) {.post-card-title}
-----------------------------------------------------------------------------------------

-   Leanne Rybintsev
    [![Leanne
    Rybintsev](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/IMG_5731.jpeg)](https://www.freecodecamp.org/news/author/leanne/)

[Leanne Rybintsev](https://www.freecodecamp.org/news/author/leanne/) 3
months ago

[![How to Switch Between Issues in Your Local Git
Repository](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/photo-1587613981449-f3962dbba9b5)](https://www.freecodecamp.org/news/how-to-switch-between-issues-in-git/)

[\#Git](https://www.freecodecamp.org/news/tag/git/)

[How to Switch Between Issues in Your Local Git Repository](https://www.freecodecamp.org/news/how-to-switch-between-issues-in-git/) {.post-card-title}
-----------------------------------------------------------------------------------------------------------------------------------

-   Sule-Balogun Olanrewaju Ganiu
    [![Sule-Balogun Olanrewaju
    Ganiu](./JavaScript%20Promise%20Tutorial_%20Resolve,%20Reject,%20and%20Chaining%20in%20JS%20and%20ES6_files/ece3b32613eb3326895fe9af59aea2ff.jpeg)](https://www.freecodecamp.org/news/author/devlarri/)

[Sule-Balogun Olanrewaju
Ganiu](https://www.freecodecamp.org/news/author/devlarri/) 3 months ago

freeCodeCamp is a donor-supported tax-exempt 501(c)(3) nonprofit
organization (United States Federal Tax Identification Number:
82-0779546)

Our mission: to help people learn to code for free. We accomplish this
by creating thousands of videos, articles, and interactive coding
lessons - all freely available to the public. We also have thousands of
freeCodeCamp study groups around the world.

Donations to freeCodeCamp go toward our education initiatives, and help
pay for servers, services, and staff.

You can [make a tax-deductible donation
here](https://freecodecamp.org/donate).

Trending Guides

[JavaScript
Closure](https://www.freecodecamp.org/news/javascript-closure-tutorial-with-js-closure-example-code/)
[CSS Box
Shadow](https://www.freecodecamp.org/news/css-tutorial-drop-shadow/)
[Python List
Append](https://www.freecodecamp.org/news/python-list-append-how-to-add-an-element-to-an-array-explained-with-examples/)
[JavaScript Array
Sort](https://www.freecodecamp.org/news/javascript-array-sort-tutorial-how-to-use-js-sort-methods-with-code-examples/)
[Symlink in
Linux](https://www.freecodecamp.org/news/symlink-tutorial-in-linux-how-to-create-and-remove-a-symbolic-link/)
[Linux Grep
Command](https://www.freecodecamp.org/news/grep-command-tutorial-how-to-search-for-a-file-in-linux-and-unix/)
[What is DNS?](https://www.freecodecamp.org/news/what-is-dns/) [Primary
Key
SQL](https://www.freecodecamp.org/news/primary-key-sql-tutorial-how-to-define-a-primary-key-in-a-database/)
[SQL Update
Statement](https://www.freecodecamp.org/news/sql-update-statement-example-queries-for-updating-table-values/)
[Screenshot on
PC](https://www.freecodecamp.org/news/how-to-screenshot-on-windows/)

[JavaScript
Promise](https://www.freecodecamp.org/news/javascript-es6-promises-for-beginners-resolve-reject-and-chaining-explained/)
[What is
GitHub?](https://www.freecodecamp.org/news/what-is-github-what-is-git-and-how-to-use-these-developer-tools/)
[Python Sort
List](https://www.freecodecamp.org/news/the-python-sort-list-array-method-ascending-and-descending-explained-with-examples/)
[Comments in
JSON](https://www.freecodecamp.org/news/json-comment-example-how-to-comment-in-json-files/)
[What is
Kanban?](https://www.freecodecamp.org/news/what-is-kanban-the-agile-methodology-defined-and-how-to-use-it-for-your-software-development-team-2/)
[Python Write to
File](https://www.freecodecamp.org/news/python-write-to-file-open-read-append-and-other-file-handling-functions-explained/)
[CSS Media
Queries](https://www.freecodecamp.org/news/css-media-queries-breakpoints-media-types-standard-resolutions-and-more/)
[HTML
Entities](https://www.freecodecamp.org/news/html-entities-symbols-special-character-codes-list/)
[Excel VBA](https://www.freecodecamp.org/news/excel-vba-tutorial/)
[LOOKUP in Excel](https://www.freecodecamp.org/news/vlookup-in-excel/)

[What is a Proxy
Server?](https://www.freecodecamp.org/news/what-is-a-proxy-server-in-english-please/)
[Cat Command in
Linux](https://www.freecodecamp.org/news/the-cat-command-in-linux-concatenation-explained-with-bash-examples/)
[CSS Background
Image](https://www.freecodecamp.org/news/how-to-add-an-image-url-to-your-div/)
[HTML Background
Color](https://www.freecodecamp.org/news/html-background-color-tutorial-how-to-change-a-div-background-color-explained-with-code-examples/)
[CSS Comment
Example](https://www.freecodecamp.org/news/comments-in-css/)

[Arrow Function
JavaScript](https://www.freecodecamp.org/news/arrow-function-javascript-tutorial-how-to-declare-a-js-function-with-the-new-es6-syntax/)
[Remove Duplicates in
Excel](https://www.freecodecamp.org/news/how-to-remove-duplicates-in-excel-delete-duplicate-rows-with-a-few-clicks/)
[dllhost.exe COM
Surrogate](https://www.freecodecamp.org/news/what-is-dllhost-exe-and-com-surrogate-in-windows-task-manager-solved/)
[Boolean Algebra Truth
Table](https://www.freecodecamp.org/news/boolean-algebra/) [Video Chat
for
Android](https://www.freecodecamp.org/news/can-you-facetime-on-android-no-but-here-are-some-alternative-video-conferencing-apps/)

Our Nonprofit

[About](https://www.freecodecamp.org/news/about/) [Alumni
Network](https://www.linkedin.com/school/free-code-camp/people/) [Open
Source](https://github.com/freeCodeCamp/)
[Shop](https://www.freecodecamp.org/shop/)
[Support](https://www.freecodecamp.org/news/support/)
[Sponsors](https://www.freecodecamp.org/news/sponsors/) [Academic
Honesty](https://www.freecodecamp.org/news/academic-honesty-policy/)
[Code of Conduct](https://www.freecodecamp.org/news/code-of-conduct/)
[Privacy Policy](https://www.freecodecamp.org/news/privacy-policy/)
[Terms of Service](https://www.freecodecamp.org/news/terms-of-service/)
[Copyright Policy](https://www.freecodecamp.org/news/copyright-policy/)

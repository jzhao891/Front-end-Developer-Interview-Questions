#Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
* What's the difference between full standards mode, almost standards mode and quirks mode?
* What's the difference between HTML and XHTML?
* Are there any problems with serving pages as `application/xhtml+xml`?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are `data-` attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* What is progressive rendering?
* Have you used different HTML templating languages before?

#### CSS Questions:

* What is the difference between classes and IDs in CSS?
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* Describe BFC(Block Formatting Context) and how it works.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

* Explain event delegation

based on event bubbling, the event is first captured and handled by target element and then propagated to outer elements(father). So event delegation is a handling that binds a event to the outer element rather than to each of its children elements. It's a easy way for event listener to manage.

eg: click'li', delete it

* add click to every 'li'
* add click listener to 'ul'(recommend)

```在'ul'节点上添加event listener：
language-javascript
// Get the element, add a click listener...
document.getElementsByTag("ul")[0].addEventListener("click", function(e) {
    // e.target is the clicked element
    // If it was a list item
    if(e.target && e.target.nodeName == "LI") {
        // List item found.  Do whatever you want.
        console.log("List item ", e.target.id.replace("post-"), " was clicked!");
    }
});
```
reference:

  https://github.com/simongong/js-stackoverflow-highest-votes/blob/master/questions21-30/event-delegation.md
* Explain how `this` works in JavaScript

function example(){

console.log(this.id);

}

function example2(e){

console.log(e.id);

}

var targetElem = document.getElementById("imp");

var target=document.getElementById("work");

example();//show "undefinde", as example is a global function(直接调用的情况下), so \this\ is the obj of window.

targetElem.onclick=example;//show "imp", as example is a declared function in obj targetElem, so 通过object调用example，\this\ is targetElem.

targetElem.onclick=function(){

  return example();

}//show "undefined", 因为example还是被直接调用了，\this\ is window

targetElem.onclick=function(){

  return example2(this);// \this\ is targetElem

}//show"imp"

targetElem.conclick=example.bind(target);//show"work", as bind() already change the context from targetElem to target, so \this\ is object target.

- reference:

-- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this

* Explain how prototypal inheritance works

javaScript在ES6之前没有显式类继承，所以要实现继承类，需要用prototype property.是继承实例（无法实现继承接口）

child.prototype=Object.create(father.prototype);

child.prototype.constructor=child;//constructor要指定给child, 否则指向的是father

可以override methode

* What do you think of AMD vs CommonJS?


* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?

  IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.

  The first pair of parentheses (function(){...}) turns the code within (in this case, a function) into an expression, and the second pair of parentheses (function(){...})() calls the function that results from that evaluated expression.

* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  * How would you go about checking for any of these states?

null is the null value of a variable;

undefined is a declared variable without valuation

undeclared will be shown when you use a variable without declaration ahead.

* What is a closure, and how/why would you use one?

In javascript, there is no private methods or variables. But in javascript, child can access variables of father, but father can't access variables of child.So we can apply this to implement closure that you can't access and modified its variables directly from outside.

application:

implement private variables and functions:

var counter=(function(){

  var privateCount=0;

  function changeBy(val){

    privateCount+=val;

  }

  return {

    increase: function(){

      changeBy(1);

    }

    decrease: function(){

      changeBy(-1);

    }

    value: function(){

      return privateCount;

    }

  }

})();

we get a counter, an object with three methods: increase,decrease,value.

console.log(counter.value()); // logs 0

counter.increment();

counter.increment();

console.log(counter.value()); // logs 2

counter.decrement();

console.log(counter.value()); // logs 1

* What's a typical use case for anonymous functions?

anonymous functions is invoked at runtime

  * use anonymous functions in function expression.

  * as a parameter passed to a function.

console.log((function(){return "alert!";})());

  * as a return

  function getfunction(){

    return function(){

      alert("alert!");

    }

  }

* How do you organize your code? (module pattern, classical inheritance?)


* What's the difference between host objects and native objects?

The native objects are sometimes referred to as “global objects” since they are the objects that JavaScript has made natively available for use.

Below find the list of native object constructors that come pre-packaged with JavaScript:

✴ Number() ✴ String() ✴ Boolean() ✴ Object() ✴ Array() ✴ Function() ✴ Date() ✴ RegExp() ✴ Error()
✴ EvalError() ✴ RangeError() ✴ ReferenceError() ✴ SyntaxError() ✴ TypeError() ✴ URIError()

Host objects are not part of the ECMAScript implementation, but are available as objects during execution. Of course, the availability and behavior of a host object depends completely on what the host environment provides. For example, in the web browser environment the window/head object and all of its containing objects (excluding what JavaScript provides) are considered host objects: user-defined object, BOM and DOM

* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?

  function Person(){} is function declaration.

  var person = Person()， person is the obj returned by Person.

  var person = new Person() is function constructor, person is a instance of class Person


* What's the difference between `.call` and `.apply`?

.call/.apply can be used for changing context of a function.

.call(obj,parameter1[,parameter2,parameter3])

.apply(obj,[parameter1,parameter2,parameter3,...])

* Explain `Function.prototype.bind`.

use bind to change context of a function(ES5)

var targetElem = document.getElementById("imp");

var target=document.getElementById("work");

targetElem.conclick=fn.bind(target);//target will be the obj that be accessed by fn, not targetElem, as bind() already change the context from targetElem to target


* When would you use `document.write()`?

The write() method is mostly used for testing: If it is used after an HTML document is fully loaded, it will delete all existing HTML.

When this method is not used for testing, it is often used to write some text to an output stream opened by the document.open(). Writing to a document that has already loaded without calling document.open() will automatically perform a document.open call. Once you have finished writing, it is recommended to call document.close(), to tell the browser to finish loading the page.

* What's the difference between feature detection, feature inference, and using the User Agent string?

Feature Detection is to verify if a feature works in a particular browser or not. The feature can be either a CSS property or a Java Script Method.

Feature inference checks for a feature just like feature detection, but uses another function because it assumes it will also exist; eg: if x exists, we can assume that y exists.比如用document.getElementsByTagNameNS是否存在来判断是否是IE环境，以保证下面是用的feature是available的

if you request a HTTP request to web server with a specific user agent, the responded contents and data related to this particular browser will  be displayed.

feature detection reference:https://developer.mozilla.org/en-US/docs/Archive/Web/Browser_feature_detection

* Explain Ajax in as much detail as possible.

Ajax use XMLHttpRequest object to communicate with web server, send and receive information of Json,XML,HTML format. it's asynchronous, so it can do all of this without having to refresh the page. This lets you update portions of a page based upon user events

* What are the advantages and disadvantages of using Ajax?

advantage：it's asynchronous, so it can do all of this without having to refresh the page. This lets you update portions of a page based upon user events

disadvantage：Security is less in AJAX application as all files are downloaded at client side;
JavaScript disabled browsers cannot use the application

* Explain how JSONP works (and how it's not really Ajax).
  While it is not possible to make a typical AJAX request to a different origin, it is possible to include a <script> from a different origin.Using this method, JSONP is able to work around the same-origin policy.

  A JSONP response is the callback function. A regular AJAX endpoint would simply respond with a string of JSON.A JSONP response, on the other hand, is actually an executable script that calls a designated JSONP callback function, passing a JSON string as a parameter.

  The way a typical JSONP call works is like this:
  1.create a new <script> tag using window.createElement(）
  2.set the src attribute to the desired JSONP endpoint
  3.add the <script> to the <head> of the DOM
  4.once loaded, the script passes data to a local callback function

  Limitation: Since a JSONP call is made by the inclusion of a script tag, requests are restricted to the HTTP GET method. There is no way to do a PUT or POST request with JSONP.

  This is an implementation:

    <script type="text/javascript">
          function onCustomerLoaded(result, methodName) {
              var html = '<ul>';
              for (var i = 0; i < result.length; i++) {
                  html += '<li>' + result[i] + '</li>';
                }
                html += '</ul>';
                document.getElementById('divCustomers').innerHTML = html;
              }
    </script>
    <script type="text/javascript" src="http://www.yiwuku.com/myService.aspx?jsonp=onCustomerLoaded"></script>
    -- return with onCustomerLoaded([“customername1","customername2"]);

* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
  Hoisting is JavaScript's default behavior of moving declarations to the top of function or global code. For that reason, it is recommended to always declare variables at the top of their scope (the top of global code and the top of function code)
* Describe event bubbling.
  event bubbling, the event is first captured and handled by target element and then propagated to outer elements(father).
* What's the difference between an "attribute" and a "property"?
  reference:http://lucybain.com/blog/2014/attribute-vs-property/
* Why is extending built-in JavaScript objects not a good idea?
  Changing the behaviour of an object that will only be used by your own code is fine. But when you change the behaviour of something that is also used by other code there is a risk you will break that other code.

  When it comes adding methods to the object and array classes in javascript, the risk of breaking something is very high, due to how javascript works. Long years of experience have taught me that this kind of stuff causes all kinds of terrible bugs in javascript
* Difference between document load event and document DOMContentLoaded event?
  The DOMContentLoaded event is fired when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. A very different event load should be used only to detect a fully-loaded page. It is an incredibly popular mistake to use load where DOMContentLoaded would be much more appropriate, so be cautious.
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`


#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP methods? List all HTTP methods that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Who inspires you in the front-end community?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).

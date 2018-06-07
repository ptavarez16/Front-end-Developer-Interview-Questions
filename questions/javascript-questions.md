# JS Questions:

### Explain event delegation
Event delegation allows you to avoid adding event listeners to specific nodes;
instead, the event listener is added to one parent.  That event listener
analyzes bubbled events to find a match on child elements.

### Explain how `this` works in JavaScript
The general idea of this is that it is a reference to an object that is
determend by where the function is called. This assoction happens at runtime
when the function is invoked, rather than when it is written.

### Explain how prototypal inheritance works
the core idea of Prototypal Inheritance is that an object can point to another
object and inherit all its properties. The main purpose is to allow multiple
instances of an object to share common properties, hence, the Singleton Pattern.

### What do you think of AMD vs CommonJS?
JavaScript Modules are small units of code, which is independent and reusable.
Their functionality is distinct, which allows them to be added and removed
without the system being disrupted. It seems to mimic how classes are used in
Java or Python.

Modules are self-contained. If a module is decoupled from other pieces of code,
it is much easier to update it. This makes the programmer a lot less
intimidating to go through the program.  It solves the namespace ambiguity
allowing the objects to be created in publicly accessible namespaces while
the functions in it are private. Modules are reusable which eliminates the
duplicacy in code and saves huge amount of time.

**CommonJS** interacts with the module system which uses the keyword require and
exports. `require` is a function which is used to import functions from another
module, on the other side, `export` is an object where you can export any
function which is put into it. CommonJS basically specifies that you need to
have a require() function in order to fetch dependencies, an export method to
export the contents from another module and a module identifier (describes the
module location) that is used to require the dependencies.

**Asynchronous Module Definition** (AMD), as the name indicates, supports asynchronous loading of the module. The requested modules are loaded in a
non-blocking manner in the background and once the loading is completed, the
callback function is executed.The define function takes the first argument as
an array of dependency modules. These modules can be functions, objects,
contructors, JSON, strings etc. RequireJS implements AMD API. The plain
javascript files and modules are loaded by using script tags. An optimizing
tool is included in it which can be run while deploying our code for better
performance.


### Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
An IIFE (pronouced as ‘iffy’) is an abbreviation for Immediately Invoked
Function Expression. It is a common Javascript design pattern used by popular
JS libraries such as jQuery, Backbone.js. Purpose of using an IIFE is to
maintain code inside of a local scope. This means, to be able to use global
object inside of IIFE, you will need to pass it as arguments.

As for an explanation, the following code doesn’t work as an IIFE because it is
a function declaration, it does invoked immediately due to its parenthesis at
the end, but there are downsides to using this approach.

`function foo() {}();`

*First, it unnecessarily takes up a name in the global namespace, increasing the possibility of name collisions. Second, the intentions of this code aren’t as self-documenting as an IIFE. And third, because it is named and isn’t self-documenting it might accidentally be invoked more than once.*
 
  #### What needs to be changed to properly make it an IIFE?
  
  For the above code to be considered an IIFE, it needs to be an anonymous function, a function without a name, this is because IIFE needs to be Invoked Immediately without invoking it a function name. We also need to wrap the anonymous function with parenthesis, so the Javascript parser treats our anonymous function as a function expression.

  `(function() {}());`

  *A function expression is when you assign a function to a variable or property of an object. Anything that is a Javascript expression, including function expression, returns a value.*
  
### What's the difference between a variable that is: `null`, `undefined` or undeclared?
- `undefined` is a variable that has been declared but no value exists and is a type of itself ‘undefined’.
- `null` is a value of a variable and is a type of object.
- **undeclared** is a variable that has been declared without ‘var, let, or const’ keyword.

  #### How would you go about checking for any of these states?
  To check, I'd use the typeof operator like so:
  ```javascript
    if (typeof(a) == "undefined") {
      // this will be executed
      console.log("a is undeclared or undefined");
    }
    else {
      console.log("a is declared and defined");
    }
  ```
  
### What is a closure, and how/why would you use one?

Closures are inner functions inside of an outer function. They have their own local scope and have access to outer function’s scope, parameters (but NOT arguments object), and they also have access to global variables.

Closures is a neat way to deal with scope issues. Reasons we use Closures is because Javascript is a function-level scope rather than as with other languages, block-level scope and Javascript is an asynchronous/event driven language. Example that Closure is frequently used is jQuery (ex. click()).

### Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
`forEach` is similar to a `for` loop. The following two code examples effectively accomplish the same thing.

```javascript
var array = [1,2,3];
for (var i = 0; i < array.length; i++){
  console.log(i);
}
```

```javascript
var array = [1,2,3];
array.forEach(function(i){
  console.log(i);
});
```

`.map()` iterates over an array, transforms each element of that array, and returns another array of the same size with the transformed members (example: transforming array of strings to uppercase).

`.forEach()` is great you need to execute a function for each individual element in an array. Good practice is that you should use .forEach() when you can’t use other array methods to accomplish your goal. I know this may sound vague, but .forEach() is a generic tool… only use it when you can’t use a more specialized tool. Use `.map()` when you want to transform elements in an array.

### What's a typical use case for anonymous functions?
Anonymous Functions are function expressions rather than the regular function declaration which are statements. Function expressions are more flexible. We can assign functions to variables, object properties, pass them as arguments to other functions, and even write a simple one line code enclosed in an anonymous functions.

A typical example would be an anonymous function used by popular frameworks used as IIFE (Immediate Invoked Function Expression).

### How do you organize your code? (module pattern, classical inheritance?)
### What's the difference between host objects and native objects?
Objects are divided from which environment and language they are supplied: Host Objects and Native Objects.

**Host Objects** are objects supplied by a certain environment. They are not always the same because each environment differs and contains host objects that accommodates execution of ECMAScript. Example, browser environment supplies objects such as window. While a node.js/server environment supplies objects such as NodeList.

**Native Objects** or Built-in Objects are standard built-in objects provided by Javascript. Native objects is sometimes referred to as ‘Global Objects’ since they are objects Javascript has provided natively available for use.

### Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
`function Person() {}` declares a function statement (statements perform an action) but does not execute, however, it does get registered into the global namespace.

In `var person = Person()`, a variable ‘var person’ has been defined and contains a value reference to a Person function. Any JavaScript Expressions (including Function Expressions) always returns a value. This may also be an Anonymous function if no name has been assign to a function but wrapped in parenthesis to be interpreted as an expression.

In `var person = new Person()`, a function constructor is being called by adding the keyword ‘new’. We are instantiating a new object of the Person class constructor. A function declaration is just a regular function unless it has been instantiated, it then becomes a class constructor.

### What's the difference between `.call` and `.apply`?
Invoking a function with .apply and .call allows us to point an object to the invoked function by passing in the object as first argument and second argument (and so on) as its values.
The function’s ‘this’ keyword will be manipulated when invoked with .apply or .call.
From what I understand, .apply and .call are methods we use to assign the ‘this’ keyword from the invoked function to reference to an object for the duration of the method invocation.

`.call`
- Counts the number of arguments separated by Comma
- Accepts one or more arguments as objects and requires to be listed explicitly, means, it is a fixed number of arguments

`.apply`
- Uses array as second argument
- This method is used if you don’t know the number of arguments to be passed or the arguments is already in an array.

### Explain `Function.prototype.bind`.
### What's the difference between feature detection, feature inference, and using the UA string?
**Feature Detection** is just a way of determining if a feature exists in certain browsers. A good example is a modern HTML5 feature ‘Location’.

**Feature Inference** is when you have determined a feature exists and assumed the next web technology feature you are implementing unto your app exists as well. Its usually bad practice to assume, so its better to explicitly specify features you want to detect and plan a fallback action.

**UA String** or User Agent String is a string text of data that each browsers send and can be access via navigator.userAgent. These “string text of data” contains information of the browser environment you are targeting.
If you open your console and run: `navigator.userAgent`, you’ll see it outputs a “string text of data” containing complete information of the environment you are currently using. Since this is an old way of doing detection, this method can be easily spoofed, thus, may not be the best route to take.

### Explain Ajax in as much detail as possible.
 AJAX is the use of JavaScript to send and receive using HTTP without reloading the page. AJAX is an acronym for asynchronous JavaScript and XML, and is used as a technique for creating client-side asynchronous web applications. AJAX is considered a group of technologies. HTML and CSS can be used in combination to mark up and style information. JavaScript and the XMLHttpRequest object provide the method for exchanging data asynchronously between the browser and the server.
 
 AJAX, sends and retrieves data from a server asynchronously. This enables the web application to continue running and dynamically display. It allows the user to interact with the information presented on the page, avoiding full page reloads.
 
### What are the advantages and disadvantages of using Ajax?
Advantages:
- Improved user experience
- Asynchronous processing
- Reduced server hits and network load
- Platform and architecture neutrality
- Multibrowser support
- Faster page renders and improved response times

Disadvantages:
- Massive usage and dependency on JavaScript (JavaScript is implemented differently for various browsers)
- Might not be well suited for designing mobile applications
- Makes your web page difficult to debug
- Increase the load on the web server

### Explain how JSONP works (and how it's not really Ajax).
### Have you ever used JavaScript templating?
Yes I have!
  #### If so, what libraries have you used?
  I have experience with Handlebars and have looked into Pug.
  
### Explain "hoisting".
Hoisting is JavaScript's default behavior of moving declarations to the top. (**Note** JavaScript only hoists declarations, not initializations.)

### Describe event bubbling.
Event bubbling occurs when a user interacts with a nested element and the event propagates up (“bubbles”) through all of the ancestor elements.

### What's the difference between an "attribute" and a "property"?
**Attribute**
- Defined by HTML, all definitions inside HTML tag are attributes.
- The type of attributes is always string.
- Attribute which has a default value doesn't change when corresponding property changes.

**Property**
- Properties belong to DOM, the nature of DOM is an object in JavaScript. We can get and set properties as we do to a normal object in JavaScript and properties can be any types.

### Why is extending built-in JavaScript objects not a good idea?

When you extend an object, you change its behaviour.

Changing the behaviour of an object that will only be used by your own code is fine. But when you change the behaviour of something that is also used by other code there is a risk you will break that other code.

When it comes adding methods to the object and array classes in javascript, the risk of breaking something is very high, due to how javascript works. Long years of experience have taught me that this kind of stuff causes all kinds of terrible bugs in javascript.

If you need custom behaviour, it is far better to define your own class (perhaps a subclass) instead of changing a native one. That way you will not break anything at all.

The ability to change how a class works without subclassing it is an important feature of any good programming language, but it is one that must be used rarely and with caution.

### Difference between document load event and document DOMContentLoaded event?
The DOMContentLoaded event is fired when the document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading (the load event can be used to detect a fully-loaded page).

### What is the difference between `==` and
The == operator will compare for equality after doing any necessary type conversions. The ===operator will not do the conversion, so if two values are not the same type === will simply return false.

### Explain the same-origin policy with regards to JavaScript.
The same-origin policy helps prevent malicious attacks by stopping code from another site executing on your site. An attacks like this is known as a Cross Site Scripting attack.

The “origin” is the same if three things are the same: the protocol (http vs. https), the domain (subdomain.yoursite.com vs. yoursite.com vs. google.com), and the port (:80 vs. :4567). If all three of these line up, then JS views the sites as the same, and code is executed. If any of them are different then the code is marked as potentially malicious and is not run.

### Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```

**Answer**
```javascript
let duplicate = function (arr) {
  return arr.concat(arr)
}

// Array.prototype.duplicate = function () {
//   return this.concat(this)
// }
```

### Why is it called a Ternary operator, what does the word "Ternary" indicate?
“Ternary” indicates three, and a ternary expression accepts three operands, the test condition, the “then” expression and the “else” expression.

### What is `"use strict";`? what are the advantages and disadvantages to using it?
‘use strict’ is a statement used to enable strict mode to entire scripts or individual functions. Strict mode is a way to opt in to a restricted variant of JavaScript.

**Advantages**
- Makes it impossible to accidentally create global variables.
- Makes assignments which would otherwise silently fail to throw an exception.
- Makes attempts to delete undeletable properties throw (where before the attempt would simply have no effect).
- Requires that function parameter names be unique.
this is undefined in the global context.
- It catches some common coding bloopers, throwing exceptions.
- It disables features that are confusing or poorly thought out.

**Disadvantages**
- Many missing features that some developers might be used to.
- No more access to function.caller and function.arguments.
- Concatenation of scripts written in different strict modes might cause issues.

### Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`

```javascript
for (let i = 1; i <= 100; i++) {
  if (i % 3 === 0 && i % 5 === 0) {
    console.log('Fizzbuzz')
  } else if (i % 3 === 0 ) {
    console.log('Fizz')
  } else if (i % 5 === 0) {
    console.log('Buzz')
  } else {
    console.log(i)
  }
}
```
### Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
The primary reason why global variables are discouraged in javascript is because, in javascript all code share a single global namespace, also javascript has implied global variables i.e. variables which are not explicitly declared in local scope are automatically added to global namespace. Relying too much on global variables can result in collisions between various scripts on the same page.

### Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
 The load event fires at the end of the document loading process. At this point, all of the objects in the document are in the DOM, and all the images, scripts, links and sub-frames have finished loading. To execute anything post document load, we fire these events. ‘DOMContentLoaded’ or jQuery’s loaded are another options.

### Explain what a single page app is and how to make one SEO-friendly.
### What is the extent of your experience with Promises and/or their polyfills?
### What are the pros and cons of using Promises instead of callbacks?
### What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
### What tools and techniques do you use debugging JavaScript code?
### What language constructions do you use for iterating over object properties and array items?
### Explain the difference between mutable and immutable objects.
- A **mutable** object is an object whose state can be modified after it is created.
- An **immutable** object is an object whose state cannot be modified after it is created.
-
  ### What is an example of an immutable object in JavaScript?
  ### What are the pros and cons of immutability?
  ### How can you achieve immutability in your own code?
  
### Explain the difference between synchronous and asynchronous functions.
### What is event loop?
This is a constantly running process that checks if the call stack is empty. Imagine it like a clock and every time it ticks it looks at the Call Stack and if it is empty it looks into the Event Queue. If there is something in the event queue that is waiting it is moved to the call stack. If not, then nothing happens.

  ### What is the difference between call stack and task queue?
  **Call Stack**
  
  JavaScript has a single call stack in which it keeps track of what function we’re currently executing and what function is to be executed after that. But first — what’s a stack? A stack is an array-like data structure but with some limitations — you can only add items to the back and only remove the last item. Another example is a pile of plates — you put them on top of each other and at any time you can only remove the top one. When you’re about to execute a function it is added on the call stack. Then if that function calls another function — the other function will be on top of the first one in the call stack.
  
  **Event Queue**
  
  Every time you call a setTimeout function or you do some async operation — it is added to the Event Table. This is a data structure which knows that a certain function should be triggered after a certain event. Once that event occurs (timeout, click, mouse move) it sends a notice. Bear in mind that the Event Table does not execute functions and does not add them to the call stack on it’s own. It’s sole purpose is to keep track of events and send them to the Event Queue.

  The Event Queue is a data structure similar to the stack — again you add items to the back but can only remove them from the front. It kind of stores the correct order in which the functions should be executed. It receives the function calls from the Event Table, but it needs to somehow send them to the Call Stack? This is where the Event Loop comes in.
  
  
### Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
### What are the differences between variables created using `let`, `var` or `const`?
### What are the differences between ES6 class and ES5 function constructors?
### Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?
### What advantage is there for using the arrow syntax for a method in a constructor?
### What is the definition of a higher-order function?
A higher-order function is a function that can take another function as an argument, or that returns a function as a result.

### Can you give an example for destructuring an object or an array?
### ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
### Can you give an example of a curry function and why this syntax offers an advantage?
### What are the benefits of using `spread syntax` and how is it different from `rest syntax`?
### How can you share code between files?
Through JavaScript imports and exports. This is how you can write code in one file and share that code so it can be used by another file or files.

### Why you might want to create static class members?
Static method calls are made directly on the class and are not callable on instances of the class. Static methods are often used to create utility functions.

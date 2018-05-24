# Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
**Answer:** `1020`

*Question: What will be the output of the code below?*
```javascript
console.log(0.1 + 0.2 == 0.3);

```
**Answer:** `false`

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
**Answer:**
```javascript
let add = function (a, b) {
  return a && b ? (a + b) : function (c) {
    return (a + c)
  }
}
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
**Answer: `'goh angasal a m\'i'`**

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
**Answer:** `bar`

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

**Answer:**

First alert `Hello World` | Second alert `ReferenceError: bar is not defined`

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
**Answer:** `foo.length = 2`

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

**Answer:** `undefined`

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```
**Answer:** `one`, `three`, `two`

*Question: What is the difference between these four promises?*
```javascript
doSomething().then(function () {
  return doSomethingElse();
});

doSomething().then(function () {
  doSomethingElse();
});

doSomething().then(doSomethingElse());

doSomething().then(doSomethingElse);
```

**Answer:**
```javascript
doSomething().then(function () {
  return doSomethingElse();
});

"'undefined' will be returned and passed down to doSomethingElse"
```

```javascript
doSomething().then(function () {
  doSomethingElse();
});

"Nothing is returned and 'undefined' passed down to doSomethingElse"
```
```javascript
doSomething().then(doSomethingElse());

"Cannot invoke a function within a promise chain. Undefined is passed down into doSomethingElse"
```

```javascript
doSomething().then(doSomethingElse);

"Correct promise chain syntax. The result of doSomething is passed down to doSomethingElse"
```

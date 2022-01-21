# Optimized.JS

This package aims to optimize your JavaScript where speed it critical. It has long been known that the JS for-loop is the fastest method of looping through Arrays, but they have always been more of a pain to code. The built-in JavaScript Array prototypes are so user-friendly, but also so slow. It is a mystery how they can be so much slower than a for-loop. This package provides shorthands for the most efficient ways of looping through arrays.

This is part of my larger goal to make a program that **fully optimizes** your JavaScript.

# JavaScript For-Loops

In JavaScript, you can loop through any array with `forEach`, it is simple and (for most cases) fast enough. The built-in JS Array prototypes are getting faster with every new version, but they are still not as fast as a for-loop. **All of the Array functions in this project are as fast as a for-loop.**

```js
let array = [1, 2, 3, 4, 5];

// this is the fastest way of looping through an array
for (var i = 0; i < array.length; i++) {
	let elem = array[i];

	/* do something great */
}

// this is much more convenient, but slow
array.forEach((elem) => {
	/* do something great */
});

// I have combined them into this (80% faster than Array.prototype.forEach)
forEach(array, (elem) => {
	/* do something great */
});
```

# Objects

Another downfall of the Array prototypes is that they are for Arrays (as the name might suggest). It is because of this that I have made this library work on both Objects and Arrays in the same container function. I do this mainly because it is monotonous to implement into both the for-loops and the protorypes. **All of the array functions in this project also work on objects**.

# Functions

These functions are made to be easy to use, just like JavaScript's convenient built-ins.

```js
import {forEach, filter, map} = require("optimized.js");

//
// For use with Arrays
//

const arr = [1, 2, 3, 4, 5, 6];

// Array.prototype.forEach alternative (80% faster)
forEach(arr, (elem, i) => {/* do something */});

// Array.prototype.filter alternative (70% faster)
filter(arr, (elem, i) => {/* do something */});

// Array.prototype.map alternative (60% faster)
map(arr, (elem, i) => {/* do something */});

//
// For use with Objects
//

const obj = {a: 1, b: 2, c: 3};

// Array.prototype.forEach alternative (80% faster)
forEach(obj, (elem, i, key) => {/* do something */});

// Array.prototype.filter alternative (70% faster)
filter(obj, (elem, i, key) => {/* do something */});

// Array.prototype.map alternative (60% faster)
map(obj, (elem, i, key) => {/* do something */});
```

# Example

Because these behave the same way as their prototype alternatives, this example is for use with an object.

```js
import {map} = require("optimized.js");

const obj = {a: 1, b: 8, x: 23, y: 1, z: 53};

const greaterThanTen = filter(obj, (elem, i, key) => elem > 10); // {x: 23, z: 53}

const addEightyEight = map(greaterThanTen, (elem, i, key) => elem + 88); // {x: 111, z: 141}
```

# Notes

The team behind JS is constantly improving their built-in functions. There are some cases where the difference between my functions and the prototypes are minimal. My functions perform best when there are lots of items and with non-empty arrays. I made this because I needed it for my game development. I wanted maximum performance, but I was tired of writing for-loops. This is much more elegant. I do plan on adding more functionality and even a code parser/optimizer in the future. If you need this in CommonJS, let me know. Personally, I love CommonJS more. Thanks!

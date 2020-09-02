# Refactoring

[Home](https://sayefdeen.github.io/reading-notes301/)

## Concepts of Functional Programming in Javascript

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

The first fundamental concept we learn when we want to understand functional programming is **pure functions**, but how to know we know if a function is pure?

1. It returns the same result if given the same arguments (it is also referred as deterministic).

2. It does not cause any observable side effects.

```javascript
// not_Pure Function
let PI = 3.14;

const calculateArea = (radius) => radius * radius * PI;

calculateArea(10); // returns 314.0

// Pure function
let PI = 3.14;

const calculateArea = (radius, pi) => radius * radius * pi;

calculateArea(10, PI); // returns 314.0
```

Why is this an impure function? Simply because it uses a global object that was not passed as a parameter to the function.

## Immutability

When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

```javascript
var values = [1, 2, 3, 4, 5];
var sumOfValues = 0;

for (var i = 0; i < values.length; i++) {
  sumOfValues += values[i];
}

sumOfValues; // 15
```

For each iteration, we are changing the i and the sumOfValue state. But how do we handle mutability in iteration? **Recursion**!

```javascript
let list = [1, 2, 3, 4, 5];
let accumulator = 0;

function sum(list, accumulator) {
  if (list.length == 0) {
    return accumulator;
  }

  return sum(list.slice(1), accumulator + list[0]);
}

sum(list, accumulator); // 15
list; // [1, 2, 3, 4, 5]
accumulator; // 0
```

# THE CALL STACK

[Home](https://sayefdeen.github.io/reading-notes301/)

## Call stack

A mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

```javascript
function greeting() {
  // [1] Some codes here
  sayHi();
  // [2] Some codes here
}
function sayHi() {
  return 'Hi!';
}

// Invoke the `greeting` function
greeting();
```

we start with an empty Call Stack. Whenever we invoke a function, it is automatically added to the Call Stack. Once the function has executed all of its code, it is automatically removed from the Call Stack. Ultimately, the Stack is empty again.

The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

At the most basic level, a call stack is a data structure that uses the Last In, First Out (**LIFO**) principle to temporarily store and manage function invocation (call).

**Temporarily store**: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

```javascript
function callMyself() {
  callMyself();
}

callMyself();
```

---

## JavaScript error messages && debugging

Most of your time as a developer is spent reading code followed by debugging that same code, most likely to be able to read it or solve an “unexpected feature” (Bugs).

### Types of error messages

1.  Reference errors

```javascript
console.log(foo); // Uncaught ReferenceError: foo is not defined
```

This is also a common thing when using const and let, they are hoisted like var and function but there is a time between the hoisting and being declared so when you try to access them a reference error occurs, the fact that this happens to let and const is called **Temporal Dead Zone (TDZ)**.

2.  Syntax errors

this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

```javascript
JSON.parse({ foo: 'bar' }); // Uncaught SyntaxError: Unexpected token o in JSON at position 1

// This can be solved by just fixing the syntax

JSON.parse('{"foo":"bar"}');
```

3.  Range errors

Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

```javascript
var foo = [];
foo.length = foo.length - 1; // Uncaught RangeError: Invalid array length
```

4.  Type Errors

Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

```javascript
var foo = {};
foo.bar; // undefined
foo.bar.baz; // Uncaught TypeError: Cannot read property 'baz' of undefined
```

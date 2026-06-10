# Passing Functions to Other Functions and Invoking Them on Demand

## Definition

In JavaScript, functions are **first-class citizens**, which means functions can:

- Be stored in variables
- Be passed as arguments to other functions
- Be returned from functions
- Be invoked later when needed

When a function is passed to another function and executed later, it is commonly called a **callback function**.

---

# Functions Are Values

Just like numbers and strings, functions can be assigned to variables.

```js
const greet = function () {
  console.log("Hello");
};

greet();
```

Output:

```txt
Hello
```

---

# Passing a Function as an Argument

```js
function greet() {
  console.log("Hello");
}

function execute(fn) {
  fn();
}

execute(greet);
```

Output:

```txt
Hello
```

Notice:

```js
execute(greet);
```

We pass the function itself, not the result of calling it.

---

# Understanding What Happens

```txt
greet -> Function Reference -> Passed into execute() -> execute calls fn()
```

---

# Function Reference vs Function Call

## Function Reference

```js
execute(greet);
```

Here we are passing the function.

---

## Function Call

```js
execute(greet());
```

Here we are calling the function immediately.

This is a very common beginner mistake.

---

# Example: Custom Callback

```js
function welcome() {
  console.log("Welcome User");
}

function process(callback) {
  callback();
}

process(welcome);
```

Output:

```txt
Welcome User
```

---

# Passing Anonymous Functions

Instead of creating a separate function:

```js
process(function () {
  console.log("Hello");
});
```

Output:

```txt
Hello
```

---

# Passing Arrow Functions

```js
process(() => {
  console.log("Hello");
});
```

Output:

```txt
Hello
```

This is very common in modern JavaScript.

---

# Real-World Example: Calculator

```js
function add(a, b) {
  return a + b;
}

function calculate(a, b, operation) {
  return operation(a, b);
}

console.log(calculate(10, 5, add));
```

Output:

```txt
15
```

---

# Multiple Operations

```js
function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

function calculate(a, b, operation) {
  return operation(a, b);
}

console.log(calculate(10, 5, add));
console.log(calculate(10, 5, multiply));
```

Output:

```txt
15
50
```

The same function behaves differently based on the callback passed.

---

# Invoking on Demand

Sometimes a function is passed now but executed later.

```js
function greet() {
  console.log("Hello");
}

function saveTask(callback) {
  console.log("Saving task...");

  callback();
}

saveTask(greet);
```

Output:

```txt
Saving task...
Hello
```

The callback is executed only when needed.

---

# Example with setTimeout

```js
function showMessage() {
  console.log("Hello After 2 Seconds");
}

setTimeout(showMessage, 2000);
```

Output after 2 seconds:

```txt
Hello After 2 Seconds
```

Here:

```js
showMessage
```

is passed to `setTimeout()` and executed later.

---

# Array Methods Use Callbacks

## map()

```js
const numbers = [1, 2, 3];

const doubled = numbers.map(function (num) {
  return num * 2;
});

console.log(doubled);
```

Output:

```txt
[2, 4, 6]
```

---

## Arrow Function Version

```js
const doubled = numbers.map(num => num * 2);
```

The function is passed to `map()` and called for each element.

---

# filter() Uses Callbacks

```js
const numbers = [1, 2, 3, 4, 5];

const evens = numbers.filter(num => num % 2 === 0);

console.log(evens);
```

Output:

```txt
[2, 4]
```

---

# Event Handling Example

```js
button.addEventListener("click", function () {
  console.log("Button Clicked");
});
```

When the button is clicked:

```txt
Button Clicked
```

The function is stored and executed later.

---

# Returning Functions

Functions can also return functions.

```js
function createGreeting() {
  return function () {
    console.log("Hello");
  };
}

const greet = createGreeting();

greet();
```

Output:

```txt
Hello
```

This concept is closely related to closures.

---

# Real-World Example: Success and Error Handlers

```js
function fetchData(onSuccess, onError) {
  const success = true;

  if (success) {
    onSuccess();
  } else {
    onError();
  }
}

fetchData(
  () => console.log("Data Loaded"),
  () => console.log("Something Went Wrong")
);
```

Output:

```txt
Data Loaded
```

This pattern is used everywhere in JavaScript.

---

# Key Points

- Functions are first-class citizens in JavaScript.
- Functions can be passed as arguments.
- Functions passed to other functions are called callbacks.
- Pass function references, not function calls.
- Callbacks allow behavior to be customized.
- `setTimeout()`, `map()`, `filter()`, and event listeners use callbacks.
- Functions can be executed immediately or on demand.
- Understanding callbacks is essential for asynchronous JavaScript, promises, and event handling.

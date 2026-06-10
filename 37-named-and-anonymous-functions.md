# Differences Between Named Functions and Anonymous Functions

## Definition

Functions in JavaScript can be:

1. **Named Functions** – Functions that have a name.
2. **Anonymous Functions** – Functions that do not have a name.

Both can perform the same tasks, but they differ in readability, debugging, hoisting behavior, and common use cases.

---

# Named Function

A named function has an identifier (name).

```js
function greet() {
  console.log("Hello");
}

greet();
```

Output:

```txt
Hello
```

Here:

```js
greet
```

is the function name.

---

# Anonymous Function

An anonymous function has no name.

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

The function itself has no name.

It is stored in the variable `greet`.

---

# Visual Difference

## Named Function

```js
function greet() {}
```

```txt
Function Name → greet
```

---

## Anonymous Function

```js
function () {}
```

```txt
No Function Name
```

---

# Syntax Comparison

## Named Function

```js
function add(a, b) {
  return a + b;
}
```

---

## Anonymous Function

```js
const add = function (a, b) {
  return a + b;
};
```

---

# Calling the Functions

## Named Function

```js
function greet() {
  console.log("Hello");
}

greet();
```

---

## Anonymous Function

```js
const greet = function () {
  console.log("Hello");
};

greet();
```

---

# Hoisting Difference

One of the biggest differences.

---

## Named Function Declaration

```js
sayHello();

function sayHello() {
  console.log("Hello");
}
```

Output:

```txt
Hello
```

Works because function declarations are hoisted.

---

## Anonymous Function Expression

```js
sayHello();

const sayHello = function () {
  console.log("Hello");
};
```

Output:

```txt
ReferenceError
```

Because only the variable declaration is hoisted, not the function assignment.

---

# Debugging Difference

Named functions provide clearer stack traces.

## Named Function

```js
function calculateTotal() {
  throw new Error("Something went wrong");
}

calculateTotal();
```

Error Stack:

```txt
calculateTotal
```

The function name appears in the stack trace.

---

## Anonymous Function

```js
const calculate = function () {
  throw new Error("Something went wrong");
};

calculate();
```

The stack trace may be less descriptive depending on the environment.

---

# Passing Functions as Arguments

Anonymous functions are commonly used as callbacks.

```js
setTimeout(function () {
  console.log("Hello");
}, 1000);
```

Output after 1 second:

```txt
Hello
```

Creating a separate named function is often unnecessary.

---

# Array Methods Example

Anonymous functions are frequently used with array methods.

```js
const numbers = [1, 2, 3];

numbers.forEach(function (num) {
  console.log(num);
});
```

Output:

```txt
1
2
3
```

---

# Arrow Functions Are Usually Anonymous

```js
const greet = () => {
  console.log("Hello");
};
```

Technically the arrow function itself is anonymous.

It is assigned to the variable `greet`.

---

# Immediate Usage

Anonymous functions are useful when a function is needed only once.

```js
setTimeout(function () {
  console.log("Executed");
}, 1000);
```

No need to create:

```js
function execute() {
  console.log("Executed");
}
```

if it will be used only once.

---

# Recursion Difference

Named functions can easily call themselves.

```js
function countdown(n) {
  if (n === 0) return;

  console.log(n);

  countdown(n - 1);
}

countdown(3);
```

Output:

```txt
3
2
1
```

---

Anonymous functions cannot directly refer to themselves unless assigned to a variable.

```js
const countdown = function (n) {
  if (n === 0) return;

  console.log(n);

  countdown(n - 1);
};
```

This works because the variable name is used.

---

# Event Listener Example

## Anonymous Function

```js
button.addEventListener("click", function () {
  console.log("Clicked");
});
```

Very common.

---

## Named Function

```js
function handleClick() {
  console.log("Clicked");
}

button.addEventListener("click", handleClick);
```

Useful when the same handler is reused.

---

# When to Use Named Functions

Use named functions when:

- The function will be reused.
- The function contains complex logic.
- Better debugging is needed.
- The function should be self-documenting.
- Recursion is required.

Example:

```js
function calculateTax(amount) {
  return amount * 0.18;
}
```

---

# When to Use Anonymous Functions

Use anonymous functions when:

- The function is used only once.
- Passing callbacks.
- Event handlers.
- Array methods (`map`, `filter`, `forEach`).
- Short inline logic.

Example:

```js
users.map(function (user) {
  return user.name;
});
```

---

# Key Points

- Named functions have an explicit function name.
- Anonymous functions have no function name.
- Function declarations are hoisted.
- Anonymous function expressions are not fully hoisted.
- Anonymous functions are commonly used as callbacks.
- Named functions are easier to debug.
- Use named functions for reusable logic.
- Use anonymous functions for short, one-time operations.
- Many modern callbacks use anonymous arrow functions.
- Understanding both is essential for writing clean JavaScript.

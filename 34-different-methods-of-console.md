# Console Methods in JavaScript

## Definition

The `console` object provides methods for printing messages, debugging code, displaying data, measuring performance, and tracking application behavior.

Console methods are extremely useful during development and debugging.

---

# What is the Console?

The console is a developer tool available in browsers and Node.js.

Example:

```js
console.log("Hello World");
```

Output:

```txt
Hello World
```

---

# 1. console.log()

## Definition

`console.log()` is the most commonly used console method.

It prints information to the console.

### Example

```js
console.log("Hello World");
```

Output:

```txt
Hello World
```

---

### Multiple Values

```js
const name = "John";
const age = 25;

console.log(name, age);
```

Output:

```txt
John 25
```

---

### Logging Objects

```js
const user = {
  name: "John",
  age: 25
};

console.log(user);
```

Output:

```txt
{ name: "John", age: 25 }
```

---

# 2. console.error()

## Definition

`console.error()` displays error messages.

In browsers, these messages are usually shown in red.

### Example

```js
console.error("Something went wrong");
```

Output:

```txt
Something went wrong
```

---

### Real-World Example

```js
try {
  JSON.parse("{");
} catch (error) {
  console.error(error.message);
}
```

Output:

```txt
Unexpected end of JSON input
```

---

# 3. console.warn()

## Definition

`console.warn()` displays warning messages.

Warnings indicate potential issues that are not necessarily errors.

### Example

```js
console.warn("Password is too weak");
```

Output:

```txt
Password is too weak
```

---

### Use Case

```js
if (password.length < 8) {
  console.warn("Use a stronger password");
}
```

---

# 4. console.info()

## Definition

`console.info()` displays informational messages.

It behaves similarly to `console.log()` in most environments.

### Example

```js
console.info("Application started");
```

Output:

```txt
Application started
```

---

### Use Case

```js
console.info("User logged in successfully");
```

---

# 5. console.table()

## Definition

`console.table()` displays arrays and objects in a table format.

### Example

```js
const users = [
  { name: "John", age: 25 },
  { name: "Sara", age: 30 }
];

console.table(users);
```

---

# 6. console.clear()

## Definition

`console.clear()` clears the console.

### Example

```js
console.clear();
```

All previous console output is removed.

---

# 7. console.count()

## Definition

`console.count()` counts how many times a label has been logged.

### Example

```js
console.count("Click");
console.count("Click");
console.count("Click");
```

Output:

```txt
Click: 1
Click: 2
Click: 3
```

---

### Use Case

Tracking button clicks or function executions.

---

# 8. console.time()

## Definition

Starts a timer.

### Example

```js
console.time("loop");

for (let i = 0; i < 1000000; i++) {}

console.timeEnd("loop");
```

Output:

```txt
loop: 5ms
```

(Time varies by system.)

---

# 9. console.timeEnd()

## Definition

Stops a timer started by `console.time()`.

### Example

```js
console.time("task");

for (let i = 0; i < 1000000; i++) {}

console.timeEnd("task");
```

Output:

```txt
task: 5ms
```

---

# 10. console.group()

## Definition

Groups related logs together.

### Example

```js
console.group("User Details");

console.log("Name: John");
console.log("Age: 25");

console.groupEnd();
```

Output:

```txt
User Details
  Name: John
  Age: 25
```

---

# 11. console.groupEnd()

## Definition

Ends a group started by `console.group()`.

```js
console.group("Example");

console.log("Inside Group");

console.groupEnd();
```

---

# 12. console.dir()

## Definition

Displays an interactive list of object properties.

### Example

```js
const user = {
  name: "John",
  age: 25
};

console.dir(user);
```

Output:

```txt
{
  name: "John",
  age: 25
}
```

Useful for exploring complex objects.

---

# 13. console.trace()

## Definition

Displays the function call stack.

### Example

```js
function first() {
  second();
}

function second() {
  console.trace();
}

first();
```

Output:

```txt
Trace
  second
  first
```

Useful for debugging.

---

# 14. console.assert()

## Definition

Logs an error message if a condition is false.

### Example

```js
console.assert(5 > 10, "Condition failed");
```

Output:

```txt
Assertion failed: Condition failed
```

---

### Passing Condition

```js
console.assert(10 > 5, "Condition failed");
```

Output:

```txt
Nothing prints
```

---

# 15. console.debug()

## Definition

Used for debugging messages.

### Example

```js
console.debug("Debug information");
```

Output:

```txt
Debug information
```

In some environments, debug messages can be filtered separately.

---

# Browser vs Node.js

Most console methods work in both:

```txt
Browser Console
Node.js Terminal
```

Some methods may have slightly different formatting depending on the environment.

---

# Key Points

- The `console` object helps developers debug and monitor applications.
- `console.log()` is the most commonly used method.
- `console.error()` is used for errors.
- `console.warn()` is used for warnings.
- `console.info()` is used for informational messages.
- `console.table()` is excellent for viewing arrays of objects.
- `console.time()` and `console.timeEnd()` help measure performance.
- `console.trace()` helps identify where a function was called.
- Console methods are essential tools for JavaScript debugging and development.

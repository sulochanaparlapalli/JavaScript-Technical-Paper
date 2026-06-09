# Throwing Errors in JavaScript

## Definition

The `throw` keyword is used to manually generate (throw) an error in JavaScript.  
It stops normal execution and sends the error to be handled by a `try...catch` block.

---

## Why we use throw?

- To stop execution when invalid data is found
- To enforce rules in functions
- To make debugging easier
- To handle custom validation logic

---

## Example

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}

console.log(divide(10, 0));
```

### Output:
```
Error: Cannot divide by zero
```

---

## Handling Custom Errors

```js
try {
  divide(10, 0);
} catch (error) {
  console.log("Error message:", error.message);
}
```

### Output:
```
Error message: Cannot divide by zero
```

---

## Throwing Different Types of Errors

```js
throw new Error("General error");
throw new TypeError("Wrong type");
throw new ReferenceError("Variable not defined");
```

---

## Custom Validation Example

```js
function registerUser(username) {
  if (!username) {
    throw new Error("Username is required");
  }
  if (username.length < 3) {
    throw new Error("Username must be at least 3 characters");
  }
  return "User registered successfully";
}

try {
  console.log(registerUser("ab"));
} catch (err) {
  console.log(err.message);
}
```

---

## Key Points

- `throw` is used to generate custom errors
- It immediately stops function execution
- Always use with `try...catch`
- Helps in input validation and debugging

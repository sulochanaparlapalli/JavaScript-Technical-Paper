# Error Handling in JavaScript (try...catch)

## Definition

Error handling is used to handle runtime errors safely so that the program does not crash.

We use:
- try → code that may cause error
- catch → handles the error
- finally → runs always (optional)

---

## Basic Syntax

```js
try {
  // risky code
} catch (error) {
  // handle error
}
```

---

## Example

```js
try {
  let result = 10 / x; // error: x is not defined
  console.log(result);
} catch (error) {
  console.log("An error occurred:", error.message);
}
```

Output:

```
An error occurred: x is not defined
```

---

## How it works

1. Code runs inside try
2. If no error → catch is skipped
3. If error occurs → catch runs

---

## Example (No Error)

```js
try {
  let a = 10;
  let b = 5;
  console.log(a + b);
} catch (error) {
  console.log("Error occurred");
}
```

Output:

```
15
```

---

## finally block

Runs always whether error occurs or not.

```js
try {
  console.log("Trying code");
} catch (error) {
  console.log("Error");
} finally {
  console.log("Always runs");
}
```

Output:

```
Trying code
Always runs
```

---

## throw (Custom Error)

```js
function checkAge(age) {
  if (age < 18) {
    throw new Error("Not allowed");
  }
  return "Allowed";
}

try {
  console.log(checkAge(15));
} catch (error) {
  console.log(error.message);
}
```

Output:

```
Not allowed
```

---

## Error Object Properties

- error.message → description
- error.name → type of error
- error.stack → debugging info

---

## Key Points

- try → risky code
- catch → handles error
- finally → always runs
- throw → create custom error

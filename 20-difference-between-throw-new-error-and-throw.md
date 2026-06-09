# Difference Between `throw new Error()` and `throw "string"` in JavaScript

## 1. `throw new Error("message")` (Recommended)

```js
throw new Error("Error message here");
```

### What happens:
- Creates an **Error object**
- Provides useful debugging information:
  - message
  - name (Error type)
  - stack trace (where the error occurred)

### Example:

```js
try {
  throw new Error("Something went wrong");
} catch (err) {
  console.log(err.message);
  console.log(err.stack);
}
```

### Output:
- Error message is displayed
- Stack trace is available for debugging

---

## 2. `throw "Error message here"` (Not recommended)

```js
throw "Error message here";
```

### What happens:
- Throws a **string instead of an Error object**

### Example:

```js
try {
  throw "Something went wrong";
} catch (err) {
  console.log(err);
}
```

### Output:
- Only the string message is displayed

---

## Key Differences

| Feature        | `throw new Error()` | `throw "string"` |
|----------------|---------------------|------------------|
| Type           | Error object        | String           |
| Stack trace    | Yes                 | No               |
| Error name     | Yes                 | No               |
| Debugging      | Easy                | Hard             |
| Best practice  | Yes                 | No               |

---

## Conclusion

Always use:

```js
throw new Error("Descriptive error message");
```

Avoid:

```js
throw "Descriptive error message";
```

Using `Error` objects makes debugging easier and follows standard JavaScript best practices.

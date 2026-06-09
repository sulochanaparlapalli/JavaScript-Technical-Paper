
# Reading Error Messages and Stack Traces

## Definition

When JavaScript encounters an error, it provides an `error message` and a `stack trace`. These help developers understand:

- What went wrong
- Where it went wrong
- How the code execution reached that point

---

## Example

```js
function first() {
  second();
}

function second() {
  third();
}

function third() {
  console.log(name);
}

first();
```

Output:

```txt
ReferenceError: name is not defined
    at third (app.js:10:15)
    at second (app.js:6:3)
    at first (app.js:2:3)
```

---

## Understanding the Stack Trace

The `stack trace` shows the sequence of function calls that led to the error.

```txt
third()
↑
second()
↑
first()
```

The error happened in `third()`.

## Key Rule:

- The error happened in the top-most function in the stack trace (usually the first function listed after the message).

- But the real root cause is always inside that function.

---

## How to Read a Stack Trace

Example:

```txt
at third (app.js:10:15)
at second (app.js:6:3)
at first (app.js:2:3)
```

### Step-by-step:

1. Start from the first line after the error message
2. Go to the file and line number
  - app.js:10:15
  - File → app.js
  - Line → 10
  - Column → 15
3. Understand what value caused the crash

---

## Common Error Types

### ReferenceError

Occurs when a variable does not exist.

```js
console.log(age);
```

Output:

```txt
ReferenceError: age is not defined
```

---

### TypeError

Occurs when an operation is performed on an inappropriate type.

```js
const user = null;

console.log(user.name);
```

Output:

```txt
TypeError
```

---

### SyntaxError

Occurs when JavaScript cannot parse code.

```js
if (true {
  console.log("Hello");
}
```

Output:

```txt
SyntaxError
```

---

## Important Debugging Rules

- Read the error message first, not the code
- Always check the line number in the stack trace
- Don't assume the error is where you think it is
- The stack trace shows the actual execution path

---

## Key Points

- Read the first line carefully.
- Follow the stack trace from top to bottom.
- Error messages often tell you exactly what is wrong.

# Debugging Strategies

## Definition

Debugging is the process of finding, understanding, and fixing errors (bugs) in a program.

A good debugging strategy helps identify problems faster and reduces development time.

---

# 1. Use `console.log()`

The simplest and most common debugging technique.

```js
const age = 20;

console.log(age);
```

Output:

```txt
20
```

Use logs to check variable values and program flow.

---

# 2. Read Error Messages Carefully

When JavaScript throws an error, read:

- Error type
- Error message
- Line number

Example:

```js
console.log(user.name);
```

Output:

```txt
ReferenceError: user is not defined
```

The error tells you exactly what is wrong.

---

# 3. Use `console.table()`

Useful for arrays and objects.

```js
const users = [
  { name: "John", age: 25 },
  { name: "Sara", age: 30 }
];

console.table(users);
```

This displays data in a readable table.

---

# 4. Verify Inputs

Check whether functions receive the expected values.

```js
function add(a, b) {
  console.log(a, b);

  return a + b;
}

add(10, 20);
```

Output:

```txt
10 20
```

---

# 5. Isolate the Problem

Break large code into smaller parts.

Instead of debugging 100 lines at once:

```js
validateUser();
saveUser();
sendEmail();
```

Test each function separately.

---

# 6. Use Browser DevTools

Browser DevTools help inspect:

- Variables
- Network requests
- DOM elements
- Console output

Press:

```txt
F12
```

or

```txt
Right Click → Inspect
```

---

# 7. Use Breakpoints

Pause code execution at a specific line.

```js
const total = price * quantity;
```

Add a breakpoint and inspect values before execution continues.

---

# 8. Use the `debugger` Keyword

```js
const age = 20;

debugger;

console.log(age);
```

When DevTools are open, execution pauses at the `debugger` statement.

---

# 9. Check Data Types

Unexpected types cause many bugs.

```js
console.log(typeof value);
```

Example:

```js
console.log(typeof "10");
```

Output:

```txt
string
```

---

# 10. Reproduce the Bug Consistently

Find the exact steps that cause the bug.

```txt
1. Open page
2. Click Login
3. Enter empty password
4. Submit
```

If you can reproduce it, you can fix it.

---

# 11. Test Small Changes

Change one thing at a time.

Avoid changing multiple parts of the code simultaneously.

---

# 12. Use `try...catch`

Catch and inspect errors.

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

# Common Debugging Workflow

```txt
1. Reproduce the bug
2. Read the error message
3. Add console logs
4. Check inputs and outputs
5. Use breakpoints/debugger
6. Fix the issue
7. Test again
```

---

# Key Points

- Debugging means finding and fixing bugs.
- Start by reading error messages carefully.
- Use `console.log()` to inspect values.
- Use `console.table()` for structured data.
- Verify function inputs and outputs.
- Break large problems into smaller parts.
- Use DevTools and breakpoints.
- The `debugger` keyword pauses execution.
- Check data types with `typeof`.
- Fix one issue at a time and retest.


# What Happens When a Function Does Not Have a Return Statement

## Definition

If a function does not explicitly return a value, JavaScript automatically returns `undefined`.

---

## Example (No Return Statement)

```js
function add(a, b) {
  let result = a + b;
}

console.log(add(2, 3));
```

Output:

```txt
undefined
```

---

## Why?

The function executes, but since there is no `return` statement, JavaScript returns `undefined` by default.

---

## Example (with Return Statement)

```js
function add(a, b) {
  return a + b;
}

console.log(add(2, 3));
```

Output:

```txt
5
```

---

## Important Note

Even functions that do "work" inside them will still return `undefined` if nothing is returned.

```js
function test() {
  console.log("Hello");
}

console.log(test());
```

Output:

```txt
Hello
undefined
```

---

## Key Points

- Every function always returns a value in JavaScript.
- If no `return` is used, the default return value is `undefined`.
- `return` not only gives output but also stops function execution.

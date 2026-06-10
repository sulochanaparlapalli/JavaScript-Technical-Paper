# Difference Between `null` and `undefined`

## Definition

Both `null` and `undefined` represent the absence of a value in JavaScript.

However, they have different meanings:

- `undefined` means a value has not been assigned yet.
- `null` means a value was intentionally set to "no value".

Understanding this difference is important because both are commonly encountered in real-world JavaScript applications.

---

# What is `undefined`?

`undefined` is the default value assigned by JavaScript when a variable exists but has not been given a value.

```js
let name;

console.log(name);
```

Output:

```txt
undefined
```

JavaScript automatically assigns `undefined`.

---

## More Examples of `undefined`

### Missing Function Argument

```js
function greet(name) {
  console.log(name);
}

greet();
```

Output:

```txt
undefined
```

---

### Accessing a Non-Existing Object Property

```js
const user = {
  name: "John"
};

console.log(user.age);
```

Output:

```txt
undefined
```

---

### Function Without Return

```js
function test() {}

const result = test();

console.log(result);
```

Output:

```txt
undefined
```

---

# What is `null`?

`null` is a value that developers explicitly assign to indicate that a variable intentionally contains no value.

```js
let user = null;

console.log(user);
```

Output:

```txt
null
```

Unlike `undefined`, JavaScript does not assign `null` automatically.

The programmer chooses to use it.

---

## Example: Resetting a Value

```js
let loggedInUser = {
  name: "John"
};

loggedInUser = null;

console.log(loggedInUser);
```

Output:

```txt
null
```

This indicates that no user is currently logged in.

---

# Visual Understanding

## Undefined

```txt
Variable exists -> No value assigned -> undefined
```

---

## Null

```txt
Variable exists -> Developer intentionally clears value -> null
```

---

# Type Comparison

```js
console.log(typeof undefined);
```

Output:

```txt
undefined
```

---

```js
console.log(typeof null);
```

Output:

```txt
object
```

---

## Why Does `typeof null` Return "object"?

This is a historical bug in JavaScript that has existed since the early versions of the language.

```js
typeof null; // "object"
```

Even though it is technically incorrect, it remains for backward compatibility.

---

# Equality Comparison

### Loose Equality

```js
console.log(null == undefined);
```

Output:

```txt
true
```

JavaScript considers them loosely equal.

---

### Strict Equality

```js
console.log(null === undefined);
```

Output:

```txt
false
```

Because their types are different.

---

# Default Parameter Example

```js
function greet(name = "Guest") {
  console.log(name);
}

greet(undefined);
```

Output:

```txt
Guest
```

---

```js
greet(null);
```

Output:

```txt
null
```

Because default parameters only replace `undefined`, not `null`.

---

# Checking for Undefined

```js
let value;

if (value === undefined) {
  console.log("Value not assigned");
}
```

Output:

```txt
Value not assigned
```

---

# Checking for Null

```js
let value = null;

if (value === null) {
  console.log("Value intentionally empty");
}
```

Output:

```txt
Value intentionally empty
```

---

# Checking for Both

Sometimes you want to check for both `null` and `undefined`.

```js
if (value == null) {
  console.log("Missing value");
}
```

This matches:

```txt
null
undefined
```

But not:

```txt
0
false
""
```

---

# Nullish Coalescing Operator (`??`)

The `??` operator treats only `null` and `undefined` as missing.

```js
const username = null;

console.log(username ?? "Guest");
```

Output:

```txt
Guest
```

---

```js
const username = "";

console.log(username ?? "Guest");
```

Output:

```txt

```

(Empty string)

Unlike `||`, `??` does not treat empty strings as missing.

---

# Key Points

- `undefined` is assigned automatically by JavaScript.
- `null` is assigned intentionally by developers.
- `undefined` means "not assigned".
- `null` means "intentionally empty".
- `typeof undefined` is `"undefined"`.
- `typeof null` is `"object"` (a historical JavaScript bug).
- `null == undefined` is `true`.
- `null === undefined` is `false`.
- Use `===` for precise comparisons.
- Use `??` when you want to handle only `null` and `undefined`.

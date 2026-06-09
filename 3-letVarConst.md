# let, var, const

## Definition

JavaScript provides three ways to declare variables.

---

## var

```js
var name = "John";
```

Features:

- Function scoped
- Can be redeclared
- Can be reassigned

```js
var name = "John";
var name = "Mike";
```

---

## let

```js
let age = 20;
```

Features:

- Block scoped
- Cannot be redeclared
- Can be reassigned

```js
let age = 20;
age = 25;
```

---

## const

```js
const PI = 3.14;
```

Features:

- Block scoped
- Cannot be redeclared
- Cannot be reassigned

```js
const PI = 3.14;
PI = 3.1415;
```

Output:

```txt
TypeError
```

---

## Key Points

- Prefer `const` by default.
- Use `let` when values need to change.
- Avoid `var`.

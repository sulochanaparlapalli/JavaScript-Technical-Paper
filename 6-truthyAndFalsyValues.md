# Truthy and Falsy Values

## Definition

In JavaScript, values are automatically converted to `Boolean` (true or false) when used in conditions like `if`, `while`, etc.

This is called `type coercion`.

---

## Falsy Values

JavaScript has only `7 falsy values`:

```js
false
0
-0
""
null
undefined
NaN
```

Any value NOT in this list is truthy.

---

## Example

```js
if ("") {
  console.log("Hello");
}
```

Output:

```txt
(nothing will be printed)
```

Nothing is printed. Because "" is falsy.

---

## Truthy Example

```js
if ("JavaScript") {
  console.log("Learning JS");
}
```

Output:

```txt
Learning JS
```

---

Other truthy examples:

```js
"0"
"false"
[]
{}
1
-1
```

## Common Mistake

```js
let score = 0;

if (!score) {
  console.log("No score");
}
```

Output:

```txt
No score
```

Even though `0` is a valid value.

---

## Key Points

- JavaScript automatically converts values to Boolean in conditions
- Only `7 falsy values exist`
- Everything else is truthy
- Be careful when using `!value` because it may give unexpected results

# 11. Different Types of Loops

## Definition

Loops are used to execute a block of code repeatedly until a condition becomes false.

---

## 1. for Loop

Used when the number of iterations is known.

```js
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

Output:

```txt
1
2
3
4
5
```

---

## 2. while Loop

Used when the number of iterations is unknown.

```js
let i = 1;

while (i <= 5) {
  console.log(i);
  i++;
}
```

Output:

```txt
1
2
3
4
5
```

---

## 3. do...while Loop

Executes the block at least once, even if the condition is false.

```js
let i = 1;

do {
  console.log(i);
  i++;
} while (i <= 5);
```

---

## 4. for...of Loop

Used to iterate over iterable values like arrays, strings, etc.

```js
const colors = ["red", "blue", "green"];

for (const color of colors) {
  console.log(color);
}
```

Output:

```txt
red
blue
green
```

---

## 5. for...in Loop

Used to iterate over object keys (properties).

```js
const user = {
  name: "John",
  age: 25
};

for (const key in user) {
  console.log(key);
}
```

Output:

```txt
name
age
```

---

## Key Points

- Use `for...of` for arrays.
- Use `for...in` for objects.
- Use `while` when iterations are unknown.
- Use `do...while` to run the block at least once.
- Avoid using `for...in` for arrays (can cause unexpected results).

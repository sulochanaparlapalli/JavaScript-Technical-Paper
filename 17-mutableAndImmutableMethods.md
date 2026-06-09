# 17. Mutable and Immutable Methods

## Definition

Array methods in JavaScript are classified into:

- **Mutable methods** → modify the original array
- **Immutable methods** → return a new array without changing original

---

## Mutable Methods

These methods directly modify the original array in memory.

```js
push()
pop()
shift()
unshift()
splice()
sort()
reverse()
```

Example:

```js
const numbers = [1, 2];

numbers.push(3);

console.log(numbers);
```

Output:

```txt
[1, 2, 3]
```

---

## Immutable Methods

These methods return a **new array** without modifying the original.

```js
map()
filter()
slice()
concat()
```

Example:

```js
const numbers = [1, 2, 3];

const doubled = numbers.map(num => num * 2);

console.log(numbers);
console.log(doubled);
```

Output:

```txt
[1, 2, 3]
[2, 4, 6]
```

---

## Key Points

- Prefer immutable operations whenever possible.
- Immutable code is easier to debug and maintain because original data is not changed.
- It helps avoid unexpected side effects in programs.
- It improves code predictability and reliability.

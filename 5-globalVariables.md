# Why Using Global Variables Is Bad

## Definition

Global variables are variables declared outside functions and blocks.

---

## Example

```js
let total = 0;

function add() {
  total += 10;
}

function subtract() {
  total -= 5;
}

add();
subtract();

console.log(total);
```

Output:

```txt
5
```

---

## Problems

### Hard to Debug

Any function can change the value.

### Naming Conflicts

Two files may use the same variable name.

### Unexpected Side Effects

Changing one function may affect another.

---

## Better Approach

```js
function add(total) {
  return total + 10;
}
```

---

## Key Points

- Minimize global variables.
- Pass values through parameters.
- Prefer local variables.

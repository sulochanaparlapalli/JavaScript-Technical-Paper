# Pass By Value and Pass By Reference

## Definition

In JavaScript, values are handled differently based on their type:

- **Primitive types** are copied (Pass by Value)
- **Objects/Arrays are referenced (Pass by Reference-like behavior)**

---

## Pass By Value (Primitives)

Primitive values are copied into a new memory location.

Examples of primitives:

`number`, `string`, `boolean`, `null`, `undefined`, `bigint`, `symbol`

---

```js
let a = 10;
let b = a;

b = 20;

console.log(a);
console.log(b);
```

Output:

```txt
10
20
```

`b` gets a copy of `a`.
Changing `b` does not affect `a`.

---

## Pass By Reference (Objects/Arrays)

Objects are stored in memory, and variables store the reference (address), not the actual value.

```js
const person1 = {
  name: "John"
};

const person2 = person1;

person2.name = "Mike";

console.log(person1.name);
```

Output:

```txt
Mike
```

Both variables point to the same object in memory.
Changing one object affects the other.

---

## Creating a Copy

To avoid modifying the original object, we create a new copy using the spread operator.

```js
const person1 = {
  name: "John"
};

const person2 = { ...person1 };

person2.name = "Mike";

console.log(person1.name);
console.log(person2.name);
```

Output:

```txt
John
Mike
```

`person2` is a new copy of `person1`, so modifying it does not affect the original.

## Key Points

- **Pass by Value**: Primitives are copied by value.
- **Pass by Reference**: Objects/Arrays are referenced by memory address.
- **Copying**: Use the spread operator to create a new copy of an object.

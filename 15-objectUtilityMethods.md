# Popular Object Utility Methods

## Definition

Object utility methods help us work with object properties, values, copying, merging, freezing, and inspecting objects.

---

## Sample Object

```js
const user = {
  name: "John",
  age: 25,
  city: "Bangalore"
};
```

---

## `Object.keys()` **(Immutable)**

Returns all keys.

```js
console.log(Object.keys(user));
```

Output:

```txt
["name", "age", "city"]
```

---

## `Object.values()` **(Immutable)**

Returns all values.

```js
console.log(Object.values(user));
```

Output:

```txt
["John", 25, "Bangalore"]
```

---

## `Object.entries()` **(Immutable)**

Returns key-value pairs.

```js
console.log(Object.entries(user));
```

Output:

```txt
[
  ["name", "John"],
  ["age", 25],
  ["city", "Bangalore"]
]
```

---

## `Object.fromEntries()` **(Immutable)**

Converts key-value pairs into an object.

```js
const data = [
  ["name", "John"],
  ["age", 25]
];

console.log(Object.fromEntries(data));
```

Output:

```txt
{
  name: "John",
  age: 25
}
```

---

## `Object.assign()` **(Mutable)**

Copies or merges objects.

```js
const obj1 = {
  name: "John"
};

const obj2 = {
  age: 25
};

const result = Object.assign({}, obj1, obj2);

console.log(result);
```

Output:

```txt
{
  name: "John",
  age: 25
}
```

---

## `Object.freeze()` **(Mutable)**

Prevents modifications.

```js
const user = {
  name: "John"
};

Object.freeze(user);

user.name = "Mike";

console.log(user);
```

Output:

```txt
{
  name: "John"
}
```

---

## `Object.seal()` **(Mutable)**

Prevents adding or deleting properties.

```js
const user = {
  name: "John"
};

Object.seal(user);

user.name = "Mike";

console.log(user);
```

Output:

```txt
{
  name: "Mike"
}
```

---

## `Object.hasOwn()` **(Immutable)**

Checks whether a property exists.

```js
const user = {
  name: "John"
};

console.log(
  Object.hasOwn(user, "name")
);
```

Output:

```txt
true
```

---

## `hasOwnProperty()` **(Immutable)**

Checks whether a property exists.

```js
const user = {
  name: "John"
};

console.log(
  user.hasOwnProperty("name")
);
```

Output:

```txt
true
```

---

## `Object.getOwnPropertyNames()` **(Immutable)**

Returns all property names.

```js
const user = {
  name: "John",
  age: 25
};

console.log(
  Object.getOwnPropertyNames(user)
);
```

Output:

```txt
["name", "age"]
```

---

## `Object.create()` **(Immutable)**

Creates a new object using another object as a prototype.

```js
const person = {
  greet() {
    console.log("Hello");
  }
};

const user = Object.create(person);

user.greet();
```

Output:

```txt
Hello
```

---

## `Object.is()` **(Immutable)**

Checks whether two values are exactly the same.

```js
console.log(
  Object.is(10, 10)
);
```

Output:

```txt
true
```

---

## `Object.getPrototypeOf()` **(Immutable)**

Returns an object's prototype.

```js
const user = {
  name: "John"
};

console.log(
  Object.getPrototypeOf(user)
);
```

Output:

```txt
[Object: null prototype] {}
```

---

## `Object.setPrototypeOf()` **(Immutable)**

Sets an object's prototype.

```js
const animal = {
  sound() {
    console.log("Animal Sound");
  }
};

const dog = {};

Object.setPrototypeOf(
  dog,
  animal
);

dog.sound();
```

Output:

```txt
Animal Sound
```

---

## `Object.preventExtensions()` **(Mutable)**

Prevents adding new properties.

```js
const user = {
  name: "John"
};

Object.preventExtensions(user);

user.age = 25;

console.log(user);
```

Output:

```txt
{
  name: "John"
}
```

---

## `Object.isFrozen()` **(Immutable)**

Checks whether an object is frozen.

```js
const user = {
  name: "John"
};

Object.freeze(user);

console.log(
  Object.isFrozen(user)
);
```

Output:

```txt
true
```

---

## `Object.isSealed()` **(Immutable)**

Checks whether an object is sealed.

```js
const user = {
  name: "John"
};

Object.seal(user);

console.log(
  Object.isSealed(user)
);
```

Output:

```txt
true
```

---

## `Object.isExtensible()` **(Immutable)**

Checks whether new properties can be added.

```js
const user = {
  name: "John"
};

console.log(
  Object.isExtensible(user)
);
```

Output:

```txt
true
```

---

## Object Destructuring

Extract object values into variables.

```js
const user = {
  name: "John",
  age: 25
};

const { name, age } = user;

console.log(name);
console.log(age);
```

Output:

```txt
John
25
```

---

## Spread Operator (...)

Copies or merges objects.

```js
const user = {
  name: "John"
};

const updatedUser = {
  ...user,
  age: 25
};

console.log(updatedUser);
```

Output:

```txt
{
  name: "John",
  age: 25
}
```

---

## Key Points

- Useful for object inspection.
- Helpful when looping through objects.

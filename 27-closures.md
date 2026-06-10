# Closures

## Definition

A closure is a function that remembers and can access variables from its outer scope even after the outer function has finished executing.

In simple terms:

A closure allows a function to "remember" the environment in which it was created.

---

## Understanding Lexical Scope

Before learning closures, you need to understand lexical scope.

```js
const globalVar = "I am global";

function outer() {
  const outerVar = "I am outer";

  function inner() {
    console.log(globalVar);
    console.log(outerVar);
  }

  inner();
}

outer();
```

Output:

```txt
I am global
I am outer
```

The `inner()` function can access variables from its parent scope.

This is called **lexical scoping**.

---

## Basic Closure Example

```js
function outer() {
  const message = "Hello";

  function inner() {
    console.log(message);
  }

  return inner;
}

const myFunction = outer();

myFunction();
```

Output:

```txt
Hello
```

### What Happened?

1. `outer()` executes.
2. `message` is created.
3. `inner()` is returned.
4. Normally, local variables are removed after a function finishes.
5. However, `inner()` still remembers `message`.

This remembered relationship is called a **closure**.

---

## Closure with Parameters

```js
function greet(name) {
  return function () {
    console.log(`Hello ${name}`);
  };
}

const greetJohn = greet("John");

greetJohn();
```

Output:

```txt
Hello John
```

The returned function remembers the value of `name`.

---

## Closure Maintaining State

One of the most common uses of closures is preserving data.

```js
function counter() {
  let count = 0;

  return function () {
    count++;
    console.log(count);
  };
}

const increment = counter();

increment();
increment();
increment();
```

Output:

```txt
1
2
3
```

Notice that `count` is not reset.

The closure remembers its value between function calls.

---

## Why Does This Work?

```js
function counter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}
```

The returned function maintains a reference to `count`.

JavaScript keeps `count` in memory because the inner function still uses it.

---

## Multiple Closures

Each closure gets its own independent memory.

```js
function counter() {
  let count = 0;

  return function () {
    count++;
    console.log(count);
  };
}

const counter1 = counter();
const counter2 = counter();

counter1();
counter1();

counter2();
counter2();
```

Output:

```txt
1
2
1
2
```

Each counter has its own `count` variable.

---

## Data Privacy Using Closures

Closures can hide data from the outside world.

```js
function createBankAccount() {
  let balance = 1000;

  return {
    deposit(amount) {
      balance += amount;
      console.log(`Balance: ${balance}`);
    },

    getBalance() {
      return balance;
    }
  };
}

const account = createBankAccount();

account.deposit(500);

console.log(account.getBalance());
```

Output:

```txt
Balance: 1500
1500
```

The `balance` variable cannot be directly accessed.

```js
console.log(account.balance);
```

Output:

```txt
undefined
```

This creates private data.

---

## Closures in Event Handlers

```js
function setupButton(buttonName) {
  return function () {
    console.log(`${buttonName} clicked`);
  };
}

const saveButton = setupButton("Save");

saveButton();
```

Output:

```txt
Save clicked
```

The returned function remembers `buttonName`.

---

## Closures with setTimeout

```js
function delayedMessage(message) {
  setTimeout(function () {
    console.log(message);
  }, 2000);
}

delayedMessage("Hello");
```

Output after 2 seconds:

```txt
Hello
```

The callback remembers `message` even after the outer function has finished.

---

## Common Mistake with var

```js
for (var i = 1; i <= 3; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
```

Output:

```txt
4
4
4
```

All callbacks share the same `i`.

---

### Solution Using let

```js
for (let i = 1; i <= 3; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
```

Output:

```txt
1
2
3
```

`let` creates a new binding for each iteration.

---

## Advantages of Closures

- Preserve data between function calls.
- Create private variables.
- Reduce global variables.
- Useful for callbacks.
- Useful for event handlers.
- Useful for timers.
- Useful for module patterns.

---

## Disadvantages of Closures

- Consume additional memory.
- Can cause memory leaks if misused.
- Sometimes harder to debug.

---

## Key Points

- A closure is a function that remembers variables from its outer scope.
- Closures rely on lexical scoping.
- Variables remain available even after the outer function finishes.
- Closures can preserve state.
- Closures can create private variables.
- Every closure has its own memory.
- Widely used in modern JavaScript development.
- Closures are one of the most frequently asked JavaScript interview topics.

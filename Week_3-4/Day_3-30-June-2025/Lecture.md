# `this` in JavaScript

* `this` refers to the context in which a function or code runs.

# How `this` Is Determined

- In a method call (`obj.method()`), `this` is the object before the dot.
- As a standalone function call (`func()`):
  - In non-strict mode: `this` is the global object.
  - In strict mode: `this` is `undefined`.
- Using `call()`, `apply()`, or `bind()` sets `this` explicitly.
- Arrow functions inherit `this` from their defining scope and cannot change it.

# Special Cases

- **Constructor call** (`new Func()`): `this` is the newly created object.
- **Class methods**:
  - Instance methods: `this` is the instance.
  - Static methods: `this` is the class itself.
- **Global context** (top-level script):
  - In non-module code: `this` is `globalThis`.
  - In modules: `this` is `undefined`.

# Other Contexts

- **Getters/setters**: `this` is the object owning the property.
- **Event handlers**: `this` is the DOM element handling the event.
- **Callbacks**: `this` depends on how the callback is invoked (often `undefined` in strict mode).

# Value Coercion

- In non-strict mode, if `this` is `null`, `undefined`, or a primitive, it defaults to the global object or is wrapped in its object form.

# Summary

- `this` is set at **runtime**, based on how a function is called—not where it's defined.
- Arrow functions inherit `this` lexically.
- Use `new`, method calls, `call`/`apply`/`bind`, and contextual rules to control `this`.


# Asynchronous JavaScript Overview
- Asynchronous JavaScript allows running tasks independently without blocking other operations.
- It uses callbacks, promises, or async/await to handle delayed tasks.

# Callbacks

- A callback is a function passed into another function to run after completion.
- Example: calling one function inside another to maintain order.
- Used for sequences like order and production steps.
- Too many nested callbacks cause "callback hell", which makes code hard to read.

# Promises

- A promise has three states: pending, resolved, or rejected.
- Promises use `.then()` for success, `.catch()` for errors, `.finally()` for final actions.
- Promises can be chained to run tasks one after another.
- Errors stop further `.then()` chains but `.finally()` always runs.

# Async/Await

- Async/await is a cleaner way to write promise-based code.
- `async` makes a function return a promise.
- `await` pauses the function until the promise resolves.
- Use `try...catch` for error handling, and `finally` for code that always runs.

# Ice Cream Shop Example

- Simulates asynchronous tasks like placing orders and preparing ingredients.
- Uses objects to store available items and `setTimeout` to simulate delays.
- Shows how promises and async/await work in real time.
- `.catch()` handles errors like closed shops, and `.finally()` logs end-of-day actions.

# Key Points

- Callbacks run code after another function finishes.
- Promises improve structure and support chaining and error handling.
- Async/await makes async code look synchronous and easier to read.
- Use `setTimeout` to simulate delays in asynchronous flow.
- `finally` runs after every promise, whether resolved or rejected.
```

```
# Asynchronous JavaScript Code Examples

# Callback Example

```javascript
function order(callback) {
  setTimeout(() => {
    console.log('Order placed');
    callback();
  }, 2000);
}

function production() {
  console.log('Production started');
}

order(production);
```

### Promise Example

```javascript
let isShopOpen = true;

function order(time, task) {
  return new Promise((resolve, reject) => {
    if (isShopOpen) {
      setTimeout(() => {
        task();
        resolve();
      }, time);
    } else {
      reject('Shop is closed');
    }
  });
}

order(1000, () => console.log('Order received'))
  .then(() => order(2000, () => console.log('Fruit cut')))
  .then(() => order(1000, () => console.log('Added water and ice')))
  .then(() => order(2000, () => console.log('Ice cream served')))
  .catch((error) => console.log('Error:', error))
  .finally(() => console.log('Day ended, shop closed'));
```

---

# Async/Await Example

```javascript
let isShopOpen = true;

function toppingsChoice() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Sprinkles');
    }, 3000);
  });
}

async function kitchen() {
  try {
    console.log('A');
    console.log('B');
    const topping = await toppingsChoice();
    console.log(topping);
    console.log('D');
    console.log('E');
  } catch (error) {
    console.log('Error:', error);
  } finally {
    console.log('Runs code anyway');
  }
}

kitchen();
```

---

# Stocks Object for Simulation

```javascript
let stocks = {
  fruits: ['strawberry', 'grapes', 'banana', 'apple'],
  liquids: ['water', 'ice'],
  holders: ['cone', 'cup', 'stick'],
  toppings: ['chocolate', 'peanuts']
};
```

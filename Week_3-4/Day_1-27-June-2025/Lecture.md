# Types of Loops in JavaScript

- JavaScript has five loop types: for, while, do-while, for-in, and for-of.
- for-in and for-of are mostly used with objects and arrays.

# The For Loop

- Has three parts: start value, condition, and increment/decrement.
- Example: `for(let i = 0; i < 5; i++)`
- To filter values (like even numbers): use `if (i % 2 === 0)`
- Infinite loop happens if condition never becomes false (e.g., missing increment).

# The While Loop

- Runs as long as the condition is true.
- You must write the start value before and the update step inside the loop.
- Example:
  ```js
  let i = 0;
  while (i < 5) {
    i++;
  }
``

* Avoid infinite loops by making sure the condition becomes false.

# For-In Loop

* Use for-in to loop through object keys.
* To get the value, use bracket notation like `object[key]`, not dot notation.

# For-Of Loop

* for-of gives values directly from arrays or strings.
* It does not work with plain objects.

```

```
# Creating and Accessing Arrays

- Create arrays using square brackets: `[1, 2, 4, 8]`.
- Elements are accessed by index, starting from 0.
- Example: `array[0]` gives the first element.

# Adding and Removing Elements

- Add to end: `array.push(value)`
- Add to start: `array.unshift(value)`
- Remove from end: `array.pop()`
- Remove from start: `array.shift()`
- Remove by index: `array.splice(startIndex, count)`

# Looping Through Arrays

- Use `for` loop to go through each element.
- Example:
  ```js
  for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
``

# Advanced Array Methods

* `forEach(callback)`: runs code for each element.
* `map(callback)`: creates a new array with modified values.
* `filter(callback)`: returns a new array with only elements that pass the test.
* `map` and `filter` can be combined for cleaner code.



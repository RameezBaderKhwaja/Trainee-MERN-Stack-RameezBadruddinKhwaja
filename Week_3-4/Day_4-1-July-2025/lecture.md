## Debugging with Console

- `console.log()` prints messages to the console.
- Log multiple variables with names using `{var1, var2}`.
- Use `%c` to style logs with CSS.
- `console.table()` shows arrays of objects in table format.
- `console.time()` and `console.timeEnd()` measure execution time.
- `console.trace()` shows where a function was called from.

## Code Conciseness and Features

- Template literals use backticks and `${}` to embed variables in strings.
- Destructuring extracts values from objects or arrays into variables.
- Spread syntax copies or merges arrays and objects.
- Tagged template literals let you customize how strings are processed.
- Trailing commas help make cleaner edits in arrays and objects.

## Loops and Array Methods

- `for` loops are used for manual iteration.
- `map()` returns a new array with transformed values.
- `filter()` returns a new array with values that pass a test.
- `reduce()` combines all array elements into a single value.

## Async and Await

- `async` makes a function return a promise.
- `await` pauses code until a promise is done.
- Makes code easier to read than chained `.then()` methods.
- Use `try...catch` to handle errors in async functions.

## Debugging with Console

- Use `console.log()` to display values:
```js
console.log('Value:', x);
console.log({ a, b }); // shows variable names
```
* Style console output:

```js
console.log('%cStyled text', 'color: red; font-weight: bold;');
```

* Display tables:

```js
console.table([{ name: 'A' }, { name: 'B' }]);
```

* Measure time:

```js
console.time('process');
doSomething();
console.timeEnd('process');
```

* Trace function calls:

```js
function test() {
  console.trace();
}
test();
```

## Code Conciseness and Features

* Template literals:

```js
const name = 'Ali';
console.log(`Hello, ${name}`);
```

* Destructuring:

```js
const user = { name: 'Ali', age: 20 };
const { name, age } = user;
```

* Spread syntax:

```js
const obj1 = { a: 1 };
const obj2 = { ...obj1, b: 2 };
```

* Tagged template (basic use):

```js
function tag(strings, value) {
  return strings[0] + value.toUpperCase();
}
console.log(tag`Hello ${'world'}`);
```

## Loops and Array Methods

* Map:

```js
const nums = [1, 2, 3];
const doubled = nums.map(n => n * 2);
```

* Filter:

```js
const even = nums.filter(n => n % 2 === 0);
```

* Reduce:

```js
const sum = nums.reduce((acc, n) => acc + n, 0);
```

* Traditional loop:

```js
for (let i = 0; i < nums.length; i++) {
  console.log(nums[i]);
}
```

## Async and Await

* Basic async function:

```js
async function fetchData() {
  try {
    const res = await fetch('/data');
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.log('Error:', err);
  }
}
fetchData();
```

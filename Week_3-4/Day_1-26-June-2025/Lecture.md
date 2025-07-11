# What is Javascript?

* High level,interpreted programming language.
* Runs on the client/browser as well as on the server(Node.js)

# Why Learn Javascript?

* It is the programming language of the browser.
* Build ver interactive user interfaces with frameworks like React.
* Used building very fast server side and full stack applications.

# Variables 

* var was not used because it is global scoped and if we use in if statement and then in any where else there is a conflict so let and const are better.

```Js
let score = 100;
console.log(score);
```
# DataTypes

```Js
const name = 'John';
const age = 30;
const rating = 4.5;
const isCool = true;
const x = null;
const y = undefined
let z;
```

# Concatenaion

```Js
console.log('My name is ' + name + 'and I am' + age);

cont hello = `My name is ${name} and I am ${age}`;
```

# String properties and methods

```Js
const s = "Hello World";

console.log(s.toUpperCase())
console.log(s.toLowerCase())
console.log(s.substring())
console.log(s.split(","))
```

# Arrays

* Variables that hold multiple values.

```Js
const fruits = ['apples','oranges','pears'];
fruits[3] = 'grapes'
fruits.push('mangos');
furits.unshift('strawberries');
fruits.pop();
console.log(Array.isArray('hello'));
cosole.log(furits.indexOf('oranges'));
console.log(furits);
```

# Object Literal

```Js
const person = {
    firstName:'John',
    lastName: 'Doe',
    age: 30,
    hobbies: ['music','movies','sports'],
    address: {
        street: '50 main st',
        city: 'Boston',
        state: 'MA'
    }
}

person.email = 'john@gmail.com';

console.log(person);
```

# ArrayObject

```js
const todos = [
    { 
        id:1,
        text: 'Take out trash',
        isCompleted: true
    },
    { 
        id:2,
        text: 'Meeting with boss',
        isCompleted: true
    },
    {
        id:3,
        text: 'Dentist appt',
        isCompleted: False
    },
]
```

# JSON

```js
const todoJSOn = JSON.stringify(todos);
console.log(todoJSON);
```

# For loop

```js
for(let i= 0; i <= 10; i++) {
    console.log('For Loop Number: ${i}');
} 
```

# While loop

```js
let i=0;
while(i < 10) {
    console.log('While Loo[ Number: ${i}')
    i++;
}
```

# For Each,map,filter

```js
const todoCompleted = todos.filter(function(todo){
 return todo.isCompleted === true;
}).map(function(todo){
    return todo.text;
})
 
 console.log(todoCompleted);
 ```

 # Conditions

 ```js

 const x = 10;

 if(x === 10) {
   console.log('x is 10');
 } else {
    console.log('x is less than 10');
 }


 const x = 4;
 const y = 11;

 if(x>5 && y > 10) {
    console.log('x is more than 5 or y is more than 10');
 }

 if(x > 5) {
    if(y > 10) {

    }
 }

const x = 11;

const color = x > 10 ? 'red': 'blue';

console.log(color);
```

# Switch Statement

```js

const x = 11;

const color = x > 10 ? 'red': 'blue';

switch(color) { 
    case 'red':
        console.log('color is red');
        break;
    case 'blue':
        console.log('color is blue');
        break;
     default:
        console.log('color is NOT red or blue');
    break;       
}

```

# Function
```js
function addNums(num1, num2) {
    console.log(num1 + num2);
}

addNums(5,4);

function addnums(num1 = 1, num2 = 1) {
    return num1+num2;
}

console.log(addNums(5,4));

``` 

# Arrow Function

```js

const addnums = {num1 = 1,num2 = 2} => {
    return num1 + num2
}

console.log(addnums(5,5))


const addNums = num1 => num1 + 5;

console.log(addNums(5));
```

# OOPS

```js
// Construtor function
function Person(firstName, lastName, dob) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.dob = dob;
    this.getBirthYear = function() {
        return this.dob.getFullYear();
    }
    this.getFullName = function(){
        return `${this.firstName} ${this.lastName}`;
    }
    
 Person.prototype.getBirthYear = function() {
    return this.dob.getFullYear();
 }   

 Person.prototype.getFullName = function() {
    return `${this.firstName} ${this.lastName}`;
 }

 // Class

 class Person {
    constructor(firstName,lastName,dob) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.dob = new Date(dob);
     }
   getFullName(){
    return `${this.firstName} ${this.lastName}`;
   }  

   getBirthYear() {
    return this.dob.getFullYear();
   }

    }
  }
}

// Instantiate object

const person1 = new Person('John','Doe','4-3-1980');
const person2 = new Person('Mary','Smith','3-6-1970');

console.log(person2.getFullName());
console.log(person1);
```

# DOM

```js

console.log(window);

alert(1);

// Single element

console.log(document.getElementById('my-form'));

const form = document.getElecmentById('my-form');
console.log(form);

console.log(document.querySelector('h1'));
//Multiple element

console.log(document.querySelectorAll('.item'));
console.log(document.getElementByClassName('item'));
console.log(document.getElementsByTagName('li'));


const items = document.querySlectorAll('item');
items.forEach((item) => console.log(item));

const ul = document.querySelector('.items');

ul.remove();
ul.lastElemnetChild.remove();
ul.firstElementChild.textContent = 'Hello';
ul.children[1]innerText = 'Brad';
ul.lastElementChild.innerHTMl = '<h1>Hello</h1>';

const btn = document.querySelector('.btn');
btn.style.background = 'red';


const btn = document.querySelector('.btn');

btn.addEventListner('click,(e) => {
e.preventDefault();
document.querySelector('#my-form').style.background = '#ccc';
document.querySelector('body').classList.add('bg-dark');
document.querySelector('.items')
.lastElemenetChild.innerHTML = '<h1>Hello</h1>;
});

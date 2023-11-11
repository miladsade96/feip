# JavaScript Coding Challenges


## Core JavaScript Concepts:

1. Suppose we have an array of users as follows:
```javascript
const users = [
    {
        id: 1111,
        name: "Milad",
        isActive: true,
        age: 20,
    },
    {
        id: 2222,
        name: "Jack",
        isActive: false,
        age: 18,
    },
    {
        id: 3333,
        name: "Michael",
        isActive: true,
        age: 30,
    }
];
```

1. 1. Extract users name and store them in a new array:
```javascript
// Method 1: Using regular for loop:

let names = [];

for (let i = 0; i < users.length; i++) {
    names.push(users[i].name);
}
```
```javascript
// Method 2: Using forEach loop:

let names = [];

users.forEach(user => {
    names.push(user.name);
});
```
```javascript
// Method 3: Using for of loop

let names = [];

for (let user of users) {
    names.push(user.name);
}
```
```javascript
// Method 4: Using for in loop

let names = [];

for (let indx in users) {
    names.push(users[indx].name);
}
```
```javascript
// Method 5: Using map function

let names = users.map(user => user.name);
```

1. 2. Get only name of active users:
```javascript
// Method 1: Using regular for loop

let names = [];

for (let j = 0; j < users.length; j++) {
    if (users[j].isActive) names.push(users[j].name);
}
```
```javascript
// Method 2: Using forEach function

let names = [];

users.forEach(user => {
    if (user.isActive) names.push(user.name);
});
```
```javascript
// Method 3: Using for of loop

let names = [];

for (let user of users) {
    if (user.isActive) names.push(user.name);
}
```
```javascript
// Method 4: Using for in loop

let names = [];

for (let indx in users) {
    if (users[indx].isActive) names.push(users[indx].name);
}
```
```javascript
// Method 5: Using filter function

let names = [];

names = users.filter(user => user.isActive).map(user => user.name);
```

1. 3. Sort active users name by age descending:
```javascript
// Method 1: Imperative

users.sort((first, second) => second.age - first.age);

let names = [];

for (let j = 0; j < users.length; j++) {
    if (users[j].isActive) names.push(users[j].name);
}
```
```javascript
// Method 2: Declarative

names = users.sort((first, second) => second.age - first.age).filter(user => user.isActive).map(user => user.name);
```

---

2. 1. What will be logged in the first and second examples?  
```javascript
let var1;
console.log(var1);
console.log(typeof var1);
```
On the first line we have declared `var1` variable but have not assigned any value to it, so the value of `var1` 
variable is `undefined`. Since in javascript the `undefined` is both value and type, the type of `var1` is also 
`undefined`.
```text
Output:

undefined
undefined
```

```javascript
let var2 = null;
console.log(var2);
console.log(typeof var2);
```
Here on the first line, we have declared `var2` variable and have assigned `null` value to it. So the value of `var2`
variable id `null`. As you probably know, in javascript there is no `null` type and the type of `null` is an `object`.
```text
Output:

null
object
```

2. 2. what is the difference between null and undefined in javascript and where to use each?
```text
null is an assigned value that represents no value. undefined represents a variable that has not been assigned a value.
null can be explicitly assigned to a variable to indicate no value, e.g. let x = null. undefined is set automatically
when a variable is declared but not initialized, e.g. let x;
```

---

3. 1. What will be logged to the console?
```javascript
console.log(foo);
foo = 1;
```
On the first line, we've tried to log the value of `foo` on the console. On the second line, we've not defined `foo`
variable using `var`, `const`, `let` keywords; So if we run this code, we will get the following error:
```text
ReferenceError: foo is not defined
```

3. 2. What about this one?
```javascript
console.log(foo);
var foo = 2;
```
We first need to know about `hoisting` in javascript in order to answer this question:
```text
Hoisting in JavaScript refers to the behavior of moving declarations to the top of their containing scope.This allows
you to reference functions and variables before they are declared.
```
So the code above is equivalent to this one because of hoisting process:
```javascript
var foo;
console.log(foo);
foo = 2;
```
On the first line, `foo` variable have been declared without assigning any value, so its value is equal to `undefined`.
On the second line, we've tried to log `foo` variable value which is `undefined`. And on the third line we've assigned
numeric value `2` to `foo` variable.

3. 3. What about this one?
```javascript
foo = 3;
console.log(foo);
var foo;
```
The code above is equivalent to the following one because of hoisting process:
```javascript
var foo;
foo = 3;
console.log(foo);
```
So on the first line, the value of `foo` variable is `undefined`, on the second line we've assigned value `3` to `foo`
and on the third line we've tried to log `foo` variable value which is `3`.

---

4. 1. Create a counter function which has increment and getValue functionality?
We first need to know about `closure` in javascript in order to answer this question:
```text
Think of a closure as a backpack. It can hold stuff inside of it. We can put stuff in the backpack, and carry it around
wherever we go. Then we can take things out of the backpack whenever we need to use them. The backpack is like a
closure. The notebook, pencil case and lunchbox are like local variables that existed when the closure was created.
Even when we leave that context (like leaving the house for school), the closure remembers and can access those
variables (like taking things from the backpack while at school). A closure in JavaScript is a function that retains
access to its surrounding state (lexical environment) even when invoked outside of its immediate lexical scope. So in
summary, closures allow inner functions to access and modify outer function variables even after the outer function has
returned. They avoid the use of global variables and provide data hiding and encapsulation.
```
```javascript
const privateCounter = () => {
    let count = 0;

    // aka public API
    function increment(val = 1) {
        count += val;
    }
    function getValue() {
        return count;
    }

    return {increment, getValue};
}

const counter = privateCounter();   // Creating a closure
console.log(counter.getValue());    // count value is 0
counter.increment();                // now count value is count + 1
console.log(counter.getValue());    // count value is 1

console.dir(counter.getValue); // --> getValue --> scopes --> Closure --> count = 1
```

4. 2. Create a function which will store inside a secret string and will return it when we call it again?
```javascript
const privateSecret = () => {
    const secret = "p2Wc)Hw^R$ce1ErmJpY?MrKH1*p";
    return () => secret;
}


const secretProvider = privateSecret();
console.log(secretProvider());
```

---

5. 1. Write a function which helps to achieve `multiply(a)(b)` and returns the product of `a` and `b`?
```javascript
// Solution #1:
function multiplyV1(a) {
    return (b) => {
        return a * b;
    }
}

console.log(multiplyV1(2)(6));  // 12
```
```javascript
// Solution #2:
const multiplyV2 = a => b => a * b;

console.log(multiplyV2(2)(8));  // 16
```
   
5. 2. Create a curry function?  
The curry function takes in a function `fn` as its argument. It returns a new curried function that can take arguments
one by one until it has the full number of arguments `fn` expects. Each time the curried function is called with less
than `fn.length` arguments, it returns a new function waiting for more arguments. When enough arguments are finally
passed in, it calls fn with all the accumulated arguments.
```javascript
function curry(fn) {
    const arity = fn.length;
    return function f1(...args) {
        if (args.length >= arity) return fn(...args);
        else {
            return function f2(...moreArgs) {
                const newArgs = args.concat(moreArgs);
                return f1(...newArgs);
            }
        }
    }
}

const curriedSum = curry((first, second, third) => first + second + third);
console.log(curriedSum(1, 2, 3));   // 6
console.log(curriedSum(1)(2, 3));   // 6
console.log(curriedSum(1, 2)(3));   // 6
console.log(curriedSum(1)(2)(3));   // 6
```

5. 3. Why do we need curry function?  
This allows us to easily create pre-configured or partially applied functions from existing functions. The curry 
function implements partial application to turn a regular multi-argument function into a chain of single-argument
functions.
```javascript
// Example #1 - get method:
const get = curry((property, object) => object[property]);
console.log(get("id")({id: 1, name: "Milad"}));     // 1
```
```javascript
// Example #2 - map method:
const map = curry((fn, values) => values.map(fn));
console.log(map(getId, [{id: 1, name: "Milad"}]));      // [1]
```

---

6. Write a function which gets an array and an element and returns a new array with this element at the end?
```javascript
function addElementToArray(arr, el) {
    return [...arr, el];
}
```

---

7. Write a function which can concatenate two arrays?
```javascript
function concatTwoArrays(arr1, arr2) {
    // return arr1.concat(...arr2)
    // Or
    return [...arr1, ...arr2];
}
```

---

8. Check that user with such name exists in the array of objects?
```javascript
const users = [
    { id: 1, name: "Jack", isActive: true },
    { id: 2, name: "John", isActive: true },
    { id: 3, name: "Mike", isActive: false},
];

const targetUser1 = "Mike";
const targetUser2 = "Milad";
```
```javascript
// Method 1: Using for loop (Beginner's solution):

const findUserV1 = (usersArray, name) => {
    let isUserExist = false;

    for (let i = 0; i < usersArray.length; i++) {
        if (usersArray[i].name === name) isUserExist = true
    }

    return isUserExist;
}

console.log(findUserV1(users, targetUser1));    // true
console.log(findUserV1(users, targetUser2));    // false
```
```javascript
// Method 2: Using find method:

const findUserV2 = (usersArray, name) => {
    const result = usersArray.find(userObj => userObj.name === name);
    return Boolean(result);
}

console.log(findUserV2(users, targetUser1));    // true
console.log(findUserV2(users, targetUser2));    // false
```
```javascript
// Method 3: Using findIndex method:

const findUserV3 = (usersArray, name) => {
    const index = usersArray.findIndex(userObj => userObj.name === name);
    return index >= 0;
}

console.log(findUserV3(users, targetUser1));    // true
console.log(findUserV3(users, targetUser2));    // false
```
```javascript
// Method 4: Using some method (Best):

const findUserV4 = (usersArray, name) => usersArray.some(userObj => userObj.name === name);

console.log(findUserV4(users, targetUser1));    // true
console.log(findUserV4(users, targetUser2));    // false
```

---

9. Remove all duplicates in the array?
```javascript
// Method 1: Using forEach method:

const uniqueArrV1 = arr => {
    const result = [];
    arr.forEach(el => {
        if (!result.includes(el)) result.push(el);
    })
    return result;
}
```
```javascript
// Method 2: Using reduce method:

const uniqueArrV2 = arr => arr.reduce((acc, el) => {
    return acc.includes(el) ? acc : [...acc, el];
}, []);
```
```javascript
// Method 3: Using Set():

const uniqueArrV3 = arr => [...new Set(arr)];
```

---

10. 1. Sort an array of numbers in ascending and descending orders?
```javascript
const sampleArr = [3, 8, 5, 2, 1];
// NOTE: sort method mutates the original array

// Ascending:
const asc = sampleArr.sort((a, b) => a - b);

// Descending:
const dsc = sampleArr.sort((a, b) => b - a);
```

10. 2. Sort array of objects by author's lastname?
```javascript
const books = [
    {name: "Harry Potter", author: "Joanne Rowling"},
    {name: "Warcross", author: "Marie Lu"},
    {name: "The Hunger Games", author: "Suzanne Collins"},
];

books.sort((book1, book2) => {
    const b1authorLName = book1.author.split(" ")[1];
    const b2authorLName = book2.author.split(" ")[1];
    return b1authorLName < b2authorLName ? -1 : 1;  // Ascending order
});
```

---

11. 1. Write a function which implements range?
```javascript
// Method 1: Using for loop:

function rangeV1(start, stop) {
    const result = [];
    for (let i = start; i <= stop; i++) result.push(i);
    return result;
}

console.log(rangeV1(1, 15));
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
```
```javascript
// Method 2: Using Array, from , keys methods:

function rangeV2(start, stop) {
    return [...Array(stop - start + 1).keys()].map(el => el + start);
}

console.log(rangeV2(1, 20));    // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
console.log(rangeV2(10, 20));   // [10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
```

11. 2. Write a function which implements range with adjustable step size?
```javascript
// Using Array.from() method:

function adjustableRange(start, stop, step = 1) {
    return Array.from({length: (stop - start) / step + 1}, (_, index) => start + index * step);
}

console.log(adjustableRange(7, 50, 3));
// [7, 10, 13, 16, 19, 22, 25, 28, 31, 34, 37, 40, 43, 46, 49]
```

---

12. Write a function which implements shuffle feature?
```javascript
function shuffle(itemsArray) {
    return itemsArray
        .map(item => ({sortingFactor: Math.random(), valueOfItem: item}))
        .sort((item1, item2) => item1.sortingFactor - item2.sortingFactor)
        .map(obj => obj.valueOfItem);
}


const sampleData = [1, 2, 3, 4, 5, 6, 7, 8, 9];
console.log(shuffle(sampleData));   // [6, 2, 5, 7, 3, 9, 4, 8, 1]

```

13. Find the number of occurrences of the minimum value in the array?
```javascript
function numOccurMin(itemsArr) {
    const minValue = Math.min(...itemsArr);
    const minArr = itemsArr.filter(el => el === minValue);
    return minArr.length;
}


const nums = [1, 2, 3, 4, 1, 1, 2, 3, 1];
console.log(numOccurMin(nums)); // 4
```

---

14. 1. What will be logged here?
```javascript
function getItem() {
    console.log(this);  // Inside function definition, this is refrencing the global object
    // Possible values are Window object, undefined or something else
    // It is all depends on the context
}

getItem();
```

14. 2. What will be logged in this case?
```javascript
const item = {
  title: "Ball",
  getItem() {
      console.log(this);
  }  
};

item.getItem(); // item object
```

14. 3. What will be logged in this case?
```javascript
class Item {
    title = "Ball";
    getItem() {
        console.log(this);
    }
}


const item = new Item();
item.getItem(); // Item class
```

14. 4. What will be logged in this case?
```javascript
class Item {
    title = "Ball";
    getItem() {
        function someFn() {
            console.log(this);
        }
        someFn();
    }
}


const item = new Item();
item.getItem(); // undefined
```

14. 5. What will be logged here?
```javascript
class Item {
    title = "Ball";
    getItem() {
        [1, 2, 3].map(function () {
            console.log(this);
        })
    }
}


const item = new Item();
item.getItem();
/*
undefined
undefined
undefined
 */
```

14. 6. How to fix previous issue so that `this` keyword references to parent context?
```javascript
// Fist solution - old school javascript
// Using a helper constant:

class Item {
    title = "Ball";
    getItem() {
        const this_ = this;
        [1, 2, 3].map(function () {
            console.log(this_);
        })
    }
}


const item = new Item();
item.getItem();
/*
Item {title: 'Ball'}
Item {title: 'Ball'}
Item {title: 'Ball'}
 */
```
Or
```javascript
// Second solution - more modern way
// Using arrow functions:

class Item {
    title = "Ball";
    getItem() {
        [1, 2, 3].map(() => {
            console.log(this);
        })
    }
}


const item = new Item();
item.getItem();
/*
Item {title: 'Ball'}
Item {title: 'Ball'}
Item {title: 'Ball'}
 */
```

---

15. 1. Design a class for employee which takes id and name in during construction of object and has a salary property?
```javascript
class Employee {
    constructor(id, name) {
        if (!id || !name) throw new Error("id and name properties are mandatory!");
        this.id = id;
        this.name = name;
    }
    
    setSalary(salary) {
        this.salary = salary;
    }
    
    getId() {
        return this.id;
    }
    
    getName() {
        return this.name;
    }
    
    getSalary() {
        return this.salary;
    }
}
```

15. 2. Design a class for manager which is an employee and can have department property?
```javascript
class Manager extends Employee {
    setDepartment(deptName) {
        this.department = deptName;
    }
    
    getDepartment() {
        return this.department;
    }
}
```

---

16. 1. Refactor Employee class with javascript prototypes approach?
```javascript
var Employee = function (id, name) {
    if (!id || !name) throw new Error("id and name properties are mandatory!");
    this.id = id;
    this.name = name;
}


Employee.prototype.setSalary = function (salary) {
    this.salary = salary;
}

Employee.prototype.getId = function () {
    return this.id;
}

Employee.prototype.getName = function () {
    return this.name;
}

Employee.prototype.getSalary = function () {
    return this.salary;
}
```

16. 2. Refactor Manager class with javascript prototypes approach?
```javascript
var Manager = function (params) {
    Employee.apply(this, arguments);
};

Manager.prototype = Object.create(Employee.prototype);
Manager.prototype.constructor = Manager;

Manager.prototype.setDepartment = function (deptName) {
    this.department = deptName;
}

Manager.prototype.getDepartment = function () {
    return this.department;
}
```

---

17. 1. Create a es6 module with function getName, getSurName and default export getFullName.
```javascript
// New file: es6.js

export const getName = name => name;

export const getSurname = surname => surname;

export default (name, surName) => `${getName(name)} ${getSurname(surName)}`;
```
```javascript
// New file: main.js

import getFullName, {getName, getSurname} from "./es6";

console.log(getName("Milad"));
console.log(getSurname("Sadeghi"));
console.log(getFullName("Milad", "Sadeghi"));
```

17. 2. Create the same with commonJS module.
```javascript
// New file: common.js

const getName = name => name;
const getSurname = surname => surname;

module.exports.getName = getName;
module.exports.getSurname = getSurname;
module.exports.getFullName = (name, surName) => `${getName(name)} ${getSurname(surName)}`;
```
```javascript
const {getName, getSurname, getFullName} = require("./common.js");

console.log(getName("Milad"));
console.log(getSurname("Sadeghi"));
console.log(getFullName("Milad", "Sadeghi"));
```

17. 3. What are the differences between ES6 and commonJS modules?  
ES6 modules and CommonJS modules are two different ways to organize and reuse code in JavaScript. ES6 modules are newer
and more modern, while CommonJS modules are older and more widely used.

**Here are some of the key differences between ES6 and CommonJS modules:**

| Feature        | ES6 modules                                             | CommonJS modules                                                                |
|----------------|---------------------------------------------------------|---------------------------------------------------------------------------------|
| **Syntax**     | Uses the `import` and `export` statements               | Uses the `require()` function and the `module.exports` object                   |
| **Loading**    | Are loaded statically                                   | Are loaded dynamically                                                          |
| **Support**    | Natively supported in modern browsers and Node.js       | Require a bundler to be used in browsers                                        |
| **Modularity** | Encourage strong modularity and encapsulation           | Can be less modular, with more global variables and dependencies                |
| **Tooling**    | Static analysis tools can easily understand ES6 modules | Static analysis tools require additional tooling to understand CommonJS modules |

**Other differences:**

* ES6 modules can only be imported at the top of a file, while CommonJS modules can be imported anywhere in a file.
* ES6 modules support named exports and default exports, while CommonJS modules only support default exports.
* ES6 modules are asynchronous by default, while CommonJS modules are synchronous by default.
* ES6 modules are designed to be tree-shakable, which means that unused code can be removed from the bundle, while CommonJS modules are not.

**Which one to use?**

In general, ES6 modules are recommended for new projects. They offer a number of advantages over CommonJS modules,
including better modularity, easier static analysis, and native support in browsers.

---

18. Create the debounce function?  
Debouncing is a programming technique that limits the rate at which a function can be called. It is useful for preventing unnecessary function calls, such as when a function is called repeatedly in response to a user event.

For example, imagine you have a search box that shows suggestions as the user types. If you call a function to fetch suggestions on every keystroke, you might end up making too many requests to the server, which can slow down the application and waste resources.

Debouncing can be used to delay the execution of the function until a certain amount of time has passed since the last time it was called. This means that the function will only be executed once, even if the user types multiple keys in a short period of time.

Here is a simple implementation of a debounce function in JavaScript:

```javascript
function debounce(func, wait) {
  let timer;
  return function() {
    const args = arguments;
    if (timer) clearTimeout(timer);
    timer = setTimeout(() => {
      func.apply(this, args);
    }, wait);
  };
}
```

This function takes two parameters:

* `func`: The function to be debounced.
* `wait`: The amount of time to wait in milliseconds before executing the function.

The function returns a new function that can be used to call the debounced function. This new function will delay the execution of the original function until `wait` milliseconds have passed since the last time it was called.

Here is an example of how to use the debounce function:

```javascript
function requestSender() {
    console.log("Request has been sent.");
}

const process = debounce(requestSender, 5000);

process();
process();
process();

// Output: After 5 seconds --> Request has been sent.
```

Debouncing is a useful technique for optimizing JavaScript applications. It can be used to improve the performance of user interfaces, prevent unnecessary API calls, and reduce the load on the server.

---

19. Create the throttle function?  
Throttling is a programming technique that limits the rate at which a function can be called. It is similar to debouncing, but with a key difference: throttling will call the function at most once in a given time interval, regardless of how many times the function is called.

This means that throttling is useful for scenarios where you want to ensure that a function is called regularly, but not too often. For example, you might want to throttle a function that updates the UI in response to user input, so that the UI doesn't become unresponsive if the user interacts with it too quickly.

Here is a simple implementation of a throttle function in JavaScript:

```javascript
function throttle(func, wait) {
    let isWaiting = false;
    return function() {
        const args = arguments;
        if (!isWaiting) {
            func.apply(this, args);
            isWaiting = true;
            setTimeout(() => {
                isWaiting = false;
            }, wait); 
        }
        
    };
}
```

This function takes two parameters:

* `func`: The function to be throttled.
* `wait`: The amount of time to wait in milliseconds before executing the function again.

The function returns a new function that can be used to call the throttled function. This new function will only call the original function if at least `wait` milliseconds have passed since the last time it was called.

Here is an example of how to use the throttle function:

```javascript
function requestSender() {
    console.log("Request has been sent.");
}

const process = throttle(requestSender, 2000);
process();

setTimeout(() => {
    process();
}, 1000);

setTimeout(() => {
    process();
}, 1200);

setTimeout(() => {
    process();
}, 2400);

/*
Output:
Immediately ---> Request has been sent.
After 2400ms ---> Request has been sent.
 */
```

Throttling is another useful technique for optimizing JavaScript applications. It can be used to improve the performance of user interfaces, prevent unnecessary API calls, and reduce the load on the server.

---

20. Highlight all the words over 8 characters long in the paragraph text with a yellow background?
```javascript
const paragraph = document.querySelector("p");
paragraph.innerHTML = paragraph.innerHTML.split(" ").map(word => {
    return word > 8 ? `<span style="background-color: yellow">${word}</span>` : word;
}).join(" ");
```

---

21. Add a link back to the source of the text after the paragraph tag?
```javascript
const linkTag = document.createElement("a");
linkTag.href = "https://hereismy.site";
linkTag.innerText = "Milad's Personal Website";
document.body.appendChild(linkTag);
```

---

22. Split each new sentence to a separate line in the paragraph text. A sentence can be assumed to be a string of a
text terminated with a period.
```javascript
const paragraph = document.querySelector("p");
paragraph.innerHTML = paragraph.innerHTML.split(/\.[^.|<]/).join(".</p><p>") + "</p>";
```

---

23. Implement an efficient click event on todo items as fast as possible?
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Fast click event implementation</title>
    </head>
    <body>
        <ul class="todo-app">
            <li class="item">Go shopping</li>
            <li class="item">Pay bills</li>
            <li class="item">Study for the exam</li>
            <li class="item">Make dinner</li>
            <li class="item">Refactor the code base</li>
        </ul>
    </body>
</html>
```
```javascript
const app = document.querySelector(".todo-app");
app.addEventListener("click", (e) => {
    if (e.target && e.target.classList.contains("item")) {
        console.log(`You clicked on item: ${e.target.innerText}`);
    }
})
```

---

24. Write an example of fetching data with XMLHttpRequest?
```javascript
const xhr = new XMLHttpRequest();
xhr.open("GET", "https://example.com");
xhr.send();

xhr.onload = function () {
    if (xhr.status !== 200) console.log(`Error: ${xhr.status} - ${xhr.statusText}`);
    else console.log(`Success: ${xhr.response}`);
}

xhr.onerror = function () {
    console.log("Request failed!");
}
```

---

25. Write an example of fetching data using fetch API?
```javascript
fetch("https://example.com").then(res => res.json()).then(data => {
    console.log(data)}).catch(err => {
    console.log(err.message)});
```

---

26. 1. Write an asynchronous function which executes a callback after finishing its asynchronous task?
```javascript
const asyFun = callback => {
    setTimeout(() => {
        callback("done");
    }, 3000);
};

function ourCB(message) {
    console.log(`Callback ${message}`);
}

asyFun(ourCB);
```

26. 2. What problems does callback solve?
- **Allowing JavaScript to be asynchronous**. JavaScript is a single-threaded language, meaning that it can only execute one task at a time. Callbacks allow JavaScript to execute multiple tasks simultaneously by allowing functions to be executed when they are ready.
- **Handling asynchronous operations**. Asynchronous operations are operations that take an unknown amount of time to complete, such as making network requests or reading files. Callbacks allow JavaScript to handle these operations by allowing functions to be executed when the operation has finished.
- **Implementing event-driven programming**. Event-driven programming is a programming paradigm in which the flow of execution is determined by events, such as user input or network messages. Callbacks allow JavaScript to implement event-driven programming by allowing functions to be executed when an event occurs.

---

27. Execute the given list of asynchronous functions in parallel and return the results as an array to the callback?
```javascript
const asyncFunc1 = (callback) => {
    setTimeout(() => {callback(1)}, 3000);
};

const asyncFunc2 = (callback) => {
    setTimeout(() => {callback(2)}, 2000);
};

const asyncFunc3 = (callback) => {
    setTimeout(() => {callback(3)}, 1000);
};
```
```javascript
// Solution:

const asyncParallel = (asyncFuncs, callback) => {
    const resultArr = new Array(asyncFuncs.length);
    let resultCounter = 0;
    
    asyncFuncs.forEach((asyncFunc, index) => {
        asyncFunc((value) => {
            resultArr[index] = value;
            resultCounter++;
            if (resultCounter >= asyncFuncs.length) callback(resultArr);
        })
    })
}

const cbFn = (res) => {
    console.log(res);
}

asyncParallel([asyncFunc1, asyncFunc2, asyncFunc3], cbFn);  // [1, 2, 3]
```

---

28. Create a promise function to be able to use callback function via promise approach?
```javascript
const asyncFunc = callback => {
    setTimeout(() => {
        callback(1)
    }, 3000);
}

const promisifyAsyncFunc = () => {
    return new Promise(function (resolve) {
        asyncFunc( data => {
            resolve(data);
    })});
}

promisifyAsyncFunc().then((result) => {
        console.log(result)
    }
);
```

---

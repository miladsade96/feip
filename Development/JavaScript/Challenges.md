# JavaScript Coding Challenges

<div style="text-align: justify">

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
</div>

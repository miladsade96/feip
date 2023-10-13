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
</div>

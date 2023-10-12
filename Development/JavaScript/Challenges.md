# JavaScript Coding Challenges

<div style="text-align: justify">

## Core JavaScript Concepts:

### Suppose we have an array of users as follows:
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

1. Extract users name and store them in a new array:
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
</div>

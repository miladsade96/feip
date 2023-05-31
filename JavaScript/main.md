# javaScript Interview Questions

<div style="text-align: justify">

## Language Fundamentals:

### What is the difference between null and undefined?  
In all programming languages, you see null values, but javascript is unique in this case; because it has both
null and undefined values. Most of the languages have data types for variables, javascript also has, but 
when of variable declaration, there is no type decided. Then after the value is assigned to the variable, it
decides the data type. So before any value is assigned to a variable in javascript, the variable contains
undefined.
```javascript
let x;
console.log(x);     // undefined
console.log(typeof x);      // undefined


let x = 1996;
console.log(x);     // 1996
console.log(typeof x);      // number
```
“Null” is the same as other programming languages, “null” means nothing. When you have a variable or object,
which you want to make empty, then you assign “null” to variable.
```javascript
let x = null;
console.log(x);     // null
console.log(typeof x);      // object - It is not true


let y;
console.log(x==y);  // True, Because null and undefined both represent nothing-ness
console.log(x===y); // False, Bacause null and undefined have different data types
```
**What is undefined in javascript?**  
A variable, which is not assigned a value is undefined.
```javascript
let x;
```
**What will be the output of *undefined == null* and *undefined === null* ? and why?**  
undefined == null is simple comparison, and it is going to return true, but undefined === null is strict
comparison, which checks both value and data type. Undefined itself is a data type but null is a primitive
data type. So the return value is false.

**Can you explicitly assign undefined to a variable?**  
Yes, because undefined itself is a kind of keyword in javascript, which you can use:
```javascript
let x = undefined;
console.log(x);     // undefined
```


### What is the difference between function scope and block scope?  
First, we need to understand what is the scope of a variable? The scope can be of a variable and function, so
the logic remains the same. The Scope of a variable is the lifetime or availability of a variable.
```javascript
function first() {
    let x = 3;
}

function second() {
    console.log(x); // Uncaught ReferenceError: x is not defined
    /* Variable x is not available because it is defined inside first function, and we are trying to access
    it inside second function. This means the scope of variable 'x' is limited to first function, in the 
    other words, variable x is local to function first().
    * */
}

first();
second();
```
The Scope of a variable can be local or global. Let's make x variable global. Global variable will be accessible
for all functions.
```javascript
let x = 10;

function first() {
    x += 5;     // 10 + 5
}

function second() {
    console.log(x);     // 15
}

first();
second();
```
Both function first and second are referring to the same variable. X variable is global and available for an entire
piece of code.


### Function scope vs. Block scope:
ES5 has function scope, and that is because of hoisting, But ES6 does not have hoisting, It has block scope. If you
declare a variable with “var” keyword, then hoisting will be there.
```javascript
console.log(x);     // undefined
var x;
```
What if we have this piece of code:
```javascript
console.log(x);     // undefined
var x = 10;
```
It is still undefined because javascript compiler internally transforms code above(finds all variable declarations
which are declared with var keyword and brings all the declarations to the top) to this one:
```javascript
var x;
console.log(x);     // undefined
x = 10;
```
At a time with "var" keyword, you can declare only one variable in a function with the same name.  
Hoisting means bringing the declarations on top. Block scope is introduced from ES6 onwards.
```javascript
let x = 9;
{
    let x = 8;
    console.log(x);     // 8
}
console.log(x);     // 9
```
Javascript compiler does not hoist variables declared with "let" keyword.
```javascript
console.log(x);     // Uncaught ReferenceError: Cannot access "x" before initialization.
let x;
```

**What is hoisting in javascript?**  
A process which is happening behind the scene, internally it is bringing the declarations on top.

**How does block scope work?**  
It is nothing but the brackets {}, in if conditions, for loop, doo while loop, etc. That is block created which
creates separate scope for declarations existing in that block.

**What is scope of a variable?**  
It is the availability or visibility or lifetime of a variable.
</div>

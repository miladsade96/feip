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
</div>

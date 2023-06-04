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
---

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

---

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
It is still undefined because the javascript compiler internally transforms code above (finds all variable declarations,
which are declared with var keyword and brings all the declarations to the top) to this one:
```javascript
var x;
console.log(x);     // undefined
x = 10;
```
At a time with “var” keyword, you can declare only one variable in a function with the same name.  
Hoisting means bringing the declarations on top. Block scope is introduced from ES6 onwards.
```javascript
let x = 9;
{
    let x = 8;
    console.log(x);     // 8
}
console.log(x);     // 9
```
Javascript compiler does not hoist variables declared with “let” keyword.
```javascript
console.log(x);     // Uncaught ReferenceError: Cannot access “x” before initialization.
let x;
```

**What is hoisting in javascript?**  
A process, which is happening behind the scene, internally it is bringing the declarations on top.

**How does block scope work?**  
It is nothing but the brackets {}, in if conditions, for loop, do while loop, etc. That is block created, which
creates separate scope for declarations existing in that block.

**What is scope of a variable?**  
It is the availability or visibility or lifetime of a variable.

---

### What is Automatic Semicolon Insertion(ASI)?  

You must have used ";” many times in javascript code.
Almost all lines are terminated by a “;”.
If you forget to
write ";” then also javascript will not show any error.
The reason for not showing error is that the compiler 
automatically adds a semicolon at the end of those lines.
```javascript
console.log("Hi")   // javascript inserts “;” at the end of line. aka ASI
console.log("There");
```
Writing a ";" at the end of line is optional in javascript. Javascript does not insert a ";" on every line break
that is on every new line.
```javascript
let a = 4 *
5
console.log(a);     // 20
```
Let's see another example:
```javascript
function test() {
    return      // ASI is happened here - there is a semicolon here.
    {
        a:5
    }
}

const obj = test();
console.log(obj);   // undefined
```


**Should you terminate all lines by a ";"?**  
It is a good practice to have a ";" at the end.

**Can “use strict” statement, or the strict mode changes the behavior of ASI?**  
No, It does not change the behavior if you write “use strict” it does not mean you have to end all lines with ";".

---

### Difference between rest and spread operator?  
From ES6 onwards, there are … used in many places. 
Sometimes they are called the rest operator and sometimes the very same … are called spread operator.
Imagine a situation where you have to create a function called sum, which can take any number of
arguments, and at the end it should return the sum of all the parameters passed to it:
```javascript
function sum(...nums) { // rest operator
    return nums.reduce((acc, item) => acc + item, 0);
}

sum(1, 2, 3);   // 6
```
For multi-parameter functions, the rest operator must be the last one:
```javascript
function logger(a, ...b) {
    console.log(a, b);      // 1 [2, 3, 4, 5]
}

logger(1, 2, 3, 4, 5);
```
The rest operator is part of ES6.
In ES5 we have an array-like object called *arguments,* which does not work with arrow functions, so we
avoid it:
```javascript
function foo() {
    console.log(arguments); // {"0": 5, "1":8}
}

foo(5, 8);
```
If we convert the function above to arrow function, It won't work:
```javascript
const foo = () => {
    console.log(arguments); // Uncaught ReferenceError: arguments is not defined in foo
}

foo(5, 8);
```
In order to make it work properly, we need to use rest operator:
```javascript
const foo = (...nums) => {
    console.log(nums);  // [5, 8]
}

foo(5, 8);
```
So whenever we use … with function to deal with any number of parameters, then we call it rest operator
(for the rest of parameters).  
As the rest operator puts the separate data values into one array, the spread does the opposite:
```javascript
let arr1 = [1, 2, 3, 4, 5];
let arr2 = [...arr1, 6, 7, 8];
console.log(arr2);  // [1, 2, 3, 4, 5, 6, 7, 8]
```
Let's see another example of spread operator. 
In this example, we want to find the biggest element in the array using math module methods:
```javascript
const array = [2, 6, 12, 97, 1, 0, 999, 567, 254];
console.log(Math.max(array));   // NaN - Not a number error
```
We need to use spread operator to feed array numbers into max method:
```javascript
const array = [2, 6, 12, 97, 1, 0, 999, 567, 254];
console.log(Math.max(...array));    /// 999
```

**Can we use arguments object in arrow functions?**  
It cannot be used.
If it is the traditional way, it works, otherwise it won't.

**Which is the best way to create a new array with assignments?**  
Using spread operator:
```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5, 6];
console.log(arr2);  // [1, 2, 3, 4, 5, 6]
```

**How can you handle the n number of parameters passed to a function?**  
```javascript
const func = function(...numbers) { // rest operator
    console.log(...numbers);    // spread operator - 1 2 3 4 5
}

func(1, 2, 3, 4, 5);
```

**Is this piece of code valid? Give a reason.**  
```javascript
function test(...a, b) {
    console.log(a,  b);
}
```
We can not have rest parameter in the beginning of the parameter list.
If we have just the parameter list, it is ok, but if we have more parameters then, the rest parameter
should be at the last position because it is the rest of the parameters.

---

### When do you get infinity or (-infinity) as output?  
Infinity is a special integer value, which is greater than any value or in other words, it is the highest possible value
available in javascript.
There are two possibilities for infinity:  
1. Positive infinity(POSITIVE_INFINITY)
2. Negative infinity(NEGATIVE_INFINITY)  


</div>

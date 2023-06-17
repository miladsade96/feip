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

#### *Relative Questions*:

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

#### *Relative Questions*:

**What is hoisting in javascript?**  
A process, which is happening behind the scene, internally it is bringing the declarations on top.

**How does block scope work?**  
It is nothing but the brackets {}, in if conditions, for loop, do while loop, etc. That is block created, which
creates separate scope for declarations existing in that block.

**What is scope of a variable?**  
It is the availability or visibility or lifetime of a variable.

---

### What is Automatic Semicolon Insertion(ASI)?  

You must have used ";" many times in javascript code.
Almost all lines are terminated by a “;”.
If you forget to
write ";" then also javascript will not show any error.
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

#### *Relative Questions*:

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

#### *Relative Questions*:

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
// function test(...a, b) {
//     console.log(a,  b);
// }
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
```javascript
console.log(Number.POSITIVE_INFINITY);      // Infinity
console.log(Number.NEGATIVE_INFINITY);      // -Infinity
```
In javascript the numbers are stored in 64-bit format. It means any value which cannot fit in the 64-bit format will
return infinity. It cannot hold the value, value is larger than 64-bit.
```javascript
console.log(9e4);       // 90000
console.log(-9e4);      // -90000
console.log(9e400);     // Infinity
console.log(-9e400);    // -Infinity
console.log(Number.MAX_VALUE);      // 1.7976931348623157e+308
console.log(Number.MIN_VALUE);      // 5e-324
console.log(Number.MAX_VALUE * 2);      // Infinity
console.log(-Number.MAX_VALUE * 2);     // -Infinity
```
All codes above are generating the infinity, but this is not the purpose. Ideally when you expect that in some 
calculation you might get some huge value, and you want to put a validation, then it is useful. For example:
```javascript
if (num === Number.NEGATIVE_INFINITY) return "Negative Infinite Value";
else return num;    // Or some calculation on num
```

#### *Relative Questions*:

**How will you go put a validation for positive or negative infinity?**  
```javascript
if (num === Number.POSITIVE_INFINITY) return "Positive Infinite Value";
else return num;    // Or some calculation on num

if (num === Number.NEGATIVE_INFINITY) return "Negative Infinite Value";
else return num;    // Or some calculation on num
```

**What is the output of the following code?**  
```javascript
console.log(1/0);   // Infinity
```

---

### When do you get NaN as output?  
NaN is a global property representing "Not-A-Number". You normally get this error when there is a non-numeric value or
operation performed.
```javascript
const a = 5;
const b = "javascript";
console.log(a * b);     // NaN - Because number and string cannot perform mathematical operations
```
How will you make sure that you always have validation on such values?  
By using a method called *isNaN()*. This method is a function which returns true or false depending on the expression:
```javascript
if (isNaN(a * b)) return "Invalid";
else if (!isNaN(a * b)) return "Valid";
```
NaN is a unique value in the other words, NaN does not match with itself. NaN return a unique value each time you refer
it:
```javascript
console.log(NaN == NaN);    // false
console.log(NaN === NaN);   // false
```
We prefer to write isFinite() method which not only checks for NaN but also checks for infinity and -infinity as well.
isFinite() method checks whether the value is a regular number or not:
```javascript
const a = 4;
const b = "test string";
console.log(isFinite(a * b));       // false
console.log(isFinite(4 * 5));       // true
console.log(isFinite(Number.MAX_VALUE * 5));        // false
console.log(isFinite(Infinity));        // flase
```

#### *Relative Questions*:

**What will be the output of the below statement?**  
```javascript
console.log(NaN == NaN);        // false
console.log(NaN === NaN);       // false
```

**What is the difference between isNaN() and isFinite()?**  
isNan() method is going to check whether the value is Not-a-number or not, while isFinite() method checks for NaN as
well as infinity values.

---

### Explain must know points of arrow function:
In most javascript interviews, you will be asked about arrow functions. You should talk about functional behaviour
aspects rather than just the syntax. Three functional behaviour that you must discuss is:
1. "this" object doesn't work with arrow function
2. "arguments" object doesn't work with arrow function
3. You can't use "new" to call arrow functions

```javascript
// Function definition
function test1() {
    // code is here
}
test1();

// Function expression
const test2 = function() {
    // code is here
}
test2();
```

Arrow function is a function expression:

```javascript
// An arrow function without any parameter:
const test3 = () => {
    console.log("Without any parameter");
}
test3();

// An arrow function with a single parameter:
const test4 = greetMessage => {
    console.log(greetMessage);
}
test4("Hi");

// An arrow function with multiple parameters:
const test5 = (a, b) => {
    console.log(a + b);
}
test5(8, 5);
```
If our arrow function is a one liner single return statement function, we can write it this way:
```javascript
const sum = (a, b) => a + b;
sum(2, 5);  // 7
```
We can build IIFE(immediately Invoked Function Expression) using arrow functions:
```javascript
// Regular IIFE:
(function IIFE() {
    console.log("IIFE");
})();

// IIFE using arrow function(IIAF - Immediately Invoked Arrow Function):
(() => {
    console.log("IIAF");
})();
```

Let's talk about those three functional behaviours:
Assume the following function: 
```javascript
const test6 = () => {
    console.log(this);  // window
}
```
If we run code above on the browser, we get the *window*.  
If we write the following code, it means that, "this" object can have the local reference in this type of function; if
this function be called with "new" keyword:
```javascript
function test7() {
    console.log(this);
}
```
But if we use arrow function, we can not have current reference, I will always point to global envirenment:
```javascript
const test8 = () => {
    console.log(this);
}
```
The following code is a clear explanation to what i've mentioned above:
```javascript
const obj = {
    test() {
        console.log(this);  // {test: f}
    }
}

obj.test();


const otherObj = {
    test: () => {
        console.log(this);  // Window
    }
}

otherObj.test();
```
The reason is earlier the function also had a job of class. That is the function used to act as a class also, depending
on the way it is called. If you call the function with the *new* keyword, then it will behaves as a class; But arrow
function does not have that duty, it is just a function.

The *arguments* object does not work with arrow functions:
```javascript
function test() {
    console.log(arguments);     // [1, 2, 3, 4]
}
test(1, 2, 3, 4);

const testArrow = () => {
    console.log(arguments);     // Uncaught ReferenceError: arguments isn't defined
}
testArrow(1, 2, 3, 4);
```
We can use *rest* operator, in order to fix this issue:
```javascript
const testArrow = (...args) => {
    console.log(args);      // [1, 2, 3, 4]
}
testArrow(1, 2, 3, 4);
```

You can't use "new" to call arrow functions:
```javascript
const test = () => {
    console.log("Test function ran!");
}

const obj = new test();     // Uncaught TypeError: test10 is not a constructor
```

#### *Relative Questions*:

**Explain the syntactical features of arrow function?**  
Already discussed above.  

**Why "this" does not work in arrow functions?**  
Already discussed above.  

**Explain the output of the following code with a reason:**  
```javascript
const obj = {
    method: () => {
        console.log(this);  // Already discussed above
    }
}
```

**How can you handle arguments object like functionality in arrow function?**  
Already discussed above.  
**Can you write IIFE with arrow function syntax?**  
Already discussed above.

---

### How does the closure work in javascript?
When a function comes under another function, a closure is created. Closure pattern remembers outer variable and also
helps to access outer scope members:
```javascript
function outer() {
    function inner() {
        console.log("Inner called!");
    }
}
inner();    // ReferenceError: inner is not defined.
```
we should write this instead in order to call inner function:
```javascript
function outer() {
    function inner() {
        console.log("Inner called!");
    }
}
outer();    // Inner called!
```
Running inner function using closure:
```javascript
function outer() {
    function inner() {
        console.log("Inner called!");
    }
    return inner;
}
const inFunc = outer();
inFunc();   // Inner called!
```
or in ES6 syntax:
```javascript
const outer = () => {
    return () => {
        console.log("Inner called!");
    }
}
const inFunc = outer();
inFunc();   // Inner called!
```
Let's see another example:
```javascript
const addOne = () => {
    let counter = 0;
    counter++;
    return counter;
}
console.log(addOne());      // 1
console.log(addOne());      // 1
console.log(addOne());      // 1
```
Because we reinitialize counter variable every time we call the *addOne* function. We can fix it using the following
code:
```javascript
const addOne = () => {
    let counter = 0;    // this is kind of global variable for arrow function below
    return () => {
        return counter++;
    }
}
const clb = addOne();
console.log(clb());     // 0
console.log(clb());     // 1
console.log(clb());     // 2
```
It is going to keep the last value of *counter* variable inside javascript environment. When we use closure, we are
making private members globally available. Closure is useful when we want to make few private members available globally
when needed.

#### *Relative Questions*:

**How can you access private variable or a function outside the scope?**  
We can do this using closure. Using returning a function without parentheses.

**Explain the advantages of the closure?**  
The main advantage of closure is that any member which is private for certain scope, can be accessed keeping it private
so that the variable is away from any accidental change of value. Accessing private members with a closure pattern
assure better approach of making a variable global.

---

### How can sum(5)(6) return 11?
This way is actually call as currying. Currying is supported by many programming languages. It's a unique way to call
inner functions where you can pass arguments partially or pass multiple arguments in a function but 1 argument at a 
time.
```javascript
sum(5, 6);  // two arguments
sum(5)(6);  // one argument at a time
```
Let's see how actual code can be:
```javascript
const sum = function (a) {
    return function (b) {
        return a + b;
    }
}

const cl = sum(5);  // 5 is passed to a and cl has the reference of inner function and stored in lexical environment
const answer = cl(6);   // 6 is passed to b
console.log(answer);    // 11
```
Simplifying the code above using currying:
```javascript
const sum = a => b => a + b;

const answer = sum(5)(6);   // Currying happens here
console.log(answer);    // 11
```
So the question is what is the practical use of currying?  
Let's see an example:
```javascript
const priceCalculator = function (price) {
    return (discountPercentage) => {
        return price * discountPercentage;
    }
}

const discountAmount = priceCalculator(300);
console.log(discountAmount(0.1));       // 30
console.log(discountAmount(0.2));       // 60
console.log(discountAmount(0.3));       // 90
console.log(discountAmount(0.4));       // 120
console.log(discountAmount(0.5));       // 150
```

#### *Relative Questions*:

**What is function currying?**  
It is a way to call functions where you can pass arguments partially or pass multiple arguments in a function but one
argument at a time.

**What will this statement do? Explain in detail.**  
```javascript
const multiplication = a => b => c => a * b * c;
```
Code above is the simplified version of the following code using currying:
```javascript
const multiplication = a => {
    return b => {
        return c => {
            return a * b * c;
        }
    }
}
```

**Explain practical usage of function currying?**  
Currying is an incredible useful technique of functional programming which solves various purposes like passing partial
parameters or avoiding unwanted repetitions.

---

### Iterable & Iterators:
The iterator concept is newly introduced in ES6. It is kind of new mechanism to iterate or traverse through data
structures. As you know Array is an iterable. It means if you want to put a *for ... of* loop on an array, you can
easily do that.
```javascript
const arr = [4, 5, 6, 7];
for (let i of arr) {
    console.log(i);
}
/*
4
5
6
7
 */
```
Similarly, strings, maps, sets, etc are all iterables.  
But image you have an object literal such as the following code:
```javascript
let obj = {
    val1: 10,
    val2: 20,
}
```
And you want to use *for ... of* loop on this object; In short, you want to make this object literal an iterable object.
You can do this in ES6 using *Symbol.iterator* . Let's see an example:
```javascript
let arr = [4, 5, 6, 7];
let itr = arr[Symbol.iterator]();   // returns iterable object
console.log(itr);   // Object [Array Iterator] {}
itr.next();     // {value: 4, done: false}
itr.next();     // {value: 5, done: false}
itr.next();     // {value: 6, done: false}
itr.next();     // {value: 7, done: false}
itr.next();     // {value: undefined, done: true}
```
Now we are going to iterate over an object literal:
```javascript
let obj = {
    start: 10,
    end: 15,
}

for (let i of obj) {
    console.log(i);     // TypeError: obj is not iterable
}
```
Let's see the rules first of all:
* When you want to make an object literal iterable, it should have method having key value as *Symbol.iterator*.
* The object literal should also have the *next()* method.
```javascript
let obj = {
    start: 10,
    end: 15,
}

obj[Symbol.iterator] = function () {
    const itr = {
        next() {
            if (obj.start <= obj.end) return {value: obj.start++, done: false};
            else return {done: true};
        }
    }
    return itr;
}

for (let i of obj) {
    console.log(i);
}

/*
10
11
12
13
14
15
 */
```
The key part is you put a method inside the object, which returns an iterable object. *Symbol.iterator* must return
the object itself because there won't be any reference otherwise.  

#### *Relative Questions*:

**What is the purpose of the iterator?**  
The use of an iterator is to make a data structure iterable which is not. When you create an object which should have
facility of putting *for ... of* loop on it, then you need to create the iterator.

**How do you create an iterator?**  
The *Symbol.iterator* method must be implemented which should return an iterator object and should also have a next()
method which returns the object.

**Explain the practical use of an iterator?**  
The use of an iterator is not very prompt when you use it in the same scope as we have seen earlier. As the custom data
structure needs to have a provision of *for ... of* kind of loop then if your object is not iterable then it won't work.
You are creating a pointer to move in data structure which you have provided to the end user who is actually a
programmer.

---

### Generators:
Generators can help you to pause and resume the code. Normally when you write a function, it returns a single value.
You can think of generators as a kind of functions which can return multiple values in phases.  
The function* is the keyword used to define a generator function and yield is an operator which pauses the generator;
yield also helps to receive input and send output.
```javascript
const genFunction = function* () {
    console.log("Hello");
    yield "YieldedValue.";  // At this time the function will be paused
    console.log("World!");
    yield;  // yield itself is capable of returning any value
    console.log("JavaScript");
}

const gObj = genFunction();
console.log(gObj);      // Object [Generator] {}
```
When a generator function is called, It does not call the function, instead it returns a generator object. There is a
*next()* method which starts the execution till the yield operator.
```javascript
console.log(gObj.next());       // Hello  {value: "YieldedValue.", done: false}
console.log(gObj.next());       // World! {value: undefined, done: false}
console.log(gObj.next());       // JavaScript {value: undefined, done: true}
console.log(gObj.next());       // {value: undefined, done: true}
```
Generators are iterable, So we can put *for ... of* loop on them:
```javascript
for (let o of gObj) console.log(o);
/*
Hello
YieldedValue.
World!
undefined
JavaScript
 */
```
Since generators are iterable, So we can use spread operator with them:
```javascript
const gArr = [...genFunction()];    // This will create an array with returned values
console.log(gArr);
/*
Hello
World!
JavaScript
[ 'YieldedValue.', undefined ]
 */
```
We can refactor our previous code related to iterator section using generators:
```javascript
let obj = {
    start: 10,
    end: 15,
    *[Symbol.iterator]() {
        for (let i = this.start; i <= this.end; i++) yield i;
    }
}

for (let i of obj) console.log(i);

/*
10
11
12
13
14
15
 */
```
We can also get all values as an array:
```javascript
let obj = {
    start: 10,
    end: 15,
    *[Symbol.iterator]() {
        for (let i = this.start; i <= this.end; i++) yield i;
    }
}

console.log([...obj]);  // [10, 11, 12, 13, 14, 15]
```
Generators work well with iterators. The yield operator is only used in generator functions. When it comes to recursive
functions or calling one generator function from another, yield* syntax is used:
```javascript
function* gen1() {
    console.log("Hello")
}

function* gen2() {
    const g1 = gen1();
    g1.next();   // We need to move the function pointer using the next() method
}

const g2 = gen2();
g2.next();      // Hello
```
We can summarize code snippet above like the following code:
```javascript
function* gen1() {
    console.log("Hello")
}

function* gen2() {
    yield* gen1();
}

const g2 = gen2();
g2.next();      // Hello
```
In case we have a recursive function:
```javascript
function* factorial() {
    const certainCondition = true;
    if (certainCondition) {
        // Exit Code
    }
    yield* factorial();
}
```
The generator object has next() method which we have already seen and it returns an object like the following:
```javascript
/*
{value: val, done: true/false}
 */
```
It also has two other methods; return() and throw(). return() method is similar to next() method, but it returns object
like the following:
```javascript
/*
{value: val, done: true}
 */
```
And it terminates the generator. So return method is used to terminate the generator. Let's see an example:
```javascript
function* gen() {
    yield "One";
    yield "Two";
}

const gObj = gen();
console.log(gObj.next());       // {value: "One", done: false}
console.log(gObj.next());       // {value: "Two", done: false}
console.log(gObj.next());       // {value: undefined, done: true}
```
But if we use return() method:
```javascript
function* gen() {
    yield "One";
    yield "Two";
}

const gObj = gen();
console.log(gObj.return());         // {value: undefined, done: true}
console.log(gObj.next());           // {value: undefined, done: true}
console.log(gObj.next());           // {value: undefined, done: true}
```
So when you want to come out of generator function or terminate it, you can use return() method. We can also pass the
condition message to return method in order to terminate generator function:
```javascript
function* gen() {
    yield "One";
    yield "Two";
}

const gObj = gen();
console.log(gObj.return("Condition Done!"));         // {value: "Condition Done!", done: true}
console.log(gObj.next());           // {value: undefined, done: true}
console.log(gObj.next());           // {value: undefined, done: true}
```
We can also suspend the termination using try...finally block:
```javascript
function* gen() {
    try {
        yield "One";
        yield "Two";
    } finally {
        yield "Finally";
    }
}

const gObj = gen();
console.log(gObj.next());       // {value: "One", done: false}
console.log(gObj.return());     // {value: "Finally", done: false}
console.log(gObj.next());       // {value: undefined, done: true}
```
Writing *yield* inside *finally* block won't allow the return() to terminate.

---

The throw() method throws an exception at the location of yield which made the last suspension in the generator
function.
```javascript
function* gen() {
    try {
        yield "One";
        yield "Two";
    } catch (err) {
        console.log(`Error is ${err}`);
    }
}

const gObj = gen();
console.log(gObj.next());       // {value: "One", done: false}
console.log(gObj.throw());      // Error is undefined   {value: undefined, done: true}
```

If there is an error condition, you will use throw() or return() methods. The methods shown earlier are used in some
situations only, with *if* condition or *switch* case, etc.  

---

Generator functions are rarely used in javascript code, but for asynchronous processes, iterators and generators
combined call work well.

#### *Relative Questions*:

**What are generator functions? Explain the syntax.**  
Generator functions give you a way where you can pause a process and continue from there after some time.

**Which is the right syntax?**  
```javascript
function* first() {
    // Some Code
}

// or

function *second() {
    // Some other code
}
```
Both are valid. You can write any syntax from blow:
1. function* (){}
2. function *(){}
3. function*(){}

But the first one is commonly used syntax.

**Explain all methods of generator object?**  
1. next(): It moves the function pointer to the next line from last suspended yield
2. return(): It allows to terminate the generator function
3. throw(): It can help to raise an error with the generator object

**Explain the use of `yield*` syntax?**  
It is used to call generator function from another generator function or even to call recursive generator function.

**Can you prevent return() from terminating the generator function?**  
Yes, by using yield statement inside try...finally block:
```javascript
function* gen() {
    try {
        yield "One";
        yield "Two";
    } finally {
        yield "Finally";
    }
}
```
</div>

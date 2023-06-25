# Javascript Interview Questions

<div style="text-align: justify">

## Arrays:

### Explain Array and Traversal in Array:

Normally when you have a variable it can store only one value.
```javascript
let a = 10; // value of 10 stored in variable a
a = 20; // value is overwritten
```
It means at a time only one value is stored. When you want to store values under one name, then you can use an array.
Array is available in all programming languages. Few languages support only specific type of array. For example an
array of integers cannot have string values. In javascript we have array which can store any type of value. In
javascript we have an **Array** class and arrays are the prototype of this class.
```javascript
let arr0 = [4, 7, 9];       // [4, 7, 9]
let arr1 = ["Hi", true, false, 900];        // ["Hi", true, false, 900]
```
Let's try to understand internally what actually happens:
```mermaid
flowchart TD
    subgraph arr1 
        first["0: 'Hi'"]
        second["1: true"]
        third["2: false"]
        fourth["3: 900"]
    end
```
0 is lower index(boundary) and 3 is upper index(boundary). This array has 4 elements. We can use **length** property in
order to get total number of elements that an array has:
```javascript
console.log(arr1.length);   // 4
```
Referring one specific element of an array using its index value:
```javascript
console.log(arr1[0]);   // Hi
```
Or if we want to access to the last element of an array, we can do this like the following:
```javascript
let arr2 = [1, 2, 3, 4, 5, 6];
// In old school javascript:
console.log(arr2[arr2.length - 1]);
// In ECMAScript 2022 or later:
console.log(arr2.at(-1));
```
We can have an array of object literals. Let's see an example:
```javascript
let products = [
    {productId: "00001", productName: "Iphone"},
    {productId: "00002", productName: "IWatch"},
    {productId: "00003", productName: "MacBook"},
];

console.log(products);
/*
[
    {productId: "00001", productName: "Iphone"},
    {productId: "00002", productName: "IWatch"},
    {productId: "00003", productName: "MacBook"},
]
 */
```
Once again referring a specific element:
```javascript
console.log(products[2]);   // {productId: "00003", productName: "MacBook"}
```
We also can access to elements properties:
```javascript
console.log(prducts[2].productName);    // MacBook
```

Traversal in an Array:  
Traversal means we are going to navigate through an array. we will begin with the most traditional way which is loop
till the last element; Let's see an example:
```javascript
let arr = ["ES5", "ES6", "ES7"];
for (let i = 0; i < arr.length; i++) console.log(arr[i]);
/*
ES5
ES6
ES7
 */
```
In ES6 onwards we have **for...in** and **for...of** to loop through an array:
```javascript
let arr1 = ["ES5", "ES6", "ES7"];
for (let ind in arr1) console.log(ind); // for...in loop returns the indexes
/*
0
1
2
 */

for (let el of arr1) console.log(el);   // for...of loop returns the actual values
/*
ES5
ES6
ES7
 */
```
There are several method to loop through an array. but at this time we just want to see **forEach** method which
receives a callback function:
```javascript
let arr = ["es5", "es6", "es7"];
arr.forEach((elementItself, elementIndex) => console.log(elementItself, elementIndex));
/*
es5 0
es6 1
es7 2
 */
```
The callback function inside the forEach loop actually takes 4 parameters as the following:
```javascript
let arr = ["es5", "es6", "es7"];
class JS {};
arr.forEach(function (elementItself, elementIndex, arrayItself, thisKeywordForCallBack=JS) {
    console.log(`${elementItself}   ${elementIndex}   ${arrayItself}   ${thisKeywordForCallBack}`);
})

/*
es5   0   es5,es6,es7   class JS {}
es6   1   es5,es6,es7   class JS {}
es7   2   es5,es6,es7   class JS {}
 */
// Fourth parameter inside callback function is not available for arrow functions.
```
forEach method cannot be stopped in between like you break the loop.

#### *Relative Questions*:

**What is the difference between for...in and for...of loop?**  
for...in loop will display the index number while for...of loop will refer the actual value of elements.

**What will be the output of the following code?**
```javascript
let arr = ["ES5", "ES6", "ES7", "ES8"];
arr.forEach(function (element, index) {
    console.log(element, index);
    if (index === 2) {
        break;  // Uncaught SyntaxError: Illegal break statement
    }
});
```
You can not break the forEach loop, and it is going to loop till the entire array.

**What will be the output of the following code?**
```javascript
let arr = [7, 9, 0];
console.log(arr[arr.length]);   // Undefined
```
This will display the *undefined* as a result.

---

### Array Element Manipulation:

Adding and removing elements in an array:
There are 4 most known methods that we can use to add or remove elements; *push()*, *pop()*, *shift* and *unshift*.
*push()* and *unshift()* are used to add elements. *push()* method adds one or more elements at the end of an array and
returns the new length; count of elements after adding elements. *unshift()* method adds one or more elements at the
beginning of an array and returns the new length; cont of elements after adding elements. *pop()* and *shift* are used
to remove elements. *pop()* method removes the last element of array, and it returns that removed element. *shift()*
method removes the first element of array, and it returns that removed element.
```javascript
const arr = ["one", "two", "three", "four", "five"];

console.log(arr.push("six"));   // 6
console.log(arr);   // ["one", "two", "three", "four", "five". "six"]

console.log(arr.unshift("zero"));   // 7
console.log(arr);   // ["zero", "one", "two", "three", "four", "five", "six"]

console.log(arr.pop());     // "six"
console.log(arr);   // ["zero", "one", "two", "three", "four", "five"]

console.log(arr.shift());   // "zero"
console.log(arr);   // ["one", "two", "three", "four", "five"]
```
Let's talk about an important method in arrays which is called *splice()* method. This method depending on what
parameters it takes, can add, insert, replace or even remove on or more elements. It also returns all the deleted
elements. Here is its syntax:
```javascript
arrName.splice(start, deleteCount, items);
// Start: Zero-based index at which to start changing the array
// deleteCount: Optional - An integer indicating the number of elements in the array to remove from start
// items: Optional - The elements to add to the array, beginning from start
```
Let's see a couple of examples:
```javascript
let arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(2));     // ["three", "four", "five"]
console.log(arr);   // ["one", "two"]

arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(2, 1));      // ["three"]
console.log(arr);   // ["one", "two", "four", "five"]

arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(2, 1, "New"));      // ["three"]
console.log(arr);   // ["one", "two", "New", "four", "five"]

arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(2, 1, "New", "Another"));      // ["three"]
console.log(arr);   // ["one", "two", "New", "Another", "four", "five"]

arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(2, 0, "New", "Another"));      // []
console.log(arr);   // ["one", "two", "New", "Another", "three", "four", "five"]

// Behave like push method:
arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(arr.length, 0, "New"));      // []
console.log(arr);   // ["one", "two", "three", "four", "five", "New"]

// Behave like unshift method:
arr = ["one", "two", "three", "four", "five"];
console.log(arr.splice(0, 0, "New"));      // []
console.log(arr);   // ["New", "one", "two", "three", "four", "five"]
```
*splice()* method is a fantastic way to deal with various types of operations within an array, but it changes the
original array which isn't very good practice in some cases.

#### *Relative Questions*:

**What is the difference between push() and unshift() methods?**  
*push()* method adds the element at the end of an array whereas *unshift()* method adds element at the beginning.

**What is the difference between pop() and shift() methods?**  
*pop()* method remove the element from the end of an array whereas *shift()* method removes element from the beginning.

**How can you insert an element at the given position?**  
*splice()* method is used to insert an element at a given position:
```javascript
arr.splice(0, 0, "New Element");
```

**How can you remove a specific element?**  
*splice()* method is used to remove a specific element:
```javascript
arr.splice(2, 1);
```

**What does splice() method return?**  
*splice()* method returns deleted items, If there is nothing to delete then it will return an empty array.



</div>
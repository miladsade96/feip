# Javascript Interview Questions

<div style="text-align: justify">

## Strings:

### String Basics

String data type in javascript is easy to handle. Javascript does not have a single character data type like C, C++
or other traditional programming languages. String is a separate data type but that can be used for both single and 
multiple characters.
When it comes to declaring a variable as string, you can use "", '' or `` to deal with string data type. For now, we
discuss single quote and double quote strings. Let's see a couple of examples:
```javascript
let str1 = "I am not new to JS";
console.log(str1);  // I am not new to JS

let str2 = "I'm not new to JS";
console.log(str2);  // I'm not new to JS

/*
let str3 = 'I'm not new to JS';

Uncught SyntaxError: Unexpected identifier m
 */
```
We can use escape sequences in javascript or even traditional programming languages.
```javascript
let str4 = 'I\'m not new to JS';
console.log(str4);  // I'm not new to JS
// \ character is instructing that this is not the end of the quote.
```
javascript valid escape sequences:
```javascript
/*
    \b ---> Backspace       ,   \v ---> Vertical tab    ,   \f ---> Form feed       ,   \u ---> For unicode
    \n ---> New line        ,   \' ---> To display '    ,   \r ---> Carriage return ,   \" ---> To display "
    \t ---> Horizontal tab  ,   \\ ---> To display \
*/
```
\u is one of escape characters which allows you to work with unicode characters. The string data type is stored in
UTF-16 format. But in case if there is a special character to be displayed then unicode is represented as a 4-digit
hexadecimal number. To display the character, you can use *\uHHHH* where *H* is the 4-digit hexadecimal value.
```javascript
let str1 = "\u00A9";
console.log(str1);  // ©️
```
For longer hexadecimal values:
```javascript
let lhv = "\u{1F601}";
console.log(lhv);   // 😄
```

#### *Relative Questions*:

---

**Explain various ways to declare a string variable?**  
```javascript
const str1 = 'This is the first way';
const str2 = "This is the second way";
const str3 = `This is the third way`;

const str4 = new String("This is the fourth way");  // str4 becomes an object instead of primitive data type
```

---

**How do you deal with unicode characters?**  
```javascript
const str1 = "\u00A9";
const str2 = "\u{1F602}";
```

---

**Show the syntax to display long unicode character?**  
```javascript
const luc = "\u{1F602}";
```

---

### ES6 Template Literals:

Let's talk about how do we can declare template string(template literal) in javascript.
```javascript
const str = `I am not new to JS`;
console.log(str);   // I am not new to JS
```
Template literal gives a way to display the expression inside the backtick(`) itself.
```javascript
const a = 20;
const str = `The value of a is ${a}`;
console.log(str);   // The value of a is 20
```
Template literal helps you to store the format as it is then escape sequence is not required for special characters,
spaces and new lines.
```javascript
const format = `This is
     second line and
          This is the third line.`;
console.log(format);
/*
This is
     second line and
          This is the third line.
*/
```

#### *Relative Questions*:

---

**What is the template literal?**  
Template literal is a newer way to declare the string variable in javascript.

---

**How do you display a value or an expression inside template string?**  
Using $ sign and {}
```javascript
let a = "JS";
const fav = `I love ${a}`;
console.log(fav);   // I love JS
```

---

**What are the advantages of using template string?**  
First, you can display a value or an expression without ending the backticks:
```javascript
const val = 10;
const score = `${val} out of 10`;
console.log(score);     // 10 out of 10
```
and the second is storing the format of sting as it is:
```javascript
const format = `This is
     second line and
          This is the third line.`;
console.log(format);
/*
This is
     second line and
          This is the third line.
*/
```

---

### .length Property and Search Methods:

Normally properties and methods should be with objects, whereas string is a primitive type. Javascript
primitive types behave like an object when executed. It means you do have properties and methods with
these primitive types as well. The string type has a length property, which returns the length (number
of characters). Let's see an example:
```javascript
const str = "Javascript";
console.log(str.length);    // 10
```
length is a property, which is always there with a string. There are two important methods related to
strings: *indexOf()* and *lastIndexOf()* which search for a character or string within a string and 
return the index number. Let's see a couple of examples:
```javascript
const str = "This is a test";
console.log(str.indexOf("is"));     // 2 - indexOf() starts searching from the beginning
console.log(str.lastIndexOf("is")); // 5 - lastIndexOf() starts searhing from the end
```
Both methods above return -1 if the value not found, and you can also give the start position:
```javascript
const str = "This is a test";
console.log(str.indexOf("is", 5));      // 5
console.log(str.lastIndexOf("is", 4));  // 2
```
There is another method called *search()*:
```javascript
const str = "This is a test";
console.log(str.search("is"));  // 2
```
There are two main differences between *search()* and *indexOf()* methods:  
1. indexOf() method can have a start position to perform search whereas search() method cannot.
2. indexOf() method cannot be used for advanced search operations like regex whereas search method can.


#### *Relative Questions*:

---

**Explain the indexOf() and the lastIndexOf() methods with syntax?**
```javascript
const str = "This is a test";
console.log(str.indexOf("is"));     // 2 - indexOf() starts searching from the beginning
console.log(str.lastIndexOf("is")); // 5 - lastIndexOf() starts searhing from the end
```

---

**What are the differences between indexOf() and search() methods?**  
We have already discussed it above.

---

**What will be the output of the below given code? Explain with the reason.**  
```javascript
let str = "This is a test";
console.log(str.indexOf("is", 5));  // 5, because it will start searching from index posiotion number 5 all 
// the way to the right side

console.log(str.lastIndexOf("is", 1));  // -1, because it will start searching from index position number 1
// all the way to the left side and since it cannot find "is", it will return -1
```
</div>

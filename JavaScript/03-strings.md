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
Fist, you can display a value or an expression without ending the backticks:
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
</div>
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
</div>
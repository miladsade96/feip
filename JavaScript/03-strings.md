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

---

### Extraction Methods:

We can divide extraction methods in two main categories:
1. String extraction methods
2. Character extraction methods

There are three methods help to extract strings: *Slice()*, *Substr()* and *Substring()*.  
Let's get started with *slice()* method. The syntax of *slice()* method is as follows:
```javascript
str.slice(startIndex, endIndex);    // endIndex is optional
```
It returns the extracted part as a new string without changing the original one. Let's see a couple of examples:
```javascript
const str = "First second third fourth";
console.log(str.slice(10)); // nd third fourth
console.log(str.slice(-10));    // ird fourth
console.log(str.slice(10, 15)); // nd th  - Because 15 itself in not included
console.log(str.slice(-10, -5));    // ird f
```
Let's get into *substr()* method. The syntax of *substr()* method is as follows:
```javascript
str.substr(startIndex, numberOfCharacters);     // numberOfCharacters is optional
```
*slice()* and *substr()* methods are more or less similar methods but *substr()* method takes the number of
characters instead of end index. It returns a portion of the string, starting at the specified index and
extending for a given number of characters afterward. Let's see a couple of examples:
```javascript
const str = "First second third fourth";
console.log(str.substr(10, 5));     // nd th
console.log(str.substr(-10, 5));    // ird f
```
Let's get into *substring()* method. The syntax of *substring()* method is as follows:
```javascript
str.substring(startIndex, endIndex);  // endIndex is optional  
```
It returns the part of the string from the start index up to and excluding the end index, or to the end of the
string if no end index is supplied. Any argument value that is less than 0 or greater than str.length is treated
as if it were 0 and str.length, respectively(It cannot take negative values). Let's see a couple of examples:
```javascript
const str = "First second third fourth";
console.log(str.substring(10));     // nd third fourth
console.log(str.substring(-10));    // First second third fourth
console.log(str.substring(10, 15)); // nd th
```

So let's talk about character extraction. There are two similar methods in terms of character extraction:
1. charAt() - Returns the character
2. charCodeAt() - Returns the integer unicode(UTF-16) value between 0 and 65535

Here are a couple of examples:
```javascript
const str = "First second";
console.log(str.charAt());  // F    default value is 0
console.log(str.charAt(3)); // s
console.log(str.charCodeAt());  // 70   default value is 0
console.log(str.charCodeAt(3)); // 115
console.log(str[2]);    // r    this is legacy syntax in javascript
```

#### *Relative Questions*:

---

**What will be the output of the code below?**  
```javascript
const str = "Hello World";
console.log(str.slice(-5, -2)); // Wor
```

---

**What are the differences between substr() and substring() methods?**  
1. substr() takes 2 arguments - the starting index, and the number of characters to extract. substring() takes 2 arguments - the starting index and the ending index (end not included).
2. substr() can take negative start and length values, substring() cannot. Negative start values in substring() are treated as 0.

---

**What will be the output of the code below?**  
```javascript
const str = "This is a test";
console.log(str.substring(-5));     // This is a test
```
Since substring() does not accept negative start indexes, passing -5 will be treated as 0.

---

**What will be the output of the code below?**
```javascript
const str = "This is a test";
console.log(str.substring(3, 3));   // ""
```
When the start and end indexes passed to substring() are equal, it will return an empty string. An empty string
is returned because there are no characters between index 3 and 3 in the string.

---

**Explain the output of the code below?**  
```javascript
const str = "Hello";
console.log(str.charAt());  // H
```
The charAt() method in JavaScript returns the character at a specified index in the string. However, in this code,
charAt() is called on the string "Hello" without passing an index. When no index is passed to charAt(), it will
default to returning the character at index 0. Therefore, the output of this code will be: "H"

</div>

# Javascript Interview Questions

<div style="text-align: justify">

## Date and Time:

### Date and Time Basics:

The Date() object is used to deal with both date and time. There are different ways to use it with different
arguments. There are four ways to create a date object instance:
* Date(): Returns current date and time along with the local time zone
```javascript
const dt = new Date();
console.log(dt);    // Sat Jul 29 2023 19:12:03 GMT+0330 (Iran Standard Time)
```
* Date(year, month, day, hours, minutes, seconds, milliseconds): This way is more preferable and better
```javascript
const dt = new Date(1996, 8, 4, 9, 25, 40, 27); // month is 0 based - 0: january, 11: december
console.log(dt);    // Wed Sep 04 1996 09:25:40 GMT+0430 (Iran Daylight Time)
```
* Date(milliseconds): In javascript this millisecond count starts from 1st january 1970
```javascript
const dt = new Date(0);
console.log(dt);    // Thu Jan 01 1970 03:30:00 GMT+0330 (Iran Standard Time)

const nowInMS = new Date().getTime();
console.log(nowInMS);   // 1690647131793

console.log(new Date(1690647131793));   // Sat Jul 29 2023 19:42:11 GMT+0330 (Iran Standard Time)
```
* Date("year-month-day"): Other parameters are optional
```javascript
const dt1 = new Date("2020-1-20");   // month is 1 based - 1: january, 12: december
console.log(dt1);    // Mon Jan 20 2020 00:00:00 GMT+0330 (Iran Standard Time)

const dt2 = new Date("2020-08-23T12:32:00.493Z"); // If you don't use T or Z the result may vary from browser to browser
console.log(dt2);   // Sun Aug 23 2020 17:02:00 GMT+0430 (Iran Daylight Time)
```
The format shown above is the **ISO 8601** extended format(yyyy-mm-ddThh:mm:ss.sssZ).

#### *Relative Questions*:

---

**Explain the different ways of create date/time object?**
```javascript
// First:
new Date();

// Second:
new Date(year, month, day, hours, minutes, seconds, milliseconds);

// Third:
new Date(milliseconds);

// Fourth:
new Date("String");
```

---

**What will be the output of the below code?**  
```javascript
const dt = new Date(2020, 8, 23);
console.log(dt);    // Wed Sep 23 2020 00:00:00 GMT+0330 (Iran Standard Time)
```

---

**Explain the various formats of ISO standard followed by javascript?**  
YYYY-MM-DDTHH:mm:ss.sssZ

---

### Date Methods:

The Date() object helps you to create the dates and also the time. We don't have a separate object for time,
we use the Date() object only. The Date() object has various methods for date and time related operations. In
this section, we will go through a few date related *set* and *get* methods. Let's see a couple of examples:
```javascript
let dt = new Date();
console.log(dt);    // Mon Jul 31 2023 18:21:00 GMT+0330 (Iran Standard Time)
// Get methods:
console.log(dt.getFullYear());  // 2023
console.log(dt.getMonth());     // 6  - 0 Based
console.log(dt.getDate());      // 31
console.log(dt.getDay());       // 1 - Day of the week(0 - 6)
console.log(dt.getUTCFullYear());   // 2023
console.log(dt.getUTCDay());    // 1

// Set methods:
dt.setFullYear(1996);   // year, month, day - month and day are optional
console.log(dt);    // Wed Jul 31 1996 18:28:50 GMT+0430 (Iran Daylight Time)
dt.setMonth(9);     // month, day - day is optional and month is 0 based
console.log(dt);    // Thu Oct 31 1996 18:34:35 GMT+0330 (Iran Standard Time)
dt.setDate(4);      // day=4
console.log(dt);    // Fri Oct 04 1996 18:36:29 GMT+0330 (Iran Standard Time)
``` 
Another useful method is *Date.parse()* which parses a string of date and returns the milliseconds:
```javascript
// Syntax:
Date.parse(dateString);
// Or
new Date(dateString);
```
Let's see an example:
```javascript
const dt = Date.parse("1996-09-04");
console.log(dt);    // 841795200000
```

#### *Relative Questions*:

---

**Get a character month?**  
```javascript
const dt = new Date();
const arrMonths = ["January", "February", "March", "april", "May", "June", "July", "August",
                   "September", "October", "November", "December"];
console.log(arrMonths[dt.getMonth()]);  // July
```

---

**Find the date before 50 days of the given date?**  
```javascript
const dt = new Date();
console.log(dt);    // Mon Jul 31 2023 18:54:07 GMT+0330 (Iran Standard Time)
dt.setDate(dt.getDate() - 50);
console.log(dt);    // Sun Jun 11 2023 18:54:07 GMT+0330 (Iran Standard Time)
```

---

**What will be the output if you add35 as date in Date() constructor?**  
```javascript
const dt = new Date(2020, 04, 35);
console.log(dt);    // Thu Jun 04 2020 00:00:00 GMT+0430 (Iran Daylight Time)
```
The autocorrection feature of the date object will validate the date automatically even if it is leap year.
</div>

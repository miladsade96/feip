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
</div>

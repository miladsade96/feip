# Javascript Interview Questions

<div style="text-align: justify">

## Object Oriented Javascript:

### What an object literal is

There are many ways to create an object in javascript. There is also a class **Object** which can allow you
to create an object. In any case of object creation, the basic idea is that we are creating a container to
bundle data pieces. Different data pieces which you may want to pass them to a function or maybe to a server,
then you bundle tha data pieces in an object and pass it. **Object** actually allows you to create a container
to put variables and even functions in it. Let's see an example:
```javascript
// First scenario:
// Product fields:
const pCode = "00001";
const pName = "Desk";
const pPrice = 1000;

function test1(productCode, productName, productPrice) {
    // Code
}

test1(pCode, pName, pPrice);

// ----------------------------------------------
// Second scenario:
// Product fields:
const product = {
    pCode: "00001",
    pName: "Desk",
    pPrice: 1000,
}

function test2(productContainer) {
    // Code
}

test2(product);
```

An object literal is simply a key:value pair data structure. Let's see a couple of examples to clarify this:
```javascript
////////// First scenario //////////

// Creating an object literal:
const obj1 = {};

// Adding key, values (propertis):
obj1.pCode = "00001";
obj1.pName = "Desk";
obj1.pPrice = 1000;
// Adding a method to object literal:
obj1.getData = function () {
    console.log(obj1.pCode, obj1.pName, obj1.pPrice);
}

console.log(obj1);      // {pCode: '00001', pName: 'Desk', pPrice: 1000, getData: ƒ}
obj1.getData();         // 00001 Desk 1000

// ------------------------------------------------------------------------------------------------

////////// Second scenario //////////

// Creating an object literal:
// Declaration of properties and methods is shifted inside an object
const obj2 = {
    pCode: "00002",
    pName: "Table",
    pPrice: 3000,
    getData() { // ES6
        console.log(this.pCode, this.pName, this.pPrice);
    }
}

console.log(obj2);      // {pCode: '00002', pName: 'Table', pPrice: 3000, getData: ƒ}
obj2.getData();         // 00002 Table 3000
```
Dynamic properties in ES6:
```javascript

```
</div>

# TypeScript


**What is typescript and why should we use it?**  
TypeScript is a superset of JavaScript, which means that it includes all the features of JavaScript, plus some additional features, such as:

* **Type safety:** TypeScript allows developers to specify the types of data that variables and functions can hold. This helps to catch errors early in the development process and prevents bugs from being introduced into the code.
* **Classes and interfaces:** TypeScript provides support for classes and interfaces, which are fundamental concepts in object-oriented programming. This makes it easier to write and maintain large and complex JavaScript applications.
* **Modern JavaScript features:** TypeScript supports all the latest JavaScript features, such as modules, generics, and arrow functions. This allows developers to take advantage of the most powerful features of JavaScript without having to worry about compatibility issues.

There are many reasons why developers should use TypeScript. Some of the key benefits include:

* **Improved code quality:** TypeScript's type system helps to improve the quality of JavaScript code by catching errors early and preventing bugs from being introduced. This can lead to faster development times and more reliable software.
* **Better developer experience:** TypeScript provides many features that make it easier and more enjoyable to write JavaScript code. For example, type checking can help developers to identify and fix errors quickly and easily.
* **Increased scalability:** TypeScript's support for classes and interfaces makes it easier to write and maintain large and complex JavaScript applications. This makes TypeScript a good choice for developing enterprise-grade software.

Overall, TypeScript is a powerful language that can help developers to write better, more reliable, and more scalable JavaScript code.

---

**What are the benefits of typescript?**  
TypeScript offers a number of benefits over JavaScript, including:

* **Improved code quality:** TypeScript's type system helps to catch errors early in the development process, preventing bugs from being introduced into the code. This can lead to faster development times and more reliable software.
* **Better developer experience:** TypeScript provides many features that make it easier and more enjoyable to write JavaScript code. For example, type checking can help developers to identify and fix errors quickly and easily.
* **Increased scalability:** TypeScript's support for classes and interfaces makes it easier to write and maintain large and complex JavaScript applications. This makes TypeScript a good choice for developing enterprise-grade software.

In addition to these general benefits, TypeScript also offers a number of specific advantages, such as:

* **Improved tooling support:** TypeScript is well-supported by popular IDEs and text editors, providing features such as code completion, error checking, and debugging.
* **Better collaboration:** TypeScript's type system can help to improve collaboration between developers by making code more readable and understandable.
* **Easier onboarding:** TypeScript can make it easier for new developers to get on board with a project by providing clear documentation of the codebase.

Overall, TypeScript is a valuable tool for any JavaScript developer who wants to write better, more reliable, and more scalable code.

Here are some examples of how TypeScript can be used to improve the quality of JavaScript code:

* **Prevent common errors:** TypeScript can help to prevent common errors such as passing the wrong type of argument to a function or trying to access a property that does not exist.
* **Make code more readable and maintainable:** TypeScript can be used to document the types of data that variables and functions can hold, making code more readable and maintainable.
* **Refactor code more safely:** TypeScript can help to refactor code more safely by ensuring that changes to the code do not break existing functionality.

If you are developing a large and complex JavaScript application, or if you simply want to improve the quality of your code, I highly recommend using TypeScript.

---

**Explain generics in typescript?**  
Generics in TypeScript are a way to create functions, classes, and interfaces that can work with a variety of data types. This makes code more reusable and flexible.

Generics are defined using type parameters. Type parameters are placeholders that can be replaced with any type when the generic function, class, or interface is used.

Here is an example of a generic function:

```typescript
function identity<T>(value: T): T {
  return value;
}
```

This function can be used with any data type, such as numbers, strings, or objects. For example, you could use it to identity a number:

```typescript
const number = 10;
const identityNumber = identity(number); // identityNumber is of type number
```

Or you could use it to identity a string:

```typescript
const string = "Hello, world!";
const identityString = identity(string); // identityString is of type string
```

Generics can also be used to define generic classes and interfaces. For example, here is a generic class:

```typescript
class Stack<T> {
  private items: T[] = [];

  push(item: T) {
    this.items.push(item);
  }

  pop(): T {
    return this.items.pop();
  }

  isEmpty(): boolean {
    return this.items.length === 0;
  }
}
```

This class can be used to create stacks of any data type. For example, you could create a stack of numbers:

```typescript
const numberStack = new Stack<number>();
numberStack.push(1);
numberStack.push(2);
numberStack.push(3);

const poppedNumber = numberStack.pop(); // poppedNumber is of type number
```

Or you could create a stack of strings:

```typescript
const stringStack = new Stack<string>();
stringStack.push("Hello");
stringStack.push("world!");

const poppedString = stringStack.pop(); // poppedString is of type string
```

---

**What are modules in typescript?**  
Modules in TypeScript are a way to organize and encapsulate code. They allow you to export specific parts of your code, so that they can be used by other modules. This can help to improve the modularity and maintainability of your code.

Modules are defined using the `export` and `import` keywords. The `export` keyword is used to export specific parts of your code, such as functions, classes, and variables. The `import` keyword is used to import specific parts of other modules into your code.

For example, here is a simple module that exports a single function:

```typescript
// my-math.ts

export function add(a: number, b: number): number {
  return a + b;
}
```

This module can be imported into other modules using the `import` keyword:

```typescript
// my-app.ts

import { add } from './my-math';

const sum = add(1, 2); // sum is of type number
```

Modules can also be used to export entire classes and interfaces. For example, here is a module that exports a simple `Person` class:

```typescript
// person.ts

export class Person {
  name: string;

  constructor(name: string) {
    this.name = name;
  }
}
```

This module can be imported into other modules using the `import` keyword:

```typescript
// my-app.ts

import { Person } from './person';

const person = new Person('John Doe'); // person is of type Person
```

---

**List the built-in types in typescript?**  
The built-in types in TypeScript are:

* **number:** Represents a numeric value, such as 1, 2.3, or 10.2e5.
* **string:** Represents a sequence of characters, such as "Hello, world!".
* **boolean:** Represents a truth value, either true or false.
* **void:** Represents the absence of a value.
* **null:** Represents the intentional absence of a value.
* **undefined:** Represents the absence of a value due to uninitialization.
* **any:** Represents any type of value.
* **object:** Represents an object, which is a collection of properties.
* **symbol:** Represents a unique identifier.

TypeScript also has a number of other built-in types, such as arrays, tuples, enums, and unions. These types are derived from the basic built-in types listed above.

---

**How to call base class constructor from child class in typescript?**  
To call the base class constructor from a child class in TypeScript, you use the `super()` keyword. The `super()` keyword refers to the parent class of the current class.

For example, the following code shows how to call the base class constructor from a child class:

```typescript
class Person {
  constructor(public name: string) {}
}

class Employee extends Person {
  constructor(public name: string, public salary: number) {
    super(name);
  }
}

const employee = new Employee("John Doe", 100000);
```

In the above example, the `Employee` class extends the `Person` class. The `Employee` class constructor calls the `super()` keyword to call the `Person` class constructor. This ensures that the `Employee` class object is initialized with all the properties of the `Person` class.

You can also pass arguments to the `super()` keyword to initialize the base class constructor parameters. For example, the following code shows how to pass arguments to the base class constructor:

```typescript
class Person {
  constructor(public name: string, public age: number) {}
}

class Employee extends Person {
  constructor(public name: string, public salary: number) {
    super(name, 30);
  }
}

const employee = new Employee("John Doe", 100000);
```

In the above example, the `Employee` class constructor passes the `name` argument to the `super()` keyword to initialize the `name` property of the `Person` class. The `Employee` class constructor also passes the value `30` to the `super()` keyword to initialize the `age` property of the `Person` class.

It is important to note that you must always call the `super()` keyword in the child class constructor if you want to initialize the base class constructor parameters. If you do not call the `super()` keyword, the base class constructor will not be called and the base class properties will not be initialized.

---

**Do we need to compile typescript files and why?**  
Yes, TypeScript files need to be compiled before they can be run in a browser or on a server. This is because TypeScript is a superset of JavaScript, and browsers and servers only understand JavaScript.

When you compile a TypeScript file, the TypeScript compiler converts the TypeScript code into JavaScript code. This JavaScript code can then be run in a browser or on a server.

---

**How to perform string interpolation in typescript?**  
To perform string interpolation in TypeScript, you use template literals. Template literals are enclosed in backticks (`), and they allow you to embed expressions within the string.

For example, the following code shows how to perform string interpolation using a template literal:

```typescript
const name = "John Doe";
const age = 30;

const greeting = `Hello, ${name}! You are ${age} years old.`;
```

You can also use template literals to perform more complex string interpolation tasks, such as formatting numbers and dates. For example, the following code shows how to format a number using a template literal:

```typescript
const price = 10.99;

const formattedPrice = `The price is $${price.toFixed(2)}`;
```

---

**What is the difference between `.ts` and `.tsx` file extensions in typescript?**  
The `.ts` file extension is used for TypeScript files that contain plain TypeScript code. The `.tsx` file extension is used for TypeScript files that contain JSX code.

JSX is a JavaScript syntax extension that allows you to write HTML-like code within your JavaScript code. This can make it easier to develop user interfaces in React and other JavaScript frameworks.

If you are developing a TypeScript application that does not use JSX, you should use the `.ts` file extension. If you are developing a TypeScript application that uses JSX, you should use the `.tsx` file extension.

---

**What are decorators in typescript?**  
Decorators in TypeScript are a way to add metadata to classes, methods, properties, and parameters. Metadata is data that describes the code, but it is not executed. Decorators can be used to perform a variety of tasks, such as:

* **Adding annotations:** Decorators can be used to add annotations to code, such as documentation or version information.
* **Modifying the behavior of code:** Decorators can be used to modify the behavior of code, such as logging method calls or validating property values.
* **Creating custom code generation:** Decorators can be used to create custom code generation, such as generating documentation or creating proxy objects.

Decorators are defined using a special syntax that consists of the `@` symbol followed by the name of the decorator function. The decorator function can take any number of arguments, which can be used to provide metadata to the code.

For example, the following code shows a simple decorator that logs method calls:

```typescript
function logMethodCall(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  console.log(`Calling method ${propertyKey}`);
}

@logMethodCall
class MyClass {
  public myMethod() {}
}
```

When the `MyClass.myMethod()` method is called, the `logMethodCall()` decorator will be executed and the method call will be logged to the console.

Decorators can also be used to modify the behavior of code. For example, the following code shows a decorator that validates property values:

```typescript
function validateProperty(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  if (descriptor.value !== 'foo') {
    throw new Error(`Property ${propertyKey} must be equal to 'foo'`);
  }
}

@validateProperty
class MyClass {
  public myProperty: string;
}
```

When a new instance of the `MyClass` class is created, the `validateProperty()` decorator will be executed and the `myProperty` property value will be validated. If the property value is not equal to `'foo'`, an error will be thrown.

---

**what is interface in typescript?**  
An interface in TypeScript is a way to define a contract in your code. It defines the shape of an object, with specified properties and methods.

Here are some key things to know about interfaces in TypeScript:

- An interface is defined using the interface keyword:

```ts
interface User {
  name: string;
  id: number;
}
```

- An interface doesn't implement anything - it just defines what properties and methods something should have.

- Interfaces can describe objects, functions, arrays, classes, etc.

- Interfaces are used for static type checking - they ensure an object meets the requirements of the interface.

- Objects that implement an interface must contain the properties and methods defined in the interface.

- Interfaces can extend other interfaces using the extends keyword.

- Interfaces can't be instantiated directly - they exist only as a type definition.

- Implementing classes must follow the interface contract - if they don't, it will result in a compile error.

So in summary, interfaces in TypeScript allow you to define reusable static types that define a contract within your code. They are useful for static analysis and enable type checking during development.

---

**What is the difference between classes and interfaces in typescript?**  
Classes and interfaces are two important concepts in TypeScript. Classes are used to define blueprints for objects, while interfaces are used to define the structure of objects.

- **Classes**: Classes can be used to define the properties and methods of objects. Classes can also be used to inherit from other classes to create new classes with new features.
- **Interfaces**: Interfaces define the structure of objects, but they do not provide any implementation. This means that interfaces cannot be used to create objects directly. Interfaces are typically used to validate the types of objects that are passed to functions and methods.

---

**How to implement class constants in typescript?**  
There are two ways to implement class constants in TypeScript:

1. Using the `static` and `readonly` keywords
2. Using the `const` keyword with the `as const` assertion

**Using the `static` and `readonly` keywords**

The first way to implement class constants in TypeScript is to use the `static` and `readonly` keywords. The `static` keyword makes the constant available on the class itself, rather than on instances of the class. The `readonly` keyword prevents the constant from being reassigned.

For example, the following code shows how to implement a class constant using the `static` and `readonly` keywords:

```typescript
class Person {
  static readonly MAX_AGE = 120;

  constructor(public name: string) {}
}

// Access the class constant
const maxAge = Person.MAX_AGE;
```

The `MAX_AGE` constant is now available on the `Person` class itself. This means that you can access the constant without having to create an instance of the class.

**Using the `const` keyword with the `as const` assertion**

The second way to implement class constants in TypeScript is to use the `const` keyword with the `as const` assertion. The `const` keyword prevents the variable from being reassigned. The `as const` assertion tells the TypeScript compiler to treat the variable as a constant.

For example, the following code shows how to implement a class constant using the `const` keyword with the `as const` assertion:

```typescript
class Person {
  constructor(public name: string) {}
}

// Access the class constant
const MAX_AGE: number as const = 120;
```

The `MAX_AGE` constant is now treated as a constant by the TypeScript compiler. This means that you cannot reassign the constant.

---

**What are getters and setters in typescript?**  
Getters and setters are methods that allow you to read and write to the properties of an object in a controlled way. Getters are used to get the value of a property, while setters are used to set the value of a property.

**Getters**

Getters are defined using the `get` keyword. Getters can take any number of arguments, and they can return any value.

For example, the following code shows a simple getter:

```typescript
class Person {
  private _name: string;

  constructor(name: string) {
    this._name = name;
  }

  get name(): string {
    return this._name;
  }
}
```

This getter returns the value of the `_name` property.

Getters can be used to perform validation and other tasks before returning the value of a property. For example, the following getter validates the value of the `_age` property before returning it:

```typescript
class Person {
  private _age: number;

  constructor(age: number) {
    if (age < 0) {
      throw new Error('The age must be a non-negative number.');
    }

    this._age = age;
  }

  get age(): number {
    return this._age;
  }
}
```

This getter will throw an error if the `_age` property is less than zero.

**Setters**

Setters are defined using the `set` keyword. Setters take one argument, which is the new value of the property.

For example, the following code shows a simple setter:

```typescript
class Person {
  private _name: string;

  constructor(name: string) {
    this._name = name;
  }

  set name(name: string) {
    this._name = name;
  }
}
```

This setter sets the value of the `_name` property to the value of the `name` parameter.

Setters can be used to perform validation and other tasks before setting the value of a property. For example, the following setter validates the value of the `_age` property before setting it:

```typescript
class Person {
  private _age: number;

  constructor(age: number) {
    this._age = age;
  }

  set age(age: number) {
    if (age < 0) {
      throw new Error('The age must be a non-negative number.');
    }

    this._age = age;
  }
}
```

This setter will throw an error if the `age` parameter is less than zero.

**Benefits of using getters and setters**

Getters and setters offer a number of benefits, including:

* **Validation:** Getters and setters can be used to perform validation on the values of properties. This can help to prevent errors in your code.
* **Encapsulation:** Getters and setters can be used to encapsulate the properties of an object. This can help to protect the properties from being modified directly.
* **Flexibility:** Getters and setters can be used to implement custom logic when reading and writing to the properties of an object. This can make your code more flexible and reusable.

---

**Does typescript support all object-oriented principles?**  
Yes, TypeScript supports all the core object-oriented principles, including:

* **Abstraction:** TypeScript supports abstract classes and interfaces, which can be used to define the structure and behavior of objects without providing a concrete implementation. This allows you to create reusable and flexible code.
* **Encapsulation:** TypeScript supports private and protected members, which can be used to protect the internal state of objects from being modified directly. This helps to ensure the correctness and maintainability of your code.
* **Inheritance:** TypeScript supports inheritance, which allows you to create new classes that inherit the properties and methods of existing classes. This allows you to reuse code and create more complex and powerful objects.
* **Polymorphism:** TypeScript supports polymorphism, which allows you to treat different types of objects in the same way. This allows you to write more generic and reusable code.

In addition to these core principles, TypeScript also supports a number of other object-oriented features, such as:

* **Decorators:** Decorators can be used to add metadata to classes, methods, and properties. This metadata can be used to modify the behavior of code at runtime.
* **Generics:** Generics allow you to write code that can be used with different types of data. This makes your code more flexible and reusable.
* **Modules:** Modules allow you to organize your code into separate units. This makes your code more modular and easier to maintain.

---

**When to use interfaces and when to use classes in typescript?**  
Interfaces and classes are both powerful tools for object-oriented programming in TypeScript. However, they have different purposes and are best used in different situations.

**When to use interfaces:**

* To define the shape of an object, without providing any implementation.
* To validate the types of objects passed to functions and methods.
* To create generic types that can be used with different types of data.

**When to use classes:**

* To define the structure and behavior of objects.
* To implement abstract classes and interfaces.
* To create new classes that inherit from existing classes.

---

**How could you check `null` and `undefined` in typescript?**  
We can use the `nullish coalecsing operator` as follows:
```javascript
function nullOrUndefinedDetector(input: any) {
  console.log(`Input value is ${input ?? "null or undefined"}`);
}

nullOrUndefinedDetector(null);          // "Input value is null or undefined"
nullOrUndefinedDetector(undefined);     // "Input value is null or undefined"
nullOrUndefinedDetector(0);             // "Input value is 0"
nullOrUndefinedDetector("0");           // "Input value is 0"
nullOrUndefinedDetector("");            // "Input value is "
nullOrUndefinedDetector({ a: 1 });      // "Input value is [object Object]"
nullOrUndefinedDetector([1, 2, 3]);     // "Input value is 1,2,3"
nullOrUndefinedDetector(true);          // "Input value is true"
nullOrUndefinedDetector(false);         // "Input value is false"
```

---

**What are the differences between the typescript and javascript?**  
TypeScript and JavaScript are both programming languages, but they have some key differences.

**TypeScript** is a superset of JavaScript, which means that all valid JavaScript code is also valid TypeScript code. TypeScript adds optional static typing to JavaScript, which can help to catch errors early and make code more maintainable.

**JavaScript** is a dynamically typed language, which means that the types of variables and expressions are not checked until runtime. This can make it easier to write code quickly, but it can also lead to errors that are difficult to debug.

**Here is a table that summarizes the key differences between TypeScript and JavaScript:**

| Feature       | TypeScript | JavaScript |
|---------------|------------|------------|
| Static typing | Optional   | Dynamic    |
| Type safety   | Higher     | Lower      |
| Compiler      | Yes        | No         |
| IDE support   | Excellent  | Good       |

**Overall, TypeScript is a good choice for developers who want to write JavaScript code that is more type-safe and maintainable.**

---

**What is a typescript map file?**  
A TypeScript map file is a file that contains information about the original TypeScript source code for a compiled JavaScript file. This information can be used to debug TypeScript code and to improve the performance of JavaScript applications.

TypeScript map files are generated by the TypeScript compiler when you compile your TypeScript code to JavaScript. The map file contains information about the following:

* The original TypeScript source code for each line of JavaScript code.
* The types of variables and expressions in the original TypeScript source code.
* The locations of type annotations in the original TypeScript source code.

TypeScript map files can be used to debug TypeScript code by allowing you to step through the original TypeScript source code as you step through the compiled JavaScript code. This can be helpful for understanding how TypeScript types are translated to JavaScript code.

---

**Could we use typescript on backend and how?**  
Yes, TypeScript can be used on the backend. In fact, TypeScript is becoming increasingly popular for backend development.

There are a few different ways to use TypeScript on the backend. One way is to use a Node.js framework that supports TypeScript, such as Express.js or Nest.js. These frameworks provide TypeScript support out of the box, so you can start using TypeScript right away.

---

**What is the difference between types `String` and `string` in typescript?**  
The difference between the types `String` and `string` in TypeScript is that `String` is a wrapper object, while `string` is a primitive type.

**Wrapper objects** are objects that wrap around primitive types and provide additional functionality. For example, the `String` object provides methods for manipulating strings, such as `charAt()`, `indexOf()`, and `substring()`.

**Primitive types** are the basic building blocks of TypeScript types. They include numbers, strings, booleans, and undefined.

In general, it is recommended to use the `string` type instead of the `String` type, unless you need to use the additional functionality provided by the `String` object. This is because primitive types are more efficient and have fewer associated overhead costs.

---

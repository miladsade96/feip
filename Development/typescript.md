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

**What is Type Erasure in TypeScript?**  
In TypeScript, type erasure refers to the process of removing type annotations during compilation. This means that the extra information you provide about the data types of variables, functions, and other elements in your TypeScript code gets stripped away when it's converted into JavaScript.

---

**How can we create an enum with string values?**  
```typescript
enum Color {
  Red = "RED",
  Green = "GREEN",
  Blue = "BLUE",
}

console.log(Color.Red);
console.log(Color.Green);
console.log(Color.Blue);
```

---

**What does the pipe(|) mean in typescript?**  
The pipe (|) symbol in TypeScript itself doesn't directly relate to function composition, unlike some other languages. However, it is used to define **union types**.

A union type describes a variable that can hold one of several different types. The pipe (|) separates each type in the union.

Here's an example:

```typescript
let value: string | number;

value = "hello"; // Ok, value is a string
value = 10;       // Ok, value is a number

value = true;   // Error: Type 'boolean' is not assignable to type 'string | number'
```

In this example:

* We define a variable `value` with a union type `string | number`. This means `value` can be either a string or a number, but not both at the same time.
* Assigning a string or a number to `value` is valid.
* Assigning a boolean value results in a compilation error because it's not one of the allowed types in the union.

Union types provide flexibility in your code by allowing a variable to hold different data types depending on the situation.

---

**Describe what are conditional types in typescript?**  
Conditional types in TypeScript are like **"if" statements for types**. They let you choose between two types based on a condition that checks another type. This makes your code more flexible and type-safe.

**Think of it like this:**

```typescript
// Basic structure:
T extends U ? X : Y 

// Example:
type MyType<T> = T extends string ? string[] : number[];

let strArray: MyType<string>; // strArray will be of type string[]
let numArray: MyType<number>; // numArray will be of type number[] 
```

---

**How to make arrays that can only be read in typescript?**  
There are two primary ways to create read-only arrays in TypeScript:

**1. Using `ReadonlyArray<T>`:**

This approach defines the array as a generic `ReadonlyArray` type, preventing modifications after initialization.

```typescript
const readOnlyArray: ReadonlyArray<number> = [1, 2, 3];

// Error: Property 'push' does not exist on type 'readonly number[]'
readOnlyArray.push(4);
```

**2. Using `readonly` Keyword:**

This method applies the `readonly` modifier to each array element, prohibiting changes to individual values.

```typescript
const readOnlyArray: readonly number[] = [1, 2, 3];

// Error: Cannot assign to '0' because it is a read-only property.
readOnlyArray[0] = 4; 
```

---

**How can we use optional chaining in typescript?**  
Optional chaining in TypeScript provides a safe way to access nested object properties without causing errors if a property is null or undefined.

**How to use it:**

Instead of writing a chain of `if` statements to check for null or undefined values, use the **question mark operator (`?.`)** between properties and method calls.

**Example:**

```typescript
interface User {
  address?: {
    street?: string;
  };
}

const user: User = {};

// Without optional chaining
if (user.address && user.address.street) {
  console.log(user.address.street); 
}

// With optional chaining
console.log(user.address?.street); // No error, logs undefined
```

---

**What is optional chaining in typescript?**  
Optional chaining (`?.`) in TypeScript is a safe way to access potentially **undefined** or **null** properties of an object.

**In short:** It prevents ugly errors when you're unsure if a property exists. Instead of crashing, it gracefully returns `undefined`.

**Example:**

```typescript
const user = {
  name: "Alice",
  // address object might not always exist
  address: { 
    street: "Wonderland Lane"
  }
};

// Without optional chaining: 
// const street = user.address.street; // Potential error if user.address is undefined

// With optional chaining:
const street = user.address?.street; // Safe, returns "Wonderland Lane" or undefined

```

---

**What is the purpose of Nullish Coalescing Operator in typescript?**  
The Nullish Coalescing Operator (`??`) in TypeScript provides a safe way to access a value from a variable that might be `null` or `undefined`.

**In short, it offers a default value when dealing with potentially missing data, but only if the data is actually missing (null or undefined), unlike the traditional OR operator (`||`) which considers other falsy values like 0 or "" as well.**

This leads to more predictable and reliable code when handling optional values.

---

**What are assertion functions in typescript?**  
Assertion functions in TypeScript are a special type of function used to tell the TypeScript compiler to treat an argument as a specific type **at compile time only**. They don't perform any runtime type checking.

**In short:** They're like type "hints" for the compiler, helping it understand your code better and catch potential errors during development, but they disappear entirely in the final JavaScript code.

**Example:**

```typescript
function assertIsNumber(value: any): asserts value is number {
  if (typeof value !== 'number') {
    throw new Error('Value must be a number');
  }
}

const input: any = "hello"; 

assertIsNumber(input); // TypeScript now knows that 'input' is a number

// ... you can now safely use 'input' as a number
console.log(input + 5); 
```

---

**Which access modifiers are implied when not specified in typescript?**  
In TypeScript, when no access modifier is specified, the implied access modifier is **`public`**.

This means that without any explicit modifier, class members (properties and methods) are accessible from anywhere, both inside and outside the class they are defined in.

---

**What is Typings in typescript?**  
Typings in TypeScript act like **instruction manuals for your JavaScript code.** They tell TypeScript what **data types** your variables, function parameters, and return values should have.

**In a nutshell:**

* **Typings = Data Type Definitions**
* They make your code more **reliable and easier to understand**.
* TypeScript uses typings to **catch errors early on**.

---

**What is the default access modifier for members of a class in typescript?**  
In TypeScript, the default access modifier for class members (properties and methods) is **public**. This means that unless you explicitly specify a different access modifier, all members will be accessible from anywhere in your code.

---

**How typescript is optionally statically typed language?**  
It seems there's a slight misunderstanding. TypeScript isn't "optionally" statically typed; it's **inherently statically typed**. However, its type system is **flexible** and allows for **implicit type inference**, which might give the impression of optional typing. Let me clarify.

**Statically Typed:** TypeScript analyzes your code for type errors *before* runtime. This means it checks if variables, function arguments, and return values are used consistently with their declared types during the compilation process.

**Type Inference:** You don't always have to explicitly write types in TypeScript. The compiler is smart enough to infer the type of a variable based on its initial value or usage context.

**Flexibility:**  While TypeScript encourages type annotations, it allows you to omit them when desired or when you want more dynamic behavior. However, this comes with trade-offs, as you lose the safety net of strict type checking in those instances.

Let's illustrate with an example:

```typescript
// Explicit type annotation
let name: string = "Alice"; 

// Type inferred automatically
let age = 30;   // TypeScript infers 'age' to be of type 'number'

// No type annotation (implied 'any' type)
let anything = "hello";
anything = 42;  // No type error, could lead to issues later
```

**Explanation:**

1. **Explicit Type:** We declared `name` as a `string`. TypeScript will enforce that only string values can be assigned to `name`.
2. **Type Inference:**  We didn't specify a type for `age`, but TypeScript infers it to be `number` based on the initial value `30`.
3. **Implicit 'any':** When you don't provide a type and TypeScript can't infer it, the variable is implicitly typed as `any`.  This is where the "optional" feeling might come from. `any` bypasses type checking and allows any value to be assigned.

**Important Note:** While using `any` or omitting types might seem convenient, it makes your code more prone to runtime errors. TypeScript's strength lies in its type system, and leveraging it fully leads to more robust and maintainable code.

---

**How to use external plain javascript libraries in typescript?**  
TypeScript offers great flexibility for integrating external JavaScript libraries, even those without built-in type definitions. Here's a breakdown of the process and an illustrative example:

**1. Installation (If Necessary)**

If the JavaScript library isn't already part of your project, install it using your preferred package manager:

```bash
npm install library-name 
# or
yarn add library-name
```

**2. Understanding Type Definitions**

TypeScript leverages type definitions (`.d.ts` files) to understand the structure and types within JavaScript libraries.

* **Option A: Existing Definitions** - Many popular libraries have community-maintained type definitions on DefinitelyTyped. You can install these using:

   ```bash
   npm install --save-dev @types/library-name
   # or
   yarn add -D @types/library-name
   ```

* **Option B: Creating Definitions** - If type definitions aren't available, you can write your own or use the `declare` keyword to provide basic typing information.

**3. Importing and Using the Library**

* **Direct Import (with Type Definitions)**

   ```typescript
   import * as libraryName from 'library-name'; 

   libraryName.someFunction(); 
   ```

* **Import with `require` (for global libraries)**

   ```typescript
   const libraryName = require('library-name');

   libraryName.someFunction();
   ```

* **Accessing Global Objects (if the library exposes them)**

   ```typescript
   window.libraryName.someFunction(); 
   ```

---

**Does typescript support function overloading?**  
Yes, TypeScript supports function overloading. Function overloading allows you to define multiple function signatures for the same function name. This enables you to create more flexible and type-safe functions that can handle different input types.

**How it works:**

1. **Multiple Signatures:** You define two or more function signatures with the same name but different parameter lists (number of parameters or their types).
2. **Type Inference:** TypeScript's type system analyzes the arguments passed to the overloaded function during compilation.
3. **Signature Matching:**  It selects the most specific signature that matches the provided arguments.
4. **Implementation:** You provide a single implementation for the function, which should handle all the defined overloads.

**Example:**

```typescript
function greet(person: string): string;
function greet(person: { name: string; age: number }): string;

function greet(person: unknown): string {
  if (typeof person === 'string') {
    return `Hello, ${person}!`;
  } else if (typeof person === 'object' && person !== null && 'name' in person) {
    return `Hello, ${person.name}! You are ${person.age} years old.`;
  } else {
    return 'Hello, there!';
  }
}

console.log(greet('Alice')); // Output: "Hello, Alice!"
console.log(greet({ name: 'Bob', age: 30 })); // Output: "Hello, Bob! You are 30 years old."
```

**Benefits of Function Overloading:**

* **Improved Type Safety:** TypeScript ensures that you call the overloaded function with arguments that match one of the defined signatures.
* **Code Readability:** Overloading makes your code more concise and easier to understand by clearly showing the different ways a function can be used.
* **Flexibility:**  You can handle different data types and variations in your function arguments without resorting to multiple function names or complex logic within a single function body.

---

**Explain how and why we could use property decorators in typescript?**  
Property decorators in TypeScript provide a concise and elegant way to **add metadata or modify the behavior of class properties**. Think of them as powerful annotations that can enhance your code's functionality without cluttering the core logic.

**Why Use Property Decorators?**

1. **Clean Separation of Concerns:**  They separate cross-cutting concerns, such as validation, logging, or reactivity, from the core property definition, making your code more maintainable and readable.
2. **Code Reusability:** Define common logic once as a decorator and apply it to multiple properties across your codebase.
3. **Enhanced Metadata:**  Decorators can attach valuable information (metadata) to properties, which can be leveraged by other parts of your application or libraries.

**How Property Decorators Work:**

A property decorator is simply a function that is applied to a class property using the `@decoratorName` syntax. This function receives metadata about the decorated property, allowing you to inspect or modify it.

**Example: Building a Validation Decorator**

Let's imagine you want to enforce that a specific property in your class should always be a string and have a minimum length. We can achieve this elegantly using a property decorator:

```typescript
// Decorator factory: Creates the actual decorator function
function MinLength(minLength: number) {
  return function (target: any, propertyKey: string) {
    let value: string;

    // Define a getter and setter for the property
    Object.defineProperty(target, propertyKey, {
      get: () => value,
      set: (newValue: string) => {
        if (newValue.length < minLength) {
          throw new Error(`Property '${propertyKey}' must be at least ${minLength} characters long.`);
        }
        value = newValue;
      },
    });
  };
}

class Product {
  @MinLength(5) // Apply the decorator with desired length
  name: string;

  constructor(name: string) {
    this.name = name; 
  }
}

// Usage
const validProduct = new Product("Valid Name"); 

const invalidProduct = new Product("Inv"); // Throws an error
```

**Explanation:**

1. **Decorator Factory (`MinLength`):**
    - Takes `minLength` as input and returns the actual decorator function.
    - This pattern allows you to create decorators with configurable parameters.

2. **Decorator Function:**
    - Receives the `target` (class prototype) and `propertyKey` (name of the decorated property).
    - Uses `Object.defineProperty` to redefine the property with a custom getter and setter.
    - The setter enforces the `minLength` validation rule.

3. **Applying the Decorator (`@MinLength(5)`):**
    - Attaches the `MinLength` decorator to the `name` property of the `Product` class, enforcing a minimum length of 5 characters.

---

**What are different components of typescript?**  
Let's break down the core components of TypeScript and illustrate them with examples.

**Fundamental TypeScript Components**

1. **Types**: The heart and soul of TypeScript. They provide static typing to your JavaScript code, meaning you declare what kind of data a variable can hold. This leads to:

    * **Early Error Detection:**  TypeScript catches type errors during compilation, preventing runtime surprises.
    * **Code Clarity and Maintainability:** Types act as self-documenting code, making it easier to understand and work with.

   **Example:**

   ```typescript
   let username: string = "Alice"; // String type
   let age: number = 30;          // Number type
   let isLoggedIn: boolean = true; // Boolean type

   // Error: Type 'number' is not assignable to type 'string'.
   username = 123; 
   ```

2. **Interfaces**: Define the structure or shape of an object, ensuring consistency in how you work with data.

   **Example:**

   ```typescript
   interface User {
       id: number;
       name: string;
       email?: string; // Optional property
   }

   let newUser: User = {
       id: 1,
       name: "Bob"
   };
   ```

3. **Classes**: A blueprint for creating objects, encapsulating data (properties) and functions (methods) that work with that data. TypeScript enhances JavaScript classes with features like access modifiers (public, private, protected) and interfaces.

   **Example:**

   ```typescript
   class Animal {
       protected name: string;

       constructor(name: string) {
           this.name = name;
       }

       makeSound(sound: string): void {
           console.log(`${this.name} makes a ${sound} sound!`);
       }
   }

   class Dog extends Animal { 
       constructor(name: string) {
           super(name);
       }

       bark(): void {
           this.makeSound("bark"); 
       }
   }

   let myDog = new Dog("Buddy");
   myDog.bark(); // Output: Buddy makes a bark sound!
   ```

4. **Generics**: Provide a way to write reusable code that can work with different types without sacrificing type safety.

   **Example:**

   ```typescript
   function identity<T>(arg: T): T {
       return arg;
   }

   let myString: string = identity<string>("Hello");
   let myNumber: number = identity<number>(100); 
   ```

5. **Enums**: A way to give more meaningful names to sets of numeric values.

   **Example:**

   ```typescript
   enum Status {
       Pending,
       Approved,
       Rejected 
   }

   let orderStatus: Status = Status.Approved;
   ```

6. **Modules**: Allow you to organize your code into smaller, reusable units, making it more maintainable. You use `import` and `export` to work with modules.

   **Example:**

   ```typescript
   // mathUtils.ts
   export function add(x: number, y: number): number {
       return x + y;
   }

   // app.ts
   import { add } from './mathUtils';
   let sum = add(5, 10);
   ```

**Key Benefits of Using TypeScript**

* **Improved Code Quality:** Enforces type safety, reducing runtime errors and bugs.
* **Enhanced Developer Productivity:**  Provides better code completion, navigation, and refactoring in IDEs.
* **Large-Scale Development:** Makes it easier to manage and scale complex projects.

Let me know if you'd like a deeper dive into a specific component or want to explore more advanced TypeScript concepts!


---

**How can we allow class defined in a module to be accessible outside of that module in typescript?**  
Certainly, let's explore how to make TypeScript classes defined within modules accessible externally.

**Fundamentals**

In TypeScript, modules serve as containers for code, enhancing organization and preventing naming collisions. By default, members (classes, functions, interfaces, etc.) within a module are internally scoped, meaning they aren't visible or usable outside that module. To grant external access, we utilize the `export` keyword.

**Example**

Let's imagine we have a module named `shapes.ts`:

```typescript
// shapes.ts
export class Rectangle {
  constructor(public width: number, public height: number) {}

  getArea(): number {
    return this.width * this.height;
  }
}
```

In this module:

1. We define a class `Rectangle`.

2. Crucially, we prefix the class declaration with `export`. This keyword signals that the `Rectangle` class should be accessible from other parts of our project.

Now, let's use this class in another file, say `app.ts`:

```typescript
// app.ts
import { Rectangle } from './shapes'; // Assuming 'shapes.ts' is in the same directory

const myRectangle = new Rectangle(5, 10);
console.log(myRectangle.getArea()); // Output: 50
```

---

**What are the differences between Private and Protected variables in typescript?**  
Let's break down the differences between `private` and `protected` variables in TypeScript:

**Private Variables**

* **Scope:** A private member is only accessible within the *same class* where it's declared. Not even subclasses (children) can access it directly.
* **Encapsulation:**  Private members enforce strong encapsulation, hiding data and implementation details from the outside world. This makes your code more maintainable because changes to private members are less likely to break other parts of your codebase.

**Protected Variables**

* **Scope:** A protected member is accessible within the *same class* where it's declared *and* by any *subclasses* (children) that inherit from that class.
* **Inheritance:** Protected members facilitate code reuse through inheritance. Subclasses can directly access and potentially modify these members, enabling specialized behavior.

**Example**

```typescript
class Animal {
  private name: string; // Private: Only accessible within Animal
  protected sound: string; // Protected: Accessible within Animal and its subclasses

  constructor(name: string, sound: string) {
    this.name = name;
    this.sound = sound;
  }

  makeSound() {
    console.log(`${this.name} says ${this.sound}`); 
  }
}

class Dog extends Animal {
  constructor(name: string) {
    super(name, 'Woof!'); // Accessing protected 'sound' from parent
  }

  // Example of a subclass-specific method
  fetch() {
    console.log(`${this.name} runs to fetch!`); // Accessing protected 'name' from parent 
  }
}

const myDog = new Dog('Buddy');
myDog.makeSound(); // Output: Buddy says Woof!
myDog.fetch();     // Output: Buddy runs to fetch!

// console.log(myDog.name);    // Error: 'name' is private and only accessible within Animal
// console.log(myDog.sound);  // Error: 'sound' is protected and only accessible within Animal and its subclasses
```

**In essence:**

* Use `private` when you want to completely hide data and behavior within a single class.
* Use `protected` when you want to enable code reuse through inheritance, allowing subclasses to access and potentially extend the behavior defined by the parent class.

---

**What is the difference between enum and const enum in typescript?**  
Let's break down the difference between regular `enum` and `const enum` in TypeScript:

**Regular `enum`**

* **Compilation:** Regular enums are compiled into JavaScript objects that hold both the key (enum member name) and value (numeric or string representation) mappings. This means they exist as data structures at runtime.
* **Runtime Presence:**  They have a runtime presence, affecting your JavaScript bundle size.
* **Reverse Mapping:** They support reverse mapping, meaning you can get the enum member name from its value.

**Example (Regular `enum`):**

```typescript
enum Status {
  Pending,
  Approved,
  Rejected
}

const requestStatus = Status.Approved; 

console.log(requestStatus); // Output: 1
console.log(Status[1]);     // Output: "Approved" (Reverse mapping)
```

**`const enum`**

* **Compilation:**  `const enum`s are completely removed by the TypeScript compiler during the transpilation process. They are inlined as their literal values wherever they are used.
* **Runtime Absence:** They have no runtime impact, resulting in smaller JavaScript output.
* **No Reverse Mapping:** They do not support reverse mapping because the enum itself doesn't exist at runtime.

**Example (`const enum`):**

```typescript
const enum Sizes {
  Small = 'S',
  Medium = 'M',
  Large = 'L'
}

const mySize = Sizes.Medium;

console.log(mySize); // Output: 'M' (directly replaced at compile time)
// console.log(Sizes[mySize]); // Error: Cannot index type 'typeof Sizes'.
```

**In Essence**

Think of `const enum` as a way to introduce strongly-typed constants that are entirely erased during compilation. They are primarily used for performance optimization, especially when you have a large number of enums or don't require runtime presence.

**When to Use Which**

* **Regular `enum`:** Use when you need reverse mapping (getting the name from the value) or when you might need to iterate over the enum keys/values at runtime.
* **`const enum`:**  Use when you prioritize minimizing JavaScript bundle size and don't need runtime representation or reverse mapping of your enum.

Let me know if you'd like a more in-depth explanation of a specific aspect or have any other questions!


---

**Why do we need abstract keyword for classes and their methods in typescript?**  
Let's break down the concept of abstract classes and methods in TypeScript:

**Why Abstract Classes?**

* **Enforcing Structure:** Abstract classes act as blueprints. They define a common structure (properties and methods) that concrete subclasses *must* follow. This ensures consistency and helps prevent errors from missing implementations.

* **Representing Incomplete Concepts:** Sometimes you have a concept that's too general to be instantiated on its own. An abstract class allows you to represent this idea, leaving the specifics for subclasses.

* **Polymorphism:**  Even though abstract classes can't be instantiated, you can use them for type checking and polymorphism. This means you can work with different subclasses through a common abstract base type.

**Why Abstract Methods?**

* **Deferred Implementation:** Abstract methods are placeholders within an abstract class. They declare a method signature but provide no actual implementation. The responsibility to provide the logic lies with the concrete subclasses.

* **Customization in Subclasses:** This forces each subclass to provide its own specific implementation for the abstract method, tailoring the behavior to its unique purpose.

**TypeScript Example**

```typescript
abstract class Shape {
  constructor(public name: string) {}

  // Abstract method (must be implemented by subclasses)
  abstract calculateArea(): number; 

  displayInfo(): void {
    console.log(`Shape: ${this.name}`);
    console.log(`Area: ${this.calculateArea()}`);
  }
}

class Circle extends Shape {
  constructor(public radius: number) {
    super("Circle"); // Call the parent class's constructor
  }

  // Implementation for the abstract method
  calculateArea(): number {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(public width: number, public height: number) {
    super("Rectangle");
  }

  // Implementation for the abstract method
  calculateArea(): number {
    return this.width * this.height;
  }
}

// Using abstract class and polymorphism
const shapes: Shape[] = [new Circle(5), new Rectangle(4, 6)];

shapes.forEach((shape) => {
  shape.displayInfo();
});
```

---

**What is Structural Typing in typescript?**  
Imagine you're trying to herd a group of animals. You don't really care what specific breed each one is, as long as they all **behave** like ducks (walk like a duck, quack like a duck). That's the essence of **structural typing**, often referred to as "duck typing" in other languages.

In TypeScript, structural typing means that **type compatibility is determined by the shape of the object**, focusing on its properties and methods rather than explicit type declarations.

**Here's a simple example:**

```typescript
interface Flyable {
  fly(): void;
}

class Bird {
  fly() {
    console.log("The bird is flying!");
  }
}

class Plane {
  fly() {
    console.log("The plane is soaring!");
  }
}

function takeFlight(obj: Flyable) {
  obj.fly();
}

const parrot = new Bird();
const airbus = new Plane();

takeFlight(parrot); // Output: The bird is flying!
takeFlight(airbus); // Output: The plane is soaring!
```

**Explanation:**

1. We define an interface `Flyable` which requires a `fly()` method.
2. We have two classes, `Bird` and `Plane`, both implementing a `fly()` method, but **without explicitly stating** that they implement the `Flyable` interface.
3. The `takeFlight` function accepts any object that has a `fly()` method, thanks to the `Flyable` type constraint.
4. Both `parrot` (a `Bird`) and `airbus` (a `Plane`) can be passed to `takeFlight` because they **structurally match** the `Flyable` interface by having the `fly()` method, even though they are different classes.

---

**What is Mixin Class in typescript?**  
Certainly, let's delve into the realm of mixin classes in TypeScript.

**What is a Mixin Class?**

In essence, a mixin is a design pattern in TypeScript (and other languages) that allows you to add properties and methods from one class to another without directly using inheritance. Think of it like adding ingredients to a recipe – each ingredient contributes its flavor without being a complete dish on its own.

**Key Characteristics of Mixins:**

1. **Composition over Inheritance:** Mixins promote composition over classical inheritance. Instead of creating a complex inheritance hierarchy, you can "mix in" desired functionalities from various mixin classes.

2. **Flexibility:** They provide flexibility in assembling classes with specific features. You can pick and choose the mixins you need, leading to more modular and maintainable code.

3. **Code Reuse:** Mixins foster code reuse by encapsulating reusable functionalities that can be shared across different classes.

**Example:**

Let's say we want to create classes representing different types of vehicles. Some vehicles have engines, while others are electric. We can use mixins to model this:

```typescript
class Vehicle {
  constructor(public name: string) {}
}

class EngineMixin {
  startEngine() {
    console.log("Engine started!");
  }
}

class ElectricMixin {
  chargeBattery() {
    console.log("Battery charging...");
  }
}

// Applying mixins using intersection types
class Car extends Vehicle implements EngineMixin {
  // Implement EngineMixin methods if needed
  startEngine: () => void;
}
applyMixins(Car, [EngineMixin]); // Applying the mixin

class ElectricCar extends Vehicle implements ElectricMixin {
  // Implement ElectricMixin methods if needed
  chargeBattery: () => void;
}
applyMixins(ElectricCar, [ElectricMixin]); // Applying the mixin

// Helper function to apply mixins
function applyMixins(derivedCtor: any, baseCtors: any[]) {
  baseCtors.forEach((baseCtor) => {
    Object.getOwnPropertyNames(baseCtor.prototype).forEach((name) => {
      if (name !== "constructor") {
        Object.defineProperty(
          derivedCtor.prototype,
          name,
          Object.getOwnPropertyDescriptor(baseCtor.prototype, name)!
        );
      }
    });
  });
}

const myCar = new Car("Sedan");
myCar.startEngine(); 

const myElectricCar = new ElectricCar("Tesla");
myElectricCar.chargeBattery(); 
```

**Explanation:**

1. **`Vehicle` Class:** A basic class for all vehicles.

2. **`EngineMixin` and `ElectricMixin`:**  These are our mixin classes. They contain functionalities (methods) related to engines and electric systems.

3. **Applying Mixins:** We use a helper function `applyMixins` to apply the mixins to our concrete classes (`Car` and `ElectricCar`).  This function essentially copies the properties and methods from the mixin prototypes onto the prototypes of our classes.

4. **Intersection Types (implements):** We use `implements` with the mixin class names to ensure type safety. This signals to TypeScript that the concrete classes should have the methods declared in the mixins.

**Advantages of Mixins:**

- Improved code organization and reusability.
- Avoidance of deep and complex inheritance chains.
- Enhanced flexibility in composing class behavior.

**Caveats:**

- Can make it harder to understand the exact prototype chain of an object.
- Potential for method name collisions if not managed carefully.

---

**What is unique symbol in typescript and tell me its use cases?**  
There isn't a single "unique symbol" in TypeScript.  Instead, TypeScript leverages the concept of **Symbols** from ECMAScript 2015 (ES6) to provide truly unique identifiers within your code.

**What Makes Symbols Special?**

* **Guaranteed Uniqueness:** Every time you create a Symbol, it's absolutely unique, even if you use the same descriptive string.
* **Hidden from Iteration:** Symbols don't appear in `for...in` loops or `Object.keys()`. This helps you create "private" object properties.

**Use Cases**

1. **Preventing Accidental Collisions:**

   Imagine you're building a library and want to add properties to objects without the risk of conflicting with other libraries or user code. Symbols solve this problem.

   ```typescript
   const MY_KEY = Symbol('mySpecialKey');

   class MyClass {
       [MY_KEY]() { 
           return 'This is a hidden method!';
       }
   }

   const instance = new MyClass();

   console.log(instance[MY_KEY]()); // Output: This is a hidden method!

   // The symbol key is protected
   for (const key in instance) {
       console.log(key); // This won't log "MY_KEY"
   }
   ```

2. **Well-Known Symbols (Built-in Functionality):**

   JavaScript itself uses Symbols to represent special internal properties. TypeScript provides type definitions for these, enabling type safety when working with built-in behaviors.

   ```typescript
   class MyIterable {
       private values = [1, 2, 3];

       [Symbol.iterator]() {
           let i = 0;
           return {
               next: () => {
                   if (i < this.values.length) {
                       return { value: this.values[i++], done: false };
                   } else {
                       return { done: true };
                   }
               }
           };
       }
   }

   const iterable = new MyIterable();

   for (const value of iterable) {
       console.log(value); // Outputs: 1, 2, 3
   }
   ```

**Key Points**

* **Descriptive Strings:**  While not mandatory, it's good practice to give your Symbols descriptive strings (`Symbol('myKey')`) for debugging.
* **Retrieving Symbol Properties:** You can access a property associated with a Symbol using the bracket notation (`object[mySymbol]`) only if you have a reference to the Symbol itself.

**In Essence**

Symbols are your go-to for generating truly unique identifiers, especially when you need to avoid naming conflicts or implement "private" properties in your TypeScript projects.

---

**How to make a read-only tuple type in typescript?**  
TypeScript doesn't have a direct "read-only tuple" type in the same way it has `ReadonlyArray`. However, you can achieve immutability for tuples using a combination of:

* **`readonly` Keyword:**  This keyword prevents modification of individual elements within the tuple.
* **`as const` Assertion:**  This assertion infers the most specific type possible, including the exact length and types of elements within the tuple, further solidifying its structure.

**Example & Explanation:**

```typescript
// Declare a read-only tuple
const point = [10, 20] as const; 

// Try to modify elements (will result in errors)
point[0] = 5;  // Error: Cannot assign to '0' because it is a read-only property.
point.push(30); // Error: Property 'push' does not exist on type 'readonly [10, 20]'.

// Access elements (allowed)
console.log(point[0]);  // Output: 10

// Type of 'point' is inferred as 'readonly [10, 20]'
type Point = typeof point; 
```

**Explanation:**

1. **`const point = [10, 20] as const;`**:
    - We declare `point` using `const`, which prevents reassignment of the entire tuple variable.
    -  `as const`  is crucial: without it, TypeScript would infer `point` as `number[]`. The assertion tells TypeScript to treat the array literal as a tuple with specific element types and length.

2. **Error on Modification Attempts:**
    - Trying to change `point[0]` or use array methods like `push` results in compile-time errors, as TypeScript enforces the read-only nature.

3. **Type Inference:**
    - The type of `point` becomes `readonly [10, 20]`. This means it's a tuple where:
        - The first element is **always** the number `10`.
        - The second element is **always** the number `20`.
        - No further elements can be added or removed.

---

**Explain project references in typescript and its benefits?**  
Project References are a powerful feature in TypeScript that allow you to split your codebase into smaller, more manageable projects. Each project can be developed and compiled independently while still maintaining type-safe dependencies between them. This promotes code reusability, maintainability, and faster build times.

**How it Works:**

Imagine you have two TypeScript projects: "my-library" and "my-app".  "my-library" contains reusable utility functions, while "my-app" is the main application that wants to use them.

1. **`tsconfig.json` in "my-library":**
    -  You compile "my-library" normally, generating a declaration file (`my-library.d.ts`) that describes the public API of your library.
    - You may optionally set `"declaration": true` in the `compilerOptions` to automatically generate declaration files during compilation.

2. **`tsconfig.json` in "my-app":**
    - You add a `"references"` array to the `compilerOptions`, specifying the path to "my-library"'s `tsconfig.json`.
    - You use `import` statements to bring in modules from "my-library" just like any other dependency.

**Example:**

**my-library/src/utils.ts:**

```typescript
export function greet(name: string): string {
  return `Hello, ${name}!`;
}
```

**my-library/tsconfig.json:**

```json
{
  "compilerOptions": {
    "outDir": "./dist",
    "declaration": true // Generate declaration files
  },
  "include": ["src/**/*"]
}
```

**my-app/src/index.ts:**

```typescript
import { greet } from 'my-library';

const message = greet('World');
console.log(message);
```

**my-app/tsconfig.json:**

```json
{
  "compilerOptions": {
    "outDir": "./dist",
    "references": [
      { "path": "../my-library" } 
    ]
  },
  "include": ["src/**/*"]
}
```

**Benefits of Project References:**

* **Modularization:** Decompose large projects into smaller, focused units.
* **Code Reusability:** Share common logic across different projects.
* **Maintainability:** Easier to understand, debug, and maintain smaller codebases.
* **Faster Builds:** TypeScript compiler can process each project independently and only recompile affected code, reducing build times especially in larger projects.
* **Improved Collaboration:** Different teams can work on separate projects with well-defined interfaces.

---

**What are the use cases for const assertion in typescript?**  
`const` assertions in TypeScript provide a way to tell the compiler that a particular variable should be treated as a constant with a literal type, even if its initial value might suggest otherwise. This has some key use cases:

**1. Inferring More Precise Types:**

TypeScript's type inference can sometimes be too broad. `const` assertions help narrow down types for better type safety and code clarity.

**Example:**

```typescript
// Without const assertion:
const colors = ['red', 'green', 'blue'];
// Type: readonly string[]

// With const assertion:
const colors = ['red', 'green', 'blue'] as const;
// Type: readonly ["red", "green", "blue"]
```

Here, without the `const` assertion, `colors` is typed as `readonly string[]`, meaning you can access any string element, but you can't modify the array. With the `const` assertion, the type becomes a tuple with specific string literal types. Now, `colors[0]` is type `'red'`, not just `string`.

**2. Enforcing Immutability:**

`const` assertions ensure that the variable and its properties (for objects) cannot be reassigned, preventing accidental modifications.

**Example:**

```typescript
const car = {
  brand: 'Toyota',
  model: 'Camry',
} as const;

// Error: Cannot assign to 'brand' because it is a read-only property
car.brand = 'Honda';
```

The `const` assertion makes `car` and its properties immutable, leading to an error when trying to modify the `brand` property.

**3. Working with Readonly Data:**

When dealing with data from external sources (APIs, configuration files), using `const` assertions signals that this data is read-only and should not be modified within your code.

**Example:**

```typescript
// Simulating data from an API
const apiResponse = {
  status: 'success',
  data: { userId: 123, username: 'johndoe' },
} as const;

// Accessing data:
const userId = apiResponse.data.userId;
// Type of userId: 123 (not just number)
```

Here, the `const` assertion clarifies that `apiResponse` shouldn't be mutated. Additionally, it allows us to use `userId` with the precise type `123`.

---

**How to choose between never, unknown and any in typescript?**  
Let's break down the differences between `never`, `unknown`, and `any` in TypeScript, along with guidelines on when to use each.

**1. `never`**

- **Meaning:** Represents values that will *never* occur.
- **Use Cases:**
    * **Functions that always throw errors:**  If a function's sole purpose is to throw an error and never return normally, its return type is `never`.
    * **Exhaustive conditional checks:**  When you have a type narrowing system where TypeScript can guarantee all possible cases are handled.

**Example:**

   ```typescript
   function alwaysThrowsError(message: string): never {
     throw new Error(message);
   }

   function handleValue(x: string | number): string {
     if (typeof x === 'string') {
       return x.toUpperCase(); 
     } else if (typeof x === 'number') {
       return x.toFixed(2); 
     } else {
       // This block is unreachable, so 'x' is narrowed to 'never'
       let unreachableValue: never = x; 
       return unreachableValue; // This line will never be executed
     }
   }
   ```

**2. `unknown`**

- **Meaning:** Represents a value whose type is *unknown* at compile time.
- **Use Cases:**
    * **Data from external sources:** When receiving data from APIs, user input, or other unpredictable sources.
    * **Type-safe fallbacks:** When you need a more restrictive alternative to `any` that enforces type checking.

**Example:**

   ```typescript
   function parseData(input: unknown): number | string | undefined {
     if (typeof input === 'string') {
       return input.toUpperCase();
     } else if (typeof input === 'number') {
       return input * 2;
     } 
     return undefined; // Or throw an error for invalid input
   }

   const userDataFromAPI: unknown = await fetchUserData(); 
   // Error: Cannot access property 'name' on type 'unknown'
   // console.log(userDataFromAPI.name); 

   if (typeof userDataFromAPI === 'object' && userDataFromAPI !== null && 'name' in userDataFromAPI) {
     // Now you can access 'name' safely
     console.log(userDataFromAPI.name); 
   }
   ```

**3. `any`**

- **Meaning:**  The "escape hatch" of TypeScript.  It bypasses type checking entirely.
- **Use Cases (Use Sparingly!):**
    * **Migrating JavaScript code:** When you're gradually adding TypeScript to an existing JavaScript project.
    * **Interfacing with highly dynamic libraries:** In rare cases where a library relies heavily on runtime type manipulation.
- **Caution:** Overusing `any` defeats the purpose of TypeScript and can lead to unexpected errors.

**Example (Not Recommended):**

   ```typescript
   function doSomething(value: any): any {
     // No type safety here!
     return value.toUpperCase(); // Could cause runtime errors
   }
   ```

---

**What is the fundamental difference between Optional Chaining and Nullish Coalescing Operator in typescript?**  
Both optional chaining (`?.`) and the nullish coalescing operator (`??`) are powerful tools in TypeScript to handle potentially undefined or null values, but they serve different purposes and behave differently:

**1. Purpose:**

* **Optional Chaining (`?.`):** Used to access properties or methods of an object **safely** when the object itself **might be null or undefined**. It prevents runtime errors by short-circuiting the expression if an intermediate value is null or undefined.
* **Nullish Coalescing (`??`):** Used to provide a **default value** when a variable or expression evaluates to **null or undefined**. It doesn't care about falsy values like `0`, `''`, or `NaN` - only strictly `null` or `undefined`.

**2. Behavior:**

* **Optional Chaining (`?.`):** If any part of the chain encounters `null` or `undefined`, the entire expression evaluates to `undefined` **without throwing an error**.
* **Nullish Coalescing (`??`):**  Returns the first operand if it's **not** `null` or `undefined`. Otherwise, it returns the second operand (the default value).

## Example:

Let's imagine we have a `User` object:

```typescript
interface User {
  name: string;
  address?: {
    street: string;
    city: string;
  };
}
```

Here, the `address` property is optional (marked by `?`).

**Scenario 1: Accessing `city` safely:**

```typescript
const user: User = { name: 'Alice' }; 

// Without optional chaining:
// const city = user.address.city; // ERROR! Cannot read property 'city' of undefined

// With optional chaining:
const city = user.address?.city; 
console.log(city); // Output: undefined (no error thrown)
```

**Scenario 2: Providing a default value for `city`:**

```typescript
const user1: User = { name: 'Bob', address: { street: 'Main St', city: 'New York' } };
const user2: User = { name: 'Charlie' }; 

const city1 = user1.address?.city ?? 'Unknown City';
const city2 = user2.address?.city ?? 'Unknown City';

console.log(city1); // Output: New York
console.log(city2); // Output: Unknown City
```

**In summary:**

- Use `?.` to **safely navigate** through potentially null/undefined properties or methods.
- Use `??` to provide a **fallback value** specifically when encountering `null` or `undefined`.


---

**What does short-circuiting mean in typescript?**  
Certainly, let's explore short-circuiting in TypeScript.

**What is Short-Circuiting?**

In essence, short-circuiting in TypeScript (and JavaScript, as they share this behavior) refers to the way logical operators `&&` (AND) and `||` (OR) function within conditional expressions. When these operators are used, the evaluation of the expression might stop before examining all the operands if the result can be determined early on. Let me elaborate:

* **`&&` (AND):**  If the left operand evaluates to `false`, the entire expression is guaranteed to be `false`. Consequently, the right operand is not evaluated.

* **`||` (OR):** If the left operand evaluates to `true`, the entire expression is guaranteed to be `true`.  Therefore, the right operand is skipped.

**Why is it called Short-Circuiting?**

Imagine an electrical circuit. A short circuit occurs when the current bypasses a portion of the intended path. Similarly, in programming, short-circuiting means the evaluation "bypasses" or skips the evaluation of certain expressions when the final outcome is already determined.

**Example Time**

Let's illustrate with a TypeScript code snippet:

```typescript
function checkValue(value: number | null) {
  if (value !== null && value > 10) { 
    console.log("Value is greater than 10");
  } else {
    console.log("Value is null or not greater than 10");
  }
}

checkValue(12); // Output: Value is greater than 10
checkValue(null); // Output: Value is null or not greater than 10 
```

In this example:

1. When `checkValue(12)` is called, `value !== null` is `true`, so the evaluation proceeds to `value > 10`, which is also `true`.

2. However, when `checkValue(null)` is called, `value !== null` is `false`. Due to short-circuiting with `&&`, the expression `value > 10` is never evaluated (which would cause an error if `value` were indeed `null`).

**Benefits of Short-Circuiting**

* **Improved Performance:** By avoiding unnecessary computations, short-circuiting can make your code slightly faster, especially in complex conditions.

* **Concise Code:** It enables you to write more compact and expressive conditional statements.

* **Conditional Execution:**  You can leverage short-circuiting to conditionally execute code, like calling a function only if a variable is not `null`.

---

**List a few rules of private fields in typescript?**
1. **Declaration with `#` Prefix:**
    - Private fields are declared using a `#` prefix before the field name. This prefix signifies that the field is private and cannot be accessed outside the containing class.

2. **Accessibility Limited to Containing Class:**
    - Unlike `private` in many other languages, TypeScript's `#` private fields are strictly bound to the class where they are declared.  They cannot be accessed by subclasses or instances of the class from outside the class definition.

3. **No Access via `this` in Inner Scopes:**
    - Within the class, even if you're inside a method or nested function, you cannot access private fields using `this.` when the context of `this` might change (e.g., in event handlers or callbacks).

4. **Runtime Enforcement:**
    - TypeScript enforces private field access at compile time. This means that the compiler will prevent any code from accessing a private field from outside the class. However, the private fields are still present in the compiled JavaScript code (just with mangled names for uniqueness).

5. **No Static Private Fields (Yet):**
    - Currently, TypeScript doesn't support static private fields. If you need a private static member, you can simulate it using a private instance field and access it through static methods within the class.

## Example:

```typescript
class BankAccount {
  #balance: number;

  constructor(initialBalance: number) {
    this.#balance = initialBalance;
  }

  deposit(amount: number): void {
    this.#balance += amount;
  }

  withdraw(amount: number): void {
    if (this.#balance >= amount) {
      this.#balance -= amount;
    } else {
      console.log("Insufficient funds.");
    }
  }

  // This method can access #balance because it's inside the class
  getBalance(): number {
    return this.#balance; 
  }
}

const myAccount = new BankAccount(1000);
myAccount.deposit(500);

// Error: Property '#balance' is private and only accessible within class 'BankAccount'.
// console.log(myAccount.#balance); 

console.log(myAccount.getBalance()); // Output: 1500 
```

---

**What are some use cases of template literal types in typescript?**  
Template literal types in TypeScript provide a powerful mechanism to create new types based on the manipulation of existing string literal types. They use template literals (backticks ``) syntax to create these new types, offering flexibility similar to string manipulation but at the type level.

Here are some common use cases:

**1. Dynamically Creating Type Aliases:**

Template literal types are useful for dynamically creating type aliases based on other types.

**Example:**

```typescript
type Fruit = "apple" | "banana";

// Create a type for each fruit with "Juice" suffix
type JuiceType<T extends string> = `${T}Juice`;

const appleJuice: JuiceType<"apple"> = "appleJuice"; // OK
const bananaSmoothie: JuiceType<"banana"> = "bananaSmoothie"; // OK

const invalidJuice: JuiceType<"grape"> = "grapeJuice"; // Error: "grapeJuice" is not assignable to "appleJuice" | "bananaJuice".
```

In this example, `JuiceType` is a generic type alias that takes a string literal type `T`. Using template literals, it creates a new type by appending "Juice" to the passed type. This allows us to define types like `appleJuice` and `bananaJuice` based on the `Fruit` type.

**2. Type Validation for String Combinations:**

Template literal types can enforce specific string patterns or combinations.

**Example:**

```typescript
type Color = "red" | "green" | "blue";
type Size = "S" | "M" | "L";

type ProductId = `${Color}-${Size}`;

const validId: ProductId = "blue-M"; // OK
const invalidId: ProductId = "blue-XL"; // Error: Type '"blue-XL"' is not assignable to type '"red-S" | "red-M" | "red-L" | "green-S" | "green-M" | "green-L" | "blue-S" | "blue-M" | "blue-L"'.
```

Here, `ProductId` combines `Color` and `Size` types using a hyphen. This ensures that only valid color-size combinations are allowed.

**3. String Manipulation at the Type Level:**

You can manipulate string literal types similarly to manipulating strings at runtime.

**Example:**

```typescript
type Uppercase<T extends string> = `${Uppercase<T>}`;

const name: Uppercase<"john"> = "JOHN"; // OK
const wrongName: Uppercase<"john"> = "John"; // Error: Type '"John"' is not assignable to type '"JOHN"'.
```

This example defines a `Uppercase` type that converts the provided string literal type to uppercase.

---

**How to check the type of variable or constant in typescript?**  
You don't directly check the type of a variable or constant at runtime in TypeScript. This is because TypeScript's type system is primarily a *design-time* feature. The type information is used by the compiler to check for errors and provide better tooling, but it is erased during the compilation to JavaScript.

However, you can leverage JavaScript's built-in operators and methods to infer the "type" of a value at runtime. Let me clarify what this means and provide examples:

**Understanding TypeScript's Type System**

TypeScript adds static typing to JavaScript. These types act as annotations for the compiler but don't exist at runtime:

```typescript
let message: string = "Hello, TypeScript!"; 
message = 123; // Compiler error: Type 'number' is not assignable to type 'string'.
```

After compilation to JavaScript, the type annotation disappears:

```javascript
let message = "Hello, TypeScript!";
message = 123; // This would run without issues in JavaScript.
```

**Runtime Type Inspection in JavaScript (and TypeScript)**

You can use JavaScript's mechanisms to get information about the *value* a variable holds at runtime:

1. **`typeof` operator:** Useful for primitive types.

   ```typescript
   let num = 10;
   let str = "Hello";
   let bool = true;
   let obj = {};
   let arr = [1, 2, 3];

   console.log(typeof num);   // "number"
   console.log(typeof str);   // "string"
   console.log(typeof bool);  // "boolean"
   console.log(typeof obj);   // "object"
   console.log(typeof arr);   // "object" (arrays are objects in JavaScript)
   console.log(typeof null);  // "object" (a quirk of JavaScript)
   ```

2. **`instanceof` operator:** Checks if an object is an instance of a particular class.

   ```typescript
   class Animal {}
   class Dog extends Animal {}

   let myDog = new Dog();

   console.log(myDog instanceof Dog);      // true
   console.log(myDog instanceof Animal);   // true (due to inheritance)
   ```

3. **`Array.isArray()`:** Specifically for checking if a value is an array.

   ```typescript
   let arr = [1, 2, 3];
   console.log(Array.isArray(arr));  // true
   ```

4. **Object Prototypes:** You can inspect the prototype chain of an object to understand its "type" in a more traditional object-oriented sense.

   ```typescript
   console.log(arr.__proto__ === Array.prototype); // true
   ```

---

**How to add types to an interface from another interface or extend types in typescript?**  
In TypeScript, you can "extend" an interface by using the `extends` keyword. This allows you to copy the members of one interface into another, creating a new interface with the combined properties.

**Example:**

```typescript
interface BasicInfo {
  name: string;
  age: number;
}

interface Employee extends BasicInfo {
  employeeId: number;
  department: string;
}

const employee: Employee = {
  name: "John Doe",
  age: 30,
  employeeId: 12345,
  department: "Engineering",
};
```

You can extend multiple interfaces by separating them with commas.

```typescript
interface Address {
  street: string;
  city: string;
}

interface Contact {
  email: string;
  phone: string;
}

interface Customer extends BasicInfo, Address, Contact {
  customerId: number;
}
```

TypeScript allows you to extend types using intersections (`&`). This combines multiple types into one.

**Example:**

```typescript
type Name = {
  firstName: string;
  lastName: string;
};

type Person = Name & {
  age: number;
};

const person: Person = {
  firstName: "Jane",
  lastName: "Doe",
  age: 25,
};
```

---

**What are the differences between type and interface in typescript?**  
Both types and interfaces serve similar purposes in TypeScript: defining the structure and types of data. However, they differ in their capabilities and intended use cases.

**Key Differences:**

| Feature       | Interface                                 | Type                                      |
|---------------|-------------------------------------------|-------------------------------------------|
| Declaration   | Uses the `interface` keyword              | Uses the `type` keyword                   |
| Extension     | Can be extended using `extends`           | Can be extended using intersections (`&`) |
| Merging       | Can be merged with other interfaces       | Cannot be merged                          |
| Primitive     | Cannot be used to describe primitives     | Can describe primitives and complex types |
| Union/Tuple   | Cannot be used to create unions/tuples    | Can be used to create unions/tuples       |

**1. Declaration:**

- **Interface:** Declared using the `interface` keyword.
- **Type:** Declared using the `type` keyword.

**2. Extension:**

- **Interface:** Can be extended using the `extends` keyword, inheriting properties from other interfaces.
- **Type:** Can be combined and extended using intersection (`&`).

**3. Merging:**

- **Interface:** Multiple declarations of the same interface name will merge their properties.
- **Type:** Cannot be merged. Re-declaration will throw an error.

**4. Describing Data:**

- **Interface:** Primarily used for describing the shape of objects. Cannot be used to describe primitives like `string` or `number` directly.
- **Type:** Can describe a wider range of types, including primitives, unions, tuples, and more complex types.

**5. Union and Tuple Types:**

- **Interface:** Cannot be used to directly define union or tuple types.
- **Type:** Ideal for defining union and tuple types.

## Example:

```typescript
// Interface
interface User {
  name: string;
  age: number;
}

// Type
type Admin = User & {
  isAdmin: boolean;
};

// Interface Extension
interface Employee extends User {
  employeeId: number;
}

// Union Type
type Status = 'pending' | 'approved' | 'rejected';

// Tuple Type
type Point = [number, number];
```

In this example:

- `User` is an interface defining the structure of a user object.
- `Admin` is a type extending the `User` interface and adding an `isAdmin` property.
- `Employee` is an interface extending the `User` interface and adding an `employeeId` property.
- `Status` is a union type defining possible statuses.
- `Point` is a tuple type defining a point with two numbers.

**When to Use Which?**

- **Interface:** Use interfaces for defining the shape of objects, especially when you need to:
    - Use object-oriented concepts like inheritance.
    - Allow for open-ended extension and merging of definitions.

- **Type:** Use types for:
    - Defining primitive types, unions, tuples.
    - Creating aliases for complex types.
    - Situations where you don't need the merging behavior of interfaces.

---

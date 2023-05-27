# React JS Interview Questions

<div style="text-align: justify">

## React Basics:

**How to set state with dynamic key name?**  
To set state with dynamic key name, you can use the setState() method with a variable key name.
This allows you to create new state keys based on user input or other dynamic data.

**Why React uses className over class attribute?**  
React uses className over class to avoid naming conflicts with the javascript class keyword.
Using className also makes it easier to use CSS modules and other tools that works with class names.

**How to write comments in React?**  
In React comments can be written using the {/**/} syntax. This syntax allows comments to be included 
directly in JSX code without causing syntax errors. Comments can be used to provide additional 
information or documentation about components or to temporarily disable arts of the code for debugging
purposes.

**What is the difference between Element and Component?**  
In React, An element is a plain javascript object that represents a single HTML element. A component, 
but, is a function, or a class that returns an element (or multiple elements). Components are used to
create reusable UI elements, while elements are used to represent the actual DOM elements that make up
the UI.

**What are the limitations of React?**  
React has some limitations, including a steep learning curve and limited SEO optimization. React's focus
on component-based architecture can make it more difficult for beginners to learn and understand, and its
reliance on javascript can make it less friendly to search engines. React can also struggle with
performance on large datasets or complex UI components. React is primarily used for frontend development
and does not have built-in support for backend development.

**What are children prop?**  
The children prop is a special prop in React that contains the child components of a component. It allows
component to render their child components directly without having to pass them down through props. The
children prop can be used with any component, including functional components.

**What is the purpose of using super constructor with props argument?**  
In React, the super() constructor with props argument is used to initialize the component's props and
state. It is required when defining a constructor in a class component and should always be called 
before accessing this.props and this.state.

**What are stateful components?**  
Stateful components, aka class components are components that maintain state. Stateful components are
useful for creating more complex UI components that need to maintain state, but they are more difficult
to test than stateless components.

**What are the major features of React?**  
React has several major features, including a virtual DOM, server-side rendering and component reusablity.
The virtual DOM helps improve performance by minimizing the number of updates to the actual DOM. 
Server-side rendering allows React to render components on the server before sending them to the client,
improving performance and SEO. Component reusability allows developers to create reusable UI components 
using javascript. One-way data binding is not a major feature of React.

**What are the advantages of React?**  
React has several advantages, including improved performance, reusable components and good community
support. React's use of a virtual DOM and its focus on component-based architecture help improve
performance and make it easier to develop complex UI components. React's component-based architecture
also makes it easier to create reusable components that can be used across multiple projects. React has
a large and active community of developers, which provides good support and resources for learning and
development.

**What are stateless components?**  
Stateless components aka functional components are components that don't use any state. Stateless
components are simpler and easier to test than stateful components, but they can't be used for more
complex UI components that need to maintain state.

**What are fragments?**  
Fragments are a way to group multiple elements without adding an extra DOM node. Fragments are useful
when you want to return multiple elements from a component, but don't want to add an unnecessary
container element to the DOM.

**What is React?**  
React is a javascript library for building user interfaces. It was developed by FaceBook and is now
maintained by a community of developers. React allows developers to create reusable UI components using
javascript. These components can then be combined to create complex user interfaces.

**What is JSX?**  
JSX is a javascript syntax extension that allows developers to write HTML-like code in javascript. JSX is
not required in React, but it is commonly used because it makes writing and managing UI components easier.


## React Props:

**What are props in React?**  
In React, props(short for properties) are a component's input data that are passed down from a parent
component. Props are read-only and cannot be changed by the child component. Props are used to customize
the behavior and appearance of a component.


## React Components:

**How to create components in React?**  
In React, components can be created using React.createElement method or JSX syntax.
React.createElement is a lower-level API for creating components, while JSX is a syntax extension that
allows developers to write HTML-like in javascript.

**When to use a class component over a function component?**  
Class components in React are used when handling a complex state and lifecycle methods. They provide
additional functionality over function components, such as the ability to use lifecycle methods like
componentDidMount and componentDidUpdate to maintain internal state. Function components are generally
used for rendering simple UI components, while class components are used for more complex functionality.


## React Arrays and Lists:

**What is *key* prop and what is the benefit of using it in arrays of elements?**  
The “key” prop in React is a special prop that provides a unique identifier for each element in an array
of elements. It is used to optimize the performance of rendering by allowing React to identify, which 
elements have changed, and to update only those elements instead of re-rendering the entire list. The “key”
prop should be unique stable identifier for each element, such as an ID or index.


## React Best Practices:

**What would be a common mistake of function being called every time the component renders?**  
A common mistake that can cause a function to be called every time the component renders is declaring the
function inside the component's render method. This can cause the function to be recreated every time the
component renders, even if the function's dependencies have not changed. To avoid this problem, function
should be declared outside the render method, or in a separate file if they are reused across multiple
components.
</div>

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

**What is the lifecycle methods order in mounting?**  
The lifecycle methods for mounting a component in React are as follows:  
ComponentWillMount, render, componentDidMount. The *componentWillMount* method is called before the component is
mounted to the DOM, *render* is called to render the component, and *componentDidMount* is called after the component
is mounted to the DOM.

**How to use styles in React?**  
In React, you can use style attribute to apply styles to the component. The style attribute takes an object that
contains css properties and values, Similar to inline styles in  HTML.

**What is CRA and its benefits?**  
CRA stands for Create React App, which is a boilerplate for creating React applications. It provides pre-configured
setup for building, testing and deploying React applications, allowing developers to focus on writing code rather than
setting up the build toolchain. Some benefits of using CRA include easy setup, automatic configuration and a built-in
development server.

**How to combine multiple inline style objects?**  
In React, you can combine multiple inline style objects using spread operator. This allows you to merge the properties
of multiple style objects into a single object that can be applied to a component
```jsx
<div style={{...style1, ...style2}}>My Component</div>
```
This will create a new style object that contains the properties of both style1 and style2.

**What is the use of react-dom package?**  
The react-dom package is used to render React components to the DOM. The react-dom package provides several methods
for rendering components, including the render method and the hydrate method.

**What is the purpose of render method of react-dom?**  
The render method of the react-dom package is used to render a React component to the client-side DOM. The render
method takes two arguments: the component to render and the DOM element to render it to.

**What is the difference between React and ReactDOM?**  
React is a library for creating components and managing state and events of those components, while ReactDOM is a 
library for rendering those components to the DOM. React provide the programming interface for working with components
, While ReactDOM provides the methods for rendering and updating the components in the browser.

**Why you can't update props in React?**  
In React, props are immutable and cannot be changed directly. Because React is designed to be a one-way data flow,
where data is passed down from parent components to child components through props. If you need to update the data, 
you should do so in the parent component and pass the updated data down as props to the child components.

**How do you conditionally render components?**  
You can use ternary operator in JSX. This allows you to specify a condition and render one component if condition is
true, and another component if condition is false. You can use other conditional statements such as *if* statements or
*switch* statements, outside the JSX to determine which component to render.

**How to conditionally apply class attributes?**  
In React, You can conditionally apply class attributes using the *className* and the ternary operator. This allows you
to add or remove classes based on some condition, such as the state of the component. The *className* is used instead
of the *class* attribute in React, because *class* is reserved in javascript.

**How to enable production mode in React?**  
To enable production mode in React, you can set NODE_ENV environment variable to *production*. This will trigger
various optimizations anf remove development-only code from the bundle. You can also use the *process.env.NODE_ENV* 
variable in the code to conditionally enable certain features. 

**How do you access props in attribute quotes?**  
In React, you can access props in attribute quotes using the *this.props* syntax and the name of the prop. For example
to access the props named *someProp*, you would use syntax "{this.props.someProp}" inside the attribute quotes.

**How to loop inside JSX?**  
To loop inside JSX, you can use map() method to map an array of data to a set of React elements. This allows you to
dynamically generate UI elements based on data, such as a list of items or a set of images.

**How to focus an input element on page load?**  
In  React, You can focus an input element on page load using the *focus()* method in the *componentDidMount()*
lifecycle method. This will set the focus to the input element after the component has been mounted in the DOM. For 
example:
```javascript
componentDidMount() {
    this.myInput.focus();
}
```

**What is the difference between constructor and getInitialState?**  
The *constructor* method and *getInitialState* are both used to initialize the state of a component in React, but they
are used in different class styles. The *constructor* method is used in ES6 classes, while *getInitialState* method is
used in ES5 classes. In general, it is recommended to use the *constructor* method in modern React code.

**How to use React label element?**  
You can use the standard HTML label element to associate a label with an input field or other form element. To do this,
you can use the *for* attribute on the label element and set it to the id of the input field. In JSX, you can use the
*htmlFor* attribute instead of *for*, because *for* is a reserved keyword in javascript.


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

**What is the recommended way for naming the components?**  
This is to use a simple name that describes the components. The name should be a noun or noun phrase that accurately
represents component's purpose. This makes it easier to understand and maintain the code, as well as to reuse the
component in other parts of the application.

**What will happen if you use props in initial state?**  
Using props in initial state will cause initial state to ignore the props. Because the initial state is only set once,
when the component is first created. If you want to use props to initialize state, you should set the state in the
constructor instead.

**What is the impact of indexes as keys?**  
Using indexes as keys can cause issues with component's state, particularly if the order of items in the list changes.
It can also lead to issues with duplicate keys if items are added or removed from the list. It is generally recommended
to use a unique identifier as the key rather than an index.

**What is the recommended order of methods in component class?**  
The recommended ordering of methods in a React component class is as follows: constructor, render, lifecycle methods,
event handlers. This ordering groups related methods together and makes it easier to understand and maintain the code.

**Why should component names start with capital latter?**  
Because in order to distinguish them from regular HTML tags and make the code easier to read. This is a convention that
is widely used in the React community and helps developer to understand the purpose and scope of different parts of the
code.

**Why we need to be careful when spreading props on DOM elements?**  
It is important to be careful because it can spread invalid HTML attributes. This can cause the component to render
incorrectly or even create security vulnerabilities. It is recommended to only spread props on components that you
trust, or to manually whitelist the valid attributes.


## React Conditional Rendering:

**What are inline conditional expressions?**  
Inline conditional expressions in React are expressions that are used to conditionally render components
based on a certain condition. They are typically used in JSX and are written using the ternary operator.
Inline conditional expressions are simple and effective way to conditionally render components without
a need for additional logic.


## React State:

**Why should we not update the state directly?**  
In React the state should not be updated directly because it can cause the component to re-render 
improperly. Instead, the setState() method should be used to update state, which triggers a re-render
of the component and ensures that the updated state is properly reflected in the UI.

**What is state in React?**  
In React, state refers to a component's internal data that can change over time. State is managed using
the setState method, which allows developers to update the state of a component and trigger a re-render
of the UI. State is used to keep track of data that changes in response to user input or other events.

**What is the purpose of the callback function as an argument of setState?**  
The callback function as an argument of the setState method in React is used to update the state
asynchronously. When the setState() method is called, the state update may not happen immediately, which
can cause issues when trying to access to updated state. The callback function is called after the state
has been updated, ensuring that the updated state is available to use.


## React State and Props:

**What is the difference between state and props?**  
The main difference between state and props in React is that state is managed within a component, while props are
passed down from a parent component. State is used to manage a component's internal data, which can change over
time, while props are used to customize a component's behavior and appearance.


## React Performance:

**What are pure components?**  
Pure components in React are components that implement the shouldComponentUpdate lifecycle method to improve 
performance. This method compares the current props and state to the next props and state, and determines whether
the component needs to be re-rendered. If the props and state have not changed, the component can skip the rendering
process.


## React Advanced Concepts:

**What are forward refs?**  
Forward refs are a way to pass a ref from parent component to a child component. This allows the parent component to 
access and manipulate the child component's DOM node. Forward refs are created using the React.forwardRef() function.

**What is React Fiber?**  
React Fiber is a new rendering engine for react that was introduced in React 16. It is designed to improve performance
and enable more flexibility in scheduling updates. With React Fiber, React can break up large updates into smaller
chunks , prioritize updates, pause and resume updates as needed.

**What is the difference between createElement and cloneElement?**  
createElement is a method used to create new React elements, while cloneElement is a method used to clone existing React
elements and pass new props to the cloned element.

**What are String Refs Legacy?**  
String refs which allow developers to set refs using a string identifier, are considered legacy because they can cause
naming conflicts and bugs. They have been replaced with callback refs and React.createRef() API.

**Why fragments are better than container divs?**  
Because they are more performant. Using a container div adds an extra DOM node which can slow down rendering and create
problems with styling. Fragments, on the other hand, allow you to group elements without adding an extra nodes to the
DOM.

**What is Context?**  
Context is a way to pass data down to the child components without using props. It is useful for data that needs to be
accessed by many components at different levels of the component hierarchy. Context provides a way to avoid the "prop
drilling" problem, where props need to be passed down through many layers of components.

**What is Lifting State Up in React?**  
Lifting State Up is a technique in React for passing data up from child components to parent components. This is useful
when multiple components need to share the same state or when a child component needs to update the state of a parent
component.

**What are error boundaries in React v16?**  
Error boundaries are a way to handle errors in React components. In React v16, error boundaries are special components
that catch and handle errors that occur during rendering. This can help to prevent entire application from crashing due
to an error in a single component.

**What is virtual DOM?**  
The virtual DOM is a representation of the browser's DOM in memory. It is used by React to optimize and speed up
updates to the actual DOM by minimizing the number of changes that need to be made. When a component's state is 
changes, React updates the virtual DOM and compares it to the previous version. It then calculates the most efficient
way to update the actual DOM based on the differences between the two versions.

**How to apply validation on props in React?**  
In React, you can apply validation on props using the PropTypes library. PropTypes allow you to define the type and
shape of a component's props, which helps to catch errors and bugs early in development.

**What are Higher-Order components?**  
They are components that enhance the behaviour of other components by adding additional functionality or props. HOCs
take a component as input and return a new component that includes the additional behaviour. This allows developers
to reuse code and separate concerns in their applications.

**How to create props proxy for HOC component?**  
To create a props proxy for a HOC component, you can wrap the component with another component that adds the additional
props. This is done by defining a new component that takes the original component as input and returns a new component
that includes the additional props.

**How virtual DOM works?**  
When a component's state changes in React, it updates the virtual DOM and calculates the most efficient way to update
the actual DOM based on the differences between the two versions. This approach minimizes the number of changes that
need to be made to the actual DOM and improves performance.

**What is the difference between shadow DOM and virtual DOM?**  
Shadow DOM and virtualDOM are two different concepts. Shadow DOM is a browser feature that allows developers encapsulate
styles and markup within components. Virtual DOM on the other hand is React feature that allows for performance
optimization by minimizing changes to the actual DOM.

**What is reconciliation?**  
Reconciliation is the process of comparing two versions of a component and updating the DOM with the changes. When a 
component's state or props change, React compares the new version of the component to the previous version and 
calculates the minimum number of changes needed to update the DOM. This process is called reconciliation and is one of
the key features of Rect that makes it so efficient.

**What is the main goal of React Fiber?**  
The main goal of React Fiber is to improve client-side rendering performance. It does this by introducing a new 
algorithm for rendering updates that is more efficient and flexible than the previous algorithm. With React Fiber,
React can break up large updates into smaller chunks, prioritize, pause and resume updates as needed.

**What are portals in React?**  
Portals in React provide a way to render a component's children in a different part of the DOM. This can be useful
for creating modal dialogs, tooltips and other UI components that need to be positioned outside the normal flow of the
page.

**What is ReactDOMServer?**  
This is a module that allows you to render react components on the server. It is provided several methods for rendering
components, including the renderToString method and the renderToStaticMarkup method.

**How are error boundaries handled in React v15?**  
Error boundaries were not supported in React v15. Error handling in React v15 was less robust and could lead to entire
application crashing if an error occurred during rendering.

**What are the recommended ways for static type checking?**  
There are several recommended ways to implement static type checking in React, including using Typescript or Flow.
Typescript and Flow are both static type checkers that can help to catch errors and bugs before they happen. The
PropTypes library is another way to perform type checking, but it is less powerful than Typescript and Flow. ESLint is
a code linter that can help to catch errors and enforce best practices, but it is not a type checker.

**How to use InnerHTML in React?**  
You can use *dangerouslySetInnerHTML* prop to set the inner HTML of a component. The *dangerouslySetInnerHTML* prop is
used to bypass React's built-in sanitization and allow arbitrary HTML to be injected into a component. However, this
should be used with caution, as it can pose a security risk.

**What will happen if you use setState in constructor?**  
If you use *setState* in a component's constructor, It will update the component's state. However, this is generally
not recommended, as it can cause problems with initialization and lead to confusing code. It is bette to set the initial
state in the constructor using *this.state* property.

**How events are different in React?**  
Events in React are different from native events in several ways. React events are synthetic events that are 
cross-browser compatible and have the same API across all browsers. React events are also camelCase instead of
lowercase. Finally, React event are different API than native events, including the ability to call *preventDefault*
and *stopPropagation* on the event object.


## React Advanced:

**What are React Mixins?**  
React Mixins are reusable code snippets that can be applied to multiple components in order to provide shared
functionality. They are a way to encapsulate logic and behaviour that cn be used across multiple components, allowing
for code reuse and reducing duplication. However, they are not recommended in modern versions of React and have been
largely replaced by higher-order components and render props.

**What id the difference between super() and super(props) in React using ES6 classes?**  
In React using ES6 classes, super() is used to call the constructor of the superclass, while super(props) is used to 
pass props to the constructor of the superclass. The super(props) syntax is necessary if you need to access props in
the constructor of a subclass.

**How to listen to state changes?**  
You can listen to state changes by using the *componentDidUpdate* lifecycle method. This method is called after a
component's state has been updated, and you can use it to perform additional actions or update the UI based on the new
state, For example you can use this method to update the DOM, call a web API or trigger an animation.

**Do Hooks replace render props and higher-order components?**  
Hooks in React can replace both render props and higher-order components in some cases. Hooks can provide same
functionality to both of these patterns, while also simplifying the code and making it more reusable. For example, the
*useEffect* Hook can replace the *componentDidMount* and *componentDidUpdate* lifecycle methods as well as some uses
of higher-order components.

**What is a switching component?**  
A switching component in React is a component that renders one of several child components based on some condition or
state. This is commonly used to switch between different views or user interface elements in response to user input
or other events.

**How to re-render the view when then browser is resized?**  
In React, you can re-render the view when the browser is resized by using a state variable and updating it on resize.
This will trigger a re-render of the component and allow you to update the layout or other properties based on the new
size of browser window. You can use the *windowAddEventListener* method to listen for the *resize* event and update the
state variable accordingly.

**What are the lifecycle methods going to be deprecated in React v16?**  
The *componentWillReceiveProps* and *componentWillUpdate* lifecycle methods are going to be deprecated in React v16.
These methods will be replaced with new lifecycle methods that are more efficient and easier to reason about. The new
methods are: *getDerivedStateFromProps* and *getSnapshotBeforeUpdate*.

**Why we need to pass a function to setState?**  
This is because in order to avoid infinite loops. If we pass an object directly, it can cause the component to
re-render and update the state endlessly. By passing a function, we can ensure that the state is updated correctly and
avoid these issues.

**What is React PropType array with shape?**  
The *shape* propType in React allows you to validate an object with a specific shape, while the *arrayOf* propType
allows you to validate an array of values. The *arrayOf* propType can be combined with the *shape* propType to validate
an array of objects with a specific shape. This is useful for validating data structures in React components.

**What is the purpose of getSnapshotBeforeUpdate() lifecycle method?**  
In React this method is used to capture information from the DOM before it changes. This method is called right before
the DOM is updated and can return a value that will be passed to the componentDidUpdate method. It is commonly used 
to preserve scroll position or other user interface during updates.

**Is it possible to use React without rendering HTML?**  
In React, It is possible to use the library for non-HTML rendering, such as SVG or Canvas. React provides a flexible
programming interface for creating components and managing state, and it can be used to generate any kind of output,
not just HTML. React is also used for building mobile applications with React Native, which uses same programming
model as React for building UIs on iOS and Android platform.

## React Refs:

**How to create refs?**  
Refs in React can be created using React.createRef() method. This method creates a new ref object, Which can be
attached to DOM element or a React component. Refs can be accessed using the current property of the ref object.

**What is the use of Refs?**  
Refs in React are used to create references to DOM elements. They allow developers to access and manipulate the
properties and methods of DOM elements directly, without the need of additional logic or event handling. Refs are
typically used when with third-party libraries or when manipulating the DOM directly is necessary.


## React Forms:

**What are uncontrolled components?**  
They are components that store their own state and are updated using refs. They are often used for simple form inputs,
where manging the state in a parent component would be unnecessary overhead.

**What are controlled components?**  
They are components that store their state in a parent component and are updated using the setState() method. The 
parent component passes down the component's state as props and also passes down a function to update the state when
needed. This approach allows for more control over the component's behaviour and simplifies debugging.


## React Events:

**What are synthetic events in React?**  
They are events that are cross-browser compatible and behave consistently across different platforms. They are also
optimized for performance by pooling event objects, which allows them to be reused and prevents excessive memory
allocation. Synthetic event have have the same interface as native events, but they are implemented differently behind
the scenes.

**How to bind methods or event handlers in JSX callbacks?**  
Methods or event handlers can be bound in JSX callbacks using arrow functions. Arrow functions inherit the context of
their parent scope, which allows them to access the component's methods and state. The bind method and the this keyword
can also be used to bind methods or event handlers, but arrow functions are the recommended approach.

**How to pass a parameter to an event handler or callback?**  
A parameter can be passed to an event handler or callback in React using an arrow function. The arrow function takes
the event as a parameter, along with any additional parameters that need to be passed. This approach ensures that the
event object is properly handled and that the correct parameters are passed to the event handler or callback.

**What is the difference between HTML and React event handling?**  
The main difference between HTML and React event handling is that React uses synthetic events, while HTML does not.
Synthetic events are cross-browser compatible and behave consistently across different platforms. They are also 
optimized for performance by pooling event objects.

</div>

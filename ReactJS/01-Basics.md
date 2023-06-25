# ReactJS Interview Questions

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

**What are the exceptions on React component naming?**  
There are several rules for naming components, including that component's name must start with capital letter, use
camelCase convention and can include numbers but not as a first character. Components should also have a descriptive
name that reflects their purpose or function in the application.
</div>

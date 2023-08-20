# ReactJS Interview Questions

<div style="text-align: justify">

## React Basics:

---

**How to set state with dynamic key name?**  
```jsx
const [state, setState] = useState({});

const handleChange = (key, value) => {
  setState(prev => ({...prev, [key]: value}));
}
```
Use the spread syntax (...) to copy the existing state.Compute the key name dynamically in square brackets [key].
This will merge the existing state and the new dynamic key value. setState accepts a function to avoid issues with
stale closure state.

---

**Why React uses className over class attribute?**  
React uses className over class to avoid naming conflicts with the javascript class keyword.
Using className also makes it easier to use CSS modules and other tools that works with class names.

---

**How to write comments in React?**  
In React comments can be written using the {/**/} syntax. This syntax allows comments to be included
directly in JSX code without causing syntax errors. Comments can be used to provide additional
information or documentation about components or to temporarily disable arts of the code for debugging
purposes.

---

**What is the difference between Element and Component?**  
In React, An element is a plain javascript object that represents a single HTML element. A component,
but, is a function, or a class that returns an element (or multiple elements). Components are used to
create reusable UI elements, while elements are used to represent the actual DOM elements that make up
the UI.

---

**What are the limitations of React?**  
* React has limited SEO optimization.
* React is focused on client-side rendering. SSR takes extra effort to set up.
* The abstraction of React and its syntax can be difficult for beginners to grasp.
* React has a lot of new concepts like JSX and the virtual DOM that require time to learn.
* React doesn't impose guidelines for project structure. Large apps can become difficult to maintain.
* React focuses solely on the view layer. You need to choose other libraries for routing, state management, etc.

---

**What is children prop?**  
The children prop is a special prop in React that contains the child components of a component. It allows
component to render their child components directly without having to pass them down through props. The
children prop can be used with any component, including functional components.
```jsx
<MainComponent>
  <ChildComponent />
</MainComponent>


function MainComponent(props) {
    return <div>{props.children}</div>
}
```

---

**What is the purpose of using super constructor with props argument?**  
In React, the super() constructor with props argument is used to initialize the component's props and
state. It is required when defining a constructor in a class component and should always be called
before accessing this.props and this.state.

---

**What are stateful components?**  
Stateful components, aka class components are components that maintain state. Stateful components are
useful for creating more complex UI components that need to maintain state, but they are more difficult
to test than stateless components.

---

**What are the major features of React?**  
- **Components** - React is component-based, allowing you to build encapsulated UI elements that manage their own state.
- **Virtual DOM** - React uses a virtual DOM to optimize performance by minimizing DOM operations.
- **JSX** - JSX is a React extension to JavaScript that allows you to write HTML-like code in components.
- **One-way data binding** - Data flows one way in React, making the flow easy to reason about.
- **Performance** - React uses different techniques like virtual DOM diffing to optimize performance.
- **Ease of integration** - React can be incrementally integrated into existing codebases because it's "just JavaScript".
- **Community and ecosystem** - React has a large community and many 3rd party libraries like React Router.
- **Declarative programming** - React uses declarative code that is easier to reason about than imperative code.
- **Flexibility** - You can use React for interesting solutions like building mobile apps with React Native.

---

**What are the advantages of React?**
- **Component-based** - Build encapsulated components that manage their own state, then compose them to make complex UIs.
- **Declarative** - React uses declarative code that is easier to reason about than imperative code.
- **Efficient** - The virtual DOM diffing algorithm enables high performance by minimizing DOM operations.
- **Flexible** - You can use React for interesting solutions like building mobile apps with React Native.
- **Modular** - Components and state management with Redux enables easier large application development.
- **Popular** - React has a large community and many 3rd party libraries available.
- **Testable** - The component model enables easy unit and integration testing.
- **Versatile** - React can be used for web, mobile, VR, and even game development.
- **SEO Friendly** - Server-side rendering enables good SEO if you need it.
- **Active ecosystem** - With constant updates and rapid release cycles.

---

**What are stateless components?**  

Stateless components in React are components that do not have state. They are "dumb" components that only
receive data via props and render DOM or other components.
```jsx
function StatelessComponent(props) {
    return <h1>Hello, {props.name}!</h1>;
}
```

---

**What are fragments?**  
Fragments are useful for:
* Returning multiple elements from components
* Avoiding adding extra DOM nodes
* Wrapping element groups without div soup
```jsx
function MyComponent() {
    return <>
        <ChildA />
        <ChildB />
        <ChildC />
    </>
}
```

---

**What is React?**  
React is a javascript library for building user interfaces. It was developed by FaceBook and is now
maintained by a community of developers. React allows developers to create reusable UI components using
javascript. These components can then be combined to create complex user interfaces.

---

**What is JSX?**  
JSX is a javascript syntax extension that allows developers to write HTML-like code in javascript. JSX is
not required in React, but it is commonly used because it makes writing and managing UI components easier.

---

**What is the lifecycle methods order in mounting?**  
The lifecycle methods for mounting a component in React are as follows:  
ComponentWillMount, render, componentDidMount. The *componentWillMount* method is called before the component is
mounted to the DOM, *render* is called to render the component, and *componentDidMount* is called after the component
is mounted to the DOM.

---

**How to use styles in React?**  
- **Inline styles** : Object with camelCased CSS properties
```jsx
<div style={{ color: 'blue', fontSize: '14px' }}>
  Hello World!
</div>
```
- **Css stylesheets**: Import a CSS file and reference classes
```jsx
import './styles.css';

function App() {
  return <div className="container">...</div> 
}
```
- **Css modules**: CSS files loaded locally with modules
```jsx
import styles from './styles.module.css';

function App() {
  return <div className={styles.container}>...</div>
}
```
- **Css in JS**: CSS written inline using libraries like Styled Components
```jsx
import styled from 'styled-components';

const Title = styled.h1`
  color: red;
`;
```
- **Tailwind css**: Use pre-built classes and styles
```jsx
function MyComponent() {
    return <div className="px-2 py-3 flex items-center">
        <h1 className="font-semibold text-stone-500">Tailwind</h1>
        <p className="py-3">is awesome</p>
    </div>
}
```



---

**What is CRA and its benefits?**  
CRA stands for Create React App, which is a boilerplate for creating React applications. It provides pre-configured
setup for building, testing and deploying React applications, allowing developers to focus on writing code rather than
setting up the build toolchain. Some benefits of using CRA include easy setup, automatic configuration and a built-in
development server.

---

**How to combine multiple inline style objects?**  
In React, you can combine multiple inline style objects using spread operator. This allows you to merge the properties
of multiple style objects into a single object that can be applied to a component
```jsx
<div style={{...style1, ...style2}}>My Component</div>
```
This will create a new style object that contains the properties of both style1 and style2.

---

**What is the use of react-dom package?**  
The react-dom package is used to render React components to the DOM. The react-dom package provides several methods
for rendering components, including the render method and the hydrate method.

---

**What is the purpose of render method of react-dom?**  
The render method of the react-dom package is used to render a React component to the client-side DOM. The render
method takes two arguments: the component to render and the DOM element to render it to.

---

**What is the difference between React and ReactDOM?**  
React is a library for creating components and managing state and events of those components, while ReactDOM is a
library for rendering those components to the DOM. React provide the programming interface for working with components
, While ReactDOM provides the methods for rendering and updating the components in the browser.

---

**Why you can't update props in React?**  
In React, props are immutable and cannot be changed directly. Because React is designed to be a one-way data flow,
where data is passed down from parent components to child components through props. If you need to update the data,
you should do so in the parent component and pass the updated data down as props to the child components.

---

**How do you conditionally render components?**  
You can use ternary operator in JSX. This allows you to specify a condition and render one component if condition is
true, and another component if condition is false. You can use other conditional statements such as *if* statements or
*switch* statements, outside the JSX to determine which component to render.

---

**How to conditionally apply class attributes?**  
In React, You can conditionally apply class attributes using the *className* and the ternary operator. This allows you
to add or remove classes based on some condition, such as the state of the component. The *className* is used instead
of the *class* attribute in React, because *class* is reserved in javascript.

---

**How to enable production mode in React?**  
To enable production mode in React, you can set NODE_ENV environment variable to *production*. This will trigger
various optimizations anf remove development-only code from the bundle. You can also use the *process.env.NODE_ENV*
variable in the code to conditionally enable certain features.

---

**How do you access props in attribute quotes?**  
In React, you can access props in attribute quotes using the *this.props* syntax and the name of the prop. For example
to access the props named *someProp*, you would use syntax "{this.props.someProp}" inside the attribute quotes.

---

**How to loop inside JSX?**  
To loop inside JSX, you can use map() method to map an array of data to a set of React elements. This allows you to
dynamically generate UI elements based on data, such as a list of items or a set of images.

---

**How to focus an input element on page load?**  
In  React, You can focus an input element on page load using the *focus()* method in the *componentDidMount()*
lifecycle method. This will set the focus to the input element after the component has been mounted in the DOM. For
example:
```javascript
componentDidMount() {
    this.myInput.focus();
}
```

---

**What is the difference between constructor and getInitialState?**  
The *constructor* method and *getInitialState* are both used to initialize the state of a component in React, but they
are used in different class styles. The *constructor* method is used in ES6 classes, while *getInitialState* method is
used in ES5 classes. In general, it is recommended to use the *constructor* method in modern React code.

---

**How to use React label element?**  
You can use the standard HTML label element to associate a label with an input field or other form element. To do this,
you can use the *for* attribute on the label element and set it to the id of the input field. In JSX, you can use the
*htmlFor* attribute instead of *for*, because *for* is a reserved keyword in javascript.

---

**What are the exceptions on React component naming?**  
There are several rules for naming components, including that component's name must start with capital letter, use
camelCase convention and can include numbers but not as a first character. Components should also have a descriptive
name that reflects their purpose or function in the application.
</div>

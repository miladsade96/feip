# ReactJS


**How to set state with dynamic key name?**
```jsx
const [state, setState] = useState({});

const handleChange = (key, value) => {
  setState(prev => ({...prev, [key]: value}));
}
```
Use the `spread syntax (...)` to copy the existing state.Compute the key name dynamically in square brackets `[key]`.
This will merge the existing state and the new dynamic key value. `setState` accepts a function to avoid issues with
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

**How to combine multiple inline style objects?**
- **Object spread syntax**: The spread syntax merges the objects into one.
```jsx
const style1 = { color: 'red' };
const style2 = { fontSize: '12px' };

<div style={{...style1, ...style2}}></div>
```
- **Object.assign**: Object.assign copies properties from source objects into a target object.
```jsx
const style1 = { color: 'red' };
const style2 = { fontSize: '12px' };

const styles = Object.assign({}, style1, style2);

<div style={styles}></div>
```
- **Concatenated Object**: You can also pre-concatenate styles into a new variable.
```jsx
const style1 = { color: 'red' };
const style2 = { fontSize: '12px' };

const styles = {
  ...style1,
  ...style2
};

<div style={styles}></div>
```

---

**What is the use of react-dom package?**  
The react-dom package is used to render React components to the DOM. The react-dom package provides several methods
for rendering components. Some of the key things it provides:
- **render() method**: Renders a React element into the DOM in the supplied container. This is used to render your app to the DOM:
```javascript
ReactDOM.render(<App />, document.getElementById('root'));
```
- **hydrate method**: Same as render() but used for hydrating SSR React markup.
- **unmountComponentAtNode() method**: Removes a mounted React component from the DOM.
- **findDOMNode() method**: Returns the underlying DOM node for a mounted React.
- **createPortal() method**: Creates a React portal and appends it to the target DOM node.

---

**What is the purpose of render method of react-dom?**  
The render() method in react-dom is used to render React elements to the DOM. Here are some key points about render():
- It is the primary method used to render a React application to the DOM.
- It takes two arguments - the React element to render, and the DOM node to render to:
```jsx
ReactDOM.render(<App />, document.getElementById('root'));
```
- This will render the <App /> into the DOM element with id 'root'.
- It should be called only once in the app, typically in index.js.
- Multiple calls to render() will replace what's already rendered.
- Returns a reference to the root React component instance.
- Only renders on the client, not server side.

---

**What is the difference between React and ReactDOM?**
- **React** is the core library that contains React components, state, props etc. It contains functionality common to React on all platforms.
- **ReactDOM** deals with the DOM and browser specific features. It provides DOM specific methods like render().  
  So in summary, React is the core library and ReactDOM is the glue between React and the DOM for web apps.

---

**Why can't we update props in React?**  
There are a few key reasons why directly modifying props in React is prohibited:
- **Unidirectional data flow**: React follows a one-way data flow paradigm, with props being passed from parent to child only. Modifying props directly breaks this.
- **State as source of truth**: A component's state should be the source of truth for data that can change, not its props.
- **Immutability**: Mutating objects/arrays in JavaScript can lead to bugs, so React avoids this by not allowing props mutation.
- **Pure components**: When props remain immutable, it's easier to optimize components by preventing unnecessary re-renders.
- **Predictability**: Immutable props aid in debugging and understanding data flow.
- **Functional components**: Functional components are stateless and only rely on props. Mutable props could cause issues.

---

**How do you conditionally render components?**
- **if/else**:
```jsx
const App = () => {
  if (condition) {
    return <ComponentA /> 
  } else {
    return <ComponentB />
  }
}
```
- **Short-circuit && operator**:
```jsx
const App = () => {
  return (
    condition && <ComponentA />
  ) 
}
```
- **Ternary operator**:
```jsx
const App = () => {
  return (
    condition ? 
      <ComponentA /> :
      <ComponentB />
  )
}
```
- **Switch statement**:
```jsx
const App = () => {
  switch(condition) {
    case 'A': 
      return <ComponentA />
    case 'B':
      return <ComponentB />
    default:
      return <ComponentC />
  }
}
```

---

**How to conditionally apply class attributes?**
- Using **Ternary operator**:
```jsx
<div className={condition ? 'classA' : 'classB'}>
```
- Using **Short-circuit && operator**:
```jsx
<div className={condition && 'classA'}>
```

---

**How to enable production mode in React?**
- Setting NODE_ENV to *production*
- Setting webpack mode to *production*
- Parcel build for production: *parcel build entry.js --production*
- Running the following command: *parcel build entry.js --production*

---

**How do you access props in attribute quotes?**  
To access props in an attribute in JSX, you can use curly braces {}:
```jsx
<input 
  type="text"
  value={this.props.value}
  onChange={this.props.onChange}
/>
```

---

**How to loop inside JSX?**  
To loop inside JSX, you can use map() method to map an array of data to a set of React elements. This allows you to
dynamically generate UI elements based on data, such as a list of items or a set of images:
```jsx
{items.map(item => (
  <div key={item.id}>{item.name}</div>  
))}
```

---

**How to focus an input element on page load?**
- Using **useRef** hook:
```jsx
const inputRef = useRef(null);

useEffect(() => {
  inputRef.current.focus();
}, [])

return (
  <input ref={inputRef} /> 
)
```
- Using **focus() method** inside componentDidMount:
```jsx
class Input extends React.Component {
  componentDidMount() {
    this.input.focus();
  }

  render() {
    return <input ref={el => this.input = el} />
  }
}
```
- Using **autoFocus** attribute:
```jsx
return (
  <input autoFocus />
)
```

---

**What is the difference between constructor and getInitialState?**  
The *constructor* method and *getInitialState* are both used to initialize the state of a component in React, but they
are used in different class styles. The *constructor* method is used in ES6 classes, while *getInitialState* method is
used in ES5 classes. In general, it is recommended to use the *constructor* method in modern React code.

---

**How to use React label element?**
- First way:
```jsx
<label htmlFor="name">Name</label>
<input id="name" type="text" />
```
- Second way:
```jsx
<label>
  Name
  <input type="text" />  
</label>
```

---

**What are the exceptions on React component naming?**  
There are several rules for naming components, including that component's name must start with capital letter, use
camelCase convention and can include numbers but not as a first character. Components should also have a descriptive
name that reflects their purpose or function in the application.

---

**What are props in React?**  
Props (properties) in React allow you to pass data from a parent component down to a child component.
Some key characteristics of props:
- They are passed to components similar to function parameters.
- They are immutable in the child component.
- They can only be passed from parent to child, not the other way.
- The child component receives them as a props object parameter.
```jsx
// Parent component
<ChildComponent name="John" age={12} />

// Child component receives props
const ChildComponent = (props) => {
  return <p>{props.name} is {props.age}</p> 
}
```

---

**How to create components in React?**  
There are two main ways to create components in React:
- **Function components**: Function components are simple JavaScript functions that accept props and return JSX
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
- **Class components**: Class components are ES6 classes that extend React.Component and render JSX in their render method
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

---

**When to use a class component over a function component?**  
Class components were used before React 16.8. They exist because they are necessary. Nowadays, most projects
done with React use Functional components as hooks have made everything easier, and the code is leaner and
more flexible. Yet, there are cases where we need to use Class components; for example when we’re required to
build an Error Boundary, or the team we joined has a project that has not migrated to React 16.8.

---

**What is *key* prop and what is the benefit of using it in arrays of elements?**  
The key prop is a special string attribute you need to include when rendering lists of elements in React.
Some benefits of using keys with arrays of elements:
- It helps React identify which items have changed, been added or removed.
- Keys should be given to the elements inside an array to give them a stable identity.
- Helps React optimize performance by recycling existing DOM elements rather than recreating them.
- Required when extracting list items as components to keep track of item identity.
```jsx
const todoItems = todos.map(item => 
  <TodoItem key={item.id} item={item}/>
)
```

---

**What would be a common mistake of function being called every time the component renders?**  
A common mistake that can cause a function to be called every time the component renders is declaring the
function inside the component's render method. This can cause the function to be recreated every time the
component renders, even if the function's dependencies have not changed. To avoid this problem, function
should be declared outside the render method, or in a separate file if they are reused across multiple
components.

---

**What is the recommended way for naming the components?**  
This is to use a simple name that describes the components. The name should be a noun or noun phrase that accurately
represents component's purpose. This makes it easier to understand and maintain the code, as well as to reuse the
component in other parts of the application.

---

**What will happen if you use props in initial state?**  
Using props in initial state will cause initial state to ignore the props. Because the initial state is only set once,
when the component is first created. If you want to use props to initialize state, you should set the state in the
constructor instead.

---

**What is the impact of indexes as keys?**  
Using indexes as keys can cause issues with component's state, particularly if the order of items in the list changes.
It can also lead to issues with duplicate keys if items are added or removed from the list. It is generally recommended
to use a unique identifier as the key rather than an index.

---

**What is the recommended order of methods in component class?**  
The recommended ordering of methods in a React component class is as follows: constructor, render, lifecycle methods,
event handlers. This ordering groups related methods together and makes it easier to understand and maintain the code.

---

**Why should component names start with capital latter?**  
Because in order to distinguish them from regular HTML tags and make the code easier to read. This is a convention that
is widely used in the React community and helps developer to understand the purpose and scope of different parts of the
code.

---

**Why we need to be careful when spreading props on DOM elements?**  
It is important to be careful because it can spread invalid HTML attributes. This can cause the component to render
incorrectly or even create security vulnerabilities. It is recommended to only spread props on components that you
trust, or to manually whitelist the valid attributes.

---

**What are inline conditional expressions?**  
Inline conditional expressions in React are expressions that are used to conditionally render components
based on a certain condition. For example:
```jsx
// Logical && operator
{isLoggedIn && <LogoutButton />}

// Or || operator
{unreadMessages || <p>No unread messages</p>}

// Ternary operator
{isPremium ? <PremiumContent /> : <RegularContent />}
<div className={isValid ? 'valid' : 'invalid'}>
```

---

**Why shouldn't we update the state directly?**  
In React the state should not be updated directly because it can cause the component to re-render
improperly. Instead, the setState() method should be used to update state, which triggers a re-render
of the component and ensures that the updated state is properly reflected in the UI.

---

**What is state in React?**  
In React, state refers to a component's internal data that can change over time. State is managed using
the setState method, which allows developers to update the state of a component and trigger a re-render
of the UI. State is used to keep track of data that changes in response to user input or other events.

---

**What is the purpose of the callback function as an argument of setState?**  
The callback function as an argument of the setState method in React is used to update the state
asynchronously. When the setState() method is called, the state update may not happen immediately, which
can cause issues when trying to access to updated state. The callback function is called after the state
has been updated, ensuring that the updated state is available to use.

---

**What is the difference between state and props?**  
The main difference between state and props in React is that state is managed within a component, while props are
passed down from a parent component. State is used to manage a component's internal data, which can change over
time, while props are used to customize a component's behavior and appearance.

---

**What are pure components?**  
Pure components in React are components that implement the shouldComponentUpdate lifecycle method to improve
performance. This method compares the current props and state to the next props and state, and determines whether
the component needs to be re-rendered. If the props and state have not changed, the component can skip the rendering
process.

---


**What are forward refs?**  
Forward refs are a way to pass a ref from parent component to a child component. This allows the parent component to
access and manipulate the child component's DOM node. Forward refs are created using the React.forwardRef() function.

---

**What is React Fiber?**  
React Fiber is a new rendering engine for react that was introduced in React 16. It is designed to improve performance
and enable more flexibility in scheduling updates. With React Fiber, React can break up large updates into smaller
chunks , prioritize updates, pause and resume updates as needed.

---

**What is the difference between createElement and cloneElement?**  
createElement is a method used to create new React elements, while cloneElement is a method used to clone existing React
elements and pass new props to the cloned element.

---

**What are String Refs Legacy?**  
String refs which allow developers to set refs using a string identifier, are considered legacy because they can cause
naming conflicts and bugs. They have been replaced with callback refs and React.createRef() API.

---

**Why fragments are better than container divs?**  
Because they are more performant. Using a container div adds an extra DOM node which can slow down rendering and create
problems with styling. Fragments, on the other hand, allow you to group elements without adding an extra nodes to the
DOM.

---

**What is Context?**  
Context is a way to pass data down to the child components without using props. It is useful for data that needs to be
accessed by many components at different levels of the component hierarchy. Context provides a way to avoid the "prop
drilling" problem, where props need to be passed down through many layers of components.

---

**What is Lifting State Up in React?**  
Lifting State Up is a technique in React for passing data up from child components to parent components. This is useful
when multiple components need to share the same state or when a child component needs to update the state of a parent
component.

---

**What are error boundaries in React v16?**  
Error boundaries are a way to handle errors in React components. In React v16, error boundaries are special components
that catch and handle errors that occur during rendering. This can help to prevent entire application from crashing due
to an error in a single component.

---

**What is virtual DOM?**  
The virtual DOM is a representation of the browser's DOM in memory. It is used by React to optimize and speed up
updates to the actual DOM by minimizing the number of changes that need to be made. When a component's state is
changes, React updates the virtual DOM and compares it to the previous version. It then calculates the most efficient
way to update the actual DOM based on the differences between the two versions.

---

**How to apply validation on props in React?**  
In React, you can apply validation on props using the PropTypes library. PropTypes allow you to define the type and
shape of a component's props, which helps to catch errors and bugs early in development.

---

**What are Higher-Order components?**  
They are components that enhance the behaviour of other components by adding additional functionality or props. HOCs
take a component as input and return a new component that includes the additional behaviour. This allows developers
to reuse code and separate concerns in their applications.

---

**How to create props proxy for HOC component?**  
To create a props proxy for a HOC component, you can wrap the component with another component that adds the additional
props. This is done by defining a new component that takes the original component as input and returns a new component
that includes the additional props.

---

**How virtual DOM works?**  
When a component's state changes in React, it updates the virtual DOM and calculates the most efficient way to update
the actual DOM based on the differences between the two versions. This approach minimizes the number of changes that
need to be made to the actual DOM and improves performance.

---

**What is the difference between shadow DOM and virtual DOM?**  
Shadow DOM and virtualDOM are two different concepts. Shadow DOM is a browser feature that allows developers encapsulate
styles and markup within components. Virtual DOM on the other hand is React feature that allows for performance
optimization by minimizing changes to the actual DOM.

---

**What is reconciliation?**  
Reconciliation is the process of comparing two versions of a component and updating the DOM with the changes. When a
component's state or props change, React compares the new version of the component to the previous version and
calculates the minimum number of changes needed to update the DOM. This process is called reconciliation and is one of
the key features of Rect that makes it so efficient.

---

**What is the main goal of React Fiber?**  
The main goal of React Fiber is to improve client-side rendering performance. It does this by introducing a new
algorithm for rendering updates that is more efficient and flexible than the previous algorithm. With React Fiber,
React can break up large updates into smaller chunks, prioritize, pause and resume updates as needed.

---

**What are portals in React?**  
Portals in React provide a way to render a component's children in a different part of the DOM. This can be useful
for creating modal dialogs, tooltips and other UI components that need to be positioned outside the normal flow of the
page.

---

**What is ReactDOMServer?**  
This is a module that allows you to render react components on the server. It is provided several methods for rendering
components, including the renderToString method and the renderToStaticMarkup method.

---

**How are error boundaries handled in React v15?**  
Error boundaries were not supported in React v15. Error handling in React v15 was less robust and could lead to entire
application crashing if an error occurred during rendering.

---

**What are the recommended ways for static type checking?**  
There are several recommended ways to implement static type checking in React, including using Typescript or Flow.
Typescript and Flow are both static type checkers that can help to catch errors and bugs before they happen. The
PropTypes library is another way to perform type checking, but it is less powerful than Typescript and Flow. ESLint is
a code linter that can help to catch errors and enforce best practices, but it is not a type checker.

---

**How to use InnerHTML in React?**  
You can use *dangerouslySetInnerHTML* prop to set the inner HTML of a component. The *dangerouslySetInnerHTML* prop is
used to bypass React's built-in sanitization and allow arbitrary HTML to be injected into a component. However, this
should be used with caution, as it can pose a security risk.

---

**What will happen if you use setState in constructor?**  
If you use *setState* in a component's constructor, It will update the component's state. However, this is generally
not recommended, as it can cause problems with initialization and lead to confusing code. It is bette to set the initial
state in the constructor using *this.state* property.

---

**How events are different in React?**  
Events in React are different from native events in several ways. React events are synthetic events that are
cross-browser compatible and have the same API across all browsers. React events are also camelCase instead of
lowercase. Finally, React event are different API than native events, including the ability to call *preventDefault*
and *stopPropagation* on the event object.

---


**What are React Mixins?**  
React Mixins are reusable code snippets that can be applied to multiple components in order to provide shared
functionality. They are a way to encapsulate logic and behaviour that cn be used across multiple components, allowing
for code reuse and reducing duplication. However, they are not recommended in modern versions of React and have been
largely replaced by higher-order components and render props.

---

**What is the difference between super() and super(props) in React using ES6 classes?**  
In React using ES6 classes, super() is used to call the constructor of the superclass, while super(props) is used to
pass props to the constructor of the superclass. The super(props) syntax is necessary if you need to access props in
the constructor of a subclass.

---

**How to listen to state changes?**  
We can do it using **useState** and **useEffect** hooks:
```jsx
import { useState, useEffect } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log('Count updated: ', count);
  }, [count]);

  return <button onClick={() => setCount(count + 1)}>Increment</button>
}
```

---

**Do Hooks replace render props and higher-order components?**  
Hooks in React can replace both render props and higher-order components in some cases. Hooks can provide same
functionality to both of these patterns, while also simplifying the code and making it more reusable. For example, the
*useEffect* Hook can replace the *componentDidMount* and *componentDidUpdate* lifecycle methods as well as some uses
of higher-order components.

---

**What is a switching component?**  
A switching component in React is a component that renders one of several child components based on some condition or
state. This is commonly used to switch between different views or user interface elements in response to user input
or other events. The common ways to implement a switching component are:
- **Using switch statement:**
```jsx
function Switch(props) {
  switch(props.page) {
    case 'home':
      return <HomePage />;
    case 'about':  
      return <AboutPage />;
    default:
      return <NotFoundPage />;
  }
}
```
- **Using a components map:**
```jsx
const components = {
  home: HomePage,
  about: AboutPage
};

function Switch(props) {
  const Component = components[props.page] || NotFoundPage;
  return <Component />;
}
```
- **Using ternary operator:**
```jsx
function Switch(props) {
  return (
    props.page === 'home'
      ? <HomePage />
      : <AboutPage />
  );
}
```

---

**How to re-render the view when then browser is resized?**  
In React, you can re-render the view when the browser is resized by using a state variable and updating it on resize.
This will trigger a re-render of the component and allow you to update the layout or other properties based on the new
size of browser window. You can use the *windowAddEventListener* method to listen for the *resize* event and update the
state variable accordingly.
```jsx
useEffect(() => {
  function handleResize() {
    setWindowSize(window.innerWidth);
  }
  
  window.addEventListener('resize', handleResize);
  
  return () => window.removeEventListener('resize', handleResize);
}, []);
```

---

**What are the lifecycle methods going to be deprecated in React v16?**  
The *componentWillReceiveProps* and *componentWillUpdate* lifecycle methods are going to be deprecated in React v16.
These methods will be replaced with new lifecycle methods that are more efficient and easier to reason about. The new
methods are: *getDerivedStateFromProps* and *getSnapshotBeforeUpdate*.

---

**Why do we need to pass a function to setState?**  
This is because in order to avoid infinite loops. If we pass an object directly, it can cause the component to
re-render and update the state endlessly. By passing a function, we can ensure that the state is updated correctly and
avoid these issues.

---

**What is React PropType array with shape?**  
The *shape* propType in React allows you to validate an object with a specific shape, while the *arrayOf* propType
allows you to validate an array of values. The *arrayOf* propType can be combined with the *shape* propType to validate
an array of objects with a specific shape. This is useful for validating data structures in React components.

---

**What is the purpose of getSnapshotBeforeUpdate() lifecycle method?**  
In React this method is used to capture information from the DOM before it changes. This method is called right before
the DOM is updated and can return a value that will be passed to the componentDidUpdate method. It is commonly used
to preserve scroll position or other user interface during updates.

---

**Is it possible to use React without rendering HTML?**  
In React, It is possible to use the library for non-HTML rendering, such as SVG or Canvas. React provides a flexible
programming interface for creating components and managing state, and it can be used to generate any kind of output,
not just HTML. React is also used for building mobile applications with React Native, which uses same programming
model as React for building UIs on iOS and Android platform.

---

**What is the recommended approach of removing an array element in react state?**  
The recommended approach is to use *filter()* method. This allows you to create a new array that contains all the
elements of original array except the one you want to remove.
```jsx
import { useState } from 'react';

function App() {
  const [items, setItems] = useState([1, 2, 3]);

  const removeItem = (index) => {
    const updatedItems = items.filter((item, i) => i !== index);
    setItems(updatedItems);
  }

  return (
    <div>
      {/* Render items */}
      <button onClick={() => removeItem(index)}>Remove</button>
    </div>
  );
}
```

---

**How do you memoize a component?**  
There are a couple ways to memoize a React functional component to avoid unnecessary re-renders when
the props haven't changed:
- **React.memo:** This is a higher order component that will memoize a functional component based on its props.
```jsx
const MyComponent = React.memo(function MyComponent(props) {
  /* only rerenders if props change */
});
```
- **useMemo hook:** This will memoize the result of a function call based on dependencies like props.
```jsx
function MyComponent(props) {
  // only recalculated if props.data changes
  const data = useMemo(() => transformData(props.data), [props.data]);  
  
  return <div>{data}</div>
}
```
- **useCallback hook:** useCallback can memoize a callback function so that reference equality is preserved between renders.
```jsx
// memoize callback
const memoizedCallback = useCallback(
    () => {
        doSomething(a, b);
    },
    [a, b],
);
```

---

**How do you implement server side rendering or SSR?**  
Here is a general approach to implement server-side rendering (SSR) in React:
- **1. Create a Universal App:**
  Your React app needs to be universal - able to run on both client and server. Use a framework like Next.js or modify your app accordingly.
- **2. Render on Server:**
  On the server, call ReactDOMServer.renderToString() to render your app to an HTML string.
```js
import ReactDOMServer from 'react-dom/server';

const appHtmlString = ReactDOMServer.renderToString(<App />);
```
- **3. Output HTML:**
  Inject the HTML string into your page template and send it as the response from the server.
- **4. Hydrate on Client:**
  The client receives the HTML from the server and ReactDOM.hydrate() hydrates those static markup into a live React app.
```jsx
ReactDOM.hydrate(<App />, document.getElementById('root'));
```
This makes React avoid re-rendering on the client for improved performance.

---

**What is the purpose of getDerivedStateFromProps() lifecycle method?**  
This lifecycle method in React is used to update the state based on changes to props. This method is called every time
the component is updated and can return a new state object. It is commonly used to synchronize the state with the props
in response to user input or server-side changes.

---

**Why ReactDOM is separated from React?**  
ReactDOM is separated from React in order to improve performance and reduce the bundle size of React applications.
Separating the rendering logic from the component logic allows for more efficient updates and reduces the amount of
javascript that needs to be downloaded by the client. This separation also allows for easier integration with other
rendering targets such as native mobile apps or desktop applications.

---

**What is the difference between setState and replaceState methods?**  
The *retState* method is used to update component state, and it merges the new state with the old one. The
*replaceState* is similar, but it overwrites the old state completely with the new state. However, *replaceState* is
deprecated in React and should not be used. Instead, you should use the *setState* method to update state in a React
component.

---

**How to pretty print JSON with React?**
- **JSON.stringify:**
```jsx
const data = { name: 'John', age: 30 };

const json = JSON.stringify(data, null, 2);

return <pre>{json}</pre>
```
- **react-json-view library:**
```jsx
import ReactJson from 'react-json-view';

const data = { name: 'John', age: 30 };

return <ReactJson src={data} />;
```
- **react-json-pretty library:**
```jsx
import JsonPretty from 'react-json-pretty';

const data = { name: 'John', age: 30 };

return <JsonPretty data={data}></JsonPretty>
```
---

**What is strict mode in React?**  
It is a mode that highlights potential problems in the code, such as identifying components with unsafe lifecycles,
warning about legacy string ref API usage, detecting unexpected side effects and detecting legacy context API.
It can help to identify issues early on and improve the overall quality of the code. Strict mode can be enabled
globally or for individual components.

---

**How do you use decorators in React?**  
Decorators in React can be used as class decorators to add a functionality to a component class. For example, you can
use a decorator to add additional lifecycle methods or state to a component. Decorators can be written as higher-order
components(HOCs) or as regular functions.

---

**What are the Pointer Events supported in React?**  
React supports both mouse and touch events through the use of Pointer Events. Pointer Events are the standardized event
model that provide a unified way to handle mouse, touch and stylus input. React provides a set of event handlers for
Pointer Events, such as *onPointerDown* and *onPointerMove* that can be used to create responsive and touch-friendly
user interfaces.

---

**How to create refs?**
```jsx
function MyComponent() {
  const ref = useRef();
  
  useEffect(() => {
    // access DOM element
    const element = ref.current;
  }, []);
  
  return <div ref={ref}></div>
}
```

---

**What is the use of Refs?**  
Refs in React are used to create references to DOM elements. They allow developers to access and manipulate the
properties and methods of DOM elements directly, without the need of additional logic or event handling. Refs are
typically used when with third-party libraries or when manipulating the DOM directly is necessary.

---


**What are uncontrolled components?**  
Uncontrolled components in React are components that maintain their own internal state. Their values are not
controlled by React. For example, this is an uncontrolled input:
```jsx
<input type="text" />
```
The input manages its own state internally, and React has no control over its value.
Some characteristics of uncontrolled components:
- They maintain their own internal state
- The state can only be updated via DOM events
- Their value is not set by React props
- Examples include native input and textarea elements
- Use refs to read their state when needed

---

**What are controlled components?**  
Controlled components in React are components that have their values controlled by React. Typically, this is done by:
1. Specifying the component's value via props
2. Updating the value via callbacks like onChange

For example, this input is a controlled component:
```jsx
function MyInput({ value, onChange }) {
  return (
    <input 
      value={value}
      onChange={onChange} 
    />
  );
}
```

The key aspects are:
- The input value is passed in via the value prop
- onChange handler updates the parent component's state
- Input is controlled through props rather than local state

Advantages of controlled components:
- Input values are predictable and trackable
- Parent maintains control over form data
- Easy to validate or sanitize input
- Can simplify complex inputs handling multiple states

---

**What are synthetic events in React?**  
They are events that are cross-browser compatible and behave consistently across different platforms. They are also
optimized for performance by pooling event objects, which allows them to be reused and prevents excessive memory
allocation. Synthetic event have the same interface as native events, but they are implemented differently behind
the scenes.

---

**How to bind methods or event handlers in JSX callbacks?**  
Methods or event handlers can be bound in JSX callbacks using arrow functions. Arrow functions inherit the context of
their parent scope, which allows them to access the component's methods and state. The bind method and the this keyword
can also be used to bind methods or event handlers, but arrow functions are the recommended approach.

---

**How to pass a parameter to an event handler or callback?**  
A parameter can be passed to an event handler or callback in React using an arrow function. The arrow function takes
the event as a parameter, along with any additional parameters that need to be passed. This approach ensures that the
event object is properly handled and that the correct parameters are passed to the event handler or callback.

---

**What is the difference between HTML and React event handling?**  
The main difference between HTML and React event handling is that React uses synthetic events, while HTML does not.
Synthetic events are cross-browser compatible and behave consistently across different platforms. They are also
optimized for performance by pooling event objects.

---


**How to import and export components using React and ES6?**  
In React and ES6, you can import and export components using the *import* and *export* keywords.
To import a component, you can use the *import* keyword followed by the component name and file
path. To export a component, you can use the *export* keyword before component declaration. For
example:
```javascript
import React from "react";
export class MyComponent extends React.Component {}
export function MyOtherComponent() {}
```

---

**How to get history on React Router v4?**  
In React Router v4, you can get the history object by using the *this.props.history* object passed
to the component. This object contains the current history of the router, including the current
location, previous locations and navigation history. You can use this object to programmatically
navigate, access the current URL or manage the browser history.

---

**How to update the component every second?**  
You can do this by using *useState* and *useEffect* hooks and *setInterval* method, For example:
```javascript
import React, { useState, useEffect } from 'react';

function StandAloneUpdate() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setCount(count => count + 1); 
    }, 1000);
    return () => clearInterval(interval);
  }, []);

  return <div>{count}</div>;
}
```

---

**How to implement default or NotFound page?**
```jsx
function App() {
    return (
        <BrowserRouter>
            <Routes>
                <Route index element={<Home />} />
                <Route path="product" element={<Product />} />
                <Route path="pricing" element={<Pricing />} />
                <Route path="login" element={<Login />} />
                <Route
                    path="app"
                    element={
                        <ProtectedRoute>
                            <AppLayout />
                        </ProtectedRoute>
                    }>
                    <Route index element={<Navigate replace to="cities" />} />
                    <Route path="cities" element={<CityList />} />
                    <Route path="cities/:id" element={<City />} />
                    <Route path="countries" element={<CountryList />} />
                    <Route path="form" element={<Form />} />
                </Route>
                <Route path="*" element={<NotFound />} />
            </Routes>
        </BrowserRouter>
    );
}
```

---

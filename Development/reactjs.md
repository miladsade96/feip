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

**How does reactjs work?**  
ReactJS is a JavaScript library for building user interfaces. Here is a brief overview of how it works:
- React uses a declarative paradigm - you describe what you want the UI to look like through components, and React takes care of updating the DOM for you.
- Components are reusable pieces of code that return React elements describing what should be rendered on the screen. They can take in data through props and maintain internal state.
- When a component's state changes, React will efficiently update and re-render the component and its children. This is made possible by React's use of a virtual DOM.
- The virtual DOM is a JavaScript representation of the actual DOM. When a component's state changes, React generates a new virtual DOM tree.
- React then compares this new virtual DOM with the previous one and figures out the minimal set of actual DOM manipulations needed to sync them up. This makes updating the real DOM very fast.
- To determine when to re-render components, React uses a uni-directional data flow based on state. State is kept as simple as possible, and any data that influences how components render is kept in this state.
- When state changes, React components auto-rerender efficiently. Props also allow passing data down the component tree to child components.

---

**What are react hooks?**  
React hooks are a feature that was added in React 16.8 which allow you to use state and other React features without
writing a class component. Hooks allow you to leverage React features without classes. This can help reduce boilerplate
code and make it easier to share logic between components. Hooks were a major addition to React and changed how most
React code is written today.

---

**What are the differences between a class component and a functional component?**  
Here are the main differences between class components and functional components in React:
- Class components are ES6 classes that extend React.Component. Functional components are plain JavaScript functions.
- Class components have state and lifecycle methods. Functional components only receive props and render UI based on those props.
- Class components require more code and syntactic overhead compared to simpler functional components.
- Functional components can now use hooks to manage state and perform side effects (as of React 16.8). Before hooks, these could only be done in class components.
- Class components should be used when you need lifecycle methods, internal state, or access to the component instance.
- Functional components are preferable when you just need to receive props and render UI, without needing internal state.
- Prior to hooks, functional components could only contain the render method and had no state. Now with hooks, functional components can pretty much do everything class components can.
- Functional components offer better performance because they avoid the class overhead and state management that class components require.

---

**What is the difference between presentational component and container component?**  
The difference between presentational and container components in React can be summarized as:

- **Presentational Components:**
  - Also known as "dumb" components
  - Responsible for how things look
  - Typically functional components
  - Receive data and callbacks via props
  - Rarely have their own state - they rely on props
  - Written to be as reusable as possible

- **Container Components:**
  - Also known as "smart" components
  - Responsible for how things work
  - Typically class components
  - Provide data and callbacks to presentational or other container components
  - Call Flux actions and provide these as callbacks to presentational components
  - May contain both presentational and container components inside, but usually don't have DOM markup of their own

---

**What does it mean for a component to be mounted in react?**  
In React, when we say a component is mounted, it means the component has been rendered into the DOM (Document Object Model).

Specifically, mounting refers to the actual process of inserting a React component into the DOM tree. This happens when:

- A component is rendered for the first time
- A component re-renders after an update and gets inserted back into the DOM.

The mounting process consists of several phases:

- `constructor()`
- `static getDerivedStateFromProps()`
- `render()`
- `componentDidMount()`

---

**What is useState() in react?**  
useState is a Hook in React that allows you to add state to functional components.

It is a function that takes the initial state as an argument and returns an array of two entries:

1. The current state value
2. A function to update this state value

For example:

```javascript
const [count, setCount] = useState(0); 
```

Here:

- `count` - holds the current state value
- `setCount` - is a function to update the state.

You can call setCount() to update the state:

```javascript
setCount(prevCount => prevCount + 1);
```

When the state updates, the component re-renders and uses the latest state value.
useState is a simpler way to add state compared to class components, since there is no need to define a separate class with this.state.

---

**How is react different from angular(1.x)?**  
Here are some key differences between React and AngularJS (Angular 1):
- React is a JavaScript library that deals with just the UI layer of an application, while AngularJS is a full MVC framework.
- React uses a reactive programming paradigm that favors immutability and encourages thinking in terms of state changes over time, while AngularJS uses two-way data binding between models and views.
- React uses a Virtual DOM and optimizes updates by comparing actual DOM changes rather than dirty checking everything like AngularJS. This makes React faster in most cases.
- AngularJS uses directives and bindings to link behavior and DOM, while React uses composable components with unidirectional data flow.
- AngularJS has built-in routing, Ajax handling, and other features, while React is focused on the view layer only.
- React has a much simpler and flexible architecture with fewer concepts to learn compared to a full framework like AngularJS.
- React has better support for server-side rendering and building mobile applications compared to AngularJS.
- AngularJS has two-way data binding between scopes, while React uses a one-way data flow model between components.
- AngularJS uses dirty checking to detect changes and redraw views, while React Only updates DOM elements that have changed.

---

**What are two types of components in react?**  
The two main types of components in React are:
1. Functional Components
2. Class Components(ES6 classes that extend React.Component)

---

**What are the advantages of using react hooks?**  
Here are some of the key advantages of using React hooks:

- Simpler code - Hooks allow function components to have state and lifecycle methods without writing a class. This reduces a lot of boilerplate code.
- Reusable logic - Hooks allow sharing stateful logic across components, rather than having to create new classes.
- Modular code - Each hook contains a specific piece of functionality, making code more modularized
- Stateful logic in function components - Hooks allow having state and lifecycle methods directly in function comonents. No need to swap between functions and classes.
- No breaking changes - Hooks are additive and don't contain any breaking changes. Older class compnent code still works.
- Easy to start using - Hooks have a small API surface and are easy to start using in new or existing React codebases
- Flexible control flow - Hooks allow splitting component logic into smaller functions that can be extracted out or calle separately.

---

**What happens during the lifecycle of a React component?**  
Here are the main phases of the component lifecycle in React:

- **Mounting:**
  - `constructor()` - Called before the component is mounted. Initialize state here.
  - static `getDerivedStateFromProps()` - Set state before render.
  - `render()` - Render UI and components in return statement.
  - `componentDidMount()` - Called after component is rendered. Cause side effects here.

- **Updating:**
  - static `getDerivedStateFromProps()` - Set state before re-rendering.
  - `shouldComponentUpdate()` - Decide if the component should re-render after changes.
  - `render()` - Rerender UI with latest changes.
  - `getSnapshotBeforeUpdate()` - Called right before DOM update. Capture DOM info here.
  - `componentDidUpdate()` - Called after update is committed. Cause side effects here.

- **Unmounting:**
  - `componentWillUnmount()` - Called before the component is unmounted and destroyed. Clean up resources here.

---

**What is the difference between component and container in redux?**  
The main differences between component and container in Redux are:
- Components are concerned with how things look. Containers are concerned with how things work.
- Components receive data and callbacks exclusively via props. Containers receive props and also connect to the Redux store to get state/dispatch.
- Components are reusable and often stateless. Containers usually wrap components and map Redux state/actions to props.
- Components define presentation and are concerned with UI. Containers handle data flow and subscribe to Redux state.
- Components can be substituted for simpler mocking/testing. Containers usually can't be shallowly tested and mock store setup is needed.
- Components receive data and callbacks from containers. Containers often generate container-specific props to pass to components.
- Components render HTML markup or other UI. Containers often render only a single component or multiple container components.
- Components should be as reusable and generic as possible. Containers are created once per page or connected feature.

---

**What happens when you call setState?**  
Here is what happens when you call setState in a React component:
1. `setState()` enqueues changes to the component state object.
2. This triggers React to re-render the component with the updated state.
3. The component's `render()` method is called and React updates the DOM.
4. The component gets re-rendered on the UI with the new changes.
5. If state update depends on previous state, the `setState()` callback can be used. The callback will fire after the render is finished.

---

**How to call loading function with react useEffect only once?**  
Here is how you can call a loading function only once using the `useEffect` hook in React:

```jsx
import { useEffect } from 'react';

function Component() {
  useEffect(() => {
    loadData();
  }, []);

  const loadData = () => {
    // API call to load data 
  };

  return <div>Component</div>; 
}
```

The key is passing an empty array as the second argument to `useEffect`. By default, `useEffect` runs after every render.
But passing an empty array [] as the second parameter tells React to only run it once on mount and unmount, like
`componentDidMount` and `componentWillUnmount` combined.

---

**How to access DOM elements in react functional component?**  
Here are a few ways to access DOM elements in React functional components:

1. Use Refs

Refs work the same in functional components as they do in class components. Create a ref with `React.createRef()`, assign it to an element, and access the current property:

```jsx
import React, { useRef } from 'react';

function MyComponent() {
  const inputRef = useRef(null);

  return <input ref={inputRef} />;

  // Access DOM element:
  inputRef.current; 
}
```

2. Use callback refs

You can pass a callback function that receives the DOM element on mount:

```jsx 
function MyComponent({ setInput }) {
  return <input ref={setInput} />;
}

// Parent component
function Parent() {
  const [input, setInput] = useState(null);
  
  return <MyComponent setInput={setInput} />
}
```

3. Use useEffect hook

If you need access to the DOM element after rendering, you can use the useEffect hook:

```jsx
useEffect(() => {
  const input = document.querySelector('#my-input');
}, []); 
```

---

**Name the different lifecycle methods for class components?**  
The main lifecycle methods for React class components include:
- **Mounting:**
  - `constructor()`
  - static `getDerivedStateFromProps()`
  - `render()`
  - `componentDidMount()`
- **Updating:**
  - static `getDerivedStateFromProps()`
  - `shouldComponentUpdate()`
  - `render()`
  - `getSnapshotBeforeUpdate()`
  - `componentDidUpdate()`
- **Unmounting:**
  - `componentWillUnmount()`

---

**What is `{this.prop.children}` and when you should use it?**  
`this.props.children` is a special prop in React that allows passing children components as data to parent components.
For example:
```jsx
<ParentComponent>
  <ChildComponent />
</ParentComponent>
```
In ParentComponent, we can output `{this.props.children}` to render ChildComponent:

```jsx
function ParentComponent(props) {
  return <div>{props.children}</div> 
}
```

---

**How would you prevent a component from re-rendering in react?**  
Here are some ways to prevent a component from re-rendering in React:

- **Using React.memo:**
The React.memo higher order component allows memorizing a component unless its props change. This can prevent unnecessary re-renders:
```jsx
const MyComponent = React.memo(function MyComponent(props) {
  // ...
});
```

- **Using Pure Component:**
Extend `React.PureComponent` instead of `React.Component` in a class. It performs a shallow comparison of props and state to prevent unnecessary re-renders.

- **Using useMemo Hook:**
Wrap a function component in `useMemo()` to memoize it and prevent re-renders:

```jsx
const MyComponent = useMemo(() => {
  //...
}, []); 
```

- **Use useCallback Hook:**
Return function from useCallback to prevent it re-creating on each render:
```jsx 
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b], 
);
```

---

**What is the typical pattern for rendering a list of components from an array in react?**  
The typical pattern for rendering a list of components from an array in React is:
- **Map over the array of data:**  
For example:
```jsx
const listItems = dataArray.map(item => {
  return <Component key={item.id} item={item} />; 
});
```

---

**What is the typical flow of data like in a React + redux app?**  
Here is a typical flow of data in a React + Redux app:

- **Initial setup:**
  - React components are created to define UI structure
  - Redux store is created to hold application state
  - Components that need data from Redux connect to the store

- **User interaction:**
  - User interacts with a connected React component
  - Callback handlers detect events like clicks
  - Action creator functions are called with details about the event

- **Dispatching actions:**
  - Action creator functions create and return Redux action objects
  - Components may call dispatch function to dispatch the actions

- **Reducers update state:**
  - Redux store runs the reducers with the dispatched action
  - Reducers calculate a new state immutably based on actions
  - Store saves updated state

- **Components re-render:**
  - MapStateToProps selects relevant data from updated state
  - This data is passed as props to connected React components
  - Components re-render with updated props

- **Display updates:**
  - Updated components rerender UI with new state
  - Changes from the state updates are reflected

---

**What are some limitations of things you should not do in the component's render method in react?**  
Here are some things to avoid in React component's render method:
- **Side effects** - Avoid directly calling `setState()` or other functions with side effects. This can lead to inconsistent UI. Instead, do side effects in `componentDidMount()` or `componentDidUpdate()`.
- **Slow computations** - Avoid expensive calculations or API calls directly in render, as this makes every update slow. Move computations outside render.
- **Non-pure functions** - Render should be idempotent and pure, meaning render should render the same output for same input. Avoid functions with side effects or randomness.
- **Updating state** - Do not update state directly from render as it can lead to infinite loops. Use setState() outside of render instead.
- **JSX spreading** - Avoid spreading props or state directly into JSX as it becomes less readable and can break optimizations. Explicitly specify attributes instead.
- **Referencing props/state in loops** - Avoid arrays.map() or loops that reference props/state in the loop body, as it forces updating each iteration. Cache the value first.
- **Rendering based on props** - Avoid conditionals that render different content based on props or state. Move conditional rendering logic higher up instead.
- **Reading DOM nodes** - Avoid reading DOM nodes in render. This breaks server-side rendering and confuses React reconciliation. Use refs sparingly instead.

In summary, render should contain only the minimally needed code to render UI based on inputs. It is the wrong place for side effects, data fetching, or non-idempotent logic.

---

**What is prop drilling and how can you avoid it?**  
`Prop drilling` is a term used in React to describe the process of passing data down through a component hierarchy.
This can be necessary when a component needs to access data that is stored in a parent component, but it can also lead
to code that is difficult to maintain and debug.

**Here are some ways to avoid prop drilling:**

- **Lift state up:** When possible, lift state up to the nearest common ancestor component. This will allow all descendant components to access the state without having to pass it down as props.
- **Use component composition:** Component composition is a way of building complex components out of smaller, more reusable components. By composing components, you can avoid passing props down through the hierarchy unnecessarily.
- **Use the React Context API:** The React Context API provides a way to share data between components without having to pass it down as props. This is a good option for sharing data that is needed by many components at different levels of the hierarchy.

---

**What is the point of `shouldComponentUpdate` method?**  
The `shouldComponentUpdate()` method is a React lifecycle method that allows you to control whether a component
should re-render. By default, React will re-render a component whenever its state or props change. However, in some
cases, you may want to prevent a component from re-rendering unnecessarily. This can improve the performance of your
application, especially if the component is complex or expensive to render.

To use `shouldComponentUpdate()`, you simply need to implement it in your component class. The method should return a
boolean value. If it returns `true`, then the component will re-render. If it returns `false`, then the component will
not re-render.

Here is a simple example:

```javascript
class MyComponent extends React.Component {
  shouldComponentUpdate(nextProps, nextState) {
    // Only re-render the component if the props or state have changed.
    return nextProps !== this.props || nextState !== this.state;
  }

  render() {
    // ...
  }
}
```

In this example, the `shouldComponentUpdate()` method will return `true` if the props or state have changed, and `false`
otherwise. This means that the component will only re-render if something has changed that will affect the output of the
component. It is important to note that you should use `shouldComponentUpdate()` with caution. If you are not careful,
you can accidentally prevent a component from re-rendering when it should, which can lead to bugs.

---

**What do these three dots(...) in React do?**  
The three dots (...) in React are used for spread syntax. Spread syntax allows you to expand an iterable object, such
as an array or object, into its individual elements. This can be useful in a variety of situations, such as when passing
props to a component, spreading an array into a function call, or merging two objects.

---

**What are the different phases of reactjs component lifecycle?**  
The React component lifecycle has three main phases:

1. **Mounting:** The mounting phase begins when a component is first created and inserted into the DOM. This includes the following lifecycle methods:
  * `constructor()`: This method is used to initialize the component's state.
  * `getDerivedStateFromProps()`: This method is used to derive the component's state from its props.
  * `render()`: This method is used to render the component to the DOM.
  * `componentDidMount()`: This method is called after the component has been mounted to the DOM.

2. **Updating:** The updating phase occurs whenever a component's state or props change. This includes the following lifecycle methods:
  * `getDerivedStateFromProps()`: This method is used to derive the component's state from its props, even if the props haven't changed.
  * `shouldComponentUpdate()`: This method is used to determine whether or not the component should re-render.
  * `render()`: This method is used to render the component to the DOM.
  * `componentDidUpdate()`: This method is called after the component has been updated.

3. **Unmounting:** The unmounting phase occurs when a component is removed from the DOM. This includes the following lifecycle method:
  * `componentWillUnmount()`: This method is called before the component is removed from the DOM.

In addition to the three main phases, there are also a few other lifecycle methods that can be used in specific situations. For example, the `getSnapshotBeforeUpdate()` method can be used to take a snapshot of the component's DOM before it is updated.

---

**What is key prop and benefit of using it in lists?**  
The `key` prop is a special attribute that you can use on list items in React. It is used by React to identify which items in the list have changed, added, or removed. This information is then used to efficiently update the DOM.

There are several benefits to using the `key` prop in lists:

* **Improved performance:** When React knows which items in a list have changed, it can efficiently update the DOM without having to re-render the entire list. This can lead to significant performance improvements, especially for large lists.
* **Reduced flicker:** When React uses the `key` prop to update a list, it can avoid flicker by reusing existing DOM elements whenever possible. This can make the user experience smoother and more responsive.
* **Improved error handling:** React uses the `key` prop to track the identity of list items. This can help to prevent errors when items are added, removed, or reordered in the list.

---

**Why do class methods need to be bound to a class instance in react?**  
Class methods need to be bound to a class instance in React because of how JavaScript works. In JavaScript, functions
are first-class objects, meaning that they can be passed around as arguments and assigned to variables. This also means
that functions have their own context, which is the object that owns the function. When you define a method on a class,
the method is created as a function object. However, the method does not have a context by default. This means that when
you call the method, the `this` keyword will refer to the global object, which is usually not what you want. To bind a
method to a class instance, you can use the `bind()` method. The `bind()` method creates a new function object that is
bound to the specified context. This means that when you call the bound function, the `this` keyword will refer to the
specified context.

In React, it is important to bind class methods to class instances because class methods are often used as event
handlers. When you pass a class method to an event handler, the method will be called with the event object as the
`this` keyword. If the method is not bound to a class instance, the `this` keyword will refer to the DOM element that
triggered the event, which is usually not what you want.

Here is an example of how to bind a class method to a class instance:

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    console.log(this); // This will refer to the class instance
  }

  render() {
    return (
      <button onClick={this.handleClick}>Click Me</button>
    );
  }
}
```

In this example, we are binding the `handleClick()` method to the class instance in the constructor. This means that
when we call the `handleClick()` method from the `render()` method, the `this` keyword will refer to the class instance.

You can also use arrow functions to avoid having to bind class methods to class instances. Arrow functions do not have
their own context, so they will always use the context of the function that they are defined in.

Here is an example of how to use an arrow function as an event handler:

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.handleClick = () => {
      console.log(this); // This will refer to the class instance
    };
  }

  render() {
    return (
      <button onClick={this.handleClick}>Click Me</button>
    );
  }
}
```

In this example, we are using an arrow function as the event handler for the `button` element. This means that the
`handleClick()` method will automatically be bound to the class instance, so we do not need to bind it explicitly.

---

**What is the difference between useRef and createRef?**  
**useRef** and **createRef** are two different ways to create refs in React. Refs are a way to access DOM elements or React elements created in the render method. They are useful for cases where you need to imperatively modify a child outside of the typical dataflow, such as focusing an input element or animating an element.

**useRef** is a hook that can be used in functional components. It creates a ref object with a `.current` property. The `.current` property can be used to store any value, but it is typically used to store a DOM element or React element.

**createRef** is a function that can be used in both functional and class components. It also creates a ref object with a `.current` property.

The main difference between useRef and createRef is that useRef is guaranteed to return the same ref object on every render, while createRef may return a new ref object on every render. This means that useRef is better suited for cases where you need to keep a reference to the same element across renders, such as when focusing an input element. createRef is better suited for cases where you need to create a new ref object on every render, such as when creating a list of items and giving each item a unique ref.

---

**What is the significance of key in reactjs?**  
The `key` prop in ReactJS is a unique identifier that is used to help React efficiently manage and update elements within a list. When rendering a list of elements, it is crucial to assign a unique key to each element. This helps React differentiate between the items and perform updates more efficiently.

Here are some of the benefits of using keys in ReactJS lists:

* **Improved performance:** Keys help React to identify which items in a list have changed, updated, or deleted. This allows React to only update the necessary elements, which can improve performance significantly.
* **Reduced bugs:** Without keys, React may not be able to correctly track and update elements in a list. This can lead to unexpected behavior and bugs.
* **Improved readability and maintainability:** Using keys makes the code more readable and maintainable. It is easier to understand which elements in a list are being updated and why.

---

**Are you familiar with flux in the context of React?**  
Yes, I am familiar with Flux in the context of React. Flux is an architectural pattern for managing data flow in React applications. It is designed to make applications more predictable and maintainable.

Flux is based on the following principles:

* **One-way data flow:** Data flows in a single direction, from the dispatcher to the stores to the views. This makes it easier to understand how data changes and propagates through the application.
* **Centralized state:** The application's state is stored in a central location, called the store. This makes it easier to track changes to the state and to ensure that the application's state is always consistent.
* **View-agnostic state:** The store does not care how the data is displayed in the view. This makes it possible to use the same store in different views, and to change the view without affecting the state.

Flux consists of four main components:

* **Actions:** Actions represent user interactions or events. When a user interacts with the application, an action is dispatched.
* **Dispatcher:** The dispatcher is responsible for receiving actions and notifying the stores about the actions.
* **Stores:** Stores contain the application's state and logic. They listen for actions from the dispatcher and update the state accordingly.
* **Views:** Views are React components that display the application's state. They subscribe to changes in the store and update themselves accordingly.

---

**What are Error Boundaries in reactjs?**  
Error boundaries in ReactJS are components that can catch JavaScript errors in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed. Error boundaries catch errors during rendering, in lifecycle methods, and in constructors of the whole tree below them.

Error boundaries are useful because they can prevent an entire application from crashing when a single component fails. For example, if a user is viewing a product list and one of the products in the list fails to render, the error boundary can catch the error and display a fallback UI, such as a message saying "Something went wrong." This allows the user to continue using the application, even though one component failed to render.

---

**What is wrong with using context in react?**  
Context is a powerful tool for managing state in React applications. However, there are some potential drawbacks to using context:

* **Performance:** Context re-renders all components that consume it whenever the context value changes. This can impact performance, especially in large applications with complex state.
* **Complexity:** Context can be difficult to debug and reason about, especially in large applications with many nested contexts.
* **Overuse:** Context can be easily overused, which can lead to performance problems and complex code.

Here are some tips for using context effectively:

* Only use context for global state that needs to be accessible by many components.
* Avoid using context for frequently updated state or state that is only needed by a few components.
* Use memoization to prevent unnecessary re-renders of components that consume context.
* Break down large contexts into smaller, more focused contexts.

---

**What is component composition in react?**  
Component composition in React is a technique for building complex UI components by combining smaller, simpler components. This allows you to reuse code and create more modular and maintainable applications.

To compose components, you simply pass other components as props to your components. For example, you could create a `Button` component that accepts a `children` prop, which could be any React element. This would allow you to create different types of buttons by simply passing different elements to the `Button` component.

For example, you could create a `PrimaryButton` component and a `SecondaryButton` component by passing different styles to the `Button` component:

```javascript
const Button = ({ children, style }) => {
  return (
    <button style={style}>
      {children}
    </button>
  );
};

const PrimaryButton = ({ children }) => {
  return (
    <Button style={{ backgroundColor: 'red', color: 'white' }}>
      {children}
    </Button>
  );
};

const SecondaryButton = ({ children }) => {
  return (
    <Button style={{ backgroundColor: 'blue', color: 'white' }}>
      {children}
    </Button>
  );
};
```

You could then use the `PrimaryButton` and `SecondaryButton` components in your application as follows:

```javascript
<div>
  <PrimaryButton>Primary Button</PrimaryButton>
  <SecondaryButton>Secondary Button</SecondaryButton>
</div>
```

---

**What does Batching mean in react?**  
Batching in React is a technique that groups state updates together and renders them at once. This can improve performance by reducing the number of times the React virtual DOM is updated.

React batches state updates in a few different ways:

* **Within event handlers:** React batches state updates that occur within event handlers. For example, if you have a button that updates two state variables when it is clicked, React will only re-render the component once.
* **Within timeouts and intervals:** React also batches state updates that occur within timeouts and intervals. This can be useful for things like animations and polling.
* **Across asynchronous operations:** React also batches state updates that occur across asynchronous operations, such as promises and fetch requests. This can help to improve performance in applications that use a lot of asynchronous code.

Batching can be disabled by calling the `flushSync()` function. However, this should be used sparingly, as it can impact performance.

---

**What are the advantages of Batching in react?**  
The advantages of batching in React are:

* **Improved performance:** Batching can reduce the number of renders that React needs to perform, which can improve performance significantly, especially in large and complex applications.
* **Smoother and more responsive UI:** Batching can make the UI smoother and more responsive by preventing it from flickering or updating too often.
* **Reduced memory usage:** Batching can reduce memory usage by preventing React from creating unnecessary copies of the virtual DOM.

---

**Which lifecycle methods of class component is replaced by useEffect hook in functional component?**  
The useEffect hook in functional components replaces the following lifecycle methods in class components:

* componentDidMount
* componentDidUpdate
* componentWillUnmount

The useEffect hook allows you to perform side effects in functional components, such as fetching data, setting up subscriptions, and manipulating the DOM.

Here is a table that compares the useEffect hook to the lifecycle methods it replaces:

| Lifecycle method     | useEffect hook                                          |
|----------------------|---------------------------------------------------------|
| componentDidMount    | Runs after the first render                             |
| componentDidUpdate   | Runs after each subsequent render, except for the first |
| componentWillUnmount | Runs before the component is unmounted                  |

---

**Compare useState and useReducer implementations?**  
useState and useReducer are both React hooks for managing state. However, they have different strengths and weaknesses.

**useState** is a simpler and more lightweight hook. It is a good choice for managing simple state, such as a boolean flag or a string. useState is easy to use and understand, even for beginners.

**useReducer** is a more complex and powerful hook. It is a good choice for managing complex state, such as an object or an array. useReducer gives you more control over how your state is updated. It also makes it easier to handle complex state transitions and logic.

Here is a comparison of useState and useReducer implementations:

| Feature            |  useState                                                 | useReducer                                            |
|--------------------|-----------------------------------------------------------|-------------------------------------------------------|
| **Simplicity**     | Simple                                                    | Complex                                               |
| **Control**        | Less control                                              | More control                                          |
| **Complexity**     | Good for simple state                                     | Good for complex state                                |
| **Use cases**      | Managing simple state, such as a boolean flag or a string | Managing complex state, such as an object or an array |

---

**Do react hooks cover all use cases for class components?**  
Yes, React hooks cover all use cases for class components. Hooks are a more modern and flexible way to manage state and side effects in functional components. They can be used to replace all of the lifecycle methods that are available in class components, such as componentDidMount, componentDidUpdate, and componentWillUnmount.

Here is a table that shows how the most common class component lifecycle methods can be replaced with hooks:

| Class component lifecycle method | React hook       |
|----------------------------------|------------------|
| componentDidMount                | useEffect        |
| componentDidUpdate               | useEffect        |
| componentWillUnmount             | useEffect        |
| shouldComponentUpdate            | useMemo          |
| getSnapshotBeforeUpdate          | useLayoutEffect  |
| componentDidCatch                | useErrorBoundary |

---

**How can I make use of Error Boundaries in react functional components?**  
To use error boundaries in React functional components, you can use the `useErrorBoundary` hook. This hook provides a way to catch errors in child components and render a fallback UI instead.

Here is an example of how to use the `useErrorBoundary` hook:

```javascript
import { useErrorBoundary } from 'react';

const MyComponent = () => {
  const [error, setError] = useState(null);

  // Catch errors in child components
  const [errorBoundary] = useErrorBoundary();

  if (errorBoundary.error) {
    return <div>Something went wrong.</div>;
  }

  return (
    <div>
      // Render your child components here
    </div>
  );
};
```

The `errorBoundary` variable returned by the `useErrorBoundary` hook contains information about the error that occurred, if any. You can use this information to render a fallback UI or to log the error to a server.

Here is an example of a fallback UI that you could render in the event of an error:

```javascript
<div>
  <h1>Error</h1>
  <p>Something went wrong. Please try again later.</p>
</div>
```

You can also use the `useErrorBoundary` hook to catch errors in asynchronous code, such as fetch requests.

Here is an example of how to catch an error in a fetch request:

```javascript
import { useErrorBoundary } from 'react';

const MyComponent = () => {
  const [error, setError] = useState(null);

  // Catch errors in asynchronous code
  const [errorBoundary] = useErrorBoundary();

  const fetchUsers = async () => {
    try {
      const response = await fetch('https://api.example.com/users');
      const users = await response.json();
      return users;
    } catch (error) {
      errorBoundary.setError(error);
    }
  };

  if (errorBoundary.error) {
    return <div>Something went wrong.</div>;
  }

  return (
    <div>
      // Render your UI here
    </div>
  );
};
```

---

**When would you use useRef?**  
You would use useRef when you need to:

* Access a DOM element or React element directly.
* Store a value that does not need to trigger a re-render when it is updated.
* Store a value that persists for the lifetime of the component.

Here are some specific examples of when to use useRef:

* **To focus an input element:** You can use useRef to store a reference to the input element and then call the focus() method on the reference when you need to focus the element.
* **To animate an element:** You can use useRef to store a reference to the element you want to animate and then use the reference to update the element's position or other properties over time.
* **To store a value that does not need to trigger a re-render:** For example, if you are using a canvas element to draw something, you can use useRef to store the canvas context and then update the canvas without triggering a re-render.
* **To store a value that persists for the lifetime of the component:** For example, if you have a component that fetches data from an API, you can use useRef to store the fetched data and then use the data throughout the component's lifecycle.

---

**How would you pass data from child to parent component in react?**  
Using `callBack` function: You can pass a callback function from the parent component to the child component. The child
component can then call the callback function to pass data back to the parent component.

To pass data back from the child component to the parent component using a callback, you need to first define a callback
function in the parent component. Then, you need to pass the callback function as a prop to the child component. The 
child component can then call the callback function to pass data back to the parent component.

For example:

```javascript
// Parent component
const ParentComponent = () => {
  const [data, setData] = useState('');

  const handleDataChange = (newData) => {
    setData(newData);
  };

  return (
    <div>
      <ChildComponent handleDataChange={handleDataChange} />
      <p>Data: {data}</p>
    </div>
  );
};

// Child component
const ChildComponent = (props) => {
  const { handleDataChange } = props;

  const handleChange = (event) => {
    const newData = event.target.value;
    handleDataChange(newData);
  };

  return (
    <div>
      <input type="text" onChange={handleChange} />
    </div>
  );
};
```

In this example, the `handleDataChange` callback function is defined in the parent component and passed as a prop to the
child component. The child component then calls the `handleDataChange` callback function to pass the input value back to
the parent component.

---

**Explain the virtual DOM concept in react?**  
The virtual DOM is a lightweight representation of the real DOM. It is used by React to efficiently update the UI.

When a React component updates, React creates a new virtual DOM and compares it to the previous virtual DOM. React then only updates the real DOM with the changes that are necessary. This makes React updates very fast, even for complex applications.

The virtual DOM is a tree data structure, just like the real DOM. Each node in the virtual DOM represents an element in the real DOM. The virtual DOM contains information about the type of element, its attributes, and its children.

When React needs to update the UI, it first creates a new virtual DOM based on the current state of the components. Then, React compares the new virtual DOM to the previous virtual DOM and identifies the changes that need to be made to the real DOM.

React then uses a reconciliation algorithm to update the real DOM with the minimum number of changes. This makes React updates very efficient, even for complex applications.

Here are some of the benefits of using the virtual DOM:

* **Performance:** The virtual DOM can significantly improve the performance of React applications by minimizing the number of DOM updates that need to be performed.
* **Efficiency:** The virtual DOM is very efficient, as it only updates the real DOM with the changes that are necessary.
* **Predictability:** The virtual DOM makes React more predictable, as it is easier to understand how the UI will change when a state update is made.
* **Maintainability:** The virtual DOM makes React code more maintainable, as it is easier to reason about and debug.

---

**Can you force a React component to re-render without calling `setState()`?**  
Yes, you can force a React component to re-render without calling setState() by using the `forceUpdate()` method. The `forceUpdate()` method is available on class components, but it is not recommended to use it on functional components.

To use the `forceUpdate()` method, you simply need to call it on the component instance. For example:

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      count: 0,
    };
  }

  forceUpdate() {
    // Force the component to re-render
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
      </div>
    );
  }
}
```

The `forceUpdate()` method is a powerful tool, but it should be used with caution. Forcing a component to re-render can lead to performance problems, as it can cause the entire component tree to be re-rendered.

---

**How would you go about investigating slow react app rendering?**  
To investigate slow React app rendering, you can follow these steps:

1. **Identify the slow components.** Use React Developer Tools to identify the components that are taking the longest to render. You can do this by enabling the "Highlight updates when components render" option in the React Developer Tools Profiler tab.
2. **Analyze the slow components.** Once you have identified the slow components, you can use React Developer Tools to analyze them and identify the root cause of the slow rendering. You can look at the following things:

  * The number of re-renders that the component is performing.
  * The time it takes for the component's `render()` function to execute.
  * The number of child components that the component is rendering.
  * The time it takes for the child components to render.

3. **Optimize the slow components.** Once you have identified the root cause of the slow rendering, you can optimize the slow components. Here are some tips:

  * Avoid unnecessary re-renders. You can use React.memo() to memoize components and prevent them from re-rendering when their props or state have not changed.
  * Use React.lazy() to load components on demand. This can improve the initial loading time of your application.
  * Use efficient rendering algorithms. You can use React.Fragment to group elements together and reduce the number of DOM nodes that need to be rendered.
  * Avoid complex computations in the render() function. You can use memo functions or React.useCallback() to memoize computations and prevent them from being recalculated unnecessarily.

4. **Test your changes.** Once you have optimized the slow components, you should test your changes to make sure that they have improved the rendering performance of your application.

---

**What is a pure functional component in react?**  
A pure functional component in React is a function component that satisfies the following two conditions:

* It always returns the same output for the same input.
* It does not have any side effects.

This means that pure functional components are predictable and easy to reason about. They also make it easier to write unit tests for your React components.

Here is an example of a pure functional component:

```javascript
const PureButton = ({ onClick, children }) => {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
};
```

---

**What is the second argument that can optionally be passed to setState() and what is its purpose?**  
The second argument that can optionally be passed to setState() is a callback function. This callback function is executed after setState() has finished updating the component's state and the component has re-rendered.

The purpose of the callback function is to allow you to perform side effects after the component has been updated. For example, you could use the callback function to update the DOM, make an API request, or dispatch a Redux action.

Here is an example of how to use the callback function in setState():

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      count: 0,
    };
  }

  handleClick() {
    this.setState((prevState) => ({
      count: prevState.count + 1,
    }), () => {
      // This callback function is executed after the component has re-rendered
      console.log(`The count is now ${this.state.count}`);
    });
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.handleClick}>Increment</button>
      </div>
    );
  }
}
```

In this example, the callback function is used to log the new count value to the console after the component has been updated.

Here are some other examples of how you could use the callback function in setState():

* Update the DOM: You could use the callback function to update the DOM after the component has been updated. For example, you could use the callback function to focus an input element or to scroll to a particular element on the page.
* Make an API request: You could use the callback function to make an API request after the component has been updated. For example, you could use the callback function to fetch data from an API and update the component's state with the fetched data.
* Dispatch a Redux action: You could use the callback function to dispatch a Redux action after the component has been updated. For example, you could use the callback function to increment the count in a Redux store.

---

**When is it important to pass props to `super()` and why?**  
It is important to pass props to super() in React class components when you need to access the props in the constructor or in any of the lifecycle methods.

If you do not pass props to super(), the props will not be available in the constructor or in any of the lifecycle methods. This can lead to errors in your code.

Here are some examples of when you need to pass props to super():

* When you need to access the props in the constructor to initialize the component's state.
* When you need to access the props in a lifecycle method, such as componentDidMount() or componentDidUpdate(), to perform side effects based on the props.
* When you need to use the props to validate the component's state.

---

**Why would you need to bind event handlers to `this`?**  
You need to bind event handlers to this in React because of the way that JavaScript handles scope. In JavaScript, the `this` keyword refers to the current context, which can be different depending on where you are in your code.

When you define an event handler function in a React component, the `this` keyword will refer to the global object, which is usually the `window` object. This can cause problems if you need to access the component's state or props in your event handler function.

To fix this problem, you need to bind the event handler function to the component instance. This will ensure that the `this` keyword refers to the component instance when the event handler function is called.

There are two ways to bind event handlers to this in React:

* **Using the constructor:** You can bind event handler functions in the constructor of your React component. This is the most common way to bind event handlers in React.
* **Using arrow functions:** You can use arrow functions to bind event handler functions inline. Arrow functions automatically bind the `this` keyword to the current context, so you do not need to explicitly bind them.

Here is an example of how to bind an event handler function in the constructor of a React component:

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    // Bind the handleClick function to the component instance
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    // This code will be executed when the button is clicked
    console.log('Button clicked!');
  }

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me!</button>
      </div>
    );
  }
}
```

Here is an example of how to bind an event handler function using an arrow function:

```javascript
class MyComponent extends React.Component {
  render() {
    return (
      <div>
        <button onClick={() => {
          // This code will be executed when the button is clicked
          console.log('Button clicked!');
        }}>Click Me!</button>
      </div>
    );
  }
}
```

---

**Why does not `this.props.children.map` work?**  
There are two main reasons why `this.props.children.map` does not work in React:

1. **`children` is not an array in all cases.** `children` can be a single React element, a string, or an array of React elements. If `children` is a single React element or a string, then `map()` will not work.
2. **`map()` mutates the original array.** `map()` creates a new array by transforming the elements of the original array. This can cause problems if you are trying to use `children` in multiple places in your component.

There are a few ways to fix these problems:

1. **Use a conditional statement to check if `children` is an array.** If `children` is an array, then you can use `map()` to iterate over the elements. Otherwise, you can render the children as-is.
2. **Use a spread operator to create a copy of the `children` array.** This will allow you to mutate the copy of the array without affecting the original array.
3. **Use a higher-order component (HOC) to encapsulate the logic for iterating over the `children` prop.** This can make your code more reusable and maintainable.

Here is an example of how to use a conditional statement to check if `children` is an array:

```javascript
const MyComponent = ({ children }) => {
  if (Array.isArray(children)) {
    return (
      <ul>
        {children.map((child) => (
          <li key={child}>{child}</li>
        ))}
      </ul>
    );
  } else {
    return children;
  }
};
```

Here is an example of how to use a spread operator to create a copy of the `children` array:

```javascript
const MyComponent = ({ children }) => {
  const childrenCopy = [...children];

  return (
    <ul>
      {childrenCopy.map((child) => (
        <li key={child}>{child}</li>
      ))}
    </ul>
  );
};
```

Here is an example of how to use a higher-order component (HOC) to encapsulate the logic for iterating over the `children` prop:

```javascript
const mapChildren = (children) => {
  if (Array.isArray(children)) {
    return (
      <ul>
        {children.map((child) => (
          <li key={child}>{child}</li>
        ))}
      </ul>
    );
  } else {
    return children;
  }
};

const MyComponent = ({ children }) => {
  return mapChildren(children);
};
```

Which method you choose to use depends on your specific needs. However, it is important to be aware of the limitations of the `children` prop and to take steps to avoid problems.

---

**How to conditionally add attributes to react components?**  
There are a few ways to conditionally add attributes to React components:

* **Using inline statements:** You can use inline statements to add attributes to React components. This is the simplest way to add attributes, but it can make your code less readable and more difficult to maintain.
* **Using if statements:** You can use if statements to conditionally add attributes to React components. This is a more flexible way to add attributes, but it can make your code more verbose.
* **Using spread syntax:** You can use spread syntax to conditionally add attributes to React components. This is a more concise and elegant way to add attributes, but it is not as widely supported as the other two methods.

**Using inline statements**

To conditionally add attributes to React components using inline statements, you can use the following syntax:

```javascript
<MyComponent {...{
  attributeName: condition ? value : undefined,
}} />
```

For example, the following code conditionally adds the `disabled` attribute to a button component:

```javascript
<button disabled={this.state.isLoading}>Click Me!</button>
```

This code will disable the button if the `isLoading` state property is set to `true`.

**Using if statements**

To conditionally add attributes to React components using if statements, you can use the following syntax:

```javascript
{condition && <MyComponent attributeName={value} />}
```

For example, the following code conditionally adds the `className` attribute to a div component:

```javascript
{this.state.isActive && <div className="active">This is active!</div>}
```

This code will add the `active` class to the div component if the `isActive` state property is set to `true`.

**Using spread syntax**

To conditionally add attributes to React components using spread syntax, you can use the following syntax:

```javascript
<MyComponent {...(condition ? { attributeName: value } : {})} />
```

For example, the following code conditionally adds the `style` attribute to a div component:

```javascript
const style = {
  backgroundColor: 'red',
};

<div {...(this.state.isActive ? { style: style } : {})} />
```

This code will add the `style` attribute to the div component if the `isActive` state property is set to `true`.

---

**Does react re-render all components and subcomponents every time setState() is called?**  
React does not re-render all components and subcomponents every time setState() is called. Instead, React maintains a
virtual DOM, which is a lightweight representation of the real DOM. When setState() is called, React updates the
virtual DOM and then compares it to the previous virtual DOM. React then only updates the real DOM with the changes
that are necessary.

This process is called reconciliation, and it is what makes React so fast and efficient.

---

**Describe how events are handled in react?**  
Events are handled in React using event handlers. Event handlers are functions that are called when a certain event
occurs, such as a click, hover, or key press. Event handlers can be defined inline or in a separate function.

To add an event handler to a React element, you use the `onClick`, `onMouseEnter`, `onKeyDown`, and other event
attributes. For example, the following code adds a click event handler to a button element:

```javascript
<button onClick={handleClick}>Click Me!</button>
```

The `handleClick()` function is the event handler function. It will be called when the button is clicked.

Event handlers can also be passed as props to React components. For example, the following code passes a click event handler to a `MyComponent` component:

```javascript
const MyComponent = ({ onClick }) => {
  // ...
};

<MyComponent onClick={handleClick} />
```

The `MyComponent` component can then use the `onClick` prop to add a click event handler to its elements.

Event handlers receive an event object as a parameter. The event object contains information about the event, such as the target element and the mouse coordinates.

To prevent the default behavior of an event, you can call the `preventDefault()` method on the event object. For example, the following code prevents the default click behavior of a button element:

```javascript
function handleClick(event) {
  event.preventDefault();

  // ...
}
```

Event handlers can also be used to propagate events up the React component tree. This is done by calling the `stopPropagation()` method on the event object. For example, the following code prevents the click event from propagating up the component tree:

```javascript
function handleClick(event) {
  event.stopPropagation();

  // ...
}
```

---

**Why would use StrictMode component in react?**  
There are a few reasons why you would use the StrictMode component in React:

* **To identify potential bugs in your code.** StrictMode enables additional development-only checks and warnings. This can help you to identify potential bugs in your code, such as impure renders and missing effect cleanup.
* **To improve the performance of your code.** StrictMode can help you to improve the performance of your code by forcing extra setup and cleanup cycles for effects. This can help to catch bugs early on and prevent them from causing performance problems in production.
* **To make your code more predictable.** StrictMode can help to make your code more predictable by ensuring that it follows certain rules, such as only rendering components once per state update.

---

**How would you use StrictMode component in react?**  
To use the StrictMode component in React, you simply need to wrap your root component with it. For example:

```javascript
import { StrictMode } from 'react';
import { createRoot } from 'react-dom/client';
const root = createRoot(document.getElementById('root'));

root.render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

Once you have wrapped your root component with StrictMode, all components in your application will be subject to the additional checks and warnings that StrictMode enables.

---

**What is the difference between useCallback and useMemo in practice?**  
`useCallback` and `useMemo` are both React hooks that can be used to improve the performance of your application. However, there are some key differences between the two.

**useCallback**

`useCallback` returns a memoized callback function. This means that the function will only be recreated if its dependencies change. This can be useful for preventing unnecessary re-renders of components.

For example, let's say you have a button component that renders a list of items. The button component has a callback function that is used to update the list of items. If you were to pass the callback function directly to the list component, the list component would re-render every time the button component re-renders.

To avoid this, you can use `useCallback` to memoize the callback function. This will ensure that the list component only re-renders when the list of items actually changes.

**useMemo**

`useMemo` returns a memoized value. This means that the value will only be recalculated if its dependencies change. This can be useful for preventing unnecessary computations from being performed.

For example, let's say you have a component that calculates a complex value. If you were to recalculate the value every time the component re-renders, this could lead to performance problems.

---

**Explain why and when to use `useMemo()`?**  
**Why to use useMemo()?**

useMemo() is a React hook that allows you to memoize expensive computations. This means that the computation will only be performed once, and the result will be cached and reused for subsequent renders. This can improve the performance of your application by reducing the number of times that expensive computations are performed.

**When to use useMemo()?**

You should use useMemo() when you need to memoize an expensive computation that is used multiple times in a component. This is especially useful for computations that are performed in the render() function, as it can prevent unnecessary re-renders.

Here are some examples of when to use useMemo():

* Calculating a complex value, such as a hash function or a checksum.
* Filtering or sorting a large array of data.
* Creating a derived state value from other state values.
* Performing a side effect, such as fetching data from an API or setting a local storage value.

**How to use useMemo()?**

To use useMemo(), you simply need to pass a callback function and an array of dependencies to the hook. The callback function will be executed only when one of the dependencies changes. The result of the callback function will be memoized and returned by the hook.

Here is an example of how to use useMemo():

```javascript
const MyComponent = () => {
  const [count, setCount] = useState(0);

  const memoizedValue = useMemo(() => {
    // Perform an expensive computation
    return Math.pow(count, 2);
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <p>Memoized value: {memoizedValue}</p>
    </div>
  );
};
```

In this example, the `memoizedValue` variable will only be updated when the `count` state variable changes. This means that the expensive computation will only be performed once, and the result will be cached and reused for subsequent renders.

---

**When to use `useCallback`, `useMemo` and `useEffect`?**  
Here is a general guideline for when to use useCallback, useMemo, and useEffect:

**useCallback:**

* When you need to memoize a callback function. This is useful for preventing unnecessary re-renders of components.
* When passing a callback function to a child component. This ensures that the child component only re-renders when the callback function itself changes.
* When using a callback function in an effect. This ensures that the effect only runs when the callback function changes.

**useMemo:**

* When you need to memoize a value. This is useful for preventing unnecessary computations from being performed.
* When calculating a complex value that is used in multiple places in a component. This prevents the value from being recalculated every time the component re-renders.
* When using a value in an effect. This ensures that the effect only runs when the value changes.

**useEffect:**

* When you need to perform a side effect. This is anything that interacts with the outside world, such as fetching data from an API or updating the DOM.
* When you need to clean up a side effect. This is important to prevent memory leaks and other performance problems.

Here are some specific examples:

**useCallback:**

* A button component that passes a callback function to its child component to update the state of the parent component.
* A component that uses a callback function in an effect to fetch data from an API.

**useMemo:**

* A component that calculates a complex value, such as a hash function or a checksum, and uses that value in multiple places.
* A component that uses a memoized value in an effect to perform a side effect, such as updating the DOM.

**useEffect:**

* A component that fetches data from an API when it mounts and updates the DOM when the data changes.
* A component that adds an event listener to the DOM when it mounts and removes the event listener when it unmounts.

---

**Can you do components inheritance in react?**  
Yes, you can do component inheritance in React. However, it is generally not recommended to do so. This is because
React uses a composition-based approach to building components. This means that you should build your components by
composing smaller, reusable components together.

---

**What is the difference between incremental DOM and virtual DOM?**  
The main difference between incremental DOM and virtual DOM is how they update the real DOM.

**Virtual DOM**

Virtual DOM is a lightweight representation of the real DOM. Whenever there is a change to the state of a component, React creates a new virtual DOM and compares it to the previous virtual DOM. React then calculates the difference between the two virtual DOMs and updates the real DOM accordingly.

This process is very efficient, as React only needs to update the parts of the real DOM that have actually changed.

**Incremental DOM**

Incremental DOM is a newer approach to updating the real DOM. Instead of creating a new virtual DOM every time there is a change, incremental DOM keeps track of the changes to the real DOM and updates it accordingly.

This approach can be even more efficient than virtual DOM, as it does not require the creation of a new virtual DOM. However, it is more complex to implement and is not as widely supported.

---

**When would you use `flushSync` in react?**  
You should use `flushSync` in React sparingly. It can be useful in some cases, but it can also hurt performance.

Here are some examples of when you might want to use `flushSync`:

* When you need to force a component to re-render immediately. This can be useful for debugging or for handling special cases.
* When you need to make sure that all updates to the DOM have been flushed before performing an action, such as taking a screenshot or printing a document.
* When you need to ensure that all updates to the state of a component have been flushed before performing a side effect, such as fetching data from an API or updating the local storage.

However, it is important to be aware of the following drawbacks of using `flushSync`:

* It can hurt performance. `flushSync` forces React to flush all pending updates synchronously. This can block other JavaScript code from running and can lead to performance problems.
* It can prevent React from batching updates. React normally batches updates to improve performance. `flushSync` prevents React from batching updates, which can lead to a decrease in performance.
* It can cause unexpected behavior. For example, if you use `flushSync` to force a component to re-render immediately, it may re-render with outdated state.

---

**When shall we use `useReducer` hook in react?**  
You should use the `useReducer` hook in React when:

* Your state is complex or consists of multiple sub-values.
* Your state update logic is complex or involves multiple steps.
* You need to share state between multiple components.
* You need to implement caching or memoization.

Here are some specific examples of when to use `useReducer`:

* Managing a shopping cart.
* Managing a complex form.
* Managing the state of a game or simulation.
* Implementing a caching system to reduce the number of API calls.
* Implementing a memoization system to prevent unnecessary re-renders.

---

**When to use useState vs. useReducer?**  
**useState** and **useReducer** are both React hooks that can be used to manage state in a component. However, there are some key differences between the two that determine when to use each one.

**useState** is the simplest way to manage state in a component. It is a good choice for simple state, such as a boolean value, a number, or a string.

**useReducer** is more powerful than useState, but it is also more complex. It is a good choice for complex state, such as an object or an array, or for state that requires complex update logic.

---

**How would you store non-state instance variables in functional component?**  
There are a few ways to store non-state instance variables in functional components in React:

* **Use useRef:** The useRef hook allows you to store a mutable value in a component without triggering a re-render. This is useful for storing values that are used by other components or that are used to perform side effects, such as fetching data from an API.

Here is an example of how to use useRef to store a non-state instance variable:

```javascript
const MyComponent = () => {
  const ref = useRef(null);

  useEffect(() => {
    // Fetch data from an API
    const fetchData = async () => {
      const response = await fetch('https://example.com/api/data');
      const data = await response.json();

      ref.current = data;
    };

    fetchData();
  }, []);

  // Use the data stored in the ref
  const data = ref.current;

  return (
    <div>
      <h1>{data.title}</h1>
    </div>
  );
};
```

In this example, the `ref` variable stores a reference to the data that is fetched from the API. The data is then used to render the component.

* **Use a context:** Contexts are a way to share state between components without having to pass props down the component tree. This can be useful for storing non-state instance variables that are needed by multiple components.

Here is an example of how to use a context to store a non-state instance variable:

```javascript
// Create a context
const MyContext = createContext(null);

// Create a provider component
const MyProvider = ({ children }) => {
  const value = {
    // Non-state instance variable
    data: {},
  };

  return (
    <MyContext.Provider value={value}>
      {children}
    </MyContext.Provider>
  );
};

// Use the context in a consumer component
const MyConsumer = () => {
  const { data } = useContext(MyContext);

  return (
    <div>
      <h1>{data.title}</h1>
    </div>
  );
};
```

In this example, the `MyContext` context stores a reference to the non-state instance variable. The `MyProvider` component provides the context to its child components. The `MyConsumer` component uses the context to access the non-state instance variable.

* **Use a global state management library:** Global state management libraries such as Redux allow you to store state in a central location and access it from anywhere in your application. This can be useful for storing non-state instance variables that are needed by multiple components throughout your application.

Here is an example of how to use Redux to store a non-state instance variable:

```javascript
// Create a Redux store
const store = createStore(reducer);

// Create a selector to access the non-state instance variable
const selectData = state => state.data;

// Use the selector in a component
const MyComponent = () => {
  const data = useSelector(selectData);

  return (
    <div>
      <h1>{data.title}</h1>
    </div>
  );
};
```

In this example, the Redux store stores the non-state instance variable. The `selectData` selector is used to access the non-state instance variable from any component in the application.

---

**What is a pure function?**  
A pure function is a function that has the following properties:

* It always returns the same output for the same input.
* It does not modify any state outside of its scope.

Pure functions are easy to reason about and test, and they can be used to build composable and predictable code.

Here is an example of a pure function:

```
function add(a, b) {
  return a + b;
}
```

This function takes two numbers as input and returns the sum of those numbers. It is a pure function because it always returns the same output for the same input and it does not modify any state outside of its scope.

---

**Explain some differences between `flux` and `angularJS(1.x)` approach?**  
Flux and AngularJS (1.x) are two different approaches to building web applications. Flux is a data flow architecture, while AngularJS (1.x) is a model-view-controller (MVC) framework.

**Flux**

Flux is a data flow architecture that is designed to make web applications more predictable and easier to test. Flux is based on the following principles:

* Unidirectional data flow: Data flows in one direction, from the dispatcher to the stores to the views. This makes it easier to reason about your code and to track down bugs.
* Single source of truth: All the application state is stored in a single place, called the store. This makes it easier to keep your application state consistent.
* Pure functions: All the functions in the application are pure, meaning that they always return the same output for the same input and they do not modify any state outside of their scope. This makes it easier to reason about your code and to test it.

**AngularJS (1.x)**

AngularJS (1.x) is a model-view-controller (MVC) framework that is designed to make web applications more scalable and maintainable. AngularJS is based on the following principles:

* Model-view-controller (MVC) architecture: The application state is stored in the model, the view is responsible for rendering the state, and the controller is responsible for handling user interactions and updating the model. This makes the application easier to scale and maintain.
* Two-way data binding: The view and the model are bound together, meaning that any changes to the model are automatically reflected in the view and any changes to the view are automatically reflected in the model. This makes the application more responsive and easier to develop.
* Dependency injection: AngularJS supports dependency injection, which makes the application easier to test and maintain.

**Differences between Flux and AngularJS (1.x)**

The following table summarizes the key differences between Flux and AngularJS (1.x):

| Feature                | Flux           | AngularJS (1.x)             |
|------------------------|----------------|-----------------------------|
| Data flow              | Unidirectional | Two-way                     |
| Single source of truth | Yes            | No                          |
| Pure functions         | Yes            | No                          |
| Architecture           | Data flow      | Model-view-controller (MVC) |
| Dependency injection   | No             | Yes                         |

---


**What is the key architectural difference between a javascript library such as react and a javascript framework such as angular?**  
The key architectural difference between a JavaScript library such as React and a JavaScript framework such as Angular is that a library provides specific functionality, while a framework provides a complete architecture for building web applications.

**JavaScript library**

A JavaScript library is a collection of code that can be used to add specific functionality to a web application. Libraries are typically lightweight and easy to use, and they can be used with a variety of different frameworks and architectures.

**JavaScript framework**

A JavaScript framework is a complete architecture for building web applications. Frameworks typically provide a set of pre-built components and features, such as routing, data binding, and dependency injection. This can make it easier to develop complex web applications, but it can also make it more difficult to customize the application.

**Key architectural difference**

The key architectural difference between a library and a framework is that a library is focused on providing functionality, while a framework is focused on providing an architecture. This means that libraries are typically more flexible and easier to customize, while frameworks are typically more opinionated and provide a more complete solution.

---

**How to avoid a need for binding in react?**  
There are two ways to avoid the need for binding in React:

**1. Use arrow functions**

Arrow functions are a type of function expression that was introduced in ES6. Arrow functions do not have their own `this` context, so they bind the `this` context of the surrounding scope.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.handleClick = () => {
      // ...
    };
  }

  render() {
    return (
      <button onClick={this.handleClick}>Click Me</button>
    );
  }
}
```

**2. Use class properties**

Class properties are a new feature of JavaScript that was introduced in ES2020. Class properties allow you to define fields and methods on a class without having to use the constructor.

To avoid binding the `handleClick()` function, we can use a class property:

```javascript
class MyComponent extends React.Component {
  handleClick = () => {
    // ...
  };

  render() {
    return (
      <button onClick={this.handleClick}>Click Me</button>
    );
  }
}
```

---

**How does react render method work exactly when we call setState?**  
When you call `setState()` in React, the following steps occur:

1. React merges the new state with the current state.
2. React creates a new virtual DOM.
3. React compares the new virtual DOM to the previous virtual DOM.
4. React updates the real DOM to match the new virtual DOM.

**Merging the state**

When React merges the new state with the current state, it replaces the values of any existing properties in the current state with the values of the corresponding properties in the new state. Any properties that do not exist in the new state will remain unchanged.

**Creating a new virtual DOM**

React creates a new virtual DOM every time you call `setState()`. The virtual DOM is a lightweight representation of the real DOM. It is a tree of objects that represents the elements and their attributes.

**Comparing the virtual DOMs**

React compares the new virtual DOM to the previous virtual DOM to determine which parts of the real DOM need to be updated. React uses a diffing algorithm to efficiently compare the two virtual DOMs.

**Updating the real DOM**

React updates the real DOM to match the new virtual DOM. React only updates the parts of the real DOM that have changed.

---

**How to useReact.memo?**  
React.memo is a higher-order component (HOC) that can be used to memoize a React component. This means that React will only re-render the component if its props have changed. This can improve the performance of your application by reducing the number of re-renders.

To use React.memo, you simply wrap your component in it:

```javascript
import React from "react";

const MyComponent = () => {
  // ...
};

const MemoizedComponent = React.memo(MyComponent);
```

React will now only re-render the `MemoizedComponent` if its props have changed.

---

**Can a custom react hook return jsx?**  
Yes, a custom React hook can return JSX. However, it is not recommended to do so.

Here are a few reasons why:

* It can make your hooks less reusable. If a hook returns JSX, it can only be used in components that have the same JSX structure.
* It can make your hooks more complex. Returning JSX from a hook can add unnecessary complexity to your code.
* It can make your hooks less testable. It is more difficult to test hooks that return JSX than hooks that do not.

---

**What is the order of `useInsertionEffect`, `useEffect` and `useLayoutEffect` hooks at component generation?**  
The order of execution of the `useInsertionEffect`, `useEffect`, and `useLayoutEffect` hooks is as follows:

1. `useInsertionEffect`
2. `useLayoutEffect`
3. `useEffect`

This means that the `useInsertionEffect` hook will always be executed first, followed by the `useLayoutEffect` hook, and then the `useEffect` hook.

This order is important because it allows you to control the order in which certain side effects are executed. For example, if you need to insert a new element into the DOM before doing a layout update, you would use the `useInsertionEffect` hook.

---

**Explain compound component pattern in react?**  
The compound component pattern in React is a way to create reusable components that encapsulate shared state and logic. This pattern is useful for building complex components that are made up of smaller, simpler components.

A compound component is a component that contains other components. It manages the state and logic of the other components, and it exposes a simplified API to the parent component.

The compound component pattern can be used to:

* Reduce boilerplate code.
* Improve code readability and maintainability.
* Make it easier to share components between different parts of an application.
* Improve the performance of applications by reducing the number of re-renders.

---

**What is react portals?**  
React portals are a way to render React components outside of the DOM hierarchy of their parent component. This can be useful for things like modals, tooltips, and dropdowns.

To create a portal, you need to use the `ReactDOM.createPortal()` method. This method takes two arguments: the component to render and the DOM element to render it into. The DOM element can be any valid DOM element, but it is typically a container element such as a `div` or a `body`.

Here is an example of how to create a portal:

```javascript
import ReactDOM from 'react-dom';

const Modal = () => {
  return (
    <div>
      <h1>This is a modal</h1>
    </div>
  );
};

const MyComponent = () => {
  const [showModal, setShowModal] = useState(false);

  return (
    <div>
      <button onClick={() => setShowModal(true)}>Open Modal</button>
      {showModal && ReactDOM.createPortal(<Modal />, document.body)}
    </div>
  );
};
```

In this example, the `MyComponent` component has a button that opens a modal when clicked. The modal is rendered using a portal, so it appears outside of the normal DOM hierarchy.

Portals can be useful for a variety of purposes. For example, you can use portals to:

* Render components outside of the overflow of their parent component.
* Render components in a different z-index than their parent component.
* Render components in a different part of the DOM than their parent component.

Here are some examples of how portals can be used:

* Modals: Portals can be used to render modals outside of the overflow of their parent component. This ensures that the modal is always visible, even if the parent component is hidden.
* Tooltips: Portals can be used to render tooltips outside of the overflow of their parent component. This ensures that the tooltip is always visible, even if the parent component is hidden.
* Dropdowns: Portals can be used to render dropdowns outside of the overflow of their parent component. This ensures that the dropdown is always visible, even if the parent component is hidden.
* Menus: Portals can be used to render menus outside of the overflow of their parent component. This ensures that the menu is always visible, even if the parent component is hidden.

Portals are a powerful tool that can be used to create more flexible and user-friendly React applications.

---

**Provide an example of any simple custom react hook. Why do we need custom hooks?**  
Here is an example of a simple custom React hook:

```javascript
import { useState } from 'react';

export const useToggle = (initialValue = false) => {
  const [isOn, setIsOn] = useState(initialValue);

  const toggle = () => {
    setIsOn(!isOn);
  };

  return [isOn, toggle];
};
```

This hook provides a simple way to toggle a boolean value. It takes an initial value as a prop, and it returns an array with two values: the current state of the boolean value and a function to toggle it.

To use the hook, you would simply import it into your component and then call it:

```javascript
import { useToggle } from './useToggle';

const MyComponent = () => {
  const [isOn, toggle] = useToggle();

  return (
    <button onClick={toggle}>{isOn ? 'Turn off' : 'Turn on'}</button>
  );
};
```

When you click the button, the `toggle` function will be called, which will toggle the state of the boolean value. The button will then be re-rendered with the updated state.

We need custom hooks because they allow us to encapsulate common state and logic into reusable components. This can make our code more readable, maintainable, and reusable.

---

**How to mitigate multiple component re-renders when using multiple `useState` calls?**  
There are a few ways to mitigate multiple component re-renders when using multiple useState calls:

1. **Use a single useState call for related state:** If you have multiple state variables that are related to each other, you can consider using a single useState call for all of them. This will reduce the number of re-renders that occur when any of the state variables change.

For example, instead of using two separate useState calls for the `firstName` and `lastName` state variables, you could use a single useState call for an object that contains both of those state variables:

```javascript
const [user, setUser] = useState({
  firstName: '',
  lastName: '',
});
```

Then, you could access the `firstName` and `lastName` state variables through the `user` object:

```javascript
const firstName = user.firstName;
const lastName = user.lastName;
```

2. **Use a memoization hook:** You can also use a memoization hook to prevent unnecessary component re-renders. Memoization hooks allow you to cache the results of expensive computations and only re-render the component if the inputs to the computation change.

For example, if you have a component that renders a list of items, and the list of items is generated from a complex computation, you could use a memoization hook to cache the results of the computation and only re-render the component if the list of items changes.

3. **Use a state management library:** If you have a complex application with a lot of state, you may want to consider using a state management library such as Redux or MobX. State management libraries provide a centralized way to manage the state of your application, which can help to reduce the number of re-renders that occur.

---

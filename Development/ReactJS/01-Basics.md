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
</div>

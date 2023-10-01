# ReactJS Interview Questions

<div style="text-align: justify">

## React Advanced:

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
</div>

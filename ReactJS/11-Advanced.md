# ReactJS Interview Questions

<div style="text-align: justify">

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

**What is the recommended approach of removing an array element in react state?**  
The recommended approach is to use *filter()* method. This allows you to create a new array that contains all the
elements of original array except the one you want to remove. This a safer and more efficient approach than using the
*splice()* method, which mutates the original array and can cause unexpected side effects.

**How do you memoize a component?**  
To memoize a component in React, you can use the *React.memo* higher-order component. This will prevent the component
from re-rendering if the props have not changed. You can also use the *shouldComponentUpdate* lifecycle method or the
*React.useMemo* hook to achieve similar results.

**How do you implement server side rendering or SSR?**  
To implement server side rendering in React, you can use the *ReactDOMServer* module. This module provides a method
called *renderToString* that allows you to render a component to HTML on the server. You can then send this HTML to the
client, where it can be hydrated into a full React application.

**What is the purpose of getDerivedStateFromProps() lifecycle method?**  
This lifecycle method in React is used to update the state based on changes to props. This method is called every time
the component is updated and can return a new state object. It is commonly used to synchronize the state with the props
in response to user input or server-side changes.

**Why ReactDOM is separated from React?**  
ReactDOM is separated from React in order to improve performance and reduce the bundle size of React applications.
Separating the rendering logic from the component logic allows for more efficient updates and reduces the amount of
javascript that needs to be downloaded by the client. This separation also allows for easier integration with other
rendering targets such as native mobile apps or desktop applications.

**What is the difference between setState and replaceState methods?**  
The *retState* method is used to update component state, and it merges the new state with the old one. The
*replaceState* is similar, but it overwrites the old state completely with the new state. However, *replaceState* is
deprecated in React and should not be used. Instead, you should use the *setState* method to update state in a React
component.

**How to pretty print JSON with React?**  
You can use *JSON.stringify()* method with a null value for the *replacer* parameter and a number value for the *space*
parameter. This will format the JSON data with indentation and line breaks for readability.

**What is strict mode in React?**  
It is a mode that highlights potential problems in the code, such as deprecated lifecycle methods or unsafe practices.
It can help to identify issues early on and improve the overall quality of the code. Strict mode can be enabled
globally or for individual components.

**How do you use decorators in React?**  
Decorators in React can be used as class decorators to add a functionality to a component class. For example, you can
use a decorator to add additional lifecycle methods or state to a component. Decorators can be written as higher-order
components(HOCs) or as regular functions.

**Why is isMounted() an antipattern and what is the proper solution?**  
The *isMounted()* method in React is considered an antipattern because it can lead to race conditions and bugs. This
method checks if the component is mounted in the DOM, but it can return a false positive if it is called during the
unmounting phase. The proper solution is to use the *componentDidMount* and *componentWillUnmount* lifecycle methods
to manage component state and cleanup.

**What are the Pointer Events supported in React?**  
React supports both mouse and touch events through the use of Pointer Events. Pointer Events are the standardized event
model that provide a unified way to handle mouse, touch and stylus input. React provides a set of event handlers for
Pointer Events, such as *onPointerDown* and *onPointerMove* that can be used to create responsive and touch-friendly
user interfaces.
</div>

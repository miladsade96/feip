# ReactJS Interview Questions

<div style="text-align: justify">

## React Advanced Concepts:

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
</div>

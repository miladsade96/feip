# ReactJS Interview Questions

<div style="text-align: justify">

## React Events:

**What are synthetic events in React?**  
They are events that are cross-browser compatible and behave consistently across different platforms. They are also
optimized for performance by pooling event objects, which allows them to be reused and prevents excessive memory
allocation. Synthetic event have the same interface as native events, but they are implemented differently behind
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

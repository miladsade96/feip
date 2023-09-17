# ReactJS Interview Questions

<div style="text-align: justify">

## React Refs:

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
</div>

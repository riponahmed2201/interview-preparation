# 📘 React.js Interview Questions & Answers

## Table of Contents

1. [Basic React Concepts (1-25)](#basic-react-concepts-1-25)
2. [Components and Props (26-40)](#components-and-props-26-40)
3. [State and Lifecycle (41-55)](#state-and-lifecycle-41-55)
4. [Hooks (56-70)](#hooks-56-70)
5. [Event Handling and Forms (71-80)](#event-handling-and-forms-71-80)
6. [Advanced Topics (81-90)](#advanced-topics-81-90)
7. [Performance and Best Practices (91-100)](#performance-and-best-practices-91-100)

---

## Basic React Concepts (1-25)

### 1. What is React?

**Answer:** React is a JavaScript library for building user interfaces, particularly web applications. It was developed by Facebook and focuses on creating reusable UI components. React uses a virtual DOM to efficiently update the user interface and follows a component-based architecture.

### 2. What are the key features of React?

**Answer:**

- **Virtual DOM**: Efficient rendering through virtual representation
- **Component-Based**: Reusable UI components
- **Unidirectional Data Flow**: Data flows down from parent to child
- **JSX**: JavaScript syntax extension
- **Declarative**: Describe what the UI should look like
- **Learn Once, Write Anywhere**: Can be used for web, mobile, and desktop

### 3. What is JSX?

**Answer:** JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code within JavaScript. It gets transpiled to regular JavaScript function calls.

```jsx
// JSX
const element = <h1>Hello, World!</h1>;

// Transpiled JavaScript
const element = React.createElement("h1", null, "Hello, World!");
```

### 4. What is the Virtual DOM?

**Answer:** The Virtual DOM is a JavaScript representation of the real DOM. React creates a virtual copy of the DOM in memory, compares it with the previous version when state changes occur, and updates only the parts that have changed in the real DOM.

### 5. What are the advantages of React?

**Answer:**

- Fast rendering with Virtual DOM
- Reusable components
- Strong community support
- SEO-friendly with server-side rendering
- Easy testing
- Backward compatibility
- Large ecosystem

### 6. What is the difference between React and ReactDOM?

**Answer:**

- **React**: Core library containing component logic, state management, and lifecycle methods
- **ReactDOM**: Platform-specific library for rendering React components to the DOM in web browsers

### 7. What is a React Element?

**Answer:** A React element is a plain JavaScript object that describes what should appear on screen. It's the smallest building block of React applications.

```jsx
const element = <div>Hello World</div>;
```

### 8. What is the difference between Element and Component?

**Answer:**

- **Element**: Immutable plain object describing component instance or DOM node
- **Component**: Function or class that returns elements and can accept props

### 9. What is ReactDOM.render()?

**Answer:** ReactDOM.render() is the method used to render React elements into the DOM. It takes a React element and a DOM container.

```jsx
ReactDOM.render(<App />, document.getElementById("root"));
```

### 10. What are the limitations of React?

**Answer:**

- High pace of development
- Poor documentation due to rapid changes
- JSX learning curve
- Only covers UI layer
- Requires additional libraries for complete solution

### 11. What is Create React App?

**Answer:** Create React App is a tool that sets up a modern React development environment with no configuration needed. It provides a development server, build scripts, and testing setup.

```bash
npx create-react-app my-app
cd my-app
npm start
```

### 12. What is the significance of keys in React?

**Answer:** Keys help React identify which items have changed, been added, or removed. They should be stable, predictable, and unique among siblings.

```jsx
const items = ["apple", "banana", "orange"];
const listItems = items.map((item) => <li key={item}>{item}</li>);
```

### 13. What is the difference between HTML and React event handling?

**Answer:**

- React events are SyntheticEvents (cross-browser wrapper)
- Event handlers receive SyntheticEvent objects
- React uses camelCase for event names
- Cannot return false to prevent default behavior (must use preventDefault)

### 14. What are Synthetic Events?

**Answer:** Synthetic Events are React's wrapper around native events. They provide consistent API across different browsers and include all standard event properties and methods.

```jsx
function Button() {
  const handleClick = (e) => {
    e.preventDefault(); // e is a SyntheticEvent
    console.log("Button clicked");
  };

  return <button onClick={handleClick}>Click me</button>;
}
```

### 15. What is the difference between controlled and uncontrolled components?

**Answer:**

- **Controlled**: Form data handled by React state
- **Uncontrolled**: Form data handled by DOM itself

```jsx
// Controlled
const [value, setValue] = useState('');
<input value={value} onChange={e => setValue(e.target.value)} />

// Uncontrolled
<input ref={inputRef} />
```

### 16. What are refs in React?

**Answer:** Refs provide a way to access DOM nodes or React elements created in the render method directly.

```jsx
const inputRef = useRef(null);

const focusInput = () => {
  inputRef.current.focus();
};

return <input ref={inputRef} />;
```

### 17. What is the difference between React.Component and React.PureComponent?

**Answer:** PureComponent implements shouldComponentUpdate with shallow prop and state comparison, while Component doesn't perform any comparison by default.

### 18. What is the render() method?

**Answer:** The render() method is required in class components and returns the JSX that represents the component's UI. It should be pure and not modify component state.

### 19. What are fragments in React?

**Answer:** Fragments let you group multiple elements without adding extra nodes to the DOM.

```jsx
return (
  <React.Fragment>
    <h1>Title</h1>
    <p>Description</p>
  </React.Fragment>
);

// Or using short syntax
return (
  <>
    <h1>Title</h1>
    <p>Description</p>
  </>
);
```

### 20. What is the significance of React Fiber?

**Answer:** React Fiber is a reimplementation of React's core algorithm. It enables incremental rendering, allowing React to split work into chunks and prioritize updates based on their importance.

### 21. What are the lifecycle methods in React?

**Answer:** Lifecycle methods are hooks that allow you to run code at specific times in a component's life:

- **Mounting**: constructor, componentDidMount
- **Updating**: componentDidUpdate, shouldComponentUpdate
- **Unmounting**: componentWillUnmount
- **Error Handling**: componentDidCatch

### 22. What is strict mode in React?

**Answer:** StrictMode is a tool for highlighting potential problems in an application. It activates additional checks and warnings for its descendants.

```jsx
<React.StrictMode>
  <App />
</React.StrictMode>
```

### 23. What are portals in React?

**Answer:** Portals provide a way to render children into a DOM node that exists outside the parent component's DOM hierarchy.

```jsx
return ReactDOM.createPortal(
  <div>Modal content</div>,
  document.getElementById("modal-root")
);
```

### 24. What is the children prop?

**Answer:** The children prop allows you to pass components as data to other components, enabling component composition.

```jsx
function Wrapper({ children }) {
  return <div className="wrapper">{children}</div>;
}

<Wrapper>
  <h1>Title</h1>
  <p>Content</p>
</Wrapper>;
```

### 25. What is reconciliation in React?

**Answer:** Reconciliation is the process React uses to diff one tree with another to determine what needs to be changed in the UI. React uses a diffing algorithm to minimize the number of changes needed.

---

## Components and Props (26-40)

### 26. What is a functional component?

**Answer:** A functional component is a JavaScript function that returns JSX. It's the simplest way to define a component.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Arrow function syntax
const Welcome = (props) => <h1>Hello, {props.name}!</h1>;
```

### 27. What is a class component?

**Answer:** A class component is an ES6 class that extends React.Component and has a render method that returns JSX.

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

### 28. When would you use a class component over a functional component?

**Answer:** With the introduction of Hooks, functional components can do everything class components can. Class components are mainly used for legacy code or when you prefer the class syntax.

### 29. What are props?

**Answer:** Props (properties) are read-only attributes passed from parent to child components. They allow data to be passed down the component tree.

```jsx
function Child({ name, age }) {
  return (
    <p>
      {name} is {age} years old
    </p>
  );
}

function Parent() {
  return <Child name="John" age={25} />;
}
```

### 30. How do you pass data from child to parent component?

**Answer:** Pass a callback function as a prop from parent to child, then call that function in the child component.

```jsx
function Parent() {
  const [message, setMessage] = useState("");

  const handleMessage = (msg) => setMessage(msg);

  return <Child onMessage={handleMessage} />;
}

function Child({ onMessage }) {
  return <button onClick={() => onMessage("Hello!")}>Send Message</button>;
}
```

### 31. What is prop drilling?

**Answer:** Prop drilling is the process of passing data from a parent component down to deeply nested child components through multiple intermediate components that don't need the data.

### 32. What are default props?

**Answer:** Default props allow you to set default values for props in case they are not provided by the parent component.

```jsx
function Button({ type = "button", children }) {
  return <button type={type}>{children}</button>;
}

// Or in class components
Button.defaultProps = {
  type: "button",
};
```

### 33. What is prop validation in React?

**Answer:** Prop validation helps catch bugs by validating the props passed to components. React has a built-in PropTypes library for this.

```jsx
import PropTypes from "prop-types";

function Button({ onClick, children }) {
  return <button onClick={onClick}>{children}</button>;
}

Button.propTypes = {
  onClick: PropTypes.func.isRequired,
  children: PropTypes.node,
};
```

### 34. What are higher-order components (HOC)?

**Answer:** A higher-order component is a function that takes a component and returns a new component with additional functionality.

```jsx
function withLoading(WrappedComponent) {
  return function WithLoadingComponent({ isLoading, ...props }) {
    if (isLoading) return <div>Loading...</div>;
    return <WrappedComponent {...props} />;
  };
}

const ButtonWithLoading = withLoading(Button);
```

### 35. What are the advantages of using arrow functions in React?

**Answer:**

- Lexical this binding (no need to bind in constructor)
- Cleaner syntax
- Implicit return for simple functions
- No hoisting issues

### 36. How do you conditionally render components?

**Answer:** You can use JavaScript expressions, ternary operators, or logical && operator for conditional rendering.

```jsx
function App({ isLoggedIn, user }) {
  return (
    <div>
      {isLoggedIn ? <Welcome user={user} /> : <Login />}
      {isLoggedIn && <Dashboard />}
    </div>
  );
}
```

### 37. What is component composition?

**Answer:** Component composition is a pattern where you combine simple components to build more complex ones, promoting reusability and maintainability.

```jsx
function Card({ header, children, footer }) {
  return (
    <div className="card">
      {header && <div className="header">{header}</div>}
      <div className="content">{children}</div>
      {footer && <div className="footer">{footer}</div>}
    </div>
  );
}
```

### 38. What is the difference between presentational and container components?

**Answer:**

- **Presentational**: Focus on how things look, receive data via props, stateless
- **Container**: Focus on how things work, manage state, connect to data sources

### 39. What are render props?

**Answer:** Render props is a technique for sharing code between components using a prop whose value is a function that returns React elements.

```jsx
function DataProvider({ render }) {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetchData().then(setData);
  }, []);

  return render(data);
}

<DataProvider render={(data) => <div>{data}</div>} />;
```

### 40. What is component lazy loading?

**Answer:** Lazy loading allows you to load components only when they're needed, improving initial load performance.

```jsx
const LazyComponent = React.lazy(() => import("./LazyComponent"));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

---

## State and Lifecycle (41-55)

### 41. What is state in React?

**Answer:** State is a JavaScript object that holds data that may change over the lifetime of a component. When state changes, the component re-renders.

```jsx
const [count, setCount] = useState(0);
```

### 42. What is the difference between state and props?

**Answer:**

- **Props**: Read-only, passed from parent, immutable
- **State**: Mutable, managed within component, can be changed with setState

### 43. How do you update state in React?

**Answer:** In functional components, use the state setter function. In class components, use setState().

```jsx
// Functional component
const [count, setCount] = useState(0);
setCount(count + 1);

// Class component
this.setState({ count: this.state.count + 1 });
```

### 44. What are the rules of using setState?

**Answer:**

- Never modify state directly
- State updates may be asynchronous
- State updates are merged in class components
- Use functional updates when new state depends on previous state

```jsx
// Correct
setCount((prevCount) => prevCount + 1);

// Incorrect
count = count + 1;
```

### 45. What is the useState Hook?

**Answer:** useState is a Hook that allows you to add state to functional components. It returns an array with the current state and a setter function.

```jsx
const [name, setName] = useState("");
const [age, setAge] = useState(0);
const [user, setUser] = useState({ name: "", age: 0 });
```

### 46. What is the useEffect Hook?

**Answer:** useEffect lets you perform side effects in functional components. It combines componentDidMount, componentDidUpdate, and componentWillUnmount.

```jsx
useEffect(() => {
  // Side effect
  document.title = `Count: ${count}`;

  // Cleanup (optional)
  return () => {
    document.title = "React App";
  };
}, [count]); // Dependency array
```

### 47. What is the dependency array in useEffect?

**Answer:** The dependency array tells React when to re-run the effect. If any value in the array changes, the effect runs again.

```jsx
useEffect(() => {
  fetchData();
}, []); // Empty array: run once on mount

useEffect(() => {
  updateTitle();
}, [count]); // Run when count changes

useEffect(() => {
  logActivity();
}); // No array: run after every render
```

### 48. What is componentDidMount?

**Answer:** componentDidMount is a lifecycle method in class components that runs after the component is mounted to the DOM. It's commonly used for API calls and subscriptions.

```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    this.fetchData();
  }

  fetchData() {
    // API call
  }
}
```

### 49. What is componentDidUpdate?

**Answer:** componentDidUpdate is called after the component updates. It receives previous props and state as arguments.

```jsx
componentDidUpdate(prevProps, prevState) {
  if (this.props.userId !== prevProps.userId) {
    this.fetchUserData();
  }
}
```

### 50. What is componentWillUnmount?

**Answer:** componentWillUnmount is called just before a component is unmounted and destroyed. It's used for cleanup like removing event listeners or canceling API calls.

```jsx
componentWillUnmount() {
  clearInterval(this.timer);
  document.removeEventListener('click', this.handleClick);
}
```

### 51. What is shouldComponentUpdate?

**Answer:** shouldComponentUpdate determines whether a component should re-render based on new props and state. It returns a boolean.

```jsx
shouldComponentUpdate(nextProps, nextState) {
  return nextProps.id !== this.props.id;
}
```

### 52. What is the component lifecycle?

**Answer:** The component lifecycle consists of three phases:

1. **Mounting**: Component is created and inserted into DOM
2. **Updating**: Component is re-rendered due to changes in props or state
3. **Unmounting**: Component is removed from DOM

### 53. How do you force a component to re-render?

**Answer:** In class components, use forceUpdate(). In functional components, update state even with the same value.

```jsx
// Class component
this.forceUpdate();

// Functional component
const [, forceUpdate] = useReducer((x) => x + 1, 0);
forceUpdate(); // Force re-render
```

### 54. What is batching in React?

**Answer:** Batching is when React groups multiple state updates into a single re-render for better performance. React automatically batches updates in event handlers.

```jsx
function handleClick() {
  setCount(count + 1);
  setFlag(!flag);
  // Only one re-render happens
}
```

### 55. What is the difference between shallow and deep comparison?

**Answer:**

- **Shallow**: Compares object references and primitive values
- **Deep**: Recursively compares all nested values

React's default comparison is shallow, which is why you should avoid mutating objects and arrays directly.

---

## Hooks (56-70)

### 56. What are React Hooks?

**Answer:** Hooks are functions that let you use state and other React features in functional components. They start with "use" and follow specific rules.

### 57. What are the rules of Hooks?

**Answer:**

1. Only call Hooks at the top level (not in loops, conditions, or nested functions)
2. Only call Hooks from React functions (components or custom Hooks)

### 58. What is useReducer?

**Answer:** useReducer is an alternative to useState for managing complex state logic. It accepts a reducer function and initial state.

```jsx
const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

const [state, dispatch] = useReducer(reducer, initialState);
```

### 59. What is useContext?

**Answer:** useContext allows you to consume context values without wrapping components in Context.Consumer.

```jsx
const ThemeContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemedButton />
    </ThemeContext.Provider>
  );
}

function ThemedButton() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Button</button>;
}
```

### 60. What is useMemo?

**Answer:** useMemo memoizes expensive calculations and only recalculates when dependencies change.

```jsx
const expensiveValue = useMemo(() => {
  return computeExpensiveValue(a, b);
}, [a, b]);
```

### 61. What is useCallback?

**Answer:** useCallback memoizes functions to prevent unnecessary re-renders of child components that depend on function props.

```jsx
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

### 62. What is the difference between useMemo and useCallback?

**Answer:**

- **useMemo**: Memoizes the result of a function
- **useCallback**: Memoizes the function itself

```jsx
const memoizedValue = useMemo(() => computeValue(a, b), [a, b]);
const memoizedCallback = useCallback(() => doSomething(a, b), [a, b]);
```

### 63. What is useRef?

**Answer:** useRef returns a mutable ref object that persists across renders. It's commonly used to access DOM elements or store mutable values.

```jsx
const inputRef = useRef(null);
const countRef = useRef(0);

useEffect(() => {
  inputRef.current.focus();
  countRef.current += 1;
});
```

### 64. What is useLayoutEffect?

**Answer:** useLayoutEffect runs synchronously after all DOM mutations but before the browser paints. It's useful for measuring DOM elements.

```jsx
useLayoutEffect(() => {
  const rect = divRef.current.getBoundingClientRect();
  setHeight(rect.height);
}, []);
```

### 65. What is useImperativeHandle?

**Answer:** useImperativeHandle customizes the instance value exposed when using ref with forwardRef.

```jsx
const FancyInput = forwardRef((props, ref) => {
  const inputRef = useRef();

  useImperativeHandle(ref, () => ({
    focus: () => inputRef.current.focus(),
  }));

  return <input ref={inputRef} />;
});
```

### 66. What are custom Hooks?

**Answer:** Custom Hooks are JavaScript functions that start with "use" and can call other Hooks. They allow you to extract and reuse stateful logic.

```jsx
function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return { count, increment, decrement };
}
```

### 67. What is useDebugValue?

**Answer:** useDebugValue displays a label for custom Hooks in React DevTools.

```jsx
function useCounter(initialValue) {
  const [count, setCount] = useState(initialValue);

  useDebugValue(count > 0 ? "Positive" : "Zero or Negative");

  return [count, setCount];
}
```

### 68. Can you use Hooks conditionally?

**Answer:** No, Hooks must always be called in the same order on every render. You cannot call them inside loops, conditions, or nested functions.

```jsx
// Wrong
if (condition) {
  const [state, setState] = useState(initialState);
}

// Correct
const [state, setState] = useState(initialState);
if (condition) {
  // Use state here
}
```

### 69. What is the difference between useEffect and useLayoutEffect?

**Answer:**

- **useEffect**: Runs asynchronously after render, doesn't block painting
- **useLayoutEffect**: Runs synchronously before painting, can cause performance issues

### 70. How do you migrate from class components to Hooks?

**Answer:**

- Replace useState for this.state
- Replace useEffect for lifecycle methods
- Move instance methods to functions or custom Hooks
- Remove constructor and binding

---

## Event Handling and Forms (71-80)

### 71. How do you handle events in React?

**Answer:** React uses SyntheticEvents and camelCase event names. Event handlers receive the event object as an argument.

```jsx
function Button() {
  const handleClick = (event) => {
    event.preventDefault();
    console.log("Clicked!");
  };

  return <button onClick={handleClick}>Click me</button>;
}
```

### 72. What is event delegation in React?

**Answer:** React uses event delegation by attaching a single event listener to the root element and managing all events from there. This improves performance and memory usage.

### 73. How do you handle form submission in React?

**Answer:** Handle the form's onSubmit event and prevent the default browser behavior.

```jsx
function LoginForm() {
  const [email, setEmail] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Submitted:", email);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

### 74. What are controlled components?

**Answer:** Controlled components are form elements whose value is controlled by React state. The input value is always driven by React state.

```jsx
const [name, setName] = useState("");

<input value={name} onChange={(e) => setName(e.target.value)} />;
```

### 75. What are uncontrolled components?

**Answer:** Uncontrolled components manage their own state internally and use refs to access their values.

```jsx
const nameRef = useRef();

const handleSubmit = () => {
  console.log(nameRef.current.value);
};

<input ref={nameRef} defaultValue="Initial" />;
```

### 76. How do you handle multiple inputs in a form?

**Answer:** Use a single state object and update based on the input's name attribute.

```jsx
const [formData, setFormData] = useState({
  name: '',
  email: ''
});

const handleChange = (e) => {
  setFormData({
    ...formData,
    [e.target.name]: e.target.value
  });
};

<input name="name" onChange={handleChange} />
<input name="email" onChange={handleChange} />
```

### 77. How do you validate forms in React?

**Answer:** You can validate forms using controlled components, custom validation functions, or libraries like Formik or Yup.

```jsx
const [errors, setErrors] = useState({});

const validate = (values) => {
  const errors = {};
  if (!values.email) errors.email = "Email is required";
  if (!values.name) errors.name = "Name is required";
  return errors;
};

const handleSubmit = (e) => {
  e.preventDefault();
  const validationErrors = validate(formData);
  if (Object.keys(validationErrors).length === 0) {
    // Submit form
  } else {
    setErrors(validationErrors);
  }
};
```

### 78. What is the difference between onChange and onInput?

**Answer:** In React, onChange fires when the value changes and is the standard way to handle input changes. onInput is less commonly used and behaves similarly to onChange in React.

### 79. How do you handle file uploads in React?

**Answer:** Use an input with type="file" and access files through the event object.

```jsx
const [file, setFile] = useState(null);

const handleFileChange = (e) => {
  setFile(e.target.files[0]);
};

<input type="file" onChange={handleFileChange} />;
```

### 80. How do you prevent default behavior in React events?

**Answer:** Call preventDefault() on the event object.

```jsx
const handleSubmit = (e) => {
  e.preventDefault(); // Prevents form submission
  // Handle form logic
};
```

---

## Advanced Topics (81-90)

### 81. What is React Context?

**Answer:** React Context provides a way to share values between components without passing props through every level of the tree.

```jsx
const ThemeContext = createContext("light");

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  return <ThemedButton />;
}

function ThemedButton() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Button</button>;
}
```

### 82. What is Redux and how does it work with React?

**Answer:** Redux is a predictable state container for JavaScript apps. It works with React through the react-redux library, providing global state management.

```jsx
// Store
const store = createStore(reducer);

// Provider
<Provider store={store}>
  <App />
</Provider>;

// Component
const count = useSelector((state) => state.count);
const dispatch = useDispatch();
```

### 83. What is React Router?

**Answer:** React Router is a library for handling client-side routing in React applications. It enables navigation between different components/pages.

```jsx
import { BrowserRouter, Route, Routes } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

### 84. What is code splitting in React?

**Answer:** Code splitting allows you to split your code into smaller chunks and load them on demand, improving performance.

```jsx
const LazyComponent = lazy(() => import("./LazyComponent"));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

### 85. What is server-side rendering (SSR)?

**Answer:** SSR renders React components on the server and sends HTML to the client. It improves SEO and initial load performance.

```jsx
// Server
import { renderToString } from "react-dom/server";
const html = renderToString(<App />);

// Client
import { hydrate } from "react-dom";
hydrate(<App />, document.getElementById("root"));
```

### 86. What is React.memo?

**Answer:** React.memo is a higher-order component that memoizes the result and only re-renders if props change.

```jsx
const MyComponent = React.memo(function MyComponent({ name }) {
  return <div>{name}</div>;
});

// With custom comparison
const MyComponent = React.memo(
  function MyComponent(props) {
    return <div>{props.name}</div>;
  },
  (prevProps, nextProps) => {
    return prevProps.name === nextProps.name;
  }
);
```

### 87. What are Error Boundaries?

**Answer:** Error Boundaries are React components that catch JavaScript errors anywhere in their child component tree and display fallback UI.

```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, errorInfo) {
    console.log("Error:", error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}
```

### 88. What is Suspense in React?

**Answer:** Suspense lets components wait for something before rendering, typically used with lazy loading and data fetching.

```jsx
<Suspense fallback={<Loading />}>
  <LazyComponent />
</Suspense>
```

### 89. What is the difference between client-side and server-side rendering?

**Answer:**

- **Client-side Rendering (CSR)**: JavaScript runs in browser, renders components after download
- **Server-side Rendering (SSR)**: HTML is generated on server, sent to browser ready to display

**CSR Pros**: Rich interactions, reduced server load
**SSR Pros**: Better SEO, faster initial load, works without JavaScript

### 90. What are React DevTools?

**Answer:** React DevTools is a browser extension that allows you to inspect React component hierarchy, view props and state, and debug React applications.

Features:

- Component tree inspection
- Props and state viewing
- Performance profiling
- Hook debugging

---

## Performance and Best Practices (91-100)

### 91. How do you optimize React application performance?

**Answer:** Several strategies can optimize React performance:

```jsx
// 1. Use React.memo for component memoization
const ExpensiveComponent = React.memo(({ data }) => {
  return <div>{/* expensive render */}</div>;
});

// 2. Use useMemo for expensive calculations
const expensiveValue = useMemo(() => {
  return heavyComputation(data);
}, [data]);

// 3. Use useCallback for stable function references
const handleClick = useCallback(() => {
  onClick(id);
}, [onClick, id]);

// 4. Code splitting with lazy loading
const LazyComponent = lazy(() => import("./Heavy"));
```

### 92. What is the React Profiler?

**Answer:** The React Profiler measures how often a React app renders and what the cost of rendering is. It helps identify performance bottlenecks.

```jsx
import { Profiler } from "react";

function onRenderCallback(id, phase, actualDuration) {
  console.log("Component:", id, "Phase:", phase, "Duration:", actualDuration);
}

<Profiler id="App" onRender={onRenderCallback}>
  <App />
</Profiler>;
```

### 93. What are the best practices for React development?

**Answer:**

1. **Component Organization**: Keep components small and focused
2. **State Management**: Use local state when possible, global state when necessary
3. **Props**: Use PropTypes or TypeScript for type checking
4. **Performance**: Memoize expensive operations and components
5. **Code Style**: Use consistent naming conventions and folder structure
6. **Testing**: Write unit and integration tests
7. **Accessibility**: Follow ARIA guidelines and semantic HTML

### 94. How do you handle asynchronous operations in React?

**Answer:** Use useEffect for side effects and manage loading/error states:

```jsx
function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;

    async function fetchUser() {
      try {
        setLoading(true);
        const userData = await api.getUser(userId);
        if (!cancelled) {
          setUser(userData);
        }
      } catch (err) {
        if (!cancelled) {
          setError(err.message);
        }
      } finally {
        if (!cancelled) {
          setLoading(false);
        }
      }
    }

    fetchUser();

    return () => {
      cancelled = true; // Cleanup to prevent state updates if component unmounts
    };
  }, [userId]);

  if (loading) return <div>Loading...</div>;
  if (error) return <div>Error: {error}</div>;
  if (!user) return <div>No user found</div>;

  return <div>Welcome, {user.name}!</div>;
}
```

### 95. What is the difference between development and production builds?

**Answer:**

- **Development**: Includes debugging tools, verbose error messages, unminified code
- **Production**: Optimized bundle, minified code, no debug tools, smaller file size

```bash
# Development
npm start

# Production build
npm run build
```

### 96. How do you implement internationalization (i18n) in React?

**Answer:** Use libraries like react-i18next for internationalization:

```jsx
import { useTranslation } from "react-i18next";

function Welcome() {
  const { t, i18n } = useTranslation();

  const changeLanguage = (lng) => {
    i18n.changeLanguage(lng);
  };

  return (
    <div>
      <h1>{t("welcome")}</h1>
      <button onClick={() => changeLanguage("en")}>English</button>
      <button onClick={() => changeLanguage("es")}>Español</button>
    </div>
  );
}
```

### 97. How do you handle environment variables in React?

**Answer:** Create environment files and prefix variables with REACT*APP*:

```bash
# .env
REACT_APP_API_URL=https://api.example.com
REACT_APP_APP_NAME=My React App

# .env.development
REACT_APP_API_URL=http://localhost:3001

# .env.production
REACT_APP_API_URL=https://api.production.com
```

```jsx
const apiUrl = process.env.REACT_APP_API_URL;
const appName = process.env.REACT_APP_APP_NAME;
```

### 98. What is the difference between React and other frameworks like Vue or Angular?

**Answer:**

**React:**

- Library focused on UI
- Component-based architecture
- Virtual DOM
- Large ecosystem
- JSX syntax
- Functional programming approach

**Vue:**

- Progressive framework
- Template-based syntax
- Smaller learning curve
- Built-in state management
- Two-way data binding

**Angular:**

- Full framework
- TypeScript by default
- Dependency injection
- MVC architecture
- More opinionated structure

### 99. How do you test React components?

**Answer:** Use testing libraries like Jest and React Testing Library:

```jsx
import { render, screen, fireEvent } from "@testing-library/react";
import "@testing-library/jest-dom";
import Counter from "./Counter";

describe("Counter Component", () => {
  test("renders initial count", () => {
    render(<Counter />);
    expect(screen.getByText("Count: 0")).toBeInTheDocument();
  });

  test("increments count when button is clicked", () => {
    render(<Counter />);
    const button = screen.getByText("Increment");
    fireEvent.click(button);
    expect(screen.getByText("Count: 1")).toBeInTheDocument();
  });

  test("decrements count when decrement button is clicked", () => {
    render(<Counter initialCount={5} />);
    const button = screen.getByText("Decrement");
    fireEvent.click(button);
    expect(screen.getByText("Count: 4")).toBeInTheDocument();
  });
});
```

### 100. What are the future trends and updates in React?

**Answer:** Current and upcoming React features:

1. **Concurrent Features**:
   - Automatic batching
   - Transitions for non-urgent updates
   - Suspense for data fetching

```jsx
import { startTransition } from "react";

function App() {
  const [isPending, startTransition] = useTransition();
  const [count, setCount] = useState(0);

  const handleClick = () => {
    startTransition(() => {
      setCount((c) => c + 1);
    });
  };

  return (
    <div>
      <button onClick={handleClick}>
        {isPending ? "Loading..." : `Count: ${count}`}
      </button>
    </div>
  );
}
```

2. **React Server Components**: Components that render on the server
3. **Improved DevTools**: Better debugging and profiling tools
4. **React 18+ Features**:
   - Automatic batching
   - Strict Mode improvements
   - New Suspense features

---

## Conclusion

This comprehensive guide covers 100 essential React.js interview questions ranging from basic concepts to advanced topics. These questions cover:

- **Fundamentals**: JSX, Virtual DOM, Components
- **State Management**: useState, useReducer, Context API
- **Performance**: Memoization, Code Splitting, Optimization
- **Advanced Topics**: SSR, Testing, Best Practices
- **Modern React**: Hooks, Concurrent Features, Suspense

### Tips for React Interviews:

1. **Practice Coding**: Be prepared to write React code during the interview
2. **Understand Concepts**: Don't just memorize answers, understand the underlying concepts
3. **Stay Updated**: Keep up with the latest React features and best practices
4. **Build Projects**: Having real-world React projects demonstrates practical knowledge
5. **Know the Ecosystem**: Familiarize yourself with popular React libraries and tools

### Additional Resources:

- [React Official Documentation](https://react.dev/)
- [React DevTools](https://chrome.google.com/webstore/detail/react-developer-tools/)
- [Create React App](https://create-react-app.dev/)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
- [React Router](https://reactrouter.com/)

Remember to practice these concepts with hands-on coding and build real projects to solidify your understanding. Good luck with your React.js interviews!

# React 19 Latest Features - Interview Questions & Answers

## Table of Contents

1. [React Compiler](#react-compiler)
2. [Server Components](#server-components)
3. [Actions](#actions)
4. [New Hooks](#new-hooks)
5. [Concurrent Features](#concurrent-features)
6. [Developer Experience](#developer-experience)
7. [Breaking Changes](#breaking-changes)

---

## React Compiler

### Q1: What is the React Compiler and how does it work?

**Answer:**
The React Compiler is an experimental build-time tool that automatically optimizes React components by memoizing expensive computations and reducing unnecessary re-renders. It works by:

- Analyzing component code at build time
- Automatically inserting `useMemo`, `useCallback`, and `memo` optimizations
- Eliminating the need for manual memoization in most cases
- Providing better performance without developer intervention

**Key benefits:**

- Automatic optimization without manual memoization
- Reduces bundle size by eliminating manual optimization code
- Improves runtime performance
- Maintains React's declarative programming model

### Q2: How do you enable the React Compiler?

**Answer:**

```javascript
// babel.config.js
module.exports = {
  plugins: [
    [
      "babel-plugin-react-compiler",
      {
        // Configuration options
        runtimeModule: "react-compiler-runtime",
      },
    ],
  ],
};

// Or in Next.js 15+
// next.config.js
module.exports = {
  experimental: {
    reactCompiler: true,
  },
};
```

---

## Server Components

### Q3: What are React Server Components and how do they differ from Client Components?

**Answer:**
React Server Components (RSC) are components that render on the server and send their output to the client as a serialized format.

**Server Components:**

- Run on the server during build time or request time
- Have direct access to server-side resources (databases, file system)
- Cannot use browser APIs or event handlers
- Reduce client-side bundle size
- Improve initial page load performance

**Client Components:**

- Run in the browser
- Can use hooks, event handlers, and browser APIs
- Interactive and stateful
- Marked with `'use client'` directive

```javascript
// Server Component (default)
async function ServerComponent() {
  const data = await fetch("https://api.example.com/data");
  return <div>{data.title}</div>;
}

// Client Component
("use client");
import { useState } from "react";

function ClientComponent() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

### Q4: What are the benefits and limitations of Server Components?

**Answer:**
**Benefits:**

- Reduced client-side bundle size
- Better SEO and initial page load
- Direct access to server-side data
- Improved security (sensitive operations stay on server)
- Better caching strategies

**Limitations:**

- Cannot use browser APIs
- No event handlers or interactivity
- Cannot use most hooks (useState, useEffect, etc.)
- Require server-side rendering setup
- More complex mental model for developers

---

## Actions

### Q5: What are Actions in React 19 and how do they work?

**Answer:**
Actions are a new pattern in React 19 for handling asynchronous operations, particularly form submissions and data mutations. They provide built-in loading states, error handling, and optimistic updates.

```javascript
import { useActionState } from "react";

function ContactForm() {
  async function submitAction(prevState, formData) {
    try {
      const response = await fetch("/api/contact", {
        method: "POST",
        body: formData,
      });
      return { success: true, message: "Form submitted!" };
    } catch (error) {
      return { success: false, error: error.message };
    }
  }

  const [state, action, isPending] = useActionState(submitAction, null);

  return (
    <form action={action}>
      <input name="email" required />
      <button disabled={isPending}>
        {isPending ? "Submitting..." : "Submit"}
      </button>
      {state?.error && <p>Error: {state.error}</p>}
      {state?.success && <p>{state.message}</p>}
    </form>
  );
}
```

### Q6: What is useActionState hook and when would you use it?

**Answer:**
`useActionState` is a hook that manages the state of an Action, providing loading states, error handling, and form data management.

**Syntax:**

```javascript
const [state, action, isPending] = useActionState(actionFn, initialState);
```

**Parameters:**

- `actionFn`: The async function to execute
- `initialState`: Initial state value

**Returns:**

- `state`: Current state of the action
- `action`: Function to trigger the action
- `isPending`: Boolean indicating if action is running

**Use cases:**

- Form submissions with loading states
- Data mutations with error handling
- Optimistic UI updates
- Server actions integration

---

## New Hooks

### Q7: What is the useOptimistic hook and how does it work?

**Answer:**
`useOptimistic` allows you to show optimistic updates while an async operation is pending, providing immediate feedback to users.

```javascript
import { useOptimistic, useActionState } from "react";

function TodoList({ todos }) {
  const [optimisticTodos, addOptimisticTodo] = useOptimistic(
    todos,
    (currentTodos, newTodo) => [...currentTodos, { ...newTodo, pending: true }]
  );

  async function addTodo(formData) {
    const newTodo = { id: Date.now(), text: formData.get("todo") };
    addOptimisticTodo(newTodo);

    // Simulate API call
    await fetch("/api/todos", {
      method: "POST",
      body: JSON.stringify(newTodo),
    });
  }

  const [, action] = useActionState(addTodo);

  return (
    <>
      <form action={action}>
        <input name="todo" />
        <button>Add Todo</button>
      </form>
      <ul>
        {optimisticTodos.map((todo) => (
          <li key={todo.id} style={{ opacity: todo.pending ? 0.5 : 1 }}>
            {todo.text}
          </li>
        ))}
      </ul>
    </>
  );
}
```

### Q8: What is the use() hook and how is it different from useEffect?

**Answer:**
The `use()` hook is a new primitive that can unwrap promises and context, and can be called conditionally unlike other hooks.

```javascript
import { use, Suspense } from "react";

// Using with Promises
function UserProfile({ userPromise }) {
  const user = use(userPromise); // Unwraps the promise
  return <div>Hello, {user.name}!</div>;
}

// Using with Context
function ThemeButton() {
  const theme = use(ThemeContext);
  return <button className={theme}>Click me</button>;
}

// Can be used conditionally
function ConditionalData({ shouldLoad, dataPromise }) {
  let data = null;
  if (shouldLoad) {
    data = use(dataPromise); // This is allowed!
  }

  return <div>{data ? data.title : "No data"}</div>;
}

function App() {
  const userPromise = fetch("/api/user").then((res) => res.json());

  return (
    <Suspense fallback={<div>Loading...</div>}>
      <UserProfile userPromise={userPromise} />
    </Suspense>
  );
}
```

**Key differences from useEffect:**

- Can be called conditionally
- Works with Suspense boundaries
- Unwraps promises directly
- No dependency array needed
- Synchronous API (though handles async data)

---

## Concurrent Features

### Q9: What improvements were made to Concurrent Features in React 19?

**Answer:**
React 19 includes several improvements to concurrent rendering:

**1. Automatic Batching Improvements:**

- Better handling of multiple state updates
- More consistent batching across different event types
- Improved performance for rapid updates

**2. Enhanced Suspense:**

- Better error boundaries integration
- Improved fallback handling
- More predictable loading states

**3. Transition Improvements:**

- `useTransition` with better priority handling
- More granular control over urgent vs non-urgent updates
- Better integration with Server Components

```javascript
import { useTransition, useState } from "react";

function SearchResults() {
  const [query, setQuery] = useState("");
  const [results, setResults] = useState([]);
  const [isPending, startTransition] = useTransition();

  function handleSearch(value) {
    setQuery(value); // Urgent update
    startTransition(() => {
      // Non-urgent update
      setResults(searchData(value));
    });
  }

  return (
    <div>
      <input value={query} onChange={(e) => handleSearch(e.target.value)} />
      {isPending && <div>Searching...</div>}
      <ResultsList results={results} />
    </div>
  );
}
```

### Q10: How does React 19 handle error boundaries with Server Components?

**Answer:**
React 19 improves error boundary handling for Server Components:

```javascript
// Error Boundary for Server Components
"use client";
import { ErrorBoundary } from "react-error-boundary";

function ServerErrorFallback({ error, resetErrorBoundary }) {
  return (
    <div role="alert">
      <h2>Server Error</h2>
      <pre>{error.message}</pre>
      <button onClick={resetErrorBoundary}>Try again</button>
    </div>
  );
}

function App() {
  return (
    <ErrorBoundary
      FallbackComponent={ServerErrorFallback}
      onError={(error, errorInfo) => {
        console.log("Server component error:", error, errorInfo);
      }}
    >
      <ServerComponent />
    </ErrorBoundary>
  );
}

// Server Component that might throw
async function ServerComponent() {
  try {
    const data = await fetchServerData();
    return <DataDisplay data={data} />;
  } catch (error) {
    throw new Error(`Failed to load data: ${error.message}`);
  }
}
```

---

## Developer Experience

### Q11: What new debugging and development tools come with React 19?

**Answer:**
React 19 introduces several developer experience improvements:

**1. Enhanced React DevTools:**

- Better Server Components inspection
- Improved profiling for Actions
- Compiler optimization visualization
- Better concurrent feature debugging

**2. Improved Error Messages:**

- More descriptive hydration mismatch errors
- Better async component error reporting
- Clearer Server/Client component boundary errors

**3. New DevTools Features:**

```javascript
// Better component tree visualization
function MyComponent() {
  // DevTools now shows compiler optimizations
  const memoizedValue = expensiveCalculation(props.data);

  // Better action debugging
  const [state, action] = useActionState(submitForm, null);

  return <div>{/* component JSX */}</div>;
}
```

### Q12: How do you handle hydration in React 19?

**Answer:**
React 19 improves hydration with better error handling and selective hydration:

```javascript
// Improved hydration with better error boundaries
import { hydrateRoot } from "react-dom/client";

const root = hydrateRoot(document.getElementById("root"), <App />, {
  onRecoverableError: (error, errorInfo) => {
    console.log("Hydration error recovered:", error, errorInfo);
    // Report to error tracking service
  },
  identifierPrefix: "my-app",
});

// Selective hydration with Suspense
function App() {
  return (
    <div>
      <Header /> {/* Hydrates immediately */}
      <Suspense fallback={<div>Loading content...</div>}>
        <MainContent /> {/* Hydrates when ready */}
      </Suspense>
      <Suspense fallback={<div>Loading sidebar...</div>}>
        <Sidebar /> {/* Hydrates independently */}
      </Suspense>
    </div>
  );
}
```

---

## Breaking Changes

### Q13: What are the major breaking changes in React 19?

**Answer:**
React 19 includes several breaking changes:

**1. Removed Legacy APIs:**

```javascript
// ❌ Removed in React 19
import { render } from "react-dom";
render(<App />, container);

// ✅ Use React 18+ API
import { createRoot } from "react-dom/client";
const root = createRoot(container);
root.render(<App />);
```

**2. StrictMode Changes:**

- More aggressive double-invoking of effects
- Better detection of side effects in render phase
- Enhanced component debugging

**3. TypeScript Changes:**

```typescript
// ❌ Old way
interface Props {
  children: React.ReactNode;
}

// ✅ New way with better Server Component support
interface Props {
  children: React.ReactNode;
}

// Server Components have different prop constraints
interface ServerProps {
  // Cannot include functions or class instances
  data: string;
  count: number;
}
```

### Q14: How do you migrate from React 18 to React 19?

**Answer:**
**Migration Steps:**

1. **Update Dependencies:**

```bash
npm update react react-dom
npm install react@19 react-dom@19
```

2. **Enable New Features Gradually:**

```javascript
// Start with existing components
function ExistingComponent() {
  return <div>Existing functionality</div>;
}

// Gradually adopt new features
function NewComponent() {
  const [state, action] = useActionState(submitAction, null);
  return <form action={action}>{/* form content */}</form>;
}
```

3. **Update Build Configuration:**

```javascript
// Enable React Compiler (optional)
// webpack.config.js
module.exports = {
  module: {
    rules: [
      {
        test: /\.[jt]sx?$/,
        use: {
          loader: "babel-loader",
          options: {
            plugins: ["babel-plugin-react-compiler"],
          },
        },
      },
    ],
  },
};
```

4. **Test Thoroughly:**

- Run existing tests to ensure no regressions
- Add tests for new features
- Check for hydration issues in SSR apps
- Verify concurrent rendering behavior

---

## Practical Examples

### Q15: Show a practical example combining multiple React 19 features

**Answer:**

```javascript
"use server";
// Server Action
async function updateProfile(prevState, formData) {
  const profile = {
    name: formData.get("name"),
    email: formData.get("email"),
  };

  try {
    await saveProfile(profile);
    return { success: true, profile };
  } catch (error) {
    return { success: false, error: error.message };
  }
}

// Client Component
("use client");
import { useActionState, useOptimistic } from "react";

function ProfileForm({ initialProfile }) {
  const [optimisticProfile, setOptimisticProfile] = useOptimistic(
    initialProfile,
    (current, update) => ({ ...current, ...update })
  );

  const [state, action, isPending] = useActionState(updateProfile, null);

  function handleSubmit(formData) {
    // Optimistic update
    setOptimisticProfile({
      name: formData.get("name"),
      email: formData.get("email"),
    });

    // Submit form
    action(formData);
  }

  return (
    <form action={handleSubmit}>
      <input
        name="name"
        defaultValue={optimisticProfile.name}
        disabled={isPending}
      />
      <input
        name="email"
        defaultValue={optimisticProfile.email}
        disabled={isPending}
      />
      <button disabled={isPending}>
        {isPending ? "Saving..." : "Save Profile"}
      </button>

      {state?.error && <div className="error">{state.error}</div>}
      {state?.success && <div className="success">Profile updated!</div>}
    </form>
  );
}
```

This example demonstrates:

- Server Actions for form handling
- `useActionState` for managing form state
- `useOptimistic` for immediate UI feedback
- Proper loading states and error handling
- Integration between server and client components

---

## Summary

React 19 brings significant improvements in performance, developer experience, and new paradigms like Server Components and Actions. The key areas to focus on for interviews are:

1. **Understanding Server vs Client Components**
2. **Mastering the new hooks (useActionState, useOptimistic, use)**
3. **Knowing how Actions work for form handling**
4. **Understanding the React Compiler benefits**
5. **Being aware of breaking changes and migration path**

These features represent a major shift towards better performance and developer productivity while maintaining React's declarative nature.

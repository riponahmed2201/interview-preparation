# 📘 JavaScript Interview Questions & Answers

## Table of Contents

- [Basic Level (1-50)](#basic-level)
- [Intermediate Level (51-150)](#intermediate-level)
- [Advanced Level (151-250)](#advanced-level)
- [Expert Level (251-300)](#expert-level)

---

## Basic Level

### 1. What is JavaScript?

**Answer:** JavaScript is a high-level, interpreted programming language that is primarily used for web development. It's a dynamic, weakly typed language that supports object-oriented, imperative, and functional programming paradigms.

### 2. What are the different data types in JavaScript?

**Answer:** JavaScript has 8 data types:

- **Primitive types:** Number, String, Boolean, Undefined, Null, Symbol, BigInt
- **Non-primitive type:** Object (includes arrays, functions, dates, etc.)

### 3. What is the difference between `var`, `let`, and `const`?

**Answer:**

- `var`: Function-scoped, can be redeclared and updated, hoisted with undefined
- `let`: Block-scoped, can be updated but not redeclared, hoisted but not initialized
- `const`: Block-scoped, cannot be updated or redeclared, must be initialized

### 4. What is hoisting in JavaScript?

**Answer:** Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their scope during compilation phase. Variables are hoisted but not their values.

```javascript
console.log(x); // undefined (not error)
var x = 5;

// Equivalent to:
var x;
console.log(x);
x = 5;
```

### 5. What is the difference between `==` and `===`?

**Answer:**

- `==` (loose equality): Compares values after type coercion
- `===` (strict equality): Compares values without type coercion

```javascript
"5" == 5; // true
"5" === 5; // false
```

### 6. What are closures in JavaScript?

**Answer:** A closure is a function that has access to variables in its outer (enclosing) scope even after the outer function has finished executing.

```javascript
function outer(x) {
  return function inner(y) {
    return x + y;
  };
}
const add5 = outer(5);
console.log(add5(3)); // 8
```

### 7. What is the `this` keyword?

**Answer:** `this` refers to the object that is executing the current function. Its value depends on how the function is called.

### 8. What are arrow functions?

**Answer:** Arrow functions are a shorter way to write functions introduced in ES6. They don't have their own `this`, `arguments`, or `super`.

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

### 9. What is the difference between `null` and `undefined`?

**Answer:**

- `undefined`: Variable declared but not assigned a value
- `null`: Intentional absence of any object value

### 10. What are template literals?

**Answer:** Template literals are string literals that allow embedded expressions using backticks and `${}`.

```javascript
const name = "John";
const message = `Hello, ${name}!`;
```

### 11. What is destructuring?

**Answer:** Destructuring allows extracting values from arrays or properties from objects into distinct variables.

```javascript
// Array destructuring
const [a, b] = [1, 2];

// Object destructuring
const { name, age } = { name: "John", age: 30 };
```

### 12. What are the different ways to create objects in JavaScript?

**Answer:**

```javascript
// Object literal
const obj1 = { name: "John" };

// Constructor function
function Person(name) {
  this.name = name;
}
const obj2 = new Person("John");

// Object.create()
const obj3 = Object.create({ name: "John" });

// ES6 Class
class Person {
  constructor(name) {
    this.name = name;
  }
}
const obj4 = new Person("John");
```

### 13. What is the difference between function declaration and function expression?

**Answer:**

- **Function Declaration:** Hoisted completely, can be called before definition
- **Function Expression:** Not hoisted, cannot be called before definition

```javascript
// Declaration (hoisted)
function declared() {
  return "I'm hoisted";
}

// Expression (not hoisted)
const expressed = function () {
  return "I'm not hoisted";
};
```

### 14. What are higher-order functions?

**Answer:** Functions that take other functions as arguments or return functions as results.

```javascript
function higherOrder(fn) {
  return function (x) {
    return fn(x) * 2;
  };
}
```

### 15. What is the purpose of the `use strict` directive?

**Answer:** Enables strict mode, which catches common coding mistakes and prevents unsafe actions like using undeclared variables.

### 16. What are callbacks?

**Answer:** A callback is a function passed as an argument to another function, to be executed after some operation is completed.

```javascript
function greet(name, callback) {
  console.log("Hello " + name);
  callback();
}

greet("John", function () {
  console.log("Callback executed");
});
```

### 17. What is event bubbling?

**Answer:** Event bubbling is when an event starts from the target element and bubbles up to the root of the DOM tree.

### 18. What is the difference between `slice()` and `splice()`?

**Answer:**

- `slice()`: Returns a new array, doesn't modify original
- `splice()`: Modifies the original array, returns removed elements

### 19. What are falsy values in JavaScript?

**Answer:** Values that evaluate to false in boolean context: `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, `NaN`

### 20. What is the difference between `for...in` and `for...of`?

**Answer:**

- `for...in`: Iterates over enumerable properties (keys)
- `for...of`: Iterates over iterable objects (values)

### 21. What is JSON and how do you parse it?

**Answer:** JSON (JavaScript Object Notation) is a data interchange format. Use `JSON.parse()` to parse and `JSON.stringify()` to convert to JSON.

### 22. What are promises in JavaScript?

**Answer:** Promises represent the eventual completion or failure of an asynchronous operation and its resulting value.

```javascript
const promise = new Promise((resolve, reject) => {
  // async operation
  if (success) resolve(value);
  else reject(error);
});
```

### 23. What is the difference between `map()` and `forEach()`?

**Answer:**

- `map()`: Returns a new array with transformed elements
- `forEach()`: Executes a function for each element, returns undefined

### 24. What is scope in JavaScript?

**Answer:** Scope determines the accessibility of variables. JavaScript has function scope, block scope, and global scope.

### 25. What are immediately invoked function expressions (IIFE)?

**Answer:** Functions that are executed immediately after they are defined.

```javascript
(function () {
  console.log("IIFE executed");
})();
```

### 26. What is the `typeof` operator?

**Answer:** Returns a string indicating the type of the unevaluated operand.

```javascript
typeof 42; // "number"
typeof "hello"; // "string"
typeof true; // "boolean"
```

### 27. What are the different ways to declare variables?

**Answer:** `var`, `let`, `const`, and implicitly (without declaration keyword, creates global variable).

### 28. What is the difference between `push()` and `unshift()`?

**Answer:**

- `push()`: Adds elements to the end of an array
- `unshift()`: Adds elements to the beginning of an array

### 29. What is the `arguments` object?

**Answer:** An array-like object containing all arguments passed to a function (not available in arrow functions).

### 30. What is the difference between shallow copy and deep copy?

**Answer:**

- Shallow copy: Copies only the first level of properties
- Deep copy: Copies all levels of nested properties

### 31. What are the different ways to clone an object?

**Answer:**

```javascript
// Shallow copy
const clone1 = Object.assign({}, obj);
const clone2 = { ...obj };

// Deep copy
const clone3 = JSON.parse(JSON.stringify(obj)); // Limited
const clone4 = structuredClone(obj); // Modern browsers
```

### 32. What is the difference between `charAt()` and `charCodeAt()`?

**Answer:**

- `charAt()`: Returns the character at specified index
- `charCodeAt()`: Returns the Unicode value of character at specified index

### 33. What are regular expressions?

**Answer:** Patterns used to match character combinations in strings. Created with `/pattern/flags` or `new RegExp()`.

### 34. What is the `bind()` method?

**Answer:** Creates a new function with a specific `this` value and optional preset arguments.

```javascript
const obj = { name: "John" };
function greet() {
  console.log(`Hello, ${this.name}`);
}
const boundGreet = greet.bind(obj);
```

### 35. What is the difference between `call()` and `apply()`?

**Answer:**

- `call()`: Invokes function with specified `this` and individual arguments
- `apply()`: Invokes function with specified `this` and arguments as array

### 36. What are primitive and non-primitive data types?

**Answer:**

- Primitive: Stored by value, immutable (number, string, boolean, null, undefined, symbol, bigint)
- Non-primitive: Stored by reference, mutable (objects, arrays, functions)

### 37. What is the spread operator?

**Answer:** Allows expansion of iterables or object properties using `...` syntax.

```javascript
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4]; // [1, 2, 3, 4]
```

### 38. What is the rest parameter?

**Answer:** Collects multiple arguments into an array using `...` syntax in function parameters.

```javascript
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}
```

### 39. What is the difference between `localStorage` and `sessionStorage`?

**Answer:**

- `localStorage`: Data persists until explicitly removed
- `sessionStorage`: Data persists only for the session (tab/window)

### 40. What are the different types of errors in JavaScript?

**Answer:**

- `SyntaxError`: Invalid syntax
- `ReferenceError`: Variable not found
- `TypeError`: Wrong type operation
- `RangeError`: Number out of range

### 41. What is the `instanceof` operator?

**Answer:** Tests whether an object is an instance of a specific constructor/class.

```javascript
const arr = [];
console.log(arr instanceof Array); // true
```

### 42. What are getters and setters?

**Answer:** Methods that get and set the values of object properties.

```javascript
const obj = {
  _value: 0,
  get value() {
    return this._value;
  },
  set value(val) {
    this._value = val;
  },
};
```

### 43. What is the difference between `Object.freeze()` and `Object.seal()`?

**Answer:**

- `Object.freeze()`: Prevents adding, deleting, or modifying properties
- `Object.seal()`: Prevents adding or deleting properties, but allows modification

### 44. What are computed property names?

**Answer:** Dynamic property names in object literals using square brackets.

```javascript
const key = "dynamicKey";
const obj = {
  [key]: "value",
};
```

### 45. What is the comma operator?

**Answer:** Evaluates multiple expressions and returns the value of the last expression.

```javascript
let x = (1, 2, 3); // x = 3
```

### 46. What is the difference between `in` operator and `hasOwnProperty()`?

**Answer:**

- `in`: Checks if property exists in object or prototype chain
- `hasOwnProperty()`: Checks if property exists only in the object itself

### 47. What are symbols in JavaScript?

**Answer:** Unique primitive values that can be used as object property keys.

```javascript
const sym = Symbol("description");
const obj = { [sym]: "value" };
```

### 48. What is the `void` operator?

**Answer:** Evaluates an expression and returns `undefined`.

```javascript
void 0; // undefined
void (function () {
  console.log("hello");
})(); // IIFE returning undefined
```

### 49. What is the difference between `isNaN()` and `Number.isNaN()`?

**Answer:**

- `isNaN()`: Attempts type coercion, then checks if NaN
- `Number.isNaN()`: Strict check without type coercion

### 50. What are tagged template literals?

**Answer:** Function calls using template literal syntax.

```javascript
function tag(strings, ...values) {
  return strings[0] + values[0] + strings[1];
}
const result = tag`Hello ${name}!`;
```

---

## Intermediate Level

### 51. What is the Event Loop in JavaScript?

**Answer:** The event loop is responsible for handling asynchronous operations. It continuously checks the call stack and task queues, moving tasks from queues to the stack when it's empty.

### 52. What are Promises and how do they work?

**Answer:** Promises represent asynchronous operations with three states: pending, fulfilled, or rejected.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success!"), 1000);
});

promise.then((result) => console.log(result));
```

### 53. What is async/await?

**Answer:** Syntactic sugar over Promises that makes asynchronous code look and behave more like synchronous code.

```javascript
async function fetchData() {
  try {
    const response = await fetch("/api/data");
    const data = await response.json();
    return data;
  } catch (error) {
    console.error(error);
  }
}
```

### 54. What is prototypal inheritance?

**Answer:** JavaScript's inheritance model where objects can inherit properties and methods from other objects through the prototype chain.

```javascript
function Animal(name) {
  this.name = name;
}
Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound`);
};

function Dog(name) {
  Animal.call(this, name);
}
Dog.prototype = Object.create(Animal.prototype);
```

### 55. What is the difference between microtasks and macrotasks?

**Answer:**

- **Microtasks**: Promise callbacks, queueMicrotask() - higher priority
- **Macrotasks**: setTimeout, setInterval, I/O operations - lower priority

### 56. What are generators in JavaScript?

**Answer:** Functions that can be paused and resumed, returning multiple values over time using `yield`.

```javascript
function* numberGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = numberGenerator();
console.log(gen.next().value); // 1
```

### 57. What is currying?

**Answer:** Technique of transforming a function with multiple arguments into a sequence of functions with single arguments.

```javascript
function curry(f) {
  return function (a) {
    return function (b) {
      return f(a, b);
    };
  };
}

const add = curry((a, b) => a + b);
const add5 = add(5);
console.log(add5(3)); // 8
```

### 58. What is debouncing and throttling?

**Answer:**

- **Debouncing**: Delays function execution until after a specified time has passed since the last call
- **Throttling**: Ensures function is called at most once per specified interval

```javascript
// Debounce
function debounce(func, delay) {
  let timeoutId;
  return function (...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => func.apply(this, args), delay);
  };
}

// Throttle
function throttle(func, delay) {
  let lastCall = 0;
  return function (...args) {
    const now = new Date().getTime();
    if (now - lastCall >= delay) {
      lastCall = now;
      func.apply(this, args);
    }
  };
}
```

### 59. What is memoization?

**Answer:** Optimization technique that caches function results to avoid repeated calculations.

```javascript
function memoize(fn) {
  const cache = {};
  return function (...args) {
    const key = JSON.stringify(args);
    if (key in cache) {
      return cache[key];
    }
    const result = fn.apply(this, args);
    cache[key] = result;
    return result;
  };
}
```

### 60. What are WeakMap and WeakSet?

**Answer:**

- **WeakMap**: Collection of key-value pairs with weak object keys
- **WeakSet**: Collection of unique objects with weak references

```javascript
const weakMap = new WeakMap();
const obj = {};
weakMap.set(obj, "value");

const weakSet = new WeakSet();
weakSet.add(obj);
```

### 61. What is the difference between Map and Object?

**Answer:**

- **Map**: Any type as keys, size property, iterable, no default keys
- **Object**: String/Symbol keys, manual size calculation, not directly iterable, has default keys

### 62. What are iterators and iterables?

**Answer:**

- **Iterable**: Object implementing `Symbol.iterator` method
- **Iterator**: Object with `next()` method returning `{value, done}`

```javascript
const iterable = {
  [Symbol.iterator]: function* () {
    yield 1;
    yield 2;
    yield 3;
  },
};
```

### 63. What is the Proxy object?

**Answer:** Allows you to intercept and customize operations on objects (property lookup, assignment, enumeration, etc.).

```javascript
const target = { name: "John" };
const proxy = new Proxy(target, {
  get(target, property) {
    console.log(`Getting ${property}`);
    return target[property];
  },
});
```

### 64. What is the Reflect API?

**Answer:** Provides methods for interceptable JavaScript operations, often used with Proxy.

```javascript
const obj = { name: "John" };
console.log(Reflect.has(obj, "name")); // true
Reflect.set(obj, "age", 30);
```

### 65. What are template literals and tagged templates?

**Answer:** Enhanced string literals with embedded expressions and custom processing functions.

```javascript
function highlight(strings, ...values) {
  return strings.reduce((result, string, i) => {
    return result + string + (values[i] ? `<strong>${values[i]}</strong>` : "");
  }, "");
}

const name = "John";
const message = highlight`Hello ${name}!`;
```

### 66. What is the difference between `Object.create()` and constructor functions?

**Answer:**

- `Object.create()`: Creates object with specified prototype
- Constructor functions: Creates object and sets properties via `this`

### 67. What are private fields in classes?

**Answer:** ES2022 feature for truly private class members using `#` prefix.

```javascript
class MyClass {
  #privateField = "private";

  #privateMethod() {
    return this.#privateField;
  }

  getPrivate() {
    return this.#privateMethod();
  }
}
```

### 68. What is the module system in JavaScript?

**Answer:** ES6 modules provide a way to organize and share code using `import`/`export`.

```javascript
// math.js
export const PI = 3.14159;
export function square(x) {
  return x * x;
}
export default function cube(x) {
  return x * x * x;
}

// main.js
import cube, { PI, square } from "./math.js";
```

### 69. What are dynamic imports?

**Answer:** Load modules dynamically at runtime using `import()` function.

```javascript
async function loadModule() {
  const module = await import("./myModule.js");
  module.doSomething();
}
```

### 70. What is the difference between CommonJS and ES6 modules?

**Answer:**

- **CommonJS**: `require()`/`module.exports`, synchronous, Node.js default
- **ES6**: `import`/`export`, asynchronous, browser and modern Node.js

### 71. What are service workers?

**Answer:** Scripts that run in the background, enabling features like push notifications, background sync, and offline functionality.

### 72. What is the Intersection Observer API?

**Answer:** Provides a way to asynchronously observe changes in intersection of target elements with viewport or ancestor element.

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      console.log("Element is visible");
    }
  });
});

observer.observe(document.querySelector("#target"));
```

### 73. What are Web Workers?

**Answer:** Allow running scripts in background threads, enabling parallel processing without blocking the main UI thread.

```javascript
// main.js
const worker = new Worker("worker.js");
worker.postMessage({ data: [1, 2, 3, 4, 5] });
worker.onmessage = (e) => console.log(e.data);

// worker.js
self.onmessage = function (e) {
  const result = e.data.data.map((x) => x * 2);
  self.postMessage(result);
};
```

### 74. What is the Mutation Observer API?

**Answer:** Provides ability to watch for changes in DOM tree.

```javascript
const observer = new MutationObserver((mutations) => {
  mutations.forEach((mutation) => {
    console.log("DOM changed:", mutation);
  });
});

observer.observe(document.body, {
  childList: true,
  subtree: true,
});
```

### 75. What are Custom Elements?

**Answer:** Web Components API that allows creating custom HTML elements.

```javascript
class MyButton extends HTMLElement {
  constructor() {
    super();
    this.innerHTML = "<button>Click me!</button>";
  }
}

customElements.define("my-button", MyButton);
```

### 76. What is Shadow DOM?

**Answer:** Provides encapsulation by creating a separate DOM tree attached to an element.

```javascript
class MyComponent extends HTMLElement {
  constructor() {
    super();
    const shadow = this.attachShadow({ mode: "open" });
    shadow.innerHTML = "<p>Shadow content</p>";
  }
}
```

### 77. What are AbortController and AbortSignal?

**Answer:** Mechanism to cancel asynchronous operations like fetch requests.

```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch("/api/data", { signal })
  .then((response) => response.json())
  .catch((err) => {
    if (err.name === "AbortError") {
      console.log("Fetch aborted");
    }
  });

// Cancel the request
controller.abort();
```

### 78. What is the Fetch API?

**Answer:** Modern alternative to XMLHttpRequest for making HTTP requests.

```javascript
fetch("/api/data", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({ key: "value" }),
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

### 79. What are URL and URLSearchParams?

**Answer:** Built-in objects for working with URLs and query parameters.

```javascript
const url = new URL("https://example.com/path?name=john&age=30");
const params = new URLSearchParams(url.search);
console.log(params.get("name")); // 'john'
```

### 80. What is the Blob API?

**Answer:** Represents immutable, raw data file-like objects.

```javascript
const blob = new Blob(["Hello, World!"], { type: "text/plain" });
const url = URL.createObjectURL(blob);
```

### 81. What are ArrayBuffer and TypedArrays?

**Answer:**

- **ArrayBuffer**: Raw binary data buffer
- **TypedArrays**: Views to read/write ArrayBuffer data

```javascript
const buffer = new ArrayBuffer(16);
const int32View = new Int32Array(buffer);
int32View[0] = 42;
```

### 82. What is the performance API?

**Answer:** Provides access to performance-related information.

```javascript
const startTime = performance.now();
// Some operation
const endTime = performance.now();
console.log(`Operation took ${endTime - startTime} milliseconds`);
```

### 83. What are getter and setter methods in classes?

**Answer:** Methods that get and set property values with custom logic.

```javascript
class Circle {
  constructor(radius) {
    this._radius = radius;
  }

  get radius() {
    return this._radius;
  }

  set radius(value) {
    if (value <= 0) throw new Error("Radius must be positive");
    this._radius = value;
  }

  get area() {
    return Math.PI * this._radius ** 2;
  }
}
```

### 84. What is method chaining?

**Answer:** Pattern where methods return the object instance, allowing consecutive method calls.

```javascript
class Calculator {
  constructor() {
    this.value = 0;
  }

  add(n) {
    this.value += n;
    return this;
  }

  multiply(n) {
    this.value *= n;
    return this;
  }
}

const result = new Calculator().add(5).multiply(3).value; // 15
```

### 85. What are static methods in classes?

**Answer:** Methods that belong to the class rather than instances.

```javascript
class MathUtils {
  static add(a, b) {
    return a + b;
  }

  static PI = 3.14159;
}

console.log(MathUtils.add(2, 3)); // 5
```

### 86. What is the `super` keyword?

**Answer:** Used to access parent class properties and methods.

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  speak() {
    super.speak();
    console.log(`${this.name} barks`);
  }
}
```

### 87. What are mixins?

**Answer:** Pattern to add functionality to classes without inheritance.

```javascript
const Flyable = {
  fly() {
    console.log(`${this.name} is flying`);
  },
};

class Bird {
  constructor(name) {
    this.name = name;
  }
}

Object.assign(Bird.prototype, Flyable);
```

### 88. What is function composition?

**Answer:** Combining simple functions to create more complex ones.

```javascript
const add = (x) => (y) => x + y;
const multiply = (x) => (y) => x * y;
const compose = (f, g) => (x) => f(g(x));

const addThenMultiply = compose(multiply(3), add(2));
console.log(addThenMultiply(5)); // (5 + 2) * 3 = 21
```

### 89. What are pure functions?

**Answer:** Functions that always return same output for same input and have no side effects.

```javascript
// Pure function
function add(a, b) {
  return a + b;
}

// Impure function
let count = 0;
function increment() {
  count++;
  return count;
}
```

### 90. What is immutability?

**Answer:** Concept where objects cannot be modified after creation.

```javascript
// Immutable update patterns
const updateObject = (obj, key, value) => ({ ...obj, [key]: value });
const updateArray = (arr, index, value) => [
  ...arr.slice(0, index),
  value,
  ...arr.slice(index + 1),
];
```

### 91. What is the Factory pattern?

**Answer:** Creates objects without specifying their exact classes.

```javascript
function createUser(type, name) {
  switch (type) {
    case "admin":
      return new AdminUser(name);
    case "regular":
      return new RegularUser(name);
    default:
      throw new Error("Unknown user type");
  }
}
```

### 92. What is the Observer pattern?

**Answer:** Defines dependency between objects so when one changes, dependents are notified.

```javascript
class Subject {
  constructor() {
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  notify(data) {
    this.observers.forEach((observer) => observer.update(data));
  }
}
```

### 93. What is the Singleton pattern?

**Answer:** Ensures only one instance of a class exists.

```javascript
class Singleton {
  constructor() {
    if (Singleton.instance) {
      return Singleton.instance;
    }
    Singleton.instance = this;
  }

  static getInstance() {
    return new Singleton();
  }
}
```

### 94. What are design patterns commonly used in JavaScript?

**Answer:** Module, Revealing Module, Singleton, Factory, Observer, Decorator, Strategy, Command patterns.

### 95. What is functional programming in JavaScript?

**Answer:** Programming paradigm using functions as first-class citizens, emphasizing immutability and pure functions.

```javascript
const numbers = [1, 2, 3, 4, 5];
const result = numbers
  .filter((n) => n % 2 === 0)
  .map((n) => n * 2)
  .reduce((sum, n) => sum + n, 0);
```

### 96. What are monads in JavaScript?

**Answer:** Design pattern for handling complex operations with chaining, like Maybe or Promise.

```javascript
class Maybe {
  constructor(value) {
    this.value = value;
  }

  static of(value) {
    return new Maybe(value);
  }

  map(fn) {
    return this.value == null ? Maybe.of(null) : Maybe.of(fn(this.value));
  }

  flatMap(fn) {
    return this.value == null ? Maybe.of(null) : fn(this.value);
  }

  filter(predicate) {
    return this.value == null || !predicate(this.value) ? Maybe.of(null) : this;
  }
}

// Transducers
const map = (fn) => (reducer) => (acc, value) => reducer(acc, fn(value));
const filter = (predicate) => (reducer) => (acc, value) =>
  predicate(value) ? reducer(acc, value) : acc;

const compose = (...fns) =>
  fns.reduce(
    (f, g) =>
      (...args) =>
        f(g(...args))
  );

const transducer = compose(
  map((x) => x * 2),
  filter((x) => x > 4)
);
```

### 167. What are advanced metaprogramming techniques?

**Answer:**

```javascript
// Dynamic property access
const createFluentAPI = (target) => {
  return new Proxy(target, {
    get(target, property) {
      if (property in target) {
        return target[property];
      }

      // Dynamic method creation
      return function (...args) {
        console.log(`Called ${property} with`, args);
        return this; // Chainable
      };
    },
  });
};

const api = createFluentAPI({});
api.getData().processResult().render(); // All methods work dynamically

// Decorators (Stage 3 proposal)
function log(target, propertyKey, descriptor) {
  const originalMethod = descriptor.value;
  descriptor.value = function (...args) {
    console.log(`Calling ${propertyKey} with`, args);
    return originalMethod.apply(this, args);
  };
}

class Calculator {
  @log
  add(a, b) {
    return a + b;
  }
}

// Symbol-based metaprogramming
const PRIVATE = Symbol("private");

class MyClass {
  constructor() {
    this[PRIVATE] = { secret: "hidden" };
  }

  getSecret() {
    return this[PRIVATE].secret;
  }
}
```

### 168. What are advanced error handling patterns?

**Answer:**

```javascript
// Result type pattern
class Result {
  constructor(value, error) {
    this.value = value;
    this.error = error;
  }

  static ok(value) {
    return new Result(value, null);
  }

  static error(error) {
    return new Result(null, error);
  }

  isOk() {
    return this.error === null;
  }

  map(fn) {
    return this.isOk() ? Result.ok(fn(this.value)) : this;
  }

  flatMap(fn) {
    return this.isOk() ? fn(this.value) : this;
  }
}

function divide(a, b) {
  return b === 0 ? Result.error("Division by zero") : Result.ok(a / b);
}

// Error boundary pattern
class ErrorBoundary {
  constructor() {
    this.errorHandlers = new Map();
  }

  register(errorType, handler) {
    this.errorHandlers.set(errorType, handler);
  }

  handle(error) {
    const handler =
      this.errorHandlers.get(error.constructor) ||
      this.errorHandlers.get("default");

    if (handler) {
      handler(error);
    } else {
      throw error;
    }
  }
}

// Async error handling
async function withRetry(fn, maxRetries = 3, delay = 1000) {
  for (let i = 0; i < maxRetries; i++) {
    try {
      return await fn();
    } catch (error) {
      if (i === maxRetries - 1) throw error;
      await new Promise((resolve) => setTimeout(resolve, delay * (i + 1)));
    }
  }
}
```

### 169. What are advanced performance optimization techniques?

**Answer:**

```javascript
// Object pooling
class ObjectPool {
  constructor(createFn, resetFn, size = 10) {
    this.createFn = createFn;
    this.resetFn = resetFn;
    this.pool = [];

    // Pre-populate pool
    for (let i = 0; i < size; i++) {
      this.pool.push(this.createFn());
    }
  }

  acquire() {
    return this.pool.length > 0 ? this.pool.pop() : this.createFn();
  }

  release(obj) {
    this.resetFn(obj);
    this.pool.push(obj);
  }
}

// Lazy evaluation with generators
function* lazyMap(iterable, fn) {
  for (const item of iterable) {
    yield fn(item);
  }
}

function* lazyFilter(iterable, predicate) {
  for (const item of iterable) {
    if (predicate(item)) yield item;
  }
}

// Usage: Only computes when needed
const numbers = [1, 2, 3, 4, 5];
const pipeline = lazyFilter(
  lazyMap(numbers, (x) => x * 2),
  (x) => x > 4
);

// Memoization with weak references
function memoizeWeak(fn) {
  const cache = new WeakMap();

  return function (obj, ...args) {
    if (!cache.has(obj)) {
      cache.set(obj, new Map());
    }

    const objCache = cache.get(obj);
    const key = JSON.stringify(args);

    if (objCache.has(key)) {
      return objCache.get(key);
    }

    const result = fn.call(this, obj, ...args);
    objCache.set(key, result);
    return result;
  };
}
```

### 170. What are advanced concurrency patterns?

**Answer:**

```javascript
// Semaphore for limiting concurrent operations
class Semaphore {
  constructor(maxConcurrent) {
    this.maxConcurrent = maxConcurrent;
    this.current = 0;
    this.queue = [];
  }

  async acquire() {
    return new Promise((resolve) => {
      if (this.current < this.maxConcurrent) {
        this.current++;
        resolve();
      } else {
        this.queue.push(resolve);
      }
    });
  }

  release() {
    this.current--;
    if (this.queue.length > 0) {
      this.current++;
      const resolve = this.queue.shift();
      resolve();
    }
  }
}

// Actor model pattern
class Actor {
  constructor(initialState, reducer) {
    this.state = initialState;
    this.reducer = reducer;
    this.mailbox = [];
    this.processing = false;
  }

  async send(message) {
    return new Promise((resolve) => {
      this.mailbox.push({ message, resolve });
      this.process();
    });
  }

  async process() {
    if (this.processing || this.mailbox.length === 0) return;

    this.processing = true;

    while (this.mailbox.length > 0) {
      const { message, resolve } = this.mailbox.shift();
      const result = await this.reducer(this.state, message);

      if (result.newState !== undefined) {
        this.state = result.newState;
      }

      resolve(result.response);
    }

    this.processing = false;
  }
}

// Channel pattern (CSP style)
class Channel {
  constructor(bufferSize = 0) {
    this.buffer = [];
    this.bufferSize = bufferSize;
    this.senders = [];
    this.receivers = [];
    this.closed = false;
  }

  async send(value) {
    if (this.closed) throw new Error("Channel closed");

    return new Promise((resolve) => {
      if (this.receivers.length > 0) {
        const receiver = this.receivers.shift();
        receiver(value);
        resolve();
      } else if (this.buffer.length < this.bufferSize) {
        this.buffer.push(value);
        resolve();
      } else {
        this.senders.push({ value, resolve });
      }
    });
  }

  async receive() {
    if (this.closed && this.buffer.length === 0) {
      throw new Error("Channel closed");
    }

    return new Promise((resolve) => {
      if (this.buffer.length > 0) {
        const value = this.buffer.shift();
        if (this.senders.length > 0) {
          const sender = this.senders.shift();
          this.buffer.push(sender.value);
          sender.resolve();
        }
        resolve(value);
      } else {
        this.receivers.push(resolve);
      }
    });
  }
}
```

### 171. What are advanced module patterns?

**Answer:**

```javascript
// Module federation pattern
const ModuleRegistry = {
  modules: new Map(),

  define(name, factory, dependencies = []) {
    this.modules.set(name, { factory, dependencies, instance: null });
  },

  async require(name) {
    const module = this.modules.get(name);
    if (!module) throw new Error(`Module ${name} not found`);

    if (module.instance) return module.instance;

    // Resolve dependencies
    const deps = await Promise.all(
      module.dependencies.map((dep) => this.require(dep))
    );

    module.instance = await module.factory(...deps);
    return module.instance;
  },
};

// Dynamic module loading with caching
class ModuleLoader {
  constructor() {
    this.cache = new Map();
    this.loading = new Map();
  }

  async load(url) {
    if (this.cache.has(url)) {
      return this.cache.get(url);
    }

    if (this.loading.has(url)) {
      return this.loading.get(url);
    }

    const promise = import(url).then((module) => {
      this.cache.set(url, module);
      this.loading.delete(url);
      return module;
    });

    this.loading.set(url, promise);
    return promise;
  }
}

// Micro-frontend module pattern
class MicroFrontendLoader {
  constructor() {
    this.apps = new Map();
  }

  async loadApp(name, config) {
    if (this.apps.has(name)) {
      return this.apps.get(name);
    }

    const { entry, container } = config;
    const module = await import(entry);

    const app = {
      mount: () => module.mount(container),
      unmount: () => module.unmount(container),
      update: (props) => module.update(props),
    };

    this.apps.set(name, app);
    return app;
  }
}
```

### 172. What are advanced state management patterns?

**Answer:**

```javascript
// State machine pattern
class StateMachine {
  constructor(initialState, transitions) {
    this.state = initialState;
    this.transitions = transitions;
    this.listeners = [];
  }

  transition(event, payload) {
    const currentTransitions = this.transitions[this.state];
    const transition = currentTransitions && currentTransitions[event];

    if (!transition) {
      throw new Error(`Invalid transition: ${this.state} -> ${event}`);
    }

    const nextState =
      typeof transition === "function" ? transition(payload) : transition;

    const previousState = this.state;
    this.state = nextState;

    this.listeners.forEach((listener) => {
      listener({ from: previousState, to: nextState, event, payload });
    });

    return nextState;
  }

  subscribe(listener) {
    this.listeners.push(listener);
    return () => {
      const index = this.listeners.indexOf(listener);
      if (index > -1) this.listeners.splice(index, 1);
    };
  }
}

// Event sourcing pattern
class EventStore {
  constructor() {
    this.events = [];
    this.snapshots = new Map();
  }

  append(streamId, events, expectedVersion) {
    const currentVersion = this.getVersion(streamId);

    if (expectedVersion !== -1 && expectedVersion !== currentVersion) {
      throw new Error("Concurrency conflict");
    }

    events.forEach((event, index) => {
      this.events.push({
        ...event,
        streamId,
        version: currentVersion + index + 1,
        timestamp: Date.now(),
      });
    });
  }

  getEvents(streamId, fromVersion = 0) {
    return this.events.filter(
      (event) => event.streamId === streamId && event.version > fromVersion
    );
  }

  getVersion(streamId) {
    const events = this.events.filter((e) => e.streamId === streamId);
    return events.length > 0 ? events[events.length - 1].version : 0;
  }

  createSnapshot(streamId, version, data) {
    this.snapshots.set(`${streamId}:${version}`, data);
  }

  getSnapshot(streamId) {
    const keys = Array.from(this.snapshots.keys())
      .filter((key) => key.startsWith(streamId + ":"))
      .sort((a, b) => {
        const versionA = parseInt(a.split(":")[1]);
        const versionB = parseInt(b.split(":")[1]);
        return versionB - versionA;
      });

    return keys.length > 0 ? this.snapshots.get(keys[0]) : null;
  }
}

// CQRS pattern
class CommandBus {
  constructor() {
    this.handlers = new Map();
  }

  register(commandType, handler) {
    this.handlers.set(commandType, handler);
  }

  async execute(command) {
    const handler = this.handlers.get(command.constructor);
    if (!handler) {
      throw new Error(`No handler for command ${command.constructor.name}`);
    }

    return handler(command);
  }
}

class QueryBus {
  constructor() {
    this.handlers = new Map();
  }

  register(queryType, handler) {
    this.handlers.set(queryType, handler);
  }

  async execute(query) {
    const handler = this.handlers.get(query.constructor);
    if (!handler) {
      throw new Error(`No handler for query ${query.constructor.name}`);
    }

    return handler(query);
  }
}
```

### 173. What are advanced testing patterns?

**Answer:**

```javascript
// Test doubles factory
class TestDoubleFactory {
  static createSpy(methods = []) {
    const spy = {};
    methods.forEach((method) => {
      spy[method] = jest.fn();
      spy[method].calls = [];
      spy[method].mockImplementation = function (...args) {
        this.calls.push(args);
      };
    });
    return spy;
  }

  static createStub(responses = {}) {
    const stub = {};
    Object.keys(responses).forEach((method) => {
      stub[method] = jest.fn().mockReturnValue(responses[method]);
    });
    return stub;
  }

  static createMock(implementation = {}) {
    return new Proxy(implementation, {
      get(target, property) {
        if (!(property in target)) {
          target[property] = jest.fn();
        }
        return target[property];
      },
    });
  }
}

// Property-based testing helper
function forAll(generator, predicate, numTests = 100) {
  for (let i = 0; i < numTests; i++) {
    const testData = generator();
    if (!predicate(testData)) {
      throw new Error(
        `Property failed with input: ${JSON.stringify(testData)}`
      );
    }
  }
}

// Example generators
const generators = {
  integer:
    (min = -1000, max = 1000) =>
    () =>
      Math.floor(Math.random() * (max - min + 1)) + min,

  array:
    (elementGen, maxLength = 10) =>
    () => {
      const length = Math.floor(Math.random() * maxLength);
      return Array.from({ length }, elementGen);
    },

  string:
    (maxLength = 20) =>
    () => {
      const length = Math.floor(Math.random() * maxLength);
      return Array.from({ length }, () =>
        String.fromCharCode(97 + Math.floor(Math.random() * 26))
      ).join("");
    },
};

// Contract testing
class ContractTester {
  constructor() {
    this.contracts = [];
  }

  define(name, contract) {
    this.contracts.push({ name, contract });
  }

  verify(implementation) {
    const results = [];

    this.contracts.forEach(({ name, contract }) => {
      try {
        contract(implementation);
        results.push({ name, passed: true });
      } catch (error) {
        results.push({ name, passed: false, error: error.message });
      }
    });

    return results;
  }
}
```

### 174. What are advanced security patterns?

**Answer:**

```javascript
// Content Security Policy helper
class CSPBuilder {
    constructor() {
        this.directives = {};
    }

    defaultSrc(...sources) {
        this.directives['default-src'] = sources;
        return this;
    }

    scriptSrc(...sources) {
        this.directives['script-src'] = sources;
        return this;
    }

    styleSrc(...sources) {
        this.directives['style-src'] = sources;
        return this;
    }

    build() {
        return Object.entries(this.directives)
            .map(([directive, sources]) => `${directive} ${sources.join(' ')}`)
            .join('; ');
    }
}

// Input sanitization
class Sanitizer {
    static html(input) {
        const div = document.createElement('div');
        div.textContent = input;
        return div.innerHTML;
    }

    static url(input) {
        try {
            const url = new URL(input);
            const allowedProtocols = ['http:', 'https:', 'mailto:'];

            if (!allowedProtocols.includes(url.protocol)) {
                throw new Error('Disallowed protocol');
            }

            return url.href;
        } catch {
            return '';
        }
    }

    static sql(input) {
        return input.replace(/['"\\]/g, '\\    map(fn) {
        return this.value == null ? Maybe.of(null) : Maybe.of(fn(this.');
    }
}

// Rate limiting
class RateLimiter {
    constructor(maxRequests, windowMs) {
        this.maxRequests = maxRequests;
        this.windowMs = windowMs;
        this.requests = new Map();
    }

    isAllowed(identifier) {
        const now = Date.now();
        const windowStart = now - this.windowMs;

        if (!this.requests.has(identifier)) {
            this.requests.set(identifier, []);
        }

        const userRequests = this.requests.get(identifier);

        // Remove old requests
        const validRequests = userRequests.filter(time => time > windowStart);
        this.requests.set(identifier, validRequests);

        if (validRequests.length >= this.maxRequests) {
            return false;
        }

        validRequests.push(now);
        return true;
    }
}

// Secure random generator
class SecureRandom {
    static string(length = 32) {
        const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
        const array = new Uint8Array(length);
        crypto.getRandomValues(array);

        return Array.from(array, byte => chars[byte % chars.length]).join('');
    }

    static uuid() {
        return crypto.randomUUID();
    }

    static integer(min = 0, max = Number.MAX_SAFE_INTEGER) {
        const range = max - min + 1;
        const array = new Uint32Array(1);
        crypto.getRandomValues(array);

        return min + (array[0] % range);
    }
}
```

### 175. What are advanced architectural patterns?

**Answer:**

```javascript
// Hexagonal architecture (Ports and Adapters)
class UserService {
  constructor(userRepository, emailService) {
    this.userRepository = userRepository; // Port
    this.emailService = emailService; // Port
  }

  async createUser(userData) {
    const user = new User(userData);
    await this.userRepository.save(user);
    await this.emailService.sendWelcomeEmail(user.email);
    return user;
  }
}

// Repository pattern
class InMemoryUserRepository {
  constructor() {
    this.users = new Map();
    this.nextId = 1;
  }

  async save(user) {
    if (!user.id) {
      user.id = this.nextId++;
    }
    this.users.set(user.id, { ...user });
    return user;
  }

  async findById(id) {
    return this.users.get(id) || null;
  }

  async findByEmail(email) {
    return Array.from(this.users.values()).find((u) => u.email === email);
  }
}

// Event-driven architecture
class EventBus {
  constructor() {
    this.listeners = new Map();
  }

  subscribe(eventType, listener) {
    if (!this.listeners.has(eventType)) {
      this.listeners.set(eventType, []);
    }
    this.listeners.get(eventType).push(listener);

    // Return unsubscribe function
    return () => {
      const listeners = this.listeners.get(eventType);
      const index = listeners.indexOf(listener);
      if (index > -1) listeners.splice(index, 1);
    };
  }

  async publish(event) {
    const listeners = this.listeners.get(event.type) || [];
    await Promise.all(listeners.map((listener) => listener(event)));
  }
}

// Dependency injection container
class DIContainer {
  constructor() {
    this.services = new Map();
    this.singletons = new Map();
  }

  register(name, factory, options = {}) {
    this.services.set(name, {
      factory,
      singleton: options.singleton || false,
      dependencies: options.dependencies || [],
    });
  }

  resolve(name) {
    const service = this.services.get(name);
    if (!service) {
      throw new Error(`Service ${name} not found`);
    }

    if (service.singleton && this.singletons.has(name)) {
      return this.singletons.get(name);
    }

    const dependencies = service.dependencies.map((dep) => this.resolve(dep));
    const instance = service.factory(...dependencies);

    if (service.singleton) {
      this.singletons.set(name, instance);
    }

    return instance;
  }
}
```

### 176. What are streaming and reactive patterns?

**Answer:**

```javascript
// Readable stream implementation
class CustomReadableStream {
  constructor() {
    this.readable = new ReadableStream({
      start(controller) {
        this.controller = controller;
      },

      pull(controller) {
        // Called when internal queue is not full
      },

      cancel(reason) {
        // Called when stream is cancelled
      },
    });
  }

  push(chunk) {
    this.controller.enqueue(chunk);
  }

  close() {
    this.controller.close();
  }

  error(err) {
    this.controller.error(err);
  }
}

// Transform stream for processing
class JSONTransformStream extends TransformStream {
  constructor() {
    let buffer = "";

    super({
      transform(chunk, controller) {
        buffer += new TextDecoder().decode(chunk);
        const lines = buffer.split("\n");
        buffer = lines.pop(); // Keep incomplete line

        lines.forEach((line) => {
          if (line.trim()) {
            try {
              const parsed = JSON.parse(line);
              controller.enqueue(parsed);
            } catch (e) {
              controller.error(e);
            }
          }
        });
      },

      flush(controller) {
        if (buffer.trim()) {
          try {
            const parsed = JSON.parse(buffer);
            controller.enqueue(parsed);
          } catch (e) {
            controller.error(e);
          }
        }
      },
    });
  }
}

// Reactive streams with backpressure
class ReactiveStream {
  constructor() {
    this.subscribers = [];
    this.buffer = [];
    this.bufferSize = 100;
  }

  subscribe(observer) {
    this.subscribers.push(observer);
    return () => {
      const index = this.subscribers.indexOf(observer);
      if (index > -1) this.subscribers.splice(index, 1);
    };
  }

  next(value) {
    if (this.subscribers.length === 0) {
      if (this.buffer.length < this.bufferSize) {
        this.buffer.push(value);
      } else {
        this.buffer.shift(); // Drop oldest
        this.buffer.push(value);
      }
      return;
    }

    this.subscribers.forEach((observer) => {
      try {
        observer.next(value);
      } catch (error) {
        observer.error && observer.error(error);
      }
    });
  }

  pipe(...operators) {
    return operators.reduce((stream, operator) => operator(stream), this);
  }
}

// Stream operators
const streamOperators = {
  map: (fn) => (source) => {
    const output = new ReactiveStream();
    source.subscribe({
      next: (value) => output.next(fn(value)),
      error: (err) => output.error(err),
      complete: () => output.complete(),
    });
    return output;
  },

  filter: (predicate) => (source) => {
    const output = new ReactiveStream();
    source.subscribe({
      next: (value) => predicate(value) && output.next(value),
      error: (err) => output.error(err),
      complete: () => output.complete(),
    });
    return output;
  },

  debounce: (delay) => (source) => {
    const output = new ReactiveStream();
    let timeoutId;

    source.subscribe({
      next: (value) => {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => output.next(value), delay);
      },
      error: (err) => output.error(err),
      complete: () => output.complete(),
    });

    return output;
  },
};
```

### 177. What are Web Assembly (WASM) integration patterns?

**Answer:**

```javascript
// Loading and using WASM modules
class WasmLoader {
  static async loadModule(wasmPath) {
    const wasmModule = await WebAssembly.instantiateStreaming(fetch(wasmPath));
    return wasmModule.instance.exports;
  }

  static async loadWithImports(wasmPath, imports) {
    const wasmModule = await WebAssembly.instantiateStreaming(
      fetch(wasmPath),
      imports
    );
    return wasmModule.instance.exports;
  }
}

// WASM memory management
class WasmMemoryManager {
  constructor(wasmExports) {
    this.exports = wasmExports;
    this.memory = wasmExports.memory;
    this.malloc = wasmExports.malloc;
    this.free = wasmExports.free;
  }

  allocateString(str) {
    const encoder = new TextEncoder();
    const bytes = encoder.encode(str);
    const ptr = this.malloc(bytes.length + 1);
    const buffer = new Uint8Array(this.memory.buffer);

    buffer.set(bytes, ptr);
    buffer[ptr + bytes.length] = 0; // Null terminator

    return ptr;
  }

  readString(ptr) {
    const buffer = new Uint8Array(this.memory.buffer);
    let length = 0;

    while (buffer[ptr + length] !== 0) {
      length++;
    }

    const decoder = new TextDecoder();
    return decoder.decode(buffer.slice(ptr, ptr + length));
  }

  deallocate(ptr) {
    this.free(ptr);
  }
}

// High-performance computing with WASM
class MathProcessor {
  constructor() {
    this.wasmModule = null;
  }

  async initialize() {
    this.wasmModule = await WasmLoader.loadModule("/math.wasm");
  }

  processLargeArray(array) {
    if (!this.wasmModule) {
      throw new Error("WASM module not initialized");
    }

    // Allocate memory in WASM
    const inputPtr = this.wasmModule.malloc(array.length * 4); // 4 bytes per float
    const outputPtr = this.wasmModule.malloc(array.length * 4);

    // Copy data to WASM memory
    const inputView = new Float32Array(
      this.wasmModule.memory.buffer,
      inputPtr,
      array.length
    );
    inputView.set(array);

    // Call WASM function
    this.wasmModule.process_array(inputPtr, outputPtr, array.length);

    // Read result
    const outputView = new Float32Array(
      this.wasmModule.memory.buffer,
      outputPtr,
      array.length
    );
    const result = Array.from(outputView);

    // Cleanup
    this.wasmModule.free(inputPtr);
    this.wasmModule.free(outputPtr);

    return result;
  }
}
```

### 178. What are advanced browser API patterns?

**Answer:**

```javascript
// File system access (Origin Private File System)
class FileSystemManager {
  constructor() {
    this.opfsRoot = null;
  }

  async initialize() {
    this.opfsRoot = await navigator.storage.getDirectory();
  }

  async writeFile(filename, data) {
    const fileHandle = await this.opfsRoot.getFileHandle(filename, {
      create: true,
    });
    const writable = await fileHandle.createWritable();
    await writable.write(data);
    await writable.close();
  }

  async readFile(filename) {
    const fileHandle = await this.opfsRoot.getFileHandle(filename);
    const file = await fileHandle.getFile();
    return await file.text();
  }

  async deleteFile(filename) {
    await this.opfsRoot.removeEntry(filename);
  }

  async listFiles() {
    const files = [];
    for await (const [name, handle] of this.opfsRoot.entries()) {
      if (handle.kind === "file") {
        files.push(name);
      }
    }
    return files;
  }
}

// Advanced WebRTC patterns
class P2PConnection {
  constructor() {
    this.peerConnection = new RTCPeerConnection({
      iceServers: [{ urls: "stun:stun.l.google.com:19302" }],
    });
    this.dataChannel = null;
    this.onMessage = null;
  }

  async createOffer() {
    this.dataChannel = this.peerConnection.createDataChannel("messages");
    this.setupDataChannel();

    const offer = await this.peerConnection.createOffer();
    await this.peerConnection.setLocalDescription(offer);
    return offer;
  }

  async createAnswer(offer) {
    await this.peerConnection.setRemoteDescription(offer);

    this.peerConnection.ondatachannel = (event) => {
      this.dataChannel = event.channel;
      this.setupDataChannel();
    };

    const answer = await this.peerConnection.createAnswer();
    await this.peerConnection.setLocalDescription(answer);
    return answer;
  }

  async addAnswer(answer) {
    await this.peerConnection.setRemoteDescription(answer);
  }

  async addIceCandidate(candidate) {
    await this.peerConnection.addIceCandidate(candidate);
  }

  setupDataChannel() {
    this.dataChannel.onopen = () => console.log("Data channel opened");
    this.dataChannel.onmessage = (event) => {
      if (this.onMessage) this.onMessage(event.data);
    };
  }

  send(message) {
    if (this.dataChannel && this.dataChannel.readyState === "open") {
      this.dataChannel.send(message);
    }
  }
}

// Media streaming patterns
class MediaStreamProcessor {
  constructor() {
    this.audioContext = null;
    this.videoProcessor = null;
  }

  async setupAudioProcessing(stream) {
    this.audioContext = new AudioContext();
    const source = this.audioContext.createMediaStreamSource(stream);

    // Add effects
    const gainNode = this.audioContext.createGain();
    const filterNode = this.audioContext.createBiquadFilter();

    filterNode.type = "lowpass";
    filterNode.frequency.value = 1000;

    source.connect(filterNode);
    filterNode.connect(gainNode);
    gainNode.connect(this.audioContext.destination);

    return { gainNode, filterNode };
  }

  async setupVideoProcessing(stream) {
    const video = document.createElement("video");
    const canvas = document.createElement("canvas");
    const ctx = canvas.getContext("2d");

    video.srcObject = stream;
    video.play();

    video.onloadedmetadata = () => {
      canvas.width = video.videoWidth;
      canvas.height = video.videoHeight;
    };

    // Process frames
    const processFrame = () => {
      ctx.drawImage(video, 0, 0);
      const imageData = ctx.getImageData(0, 0, canvas.width, canvas.height);

      // Apply effects (e.g., grayscale)
      for (let i = 0; i < imageData.data.length; i += 4) {
        const avg =
          (imageData.data[i] + imageData.data[i + 1] + imageData.data[i + 2]) /
          3;
        imageData.data[i] = avg; // Red
        imageData.data[i + 1] = avg; // Green
        imageData.data[i + 2] = avg; // Blue
      }

      ctx.putImageData(imageData, 0, 0);
      requestAnimationFrame(processFrame);
    };

    processFrame();
    return canvas.captureStream();
  }
}

// Battery and device info patterns
class DeviceMonitor {
  constructor() {
    this.battery = null;
    this.connection = null;
  }

  async initialize() {
    if ("getBattery" in navigator) {
      this.battery = await navigator.getBattery();
      this.setupBatteryListeners();
    }

    if ("connection" in navigator) {
      this.connection = navigator.connection;
      this.setupConnectionListeners();
    }
  }

  setupBatteryListeners() {
    this.battery.addEventListener("chargingchange", () => {
      console.log("Charging:", this.battery.charging);
    });

    this.battery.addEventListener("levelchange", () => {
      console.log("Battery level:", this.battery.level * 100 + "%");
    });
  }

  setupConnectionListeners() {
    this.connection.addEventListener("change", () => {
      console.log("Connection type:", this.connection.effectiveType);
      console.log("Downlink:", this.connection.downlink);
    });
  }

  getDeviceInfo() {
    return {
      battery: this.battery
        ? {
            level: this.battery.level,
            charging: this.battery.charging,
            chargingTime: this.battery.chargingTime,
            dischargingTime: this.battery.dischargingTime,
          }
        : null,
      connection: this.connection
        ? {
            effectiveType: this.connection.effectiveType,
            downlink: this.connection.downlink,
            rtt: this.connection.rtt,
            saveData: this.connection.saveData,
          }
        : null,
      memory: "memory" in performance ? performance.memory : null,
      hardwareConcurrency: navigator.hardwareConcurrency,
    };
  }
}
```

### 179. What are advanced debugging and profiling techniques?

**Answer:**

```javascript
// Performance profiler
class PerformanceProfiler {
  constructor() {
    this.marks = new Map();
    this.measures = [];
  }

  mark(name) {
    this.marks.set(name, performance.now());
    performance.mark(name);
  }

  measure(name, startMark, endMark) {
    const start = this.marks.get(startMark);
    const end = this.marks.get(endMark) || performance.now();
    const duration = end - start;

    this.measures.push({ name, duration, start, end });
    performance.measure(name, startMark, endMark);

    return duration;
  }

  profile(fn, name = "anonymous") {
    return async (...args) => {
      const startMark = `${name}-start`;
      const endMark = `${name}-end`;

      this.mark(startMark);
      const result = await fn.apply(this, args);
      this.mark(endMark);

      const duration = this.measure(name, startMark, endMark);
      console.log(`${name} took ${duration.toFixed(2)}ms`);

      return result;
    };
  }

  getReport() {
    return {
      measures: this.measures,
      performanceEntries: performance.getEntriesByType("measure"),
      memoryInfo: performance.memory,
    };
  }
}

// Memory leak detector
class MemoryLeakDetector {
  constructor() {
    this.baseline = null;
    this.snapshots = [];
    this.observers = [];
  }

  takeSnapshot(label) {
    if (performance.memory) {
      const snapshot = {
        label,
        timestamp: Date.now(),
        usedJSHeapSize: performance.memory.usedJSHeapSize,
        totalJSHeapSize: performance.memory.totalJSHeapSize,
        jsHeapSizeLimit: performance.memory.jsHeapSizeLimit,
      };

      this.snapshots.push(snapshot);

      if (!this.baseline) {
        this.baseline = snapshot;
      }

      return snapshot;
    }
    return null;
  }

  analyzeLeaks() {
    if (this.snapshots.length < 2) return null;

    const latest = this.snapshots[this.snapshots.length - 1];
    const previous = this.snapshots[this.snapshots.length - 2];

    const growth = latest.usedJSHeapSize - previous.usedJSHeapSize;
    const totalGrowth = latest.usedJSHeapSize - this.baseline.usedJSHeapSize;

    return {
      growth,
      totalGrowth,
      growthRate: growth / (latest.timestamp - previous.timestamp),
      percentageIncrease: (totalGrowth / this.baseline.usedJSHeapSize) * 100,
    };
  }

  startMonitoring(interval = 5000) {
    const monitor = setInterval(() => {
      const snapshot = this.takeSnapshot(`auto-${Date.now()}`);
      const analysis = this.analyzeLeaks();

      if (analysis && analysis.percentageIncrease > 50) {
        console.warn("Potential memory leak detected:", analysis);
      }
    }, interval);

    this.observers.push(monitor);
    return monitor;
  }

  stopMonitoring() {
    this.observers.forEach((observer) => clearInterval(observer));
    this.observers = [];
  }
}

// Advanced error tracking
class ErrorTracker {
  constructor() {
    this.errors = [];
    this.listeners = [];
    this.setupGlobalHandlers();
  }

  setupGlobalHandlers() {
    window.addEventListener("error", (event) => {
      this.trackError({
        type: "javascript",
        message: event.message,
        filename: event.filename,
        lineno: event.lineno,
        colno: event.colno,
        error: event.error,
        stack: event.error?.stack,
        timestamp: Date.now(),
        userAgent: navigator.userAgent,
        url: window.location.href,
      });
    });

    window.addEventListener("unhandledrejection", (event) => {
      this.trackError({
        type: "unhandled-promise",
        message: event.reason?.message || "Unhandled promise rejection",
        error: event.reason,
        stack: event.reason?.stack,
        timestamp: Date.now(),
        userAgent: navigator.userAgent,
        url: window.location.href,
      });
    });
  }

  trackError(errorInfo) {
    // Add context information
    const enhancedError = {
      ...errorInfo,
      id: crypto.randomUUID(),
      sessionId: this.getSessionId(),
      userId: this.getUserId(),
      breadcrumbs: this.getBreadcrumbs(),
      deviceInfo: this.getDeviceInfo(),
    };

    this.errors.push(enhancedError);
    this.notifyListeners(enhancedError);

    // Send to error reporting service
    this.reportError(enhancedError);
  }

  addBreadcrumb(message, category = "info", data = {}) {
    if (!this.breadcrumbs) this.breadcrumbs = [];

    this.breadcrumbs.push({
      message,
      category,
      data,
      timestamp: Date.now(),
    });

    // Keep only last 50 breadcrumbs
    if (this.breadcrumbs.length > 50) {
      this.breadcrumbs.shift();
    }
  }

  getBreadcrumbs() {
    return this.breadcrumbs || [];
  }

  getSessionId() {
    if (!this.sessionId) {
      this.sessionId =
        sessionStorage.getItem("sessionId") || crypto.randomUUID();
      sessionStorage.setItem("sessionId", this.sessionId);
    }
    return this.sessionId;
  }

  getUserId() {
    return localStorage.getItem("userId") || "anonymous";
  }

  getDeviceInfo() {
    return {
      userAgent: navigator.userAgent,
      platform: navigator.platform,
      language: navigator.language,
      cookieEnabled: navigator.cookieEnabled,
      onLine: navigator.onLine,
      screen: {
        width: screen.width,
        height: screen.height,
        colorDepth: screen.colorDepth,
      },
      viewport: {
        width: window.innerWidth,
        height: window.innerHeight,
      },
    };
  }

  async reportError(errorInfo) {
    try {
      await fetch("/api/errors", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify(errorInfo),
      });
    } catch (reportingError) {
      console.error("Failed to report error:", reportingError);
    }
  }

  subscribe(listener) {
    this.listeners.push(listener);
    return () => {
      const index = this.listeners.indexOf(listener);
      if (index > -1) this.listeners.splice(index, 1);
    };
  }

  notifyListeners(errorInfo) {
    this.listeners.forEach((listener) => {
      try {
        listener(errorInfo);
      } catch (e) {
        console.error("Error listener failed:", e);
      }
    });
  }
}
```

### 180. What are micro-frontend patterns?

**Answer:**

```javascript
// Module federation runtime
class ModuleFederation {
  constructor() {
    this.remotes = new Map();
    this.shared = new Map();
  }

  registerRemote(name, url) {
    this.remotes.set(name, { url, loaded: false, module: null });
  }

  async loadRemote(name) {
    const remote = this.remotes.get(name);
    if (!remote) throw new Error(`Remote ${name} not found`);

    if (remote.loaded) return remote.module;

    const script = document.createElement("script");
    script.src = remote.url;
    script.type = "module";

    return new Promise((resolve, reject) => {
      script.onload = async () => {
        try {
          const module = await import(remote.url);
          remote.module = module;
          remote.loaded = true;
          resolve(module);
        } catch (error) {
          reject(error);
        }
      };

      script.onerror = reject;
      document.head.appendChild(script);
    });
  }

  shareModule(name, module) {
    this.shared.set(name, module);
  }

  getShared(name) {
    return this.shared.get(name);
  }
}

// Single-SPA style micro-frontend orchestrator
class MicroFrontendOrchestrator {
  constructor() {
    this.apps = new Map();
    this.currentApp = null;
  }

  registerApp(name, config) {
    this.apps.set(name, {
      ...config,
      status: "NOT_LOADED",
    });
  }

  async loadApp(name) {
    const app = this.apps.get(name);
    if (!app) throw new Error(`App ${name} not found`);

    if (app.status === "LOADED") return app;

    app.status = "LOADING";

    try {
      const module = await import(app.url);

      app.mount = module.mount || (() => {});
      app.unmount = module.unmount || (() => {});
      app.update = module.update || (() => {});

      app.status = "LOADED";
      return app;
    } catch (error) {
      app.status = "LOAD_ERROR";
      throw error;
    }
  }

  async mountApp(name, container) {
    const app = await this.loadApp(name);

    if (this.currentApp && this.currentApp !== app) {
      await this.unmountApp(this.currentApp.name);
    }

    app.status = "MOUNTING";
    await app.mount(container);
    app.status = "MOUNTED";

    this.currentApp = app;
  }

  async unmountApp(name) {
    const app = this.apps.get(name);
    if (!app || app.status !== "MOUNTED") return;

    app.status = "UNMOUNTING";
    await app.unmount();
    app.status = "LOADED";

    if (this.currentApp === app) {
      this.currentApp = null;
    }
  }

  async navigateToApp(name, container) {
    await this.mountApp(name, container);
  }
}

// Shared state management across micro-frontends
class SharedStateManager {
  constructor() {
    this.state = {};
    this.subscribers = new Map();
    this.middleware = [];
  }

  subscribe(selector, callback) {
    const key =
      typeof selector === "string" ? selector : JSON.stringify(selector);

    if (!this.subscribers.has(key)) {
      this.subscribers.set(key, []);
    }

    this.subscribers.get(key).push(callback);

    return () => {
      const callbacks = this.subscribers.get(key);
      const index = callbacks.indexOf(callback);
      if (index > -1) callbacks.splice(index, 1);
    };
  }

  setState(path, value) {
    const oldState = { ...this.state };

    // Set nested property
    const keys = path.split(".");
    let current = this.state;

    for (let i = 0; i < keys.length - 1; i++) {
      if (!(keys[i] in current)) {
        current[keys[i]] = {};
      }
      current = current[keys[i]];
    }

    current[keys[keys.length - 1]] = value;

    // Run middleware
    this.middleware.forEach((middleware) => {
      middleware({
        type: "SET_STATE",
        path,
        value,
        oldState,
        newState: this.state,
      });
    });

    // Notify subscribers
    this.notifySubscribers(path);
  }

  getState(path) {
    if (!path) return this.state;

    const keys = path.split(".");
    let current = this.state;

    for (const key of keys) {
      if (current[key] === undefined) return undefined;
      current = current[key];
    }

    return current;
  }

  notifySubscribers(path) {
    // Notify exact path subscribers
    const exactSubscribers = this.subscribers.get(path) || [];
    exactSubscribers.forEach((callback) => callback(this.getState(path)));

    // Notify wildcard subscribers
    const wildcardSubscribers = this.subscribers.get("*") || [];
    wildcardSubscribers.forEach((callback) => callback(this.state));
  }

  addMiddleware(middleware) {
    this.middleware.push(middleware);
  }
}

// Cross-frame communication
class CrossFrameMessenger {
  constructor() {
    this.handlers = new Map();
    this.setupMessageListener();
  }

  setupMessageListener() {
    window.addEventListener("message", (event) => {
      const { type, payload, id } = event.data;

      if (this.handlers.has(type)) {
        const handler = this.handlers.get(type);
        const result = handler(payload);

        // Send response if ID provided
        if (id) {
          event.source.postMessage(
            {
              type: `${type}_RESPONSE`,
              payload: result,
              id,
            },
            event.origin
          );
        }
      }
    });
  }

  on(type, handler) {
    this.handlers.set(type, handler);
  }

  send(targetWindow, type, payload) {
    targetWindow.postMessage({ type, payload }, "*");
  }

  async sendWithResponse(targetWindow, type, payload, timeout = 5000) {
    const id = crypto.randomUUID();

    return new Promise((resolve, reject) => {
      const timer = setTimeout(() => {
        reject(new Error("Message timeout"));
      }, timeout);

      const responseHandler = (event) => {
        if (event.data.type === `${type}_RESPONSE` && event.data.id === id) {
          clearTimeout(timer);
          window.removeEventListener("message", responseHandler);
          resolve(event.data.payload);
        }
      };

      window.addEventListener("message", responseHandler);

      targetWindow.postMessage({ type, payload, id }, "*");
    });
  }
}
```

---

## Expert Level

### 251. What are the internals of JavaScript engines optimization?

**Answer:** JavaScript engines use several optimization strategies:

```javascript
// Hidden class optimization - keep object shapes consistent
function Point(x, y) {
  this.x = x; // Always initialize properties in same order
  this.y = y;
}

// Inline caching - monomorphic calls are faster
function processPoint(point) {
  return point.x + point.y; // V8 can inline this for Point objects
}

// Avoid polymorphic calls
function slowProcessing(obj) {
  return obj.value; // Different object shapes make this slow
}

// Loop optimization - avoid changing loop variables inside
function optimizedLoop(arr) {
  for (let i = 0; i < arr.length; i++) {
    // Length is cached
    process(arr[i]);
  }
}

// Function inlining - small functions get inlined
function add(a, b) {
  return a + b;
} // Likely to be inlined
function calculate(x) {
  return add(x, 5); // add() might be inlined here
}
```

### 252. How does garbage collection work in V8?

**Answer:** V8 uses generational garbage collection with multiple strategies:

```javascript
// Generational hypothesis - most objects die young
class GCDemo {
  constructor() {
    this.data = new Array(1000000).fill(0); // Old generation
  }

  processData() {
    const temp = this.data.map((x) => x * 2); // Young generation
    return temp.reduce((a, b) => a + b); // temp becomes garbage quickly
  }
}

// Weak references don't prevent GC
class CacheWithWeakRef {
  constructor() {
    this.cache = new Map();
  }

  set(key, value) {
    this.cache.set(key, new WeakRef(value));
  }

  get(key) {
    const ref = this.cache.get(key);
    const value = ref?.deref();

    if (!value) {
      this.cache.delete(key); // Object was garbage collected
    }

    return value;
  }
}

// FinalizationRegistry for cleanup
const cleanup = new FinalizationRegistry((filename) => {
  console.log(`Cleaning up file: ${filename}`);
  // Cleanup operations
});

class FileHandler {
  constructor(filename) {
    this.filename = filename;
    cleanup.register(this, filename, this);
  }
}
```

### 253. What are advanced compilation techniques in JavaScript?

**Answer:** Modern JavaScript engines use sophisticated compilation:

```javascript
// Speculative optimization - engines guess types
function speculativeAdd(a, b) {
  return a + b; // V8 assumes numbers, compiles optimized version
}

speculativeAdd(1, 2); // Confirms number assumption
speculativeAdd(3, 4); // Still numbers, stays optimized
speculativeAdd("hello", "world"); // Deoptimizes!

// Loop unrolling optimization
function unrolledSum(arr) {
  let sum = 0;
  // Engine might unroll small, predictable loops
  for (let i = 0; i < 4; i++) {
    sum += arr[i];
  }
  return sum;
}

// Profile-guided optimization
function hotPath(condition) {
  if (condition) {
    // If this is usually true...
    return expensiveCalculation(); // This path gets optimized
  } else {
    return fallbackCalculation(); // This path stays interpreted
  }
}

// Escape analysis - stack allocation for non-escaping objects
function noEscape() {
  const obj = { x: 1, y: 2 }; // Might be allocated on stack
  return obj.x + obj.y; // obj doesn't escape function
}

function escapes() {
  const obj = { x: 1, y: 2 }; // Must be heap allocated
  return obj; // obj escapes function
}
```

### 254. What are advanced memory management patterns?

**Answer:**

```javascript
// Custom memory allocator for performance-critical code
class MemoryPool {
  constructor(itemSize, poolSize) {
    this.itemSize = itemSize;
    this.buffer = new ArrayBuffer(itemSize * poolSize);
    this.freeList = [];
    this.views = [];

    // Initialize free list
    for (let i = 0; i < poolSize; i++) {
      this.freeList.push(i * itemSize);
      this.views.push(new DataView(this.buffer, i * itemSize, itemSize));
    }
  }

  allocate() {
    if (this.freeList.length === 0) {
      throw new Error("Memory pool exhausted");
    }

    const offset = this.freeList.pop();
    return {
      view: new DataView(this.buffer, offset, this.itemSize),
      offset,
      free: () => this.freeList.push(offset),
    };
  }

  getUtilization() {
    const total = this.views.length;
    const free = this.freeList.length;
    return (total - free) / total;
  }
}

// Copy-on-write data structures
class COWArray {
  constructor(data = []) {
    this.data = data;
    this.refs = 1;
  }

  clone() {
    this.refs++;
    const clone = Object.create(COWArray.prototype);
    clone.data = this.data;
    clone.refs = this.refs;
    return clone;
  }

  push(item) {
    if (this.refs > 1) {
      // Copy before write
      this.data = [...this.data];
      this.refs = 1;
    }
    this.data.push(item);
    return this;
  }

  get(index) {
    return this.data[index];
  }
}

// Memory-mapped file simulation
class VirtualMemoryMap {
  constructor(size, pageSize = 4096) {
    this.size = size;
    this.pageSize = pageSize;
    this.pages = new Map();
    this.accessPattern = new Map();
  }

  read(offset, length) {
    const startPage = Math.floor(offset / this.pageSize);
    const endPage = Math.floor((offset + length - 1) / this.pageSize);

    for (let page = startPage; page <= endPage; page++) {
      this.ensurePageLoaded(page);
      this.recordAccess(page);
    }

    // Simulate reading across pages
    const result = new Uint8Array(length);
    let resultOffset = 0;

    for (let page = startPage; page <= endPage; page++) {
      const pageData = this.pages.get(page);
      const pageOffset = page === startPage ? offset % this.pageSize : 0;
      const bytesToCopy = Math.min(
        this.pageSize - pageOffset,
        length - resultOffset
      );

      result.set(
        pageData.subarray(pageOffset, pageOffset + bytesToCopy),
        resultOffset
      );
      resultOffset += bytesToCopy;
    }

    return result;
  }

  ensurePageLoaded(pageIndex) {
    if (!this.pages.has(pageIndex)) {
      // Simulate loading page from storage
      const page = new Uint8Array(this.pageSize);
      page.fill(pageIndex); // Dummy data
      this.pages.set(pageIndex, page);
    }
  }

  recordAccess(pageIndex) {
    const now = performance.now();
    this.accessPattern.set(pageIndex, now);

    // LRU eviction
    if (this.pages.size > 100) {
      // Max 100 pages in memory
      const lruPage = Array.from(this.accessPattern.entries()).sort(
        ([, a], [, b]) => a - b
      )[0][0];

      this.pages.delete(lruPage);
      this.accessPattern.delete(lruPage);
    }
  }
}
```

### 255. What are advanced concurrency and parallelism patterns?

**Answer:**

```javascript
// Lock-free data structures using atomics
class LockFreeQueue {
  constructor(size) {
    this.buffer = new SharedArrayBuffer(size * 4 + 8);
    this.data = new Int32Array(this.buffer, 0, size);
    this.head = new Int32Array(this.buffer, size * 4, 1);
    this.tail = new Int32Array(this.buffer, size * 4 + 4, 1);
    this.size = size;
  }

  enqueue(value) {
    while (true) {
      const currentTail = Atomics.load(this.tail, 0);
      const nextTail = (currentTail + 1) % this.size;

      if (nextTail === Atomics.load(this.head, 0)) {
        return false; // Queue full
      }

      if (
        Atomics.compareExchange(this.tail, 0, currentTail, nextTail) ===
        currentTail
      ) {
        Atomics.store(this.data, currentTail, value);
        return true;
      }
    }
  }

  dequeue() {
    while (true) {
      const currentHead = Atomics.load(this.head, 0);

      if (currentHead === Atomics.load(this.tail, 0)) {
        return null; // Queue empty
      }

      const value = Atomics.load(this.data, currentHead);
      const nextHead = (currentHead + 1) % this.size;

      if (
        Atomics.compareExchange(this.head, 0, currentHead, nextHead) ===
        currentHead
      ) {
        return value;
      }
    }
  }
}

// Work-stealing scheduler
class WorkStealingScheduler {
  constructor(numWorkers) {
    this.workers = [];
    this.queues = [];

    for (let i = 0; i < numWorkers; i++) {
      const queue = [];
      this.queues.push(queue);

      const worker = new Worker(
        `
                const queue = [];
                let running = true;
                
                self.onmessage = function(e) {
                    if (e.data.type === 'task') {
                        queue.push(e.data.task);
                        processQueue();
                    } else if (e.data.type === 'steal') {
                        const task = queue.pop(); // Steal from end
                        self.postMessage({type: 'stolen', task, workerId: ${i}});
                    } else if (e.data.type === 'stop') {
                        running = false;
                    }
                };
                
                function processQueue() {
                    while (queue.length > 0 && running) {
                        const task = queue.shift(); // Process from front
                        if (task) {
                            try {
                                const result = eval(\`(\${task.code})\`)(...task.args);
                                self.postMessage({
                                    type: 'result',
                                    taskId: task.id,
                                    result,
                                    workerId: ${i}
                                });
                            } catch (error) {
                                self.postMessage({
                                    type: 'error',
                                    taskId: task.id,
                                    error: error.message,
                                    workerId: ${i}
                                });
                            }
                        }
                    }
                    
                    // Try to steal work if idle
                    if (queue.length === 0) {
                        self.postMessage({type: 'idle', workerId: ${i}});
                    }
                }
            `,
        { type: "module" }
      );

      this.workers.push(worker);
    }
  }

  schedule(task) {
    // Add to least loaded queue
    const leastLoadedIndex = this.queues.reduce(
      (minIndex, queue, index) =>
        queue.length < this.queues[minIndex].length ? index : minIndex,
      0
    );

    this.queues[leastLoadedIndex].push(task);
    this.workers[leastLoadedIndex].postMessage({ type: "task", task });
  }

  stealWork(idleWorkerId) {
    // Find most loaded queue
    const mostLoadedIndex = this.queues.reduce(
      (maxIndex, queue, index) =>
        queue.length > this.queues[maxIndex].length ? index : maxIndex,
      0
    );

    if (this.queues[mostLoadedIndex].length > 1) {
      this.workers[mostLoadedIndex].postMessage({ type: "steal" });
    }
  }
}

// Continuation-passing style for cooperative multitasking
class CooperativeScheduler {
  constructor() {
    this.tasks = [];
    this.running = false;
    this.quantum = 16; // 16ms time slice
  }

  schedule(taskGenerator) {
    const task = {
      generator: taskGenerator,
      iterator: taskGenerator(),
      priority: 0,
      startTime: performance.now(),
    };

    this.tasks.push(task);

    if (!this.running) {
      this.run();
    }
  }

  run() {
    this.running = true;

    const runSlice = () => {
      if (this.tasks.length === 0) {
        this.running = false;
        return;
      }

      const startTime = performance.now();

      while (
        this.tasks.length > 0 &&
        performance.now() - startTime < this.quantum
      ) {
        const task = this.tasks.shift();

        try {
          const result = task.iterator.next();

          if (!result.done) {
            // Task yielded, reschedule
            task.priority++;
            this.insertByPriority(task);
          }
        } catch (error) {
          console.error("Task error:", error);
        }
      }

      // Continue in next frame
      requestAnimationFrame(runSlice);
    };

    requestAnimationFrame(runSlice);
  }

  insertByPriority(task) {
    let insertIndex = 0;
    while (
      insertIndex < this.tasks.length &&
      this.tasks[insertIndex].priority <= task.priority
    ) {
      insertIndex++;
    }
    this.tasks.splice(insertIndex, 0, task);
  }
}

// Usage example
function* longRunningTask() {
  for (let i = 0; i < 1000000; i++) {
    // Do some work
    if (i % 1000 === 0) {
      yield; // Yield control back to scheduler
    }
  }
}
```

### 256. What are advanced reactive programming patterns?

**Answer:**

```javascript
// Cold vs Hot Observables
class ColdObservable {
  constructor(subscriber) {
    this.subscriber = subscriber;
  }

  subscribe(observer) {
    // Each subscription gets its own execution
    return this.subscriber(observer);
  }
}

class HotObservable {
  constructor() {
    this.observers = [];
    this.value = null;
    this.hasValue = false;
  }

  subscribe(observer) {
    this.observers.push(observer);

    // Hot observables share the same execution
    if (this.hasValue) {
      observer.next(this.value);
    }

    return () => {
      const index = this.observers.indexOf(observer);
      if (index > -1) this.observers.splice(index, 1);
    };
  }

  next(value) {
    this.value = value;
    this.hasValue = true;
    this.observers.forEach((observer) => observer.next(value));
  }
}

// Subject (both Observable and Observer)
class Subject {
  constructor() {
    this.observers = [];
    this.closed = false;
    this.error = null;
  }

  subscribe(observer) {
    if (this.closed) {
      if (this.error) {
        observer.error(this.error);
      } else {
        observer.complete();
      }
      return () => {};
    }

    this.observers.push(observer);
    return () => {
      const index = this.observers.indexOf(observer);
      if (index > -1) this.observers.splice(index, 1);
    };
  }

  next(value) {
    if (!this.closed) {
      this.observers.forEach((observer) => observer.next(value));
    }
  }

  error(err) {
    if (!this.closed) {
      this.closed = true;
      this.error = err;
      this.observers.forEach((observer) => observer.error(err));
      this.observers = [];
    }
  }

  complete() {
    if (!this.closed) {
      this.closed = true;
      this.observers.forEach((observer) => observer.complete());
      this.observers = [];
    }
  }
}

// Reactive operators
const operators = {
  map: (fn) => (source) =>
    new ColdObservable((observer) => {
      return source.subscribe({
        next: (value) => observer.next(fn(value)),
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    }),

  filter: (predicate) => (source) =>
    new ColdObservable((observer) => {
      return source.subscribe({
        next: (value) => predicate(value) && observer.next(value),
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    }),

  debounceTime: (delay) => (source) =>
    new ColdObservable((observer) => {
      let timeoutId;

      return source.subscribe({
        next: (value) => {
          clearTimeout(timeoutId);
          timeoutId = setTimeout(() => observer.next(value), delay);
        },
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    }),

  switchMap: (fn) => (source) =>
    new ColdObservable((observer) => {
      let innerSubscription;

      const subscription = source.subscribe({
        next: (value) => {
          if (innerSubscription) {
            innerSubscription(); // Unsubscribe from previous inner observable
          }

          const innerObservable = fn(value);
          innerSubscription = innerObservable.subscribe({
            next: (innerValue) => observer.next(innerValue),
            error: (err) => observer.error(err),
            complete: () => {}, // Don't complete outer observable
          });
        },
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });

      return () => {
        subscription();
        if (innerSubscription) innerSubscription();
      };
    }),

  combineLatest: (...sources) =>
    new ColdObservable((observer) => {
      const values = new Array(sources.length);
      const hasValue = new Array(sources.length).fill(false);
      let completedCount = 0;

      const subscriptions = sources.map((source, index) => {
        return source.subscribe({
          next: (value) => {
            values[index] = value;
            hasValue[index] = true;

            if (hasValue.every(Boolean)) {
              observer.next([...values]);
            }
          },
          error: (err) => observer.error(err),
          complete: () => {
            completedCount++;
            if (completedCount === sources.length) {
              observer.complete();
            }
          },
        });
      });

      return () => subscriptions.forEach((sub) => sub());
    }),
};

// Reactive state management
class ReactiveStore {
  constructor(initialState = {}) {
    this.state$ = new Subject();
    this.state = initialState;
    this.reducers = new Map();
    this.effects = [];
  }

  select(selector) {
    return new ColdObservable((observer) => {
      let lastSelected = selector(this.state);
      observer.next(lastSelected);

      return this.state$.subscribe({
        next: (state) => {
          const selected = selector(state);
          if (selected !== lastSelected) {
            lastSelected = selected;
            observer.next(selected);
          }
        },
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    });
  }

  dispatch(action) {
    const reducer = this.reducers.get(action.type);
    if (reducer) {
      const newState = reducer(this.state, action);
      if (newState !== this.state) {
        this.state = newState;
        this.state$.next(this.state);

        // Run effects
        this.effects.forEach((effect) => {
          try {
            effect(action, this.state);
          } catch (error) {
            console.error("Effect error:", error);
          }
        });
      }
    }
  }

  addReducer(actionType, reducer) {
    this.reducers.set(actionType, reducer);
  }

  addEffect(effect) {
    this.effects.push(effect);
  }
}
```

### 257. What are advanced compiler optimization techniques?

**Answer:**

```javascript
// Dead code elimination awareness
function optimizeForDCE() {
  if (process.env.NODE_ENV === "production") {
    return productionCode();
  } else {
    // This branch will be eliminated in production builds
    console.log("Development mode");
    return developmentCode();
  }
}

// Tree shaking friendly exports
// Good - named exports are tree-shakable
export function usedFunction() {
  /* ... */
}
export function unusedFunction() {
  /* ... */
} // Will be removed

// Bad - default export of object prevents tree shaking
export default {
  usedFunction() {
    /* ... */
  },
  unusedFunction() {
    /* ... */
  }, // Cannot be removed
};

// Constant folding optimization
const CONFIG = {
  API_URL: "https://api.example.com",
  MAX_RETRIES: 3,
  TIMEOUT: 5000,
};

// Bundler can inline these constants
function makeRequest() {
  return fetch(CONFIG.API_URL, {
    timeout: CONFIG.TIMEOUT,
  });
}

// Function inlining considerations
// Small, pure functions are good candidates for inlining
const add = (a, b) => a + b;
const multiply = (a, b) => a * b;

// This might be optimized to: (x + y) * 2
function calculate(x, y) {
  return multiply(add(x, y), 2);
}

// Loop optimization patterns
function efficientLoop(array) {
  // Hoist invariant computations
  const length = array.length;
  const multiplier = getMultiplier(); // Computed once

  // Use countdown loops when possible (faster comparison to 0)
  for (let i = length; i--; ) {
    array[i] *= multiplier;
  }
}

// Branch prediction friendly code
function predictableBranching(items) {
  // Sort by likelihood - most common case first
  return items.map((item) => {
    if (item.type === "common") {
      // 80% of cases
      return processCommon(item);
    } else if (item.type === "rare") {
      // 15% of cases
      return processRare(item);
    } else {
      // 5% of cases
      return processVeryRare(item);
    }
  });
}
```

### 258. What are advanced memory optimization patterns?

**Answer:**

```javascript
// Object pooling for frequent allocations
class ParticlePool {
  constructor(initialSize = 100) {
    this.pool = [];
    this.active = [];

    // Pre-allocate objects
    for (let i = 0; i < initialSize; i++) {
      this.pool.push(this.createParticle());
    }
  }

  createParticle() {
    return {
      x: 0,
      y: 0,
      z: 0,
      vx: 0,
      vy: 0,
      vz: 0,
      life: 1.0,
      reset() {
        this.x = this.y = this.z = 0;
        this.vx = this.vy = this.vz = 0;
        this.life = 1.0;
      },
    };
  }

  acquire() {
    let particle;

    if (this.pool.length > 0) {
      particle = this.pool.pop();
      particle.reset();
    } else {
      // Pool exhausted, create new one
      particle = this.createParticle();
    }

    this.active.push(particle);
    return particle;
  }

  release(particle) {
    const index = this.active.indexOf(particle);
    if (index > -1) {
      this.active.splice(index, 1);
      this.pool.push(particle);
    }
  }

  update(deltaTime) {
    for (let i = this.active.length - 1; i >= 0; i--) {
      const particle = this.active[i];
      particle.life -= deltaTime;

      if (particle.life <= 0) {
        this.release(particle);
      } else {
        // Update particle position
        particle.x += particle.vx * deltaTime;
        particle.y += particle.vy * deltaTime;
        particle.z += particle.vz * deltaTime;
      }
    }
  }
}

// String interning for memory efficiency
class StringInterner {
  constructor() {
    this.strings = new Map();
    this.reverseMap = new Map();
    this.nextId = 0;
  }

  intern(str) {
    if (this.strings.has(str)) {
      return this.strings.get(str);
    }

    const id = this.nextId++;
    this.strings.set(str, id);
    this.reverseMap.set(id, str);
    return id;
  }

  getString(id) {
    return this.reverseMap.get(id);
  }

  // Use for frequently compared strings
  compare(id1, id2) {
    return id1 === id2; // Much faster than string comparison
  }
}

// Flyweight pattern for reducing memory usage
class CharacterFlyweight {
  constructor(char, font, size) {
    this.char = char;
    this.font = font;
    this.size = size;
  }

  render(context, x, y, color) {
    context.font = `${this.size}px ${this.font}`;
    context.fillStyle = color;
    context.fillText(this.char, x, y);
  }
}

class CharacterFactory {
  constructor() {
    this.flyweights = new Map();
  }

  getFlyweight(char, font, size) {
    const key = `${char}-${font}-${size}`;

    if (!this.flyweights.has(key)) {
      this.flyweights.set(key, new CharacterFlyweight(char, font, size));
    }

    return this.flyweights.get(key);
  }

  getSize() {
    return this.flyweights.size;
  }
}

// Copy-on-write for large data structures
class COWMap {
  constructor(data = new Map()) {
    this.data = data;
    this.refCount = 1;
    this.isOriginal = true;
  }

  clone() {
    this.refCount++;
    const clone = new COWMap(this.data);
    clone.refCount = this.refCount;
    clone.isOriginal = false;
    return clone;
  }

  set(key, value) {
    if (this.refCount > 1 || !this.isOriginal) {
      // Copy on write
      this.data = new Map(this.data);
      this.refCount = 1;
      this.isOriginal = true;
    }

    this.data.set(key, value);
    return this;
  }

  get(key) {
    return this.data.get(key);
  }

  has(key) {
    return this.data.has(key);
  }
}

// Memory-conscious event system
class WeakEventEmitter {
  constructor() {
    this.listeners = new WeakMap();
  }

  on(target, event, callback) {
    if (!this.listeners.has(target)) {
      this.listeners.set(target, new Map());
    }

    const events = this.listeners.get(target);
    if (!events.has(event)) {
      events.set(event, new Set());
    }

    events.get(event).add(callback);
  }

  off(target, event, callback) {
    const events = this.listeners.get(target);
    if (events && events.has(event)) {
      events.get(event).delete(callback);
    }
  }

  emit(target, event, data) {
    const events = this.listeners.get(target);
    if (events && events.has(event)) {
      events.get(event).forEach((callback) => {
        try {
          callback(data);
        } catch (error) {
          console.error("Event callback error:", error);
        }
      });
    }
  }
}
```

### 259. What are advanced security patterns in JavaScript?

**Answer:**

```javascript
// Secure random token generation
class TokenGenerator {
    static generateSecure(length = 32) {
        const array = new Uint8Array(length);
        crypto.getRandomValues(array);
        return Array.from(array, byte => byte.toString(16).padStart(2, '0')).join('');
    }

    static generateJWT(payload, secret) {
        const header = { typ: 'JWT', alg: 'HS256' };
        const encodedHeader = btoa(JSON.stringify(header));
        const encodedPayload = btoa(JSON.stringify(payload));

        return crypto.subtle.importKey(
            'raw',
            new TextEncoder().encode(secret),
            { name: 'HMAC', hash: 'SHA-256' },
            false,
            ['sign']
        ).then(key => {
            const data = `${encodedHeader}.${encodedPayload}`;
            return crypto.subtle.sign('HMAC', key, new TextEncoder().encode(data))
                .then(signature => {
                    const encodedSignature = btoa(String.fromCharCode(...new Uint8Array(signature)));
                    return `${data}.${encodedSignature}`;
                });
        });
    }
}

// Input validation and sanitization
class InputValidator {
    static sanitizeHTML(input) {
        const div = document.createElement('div');
        div.textContent = input;
        return div.innerHTML;
    }

    static validateEmail(email) {
        const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return regex.test(email) && email.length <= 254;
    }

    static validateURL(url) {
        try {
            const parsed = new URL(url);
            const allowedProtocols = ['http:', 'https:'];
            return allowedProtocols.includes(parsed.protocol);
        } catch {
            return false;
        }
    }

    static sanitizeSQL(input) {
        return input.replace(/['"\\]/g, '\\            const value = Atomics.load(this.data, currentHead);
            ')
                   .replace(/\x00/g, '\\0');
    }

    static validateCSRFToken(token, expectedToken) {
        if (!token || !expectedToken || token.length !== expectedToken.length) {
            return false;
        }

        // Constant-time comparison
        let result = 0;
        for (let i = 0; i < token.length; i++) {
            result |= token.charCodeAt(i) ^ expectedToken.charCodeAt(i);
        }
        return result === 0;
    }
}

// Secure communication wrapper
class SecureAPI {
    constructor(baseURL, options = {}) {
        this.baseURL = baseURL;
        this.options = options;
        this.rateLimiter = new Map();
    }

    async request(endpoint, options = {}) {
        // Rate limiting
        if (!this.checkRateLimit(endpoint)) {
            throw new Error('Rate limit exceeded');
        }

        // Add security headers
        const headers = {
            'Content-Type': 'application/json',
            'X-Requested-With': 'XMLHttpRequest',
            ...options.headers
        };

        // Add CSRF token if available
        const csrfToken = this.getCSRFToken();
        if (csrfToken) {
            headers['X-CSRF-Token'] = csrfToken;
        }

        const url = `${this.baseURL}${endpoint}`;
        const config = {
            ...options,
            headers,
            credentials: 'same-origin', // Prevent CSRF
            mode: 'same-origin'         // Prevent CORS issues
        };

        try {
            const response = await fetch(url, config);

            if (!response.ok) {
                throw new Error(`HTTP ${response.status}: ${response.statusText}`);
            }

            // Validate Content-Type
            const contentType = response.headers.get('Content-Type');
            if (!contentType || !contentType.includes('application/json')) {
                throw new Error('Invalid Content-Type');
            }

            return await response.json();
        } catch (error) {
            console.error('API request failed:', error);
            throw error;
        }
    }

    checkRateLimit(endpoint, limit = 100, window = 60000) {
        const now = Date.now();
        const key = endpoint;

        if (!this.rateLimiter.has(key)) {
            this.rateLimiter.set(key, []);
        }

        const requests = this.rateLimiter.get(key);

        // Remove old requests
        while (requests.length > 0 && requests[0] <= now - window) {
            requests.shift();
        }

        if (requests.length >= limit) {
            return false;
        }

        requests.push(now);
        return true;
    }

    getCSRFToken() {
        const meta = document.querySelector('meta[name="csrf-token"]');
        return meta ? meta.getAttribute('content') : null;
    }
}

// Content Security Policy builder
class CSPBuilder {
    constructor() {
        this.directives = new Map();
        this.nonces = new Set();
    }

    defaultSrc(...sources) {
        this.directives.set('default-src', sources);
        return this;
    }

    scriptSrc(...sources) {
        this.directives.set('script-src', sources);
        return this;
    }

    styleSrc(...sources) {
        this.directives.set('style-src', sources);
        return this;
    }

    imgSrc(...sources) {
        this.directives.set('img-src', sources);
        return this;
    }

    addNonce() {
        const nonce = TokenGenerator.generateSecure(16);
        this.nonces.add(nonce);
        return nonce;
    }

    build() {
        const policy = Array.from(this.directives.entries())
            .map(([directive, sources]) => {
                let sourceList = sources.join(' ');

                // Add nonces to script and style sources
                if (['script-src', 'style-src'].includes(directive) && this.nonces.size > 0) {
                    const nonceList = Array.from(this.nonces)
                        .map(nonce => `'nonce-${nonce}'`)
                        .join(' ');
                    sourceList += ` ${nonceList}`;
                }

                return `${directive} ${sourceList}`;
            })
            .join('; ');

        return policy;
    }
}

// Secure storage wrapper
class SecureStorage {
    constructor(encryptionKey) {
        this.key = encryptionKey;
    }

    async encrypt(data) {
        const encoder = new TextEncoder();
        const dataBuffer = encoder.encode(JSON.stringify(data));

        const iv = crypto.getRandomValues(new Uint8Array(12));
        const encrypted = await crypto.subtle.encrypt(
            { name: 'AES-GCM', iv },
            this.key,
            dataBuffer
        );

        // Combine IV and encrypted data
        const combined = new Uint8Array(iv.length + encrypted.byteLength);
        combined.set(iv);
        combined.set(new Uint8Array(encrypted), iv.length);

        return btoa(String.fromCharCode(...combined));
    }

    async decrypt(encryptedData) {
        const combined = new Uint8Array(
            atob(encryptedData).split('').map(c => c.charCodeAt(0))
        );

        const iv = combined.slice(0, 12);
        const encrypted = combined.slice(12);

        const decrypted = await crypto.subtle.decrypt(
            { name: 'AES-GCM', iv },
            this.key,
            encrypted
        );

        const decoder = new TextDecoder();
        return JSON.parse(decoder.decode(decrypted));
    }

    async setItem(key, value) {
        const encrypted = await this.encrypt(value);
        localStorage.setItem(key, encrypted);
    }

    async getItem(key) {
        const encrypted = localStorage.getItem(key);
        if (!encrypted) return null;

        try {
            return await this.decrypt(encrypted);
        } catch (error) {
            console.error('Decryption failed:', error);
            return null;
        }
    }
}
```

### 300. What are the future directions and emerging patterns in JavaScript?

**Answer:**

```javascript
// Pattern matching (Stage 1 proposal)
function processValue(value) {
    return match (value) {
        when (Number) -> `Number: ${value}`;
        when (String) -> `String: ${value}`;
        when ({ type: 'user', id }) -> `User ID: ${id}`;
        when ([first, ...rest]) -> `Array with first: ${first}`;
        when _ -> 'Unknown type';
    };
}

// Pipeline operator (Stage 2 proposal)
function transformData(data) {
    return data
        |> validateInput(%)
        |> normalizeData(%)
        |> processData(%)
        |> formatOutput(%);
}

// Record and Tuple (Stage 2 proposal)
const record = #{
    name: "John",
    age: 30
};

const tuple = #[1, 2, 3];

// These are deeply immutable and compared by value
const sameRecord = #{ name: "John", age: 30 };
console.log(record === sameRecord); // true

// Temporal API (Stage 3)
import { Temporal } from 'temporal-polyfill';

function advancedDateHandling() {
    const now = Temporal.Now.plainDateTimeISO();
    const birthday = Temporal.PlainDate.from('1990-05-15');
    const nextBirthday = birthday.with({ year: now.year + 1 });

    const duration = nextBirthday.since(now.toPlainDate());
    return `${duration.days} days until next birthday`;
}

// Import assertions (Stage 3)
import config from './config.json' assert { type: 'json' };
import styles from './styles.css' assert { type: 'css' };

// Top-level await (Stage 4)
const data = await fetch('/api/data').then(r => r.json());
const module = await import('./dynamic-module.js');

// WebAssembly integration patterns
class WasmModule {
    static async load(wasmPath) {
        const wasmModule = await WebAssembly.instantiateStreaming(fetch(wasmPath));
        return new WasmModule(wasmModule.instance);
    }

    constructor(instance) {
        this.instance = instance;
        this.memory = instance.exports.memory;
        this.exports = instance.exports;
    }

    // Type-safe wasm function calls
    callFunction(name, ...args) {
        const fn = this.exports[name];
        if (!fn) throw new Error(`Function ${name} not found`);value));
    }

    flatMap(fn) {
        return this.value == null ? Maybe.of(null) : fn(this.value);
    }
}
```

### 97. What is lazy evaluation?

**Answer:** Delaying computation until the result is needed.

```javascript
function* fibonacci() {
  let [a, b] = [0, 1];
  while (true) {
    yield a;
    [a, b] = [b, a + b];
  }
}

const fib = fibonacci();
console.log(fib.next().value); // 0 (computed only when needed)
```

### 98. What are Web APIs vs JavaScript APIs?

**Answer:**

- **Web APIs**: Browser-provided (DOM, Fetch, Storage)
- **JavaScript APIs**: Language built-ins (Array, Object, Promise)

### 99. What is the difference between microtasks and animation frames?

**Answer:**

- **Microtasks**: Executed before next render
- **Animation frames**: Executed before next repaint, optimized for animations

### 100. What are the different ways to handle errors in JavaScript?

**Answer:**

```javascript
// try-catch
try {
  riskyOperation();
} catch (error) {
  handleError(error);
}

// Promise catch
promise.catch((error) => handleError(error));

// Global error handlers
window.addEventListener("error", (event) => {
  console.error("Global error:", event.error);
});

window.addEventListener("unhandledrejection", (event) => {
  console.error("Unhandled promise rejection:", event.reason);
});
```

### 101. What are JavaScript engines and how do they work?

**Answer:** JavaScript engines (V8, SpiderMonkey, JavaScriptCore) parse, compile, and execute JavaScript code. They use techniques like JIT compilation and optimization.

### 102. What is the call stack?

**Answer:** Data structure that keeps track of function calls. Follows LIFO (Last In, First Out) principle.

```javascript
function first() {
  console.log("First");
  second();
}

function second() {
  console.log("Second");
  third();
}

function third() {
  console.log("Third");
}

first(); // Call stack: first -> second -> third
```

### 103. What is memory management in JavaScript?

**Answer:** JavaScript uses automatic memory management with garbage collection. Memory is allocated for objects and freed when no longer referenced.

### 104. What are memory leaks and how to prevent them?

**Answer:** Memory leaks occur when objects are not properly garbage collected.

```javascript
// Common leak: forgotten timers
const timer = setInterval(() => {
  // Some work
}, 1000);
// Always clear: clearInterval(timer);

// Common leak: closures holding references
function createHandler() {
  const largeObject = new Array(1000000);
  return function () {
    // largeObject is kept in closure even if not used
  };
}

// Solution: null references when done
let handler = createHandler();
// Later: handler = null;
```

### 105. What is tree shaking?

**Answer:** Process of eliminating dead code (unused exports) during bundling to reduce bundle size.

```javascript
// math.js
export function add(a, b) {
  return a + b;
}
export function subtract(a, b) {
  return a - b;
} // unused

// main.js
import { add } from "./math.js"; // only add is bundled
```

### 106. What are source maps?

**Answer:** Files that map minified code back to original source code for debugging.

### 107. What is the difference between bundling and code splitting?

**Answer:**

- **Bundling**: Combining multiple files into fewer files
- **Code splitting**: Breaking code into smaller chunks loaded on demand

### 108. What are polyfills and transpilation?

**Answer:**

- **Polyfills**: Code that implements features missing in older browsers
- **Transpilation**: Converting modern JavaScript to older versions (Babel)

### 109. What is the difference between `Object.keys()`, `Object.values()`, and `Object.entries()`?

**Answer:**

```javascript
const obj = { a: 1, b: 2, c: 3 };

Object.keys(obj); // ['a', 'b', 'c']
Object.values(obj); // [1, 2, 3]
Object.entries(obj); // [['a', 1], ['b', 2], ['c', 3]]
```

### 110. What is `Object.fromEntries()`?

**Answer:** Creates an object from an array of key-value pairs (opposite of Object.entries).

```javascript
const entries = [
  ["a", 1],
  ["b", 2],
];
const obj = Object.fromEntries(entries); // { a: 1, b: 2 }
```

### 111. What are optional chaining and nullish coalescing?

**Answer:**

```javascript
// Optional chaining (?.)
const user = { profile: { name: "John" } };
console.log(user?.profile?.name); // 'John'
console.log(user?.profile?.age); // undefined

// Nullish coalescing (??)
const value = null ?? "default"; // 'default'
const value2 = 0 ?? "default"; // 0 (not 'default')
```

### 112. What is the logical assignment operators?

**Answer:**

```javascript
// Logical AND assignment (&&=)
let a = true;
a &&= false; // a becomes false

// Logical OR assignment (||=)
let b = false;
b ||= true; // b becomes true

// Nullish coalescing assignment (??=)
let c = null;
c ??= "default"; // c becomes 'default'
```

### 113. What are numeric separators?

**Answer:** Underscores in numeric literals for better readability.

```javascript
const million = 1_000_000;
const binary = 0b1010_0001;
const hex = 0xff_ec_de_5e;
```

### 114. What is the `globalThis` object?

**Answer:** Standard way to access the global object across different JavaScript environments.

```javascript
// Works in browsers, Node.js, Web Workers
console.log(globalThis); // window (browser), global (Node.js), self (Worker)
```

### 115. What are BigInt and when to use it?

**Answer:** Arbitrary precision integers for numbers larger than Number.MAX_SAFE_INTEGER.

```javascript
const bigInt = 9007199254740991n;
const anotherBigInt = BigInt(9007199254740991);

console.log(bigInt + 1n); // 9007199254740992n
```

### 116. What is the difference between `setTimeout`, `setImmediate`, and `process.nextTick`?

**Answer:**

- `setTimeout`: Macrotask, minimum delay
- `setImmediate`: Macrotask, Node.js specific
- `process.nextTick`: Microtask, Node.js specific, highest priority

### 117. What are the different module formats?

**Answer:**

- **ES6 Modules**: `import`/`export`
- **CommonJS**: `require`/`module.exports`
- **AMD**: Asynchronous Module Definition
- **UMD**: Universal Module Definition
- **System**: SystemJS format

### 118. What is hoisting behavior with different declarations?

**Answer:**

```javascript
console.log(varVariable); // undefined
console.log(letVariable); // ReferenceError
console.log(constVariable); // ReferenceError

var varVariable = "var";
let letVariable = "let";
const constVariable = "const";

// Function declarations are fully hoisted
console.log(myFunction()); // Works

function myFunction() {
  return "Hello";
}
```

### 119. What is the temporal dead zone?

**Answer:** Period between entering scope and variable declaration where accessing the variable throws ReferenceError.

```javascript
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 5;
```

### 120. What are the different ways to create arrays?

**Answer:**

```javascript
// Array literal
const arr1 = [1, 2, 3];

// Array constructor
const arr2 = new Array(1, 2, 3);
const arr3 = new Array(5); // [empty × 5]

// Array.from()
const arr4 = Array.from("hello"); // ['h', 'e', 'l', 'l', 'o']

// Array.of()
const arr5 = Array.of(1, 2, 3); // [1, 2, 3]

// Fill and map
const arr6 = Array(5)
  .fill(0)
  .map((_, i) => i);
```

### 121. What are array methods and their use cases?

**Answer:**

```javascript
const arr = [1, 2, 3, 4, 5];

// Transformation
arr.map((x) => x * 2); // [2, 4, 6, 8, 10]
arr.filter((x) => x % 2 === 0); // [2, 4]
arr.reduce((sum, x) => sum + x, 0); // 15

// Search
arr.find((x) => x > 3); // 4
arr.findIndex((x) => x > 3); // 3
arr.includes(3); // true

// Mutation
arr.push(6); // Add to end
arr.unshift(0); // Add to start
arr.splice(1, 2, "a", "b"); // Remove and insert
```

### 122. What is the difference between shallow and deep comparison?

**Answer:**

```javascript
// Shallow comparison
const obj1 = { a: 1, b: { c: 2 } };
const obj2 = { a: 1, b: { c: 2 } };

// Shallow equality check
function shallowEqual(obj1, obj2) {
  const keys1 = Object.keys(obj1);
  const keys2 = Object.keys(obj2);

  if (keys1.length !== keys2.length) return false;

  return keys1.every((key) => obj1[key] === obj2[key]);
}

// Deep equality check
function deepEqual(obj1, obj2) {
  if (obj1 === obj2) return true;
  if (obj1 == null || obj2 == null) return false;
  if (typeof obj1 !== typeof obj2) return false;

  const keys1 = Object.keys(obj1);
  const keys2 = Object.keys(obj2);

  if (keys1.length !== keys2.length) return false;

  return keys1.every((key) => deepEqual(obj1[key], obj2[key]));
}
```

### 123. What are different ways to copy objects and arrays?

**Answer:**

```javascript
const originalObj = { a: 1, b: { c: 2 } };
const originalArr = [1, [2, 3]];

// Shallow copy - Object
const shallowObj1 = { ...originalObj };
const shallowObj2 = Object.assign({}, originalObj);

// Shallow copy - Array
const shallowArr1 = [...originalArr];
const shallowArr2 = originalArr.slice();

// Deep copy (limited)
const deepObj = JSON.parse(JSON.stringify(originalObj));

// Deep copy (modern)
const deepObj2 = structuredClone(originalObj);

// Custom deep copy
function deepCopy(obj) {
  if (obj === null || typeof obj !== "object") return obj;
  if (obj instanceof Date) return new Date(obj);
  if (obj instanceof Array) return obj.map((item) => deepCopy(item));
  if (typeof obj === "object") {
    const copy = {};
    Object.keys(obj).forEach((key) => (copy[key] = deepCopy(obj[key])));
    return copy;
  }
}
```

### 124. What is event delegation?

**Answer:** Technique using event bubbling to handle events for multiple elements with a single event listener.

```javascript
document.getElementById("parent").addEventListener("click", function (e) {
  if (e.target && e.target.matches(".child")) {
    console.log("Child clicked:", e.target.textContent);
  }
});
```

### 125. What are custom events?

**Answer:** User-defined events that can be dispatched and listened to.

```javascript
// Create custom event
const customEvent = new CustomEvent("myEvent", {
  detail: { message: "Hello World" },
});

// Listen for custom event
document.addEventListener("myEvent", (e) => {
  console.log(e.detail.message);
});

// Dispatch custom event
document.dispatchEvent(customEvent);
```

### 126. What is the difference between `preventDefault()` and `stopPropagation()`?

**Answer:**

- `preventDefault()`: Prevents default browser behavior
- `stopPropagation()`: Prevents event bubbling to parent elements

```javascript
document.querySelector("a").addEventListener("click", function (e) {
  e.preventDefault(); // Don't follow link
  e.stopPropagation(); // Don't bubble to parent
});
```

### 127. What are passive event listeners?

**Answer:** Event listeners that never call `preventDefault()`, allowing browser optimizations.

```javascript
element.addEventListener("touchstart", handler, { passive: true });
```

### 128. What is requestAnimationFrame?

**Answer:** Method to execute code before the next repaint, optimized for animations.

```javascript
function animate() {
  // Animation logic
  requestAnimationFrame(animate);
}

requestAnimationFrame(animate);
```

### 129. What is the Resize Observer API?

**Answer:** Provides notifications when elements change size.

```javascript
const observer = new ResizeObserver((entries) => {
  entries.forEach((entry) => {
    console.log("Size changed:", entry.contentRect);
  });
});

observer.observe(document.querySelector("#myElement"));
```

### 130. What is the Page Visibility API?

**Answer:** Provides information about whether a page is visible to the user.

```javascript
document.addEventListener("visibilitychange", () => {
  if (document.hidden) {
    console.log("Page is hidden");
  } else {
    console.log("Page is visible");
  }
});
```

### 131. What are IndexedDB basics?

**Answer:** Client-side database API for storing large amounts of structured data.

```javascript
const request = indexedDB.open("MyDB", 1);

request.onupgradeneeded = (event) => {
  const db = event.target.result;
  const objectStore = db.createObjectStore("users", { keyPath: "id" });
};

request.onsuccess = (event) => {
  const db = event.target.result;
  const transaction = db.transaction(["users"], "readwrite");
  const objectStore = transaction.objectStore("users");
  objectStore.add({ id: 1, name: "John" });
};
```

### 132. What is the Cache API?

**Answer:** Programmatic interface for managing HTTP request/response cache.

```javascript
caches.open("my-cache").then((cache) => {
  cache.addAll(["/index.html", "/styles.css", "/script.js"]);
});

// In service worker
self.addEventListener("fetch", (event) => {
  event.respondWith(
    caches.match(event.request).then((response) => {
      return response || fetch(event.request);
    })
  );
});
```

### 133. What are different storage mechanisms in browsers?

**Answer:**

- `localStorage`: Persistent, domain-scoped, ~5-10MB
- `sessionStorage`: Session-scoped, domain-scoped, ~5-10MB
- `IndexedDB`: Large amounts of structured data, asynchronous
- `Cache API`: HTTP request/response cache for service workers
- `Cookies`: Small data, sent with requests, ~4KB

### 134. What is the Broadcast Channel API?

**Answer:** Allows communication between different contexts (tabs, workers) of the same origin.

```javascript
const channel = new BroadcastChannel("my-channel");

// Send message
channel.postMessage({ type: "greeting", data: "Hello!" });

// Receive message
channel.addEventListener("message", (event) => {
  console.log("Received:", event.data);
});
```

### 135. What are error boundaries concept in JavaScript?

**Answer:** Though primarily a React concept, JavaScript error handling patterns:

```javascript
class ErrorHandler {
  static wrap(fn) {
    return function (...args) {
      try {
        return fn.apply(this, args);
      } catch (error) {
        ErrorHandler.handleError(error);
        return null;
      }
    };
  }

  static handleError(error) {
    console.error("Caught error:", error);
    // Log to service, show user-friendly message
  }
}

// Usage
const safeFunction = ErrorHandler.wrap(riskyFunction);
```

### 136. What is CSP (Content Security Policy) and JavaScript?

**Answer:** Security standard that helps prevent XSS attacks by controlling resource loading.

```javascript
// Inline scripts blocked by CSP need nonce or hash
<script nonce="random-nonce">
  console.log('This script has proper nonce');
</script>;

// eval() and Function constructor blocked by CSP
// Use safer alternatives
const safeDynamicCode = new Function("return 1 + 1")(); // May be blocked
```

### 137. What is CORS and how does it affect JavaScript?

**Answer:** Cross-Origin Resource Sharing controls access to resources across different origins.

```javascript
// Simple CORS request
fetch("https://api.example.com/data").then((response) => {
  if (!response.ok) throw new Error("CORS error");
  return response.json();
});

// Preflight request (complex CORS)
fetch("https://api.example.com/data", {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
    "X-Custom-Header": "value",
  },
  body: JSON.stringify({ data: "value" }),
});
```

### 138. What are the security best practices for JavaScript?

**Answer:**

- Validate and sanitize input
- Use Content Security Policy
- Avoid `eval()` and `Function` constructor
- Implement proper authentication/authorization
- Use HTTPS
- Sanitize data before DOM insertion
- Implement rate limiting
- Use secure cookies

### 139. What is XSS and how to prevent it?

**Answer:** Cross-Site Scripting attack where malicious scripts are injected.

```javascript
// Vulnerable code
element.innerHTML = userInput; // DON'T DO THIS

// Safe alternatives
element.textContent = userInput; // Safe for text
element.insertAdjacentText("beforeend", userInput); // Safe

// For HTML content, use DOMPurify or similar
const cleanHTML = DOMPurify.sanitize(userHTML);
element.innerHTML = cleanHTML;
```

### 140. What is the same-origin policy?

**Answer:** Security concept that restricts scripts from one origin accessing resources from another origin.

### 141. What are Web Locks API?

**Answer:** Coordinates access to shared resources across different contexts.

```javascript
navigator.locks.request("my-resource", async (lock) => {
  // Only one context can execute this at a time
  console.log("Lock acquired");
  await doWorkWithSharedResource();
});
```

### 142. What is the Screen Wake Lock API?

**Answer:** Prevents device screen from turning off.

```javascript
let wakeLock = null;

async function requestWakeLock() {
  try {
    wakeLock = await navigator.wakeLock.request("screen");
  } catch (err) {
    console.error("Failed to request wake lock:", err);
  }
}

// Release wake lock
if (wakeLock) {
  wakeLock.release();
}
```

### 143. What is the Web Share API?

**Answer:** Allows web apps to share content using the device's native sharing mechanism.

```javascript
if (navigator.share) {
  navigator
    .share({
      title: "Example Title",
      text: "Check this out!",
      url: "https://example.com",
    })
    .then(() => {
      console.log("Successful share");
    });
}
```

### 144. What are progressive enhancement and graceful degradation?

**Answer:**

- **Progressive Enhancement**: Start with basic functionality, add advanced features
- **Graceful Degradation**: Start with full functionality, provide fallbacks

```javascript
// Progressive enhancement
if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("/sw.js");
}

// Feature detection
if (typeof fetch !== "undefined") {
  // Use fetch
} else {
  // Fall back to XMLHttpRequest
}
```

### 145. What is feature detection vs browser detection?

**Answer:**

```javascript
// Feature detection (good)
if ("geolocation" in navigator) {
  navigator.geolocation.getCurrentPosition(success);
}

// Browser detection (avoid)
if (navigator.userAgent.includes("Chrome")) {
  // Don't do this
}
```

### 146. What are polyfills and how to use them?

**Answer:** Code that implements features not natively supported by browsers.

```javascript
// Array.includes polyfill
if (!Array.prototype.includes) {
  Array.prototype.includes = function (searchElement, fromIndex) {
    return this.indexOf(searchElement, fromIndex) !== -1;
  };
}

// Modern approach: core-js
import "core-js/features/array/includes";
```

### 147. What is tree shaking and dead code elimination?

**Answer:** Build-time optimization that removes unused code.

```javascript
// utils.js
export function usedFunction() {
  /* ... */
}
export function unusedFunction() {
  /* ... */
} // Will be removed

// main.js
import { usedFunction } from "./utils.js";
// unusedFunction is not imported, so it's tree-shaken
```

### 148. What are different JavaScript testing strategies?

**Answer:**

- **Unit Testing**: Testing individual functions/components
- **Integration Testing**: Testing component interactions
- **E2E Testing**: Testing complete user workflows
- **Snapshot Testing**: Testing component output consistency

### 149. What is the difference between mocking, stubbing, and spying?

**Answer:**

- **Mock**: Fake object that verifies interactions
- **Stub**: Fake object that returns predetermined responses
- **Spy**: Wrapper around real object that records interactions

### 150. What are performance optimization techniques?

**Answer:**

- Code splitting and lazy loading
- Minimize bundle size
- Use CDN for static assets
- Implement caching strategies
- Optimize images and assets
- Use service workers
- Minimize DOM manipulation
- Debounce/throttle expensive operations
- Use virtual scrolling for large lists

---

## Advanced Level

### 151. What is the V8 compilation process?

**Answer:** V8 uses multiple compilation tiers:

1. **Parser**: Converts source to AST
2. **Ignition**: Bytecode interpreter
3. **TurboFan**: Optimizing compiler for hot code
4. **Deoptimization**: Falls back when assumptions break

### 152. What are hidden classes in V8?

**Answer:** Internal structures that describe object layout for optimization.

```javascript
// Same hidden class
function Point(x, y) {
  this.x = x; // Property added in same order
  this.y = y; // Creates consistent hidden class
}

const p1 = new Point(1, 2);
const p2 = new Point(3, 4); // Same hidden class as p1

// Different hidden class
const p3 = {};
p3.y = 4; // Different order
p3.x = 3; // Different hidden class than p1, p2
```

### 153. What is inline caching?

**Answer:** V8 optimization that caches property access locations based on object types.

```javascript
function getX(obj) {
  return obj.x; // V8 caches where 'x' is located
}

// Monomorphic: always same type (fast)
getX({ x: 1, y: 2 });
getX({ x: 3, y: 4 });

// Polymorphic: multiple types (slower)
getX({ x: 1 });
getX({ a: 1, x: 2 });
getX({ b: 1, c: 2, x: 3 });
```

### 154. What are the different garbage collection strategies?

**Answer:**

- **Mark and Sweep**: Marks reachable objects, sweeps unreachable ones
- **Generational**: Separates young and old objects
- **Incremental**: Spreads GC work across multiple frames
- **Concurrent**: GC runs parallel to main thread

### 155. What is the WeakRef and FinalizationRegistry?

**Answer:** Advanced memory management APIs for weak references and cleanup.

```javascript
// WeakRef - doesn't prevent garbage collection
let obj = { data: "important" };
const weakRef = new WeakRef(obj);

// Later...
obj = null; // Object can be garbage collected
const deref = weakRef.deref();
if (deref) {
  console.log(deref.data);
} else {
  console.log("Object was garbage collected");
}

// FinalizationRegistry - cleanup when objects are GC'd
const registry = new FinalizationRegistry((heldValue) => {
  console.log(`Cleanup: ${heldValue}`);
});

let resource = { id: 1 };
registry.register(resource, "Resource 1");
resource = null; // Eventually triggers cleanup
```

### 156. What is the event loop in detail?

**Answer:** JavaScript's concurrency model with call stack, heap, and queues.

```javascript
console.log("1");

setTimeout(() => console.log("2"), 0); // Macrotask queue

Promise.resolve().then(() => console.log("3")); // Microtask queue

console.log("4");

// Output: 1, 4, 3, 2
// Microtasks have higher priority than macrotasks
```

### 157. What are the different task queues?

**Answer:**

- **Microtask Queue**: Promises, queueMicrotask, MutationObserver
- **Macrotask Queue**: setTimeout, setInterval, I/O operations
- **Animation Queue**: requestAnimationFrame callbacks

### 158. What is shared array buffer and atomics?

**Answer:** Allows sharing memory between main thread and web workers with atomic operations.

```javascript
// Main thread
const sharedBuffer = new SharedArrayBuffer(1024);
const sharedArray = new Int32Array(sharedBuffer);

const worker = new Worker("worker.js");
worker.postMessage({ sharedBuffer });

// Worker thread (worker.js)
self.onmessage = function (e) {
  const sharedArray = new Int32Array(e.data.sharedBuffer);

  // Atomic operations
  Atomics.store(sharedArray, 0, 42);
  Atomics.add(sharedArray, 0, 8);
  const value = Atomics.load(sharedArray, 0); // 50
};
```

### 159. What are transferable objects?

**Answer:** Objects that can be transferred between contexts without copying.

```javascript
const buffer = new ArrayBuffer(1024);
const worker = new Worker("worker.js");

// Transfer ownership to worker
worker.postMessage(buffer, [buffer]);

// buffer is now neutered in main thread
console.log(buffer.byteLength); // 0
```

### 160. What is the difference between structured cloning and JSON serialization?

**Answer:**

```javascript
const obj = {
  date: new Date(),
  regex: /pattern/gi,
  func: () => "hello",
  undefined: undefined,
  null: null,
  circular: null,
};
obj.circular = obj;

// JSON serialization (limited)
const json = JSON.stringify(obj);
// Loses: functions, undefined, Date becomes string, no circular refs

// Structured cloning (comprehensive)
const cloned = structuredClone(obj);
// Preserves: Date objects, handles circular refs
// Still loses: functions
```

### 161. What are advanced proxy patterns?

**Answer:**

```javascript
// Revocable proxy
const { proxy, revoke } = Proxy.revocable(target, handler);
revoke(); // Proxy becomes unusable

// Proxy for validation
function createValidatedObject(schema) {
  return new Proxy(
    {},
    {
      set(target, property, value) {
        if (!schema[property]) {
          throw new Error(`Unknown property: ${property}`);
        }
        if (typeof value !== schema[property]) {
          throw new Error(`Invalid type for ${property}`);
        }
        target[property] = value;
        return true;
      },
    }
  );
}

const user = createValidatedObject({
  name: "string",
  age: "number",
});
```

### 162. What is the Temporal API?

**Answer:** Upcoming API for better date/time handling.

```javascript
// Current Temporal proposal (not yet standardized)
import { Temporal } from "@js-temporal/polyfill";

const now = Temporal.Now.plainDateTimeISO();
const birthday = Temporal.PlainDate.from("1990-05-15");
const duration = now.toPlainDate().since(birthday);

console.log(`You are ${duration.years} years old`);
```

### 163. What are advanced generator patterns?

**Answer:**

```javascript
// Generator delegation
function* gen1() {
  yield 1;
  yield 2;
}

function* gen2() {
  yield 3;
  yield* gen1(); // Delegate to another generator
  yield 4;
}

// Async generators
async function* asyncGenerator() {
  let i = 0;
  while (i < 3) {
    await new Promise((resolve) => setTimeout(resolve, 1000));
    yield i++;
  }
}

// Two-way communication
function* communicatingGen() {
  const a = yield "First";
  const b = yield `Received: ${a}`;
  return `Final: ${b}`;
}

const gen = communicatingGen();
console.log(gen.next()); // {value: 'First', done: false}
console.log(gen.next("Hello")); // {value: 'Received: Hello', done: false}
console.log(gen.next("World")); // {value: 'Final: World', done: true}
```

### 164. What are advanced async patterns?

**Answer:**

```javascript
// Async iteration
async function* asyncIterable() {
  for (let i = 0; i < 3; i++) {
    await new Promise((resolve) => setTimeout(resolve, 1000));
    yield i;
  }
}

for await (const value of asyncIterable()) {
  console.log(value); // 0, 1, 2 (with delays)
}

// Promise combinators
const promises = [fetch("/api/1"), fetch("/api/2"), fetch("/api/3")];

// All or nothing
const allResults = await Promise.all(promises);

// First to resolve
const firstResult = await Promise.race(promises);

// All settled (success or failure)
const settledResults = await Promise.allSettled(promises);

// First successful
const anyResult = await Promise.any(promises);
```

### 165. What are observables and reactive programming?

**Answer:** Pattern for handling asynchronous data streams.

```javascript
// Simple Observable implementation
class Observable {
  constructor(subscriber) {
    this.subscriber = subscriber;
  }

  subscribe(observer) {
    return this.subscriber(observer);
  }

  map(transformFn) {
    return new Observable((observer) => {
      return this.subscribe({
        next: (value) => observer.next(transformFn(value)),
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    });
  }

  filter(predicate) {
    return new Observable((observer) => {
      return this.subscribe({
        next: (value) => predicate(value) && observer.next(value),
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    });
  }
}

// Usage
const numbers = new Observable((observer) => {
  [1, 2, 3, 4, 5].forEach((n) => observer.next(n));
  observer.complete();
});

numbers
  .filter((n) => n % 2 === 0)
  .map((n) => n * 2)
  .subscribe({
    next: console.log, // 4, 8
    complete: () => console.log("Done"),
  });
```

### 166. What are advanced functional programming concepts?

**Answer:**

```javascript
// Functors
class Box {
    constructor(value) {
        this.value = value;
    }

    map(fn) {
        return new Box(fn(this.value));
    }

    fold(fn) {
        return fn(this.value);
    }
}

// Monads (simplified Maybe)
class Maybe {
    constructor(value) {
        this.value = value;
    }

    static of(value) {
        return new Maybe(value);
    }

    map(fn) {
        return this.value == null ? Maybe.of(null) : Maybe.of(fn(this.
```

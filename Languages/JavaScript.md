---
## Programming Languages

### JavaScript

#### 1. What is the difference between `let`, `const`, and `var`?
- **`var`:** Function-scoped, can be re-declared and re-assigned.
- **`let`:** Block-scoped, can be re-assigned but not re-declared.
- **`const`:** Block-scoped, cannot be re-assigned or re-declared.

#### 2. What is a closure?
A closure is a function bundled together with references to its surrounding state. It gives you access to an outer function's scope from an inner function.

```javascript
function makeFunc() {
  const name = 'Mozilla';
  function displayName() {
    console.log(name); // 'Mozilla'
  }
  return displayName;
}

const myFunc = makeFunc();
myFunc(); // logs 'Mozilla'
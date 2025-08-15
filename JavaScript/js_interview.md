JavaScript (JS)

    Basics
    Variables (var, let, const)
    Data Types (string, number, boolean, array, object)
    Functions (declaration, expression, arrow functions)
    DOM Manipulation
    Selecting elements (document.querySelector, getElementById)
    Event listeners (addEventListener)
    Modifying elements (innerHTML, style, classList)
    Control Flow
    Loops (for, while, forEach)
    Conditional statements (if, else, switch)
    ES6 Features
    Template literals
    Destructuring
    Default parameters
    Spread/rest operators
    Modules (import/export)
    APIs
    Fetch API and Promises
    REST APIs
    Working with JSON

# 🎯 JavaScript Interview Prep — Real-World Q&A

> Sharpen your skills for real-time interview sessions. Covering from JS fundamentals to working with APIs.

---

## ✅ Basics & Variables

### 1. What's the difference between `var`, `let`, and `const`?

- `var`: Function-scoped, hoisted, can be redeclared and updated.
- `let`: Block-scoped, hoisted but not initialized, can be updated but not redeclared.
- `const`: Block-scoped, hoisted but must be initialized and cannot be reassigned.

### 2. Why should we avoid using `var` in modern JavaScript?

- Because `var` can lead to unexpected behavior due to hoisting and lack of block scope.

---

## ✅ Data Types

### 3. What are JavaScript’s primitive data types?

- string
- number
- boolean
- null
- undefined
- bigint
- symbol

### 4. How is `null` different from `undefined`?

- `undefined`: a variable is declared but not assigned.
- `null`: an intentional absence of any object value.

---

## ✅ Functions

### 5. Difference between function declaration and function expression?

```js
// Declaration
function greet() {
  console.log("Hello");
}

// Expression
const greet = function () {
  console.log("Hello");
};
```

# 🧠 JavaScript Scope, Hoisting, Initialization, and Redeclaration

---

## 📌 1. What is Scope?

**Scope** defines where a variable is accessible in your code.

### 🔸 Types of Scope:

| Scope Type   | Description                                  | Applies To                 |
| ------------ | -------------------------------------------- | -------------------------- |
| **Global**   | Declared outside any function or block       | `var`, `let`, `const`      |
| **Function** | Declared inside a function                   | `var`, `let`, `const`      |
| **Block**    | Declared inside `{ }` (if, for, while, etc.) | `let`, `const` (NOT `var`) |

---

## 🧪 Example: Scope Behavior

```js
function test() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a); // ✅ 1 — function-scoped
  console.log(b); // ❌ ReferenceError — block-scoped
  console.log(c); // ❌ ReferenceError — block-scoped
}
```

# 🧠 JavaScript Hoisting Explained (with `var`, `let`, `const`)

---

## ✅ What is Hoisting?

> **Hoisting** is JavaScript's behavior of moving **declarations** to the top of their **scope** during compilation.

- Only the **declaration** (not the assignment) is hoisted.
- Applies to:
  - `var`, `let`, `const` (variables)
  - `function` (function declarations only)

---

## 🧪 Example 1: `var` Hoisting

```js
console.log(a); // ✅ undefined
var a = 10;
```

### 🔍 Explanation:

- `var a` is hoisted to the top of the scope as `var a;`
- The assignment `a = 10` stays in place.
- So it becomes:

```js
var a;
console.log(a); // undefined
a = 10;
```

---

## 🧪 Example 2: `let` Hoisting

```js
console.log(b); // ❌ ReferenceError: Cannot access 'b' before initialization
let b = 20;
```

### 🔍 Explanation:

- `let b` **is hoisted**, but it's in a **Temporal Dead Zone (TDZ)** until the line where it's declared.
- So even though it’s moved up, it’s not accessible before that line.
- JavaScript throws a ReferenceError if you try to access it before declaration.

---

## 🧪 Example 3: `const` Hoisting

```js
console.log(c); // ❌ ReferenceError: Cannot access 'c' before initialization
const c = 30;
```

### 🔍 Explanation:

- Same behavior as `let`: hoisted, but not initialized.
- Also in a TDZ.
- Must be assigned during declaration, or it throws a SyntaxError.

---

## 🔍 Summary Table

| Keyword | Hoisted? | Initialized? | Scope          | Redeclarable? | Temporal Dead Zone? |
| ------- | -------- | ------------ | -------------- | ------------- | ------------------- |
| `var`   | ✅ Yes   | 🚫 No        | Function scope | ✅ Yes        | ❌ No               |
| `let`   | ✅ Yes   | 🚫 No        | Block scope    | ❌ No         | ✅ Yes              |
| `const` | ✅ Yes   | 🚫 No        | Block scope    | ❌ No         | ✅ Yes              |

---

## 🧠 What is the Temporal Dead Zone (TDZ)?

- TDZ is the time between the start of the block and the actual declaration of the variable.
- During this time, accessing the variable will throw an error.

```js
{
  // TDZ starts
  console.log(name); // ❌ ReferenceError
  let name = "Shahjalal";
  // TDZ ends
}
```

---

## 🧪 Bonus: Hoisting in Blocks

```js
{
  console.log(x); // ❌ ReferenceError (TDZ)
  let x = 5;

  console.log(y); // ❌ ReferenceError (TDZ)
  const y = 10;

  console.log(z); // ✅ undefined
  var z = 15;
}
```

---

## 🧪 Hoisting and Scope Together

```js
function demo() {
  console.log(a); // ✅ undefined
  var a = 10;

  console.log(b); // ❌ ReferenceError
  let b = 20;

  console.log(c); // ❌ ReferenceError
  const c = 30;
}

demo();
```

---

## ⚠️ Common Mistake

```js
if (true) {
  var v = 1;
}
console.log(v); // ✅ 1 (var is function-scoped, not block-scoped)

if (true) {
  let l = 2;
}
console.log(l); // ❌ ReferenceError (let is block-scoped)
```

---

## 🧪 Real World Trap

```js
function example() {
  console.log(hoistedVar); // ✅ undefined
  var hoistedVar = "I am hoisted";

  console.log(notHoisted); // ❌ ReferenceError
  let notHoisted = "I am not hoisted";
}
```

---

## 🔚 Final Rule of Thumb

- `var`: **Hoisted & initialized as `undefined`**, accessible before declaration.
- `let`/`const`: **Hoisted but NOT initialized**, **TDZ applies**.
- Don't access `let`/`const` before their declaration line.
  TDZ = Temporal Dead Zone

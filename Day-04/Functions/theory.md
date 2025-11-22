# 🧠 **JS-MASTERY — Full Deep Lesson on Functions**

**(Function Declaration vs Function Expression vs Arrow Function)**

# 🚀 **1. What is a Function? (Quick Recall)**

A **function** is a reusable block of code.
In JavaScript, a function itself is a **value** — it can be stored, passed, returned, etc.

But **how you create it** matters a LOT (hoisting, `this`, TDZ, etc).

We have **3 major types**:

1️⃣ Function Declaration
2️⃣ Function Expression
3️⃣ Arrow Function

Let's go deep into each.

---

# 🟦 **2. Function Declaration**

### 📌 **Syntax**

```js
function greet() {
  console.log("Hello!");
}
```

### 📌 **Key Features**

| Feature                    | Description                             |
| -------------------------- | --------------------------------------- |
| **Name required**          | Yes                                     |
| **Hoisted (fully)**        | YES — you can call it before writing it |
| **Creates separate scope** | Yes                                     |
| **Has its own `this`**     | Yes                                     |

### 🧠 **Mental Model**

Declarations are “lifted” entirely during the creation phase.
So they're **available before code executes**.

### 📌 Example:

```js
sayHi(); // works!

function sayHi() {
  console.log("Hi!");
}
```

---

# 🟧 **3. Function Expression**

### 📌 **Syntax**

```js
const greet = function () {
  console.log("Hello!");
};
```

### 📌 **Key Features**

| Feature                     | Description                                          |
| --------------------------- | ---------------------------------------------------- |
| Name optional               | Yes                                                  |
| Hoisted?                    | **NO** — (only variable hoisted, NOT function value) |
| Lives in TDZ (if let/const) | Yes                                                  |
| Has its own `this`          | Yes                                                  |

### 🧠 **Mental Model**

Variable is hoisted, **but not initialized**, so before assignment the function DOES NOT EXIST.

### 📌 Example:

```js
hello(); // ❌ error

const hello = function() {
  console.log("Hello!");
};
```

---

# 🟩 **4. Arrow Function**

### 📌 **Syntax**

```js
const greet = () => {
  console.log("Hello!");
};
```

### 📌 **Key Features**

| Feature                       | Description                          |
| ----------------------------- | ------------------------------------ |
| Short syntax                  | Yes                                  |
| Hoisted?                      | **NO** (same as function expression) |
| `this` binding                | **NO own this** (lexical this)       |
| arguments object              | **NO**                               |
| Not suitable for constructors | Correct                              |
| Implicit return possible      | Yes                                  |

### 🧠 **Mental Model**

Arrow functions **borrow `this` from the surrounding scope**.
They are meant for short logic, not object methods.

### 📌 Example (implicit return)

```js
const double = x => x * 2;
```

### ❗ Big difference: `this`

```js
const user = {
  name: "Usman",
  show: () => {
    console.log(this.name); // ❌ undefined
  }
};

user.show();
```

Arrow function takes `this` from outside → global → undefined.

---

# 🔥 **5. Side-by-Side Comparison**

| Feature                     | Declaration | Expression  | Arrow  |
| --------------------------- | ----------- | ----------- | ------ |
| Hoisted                     | ✅ fully     | ❌ no        | ❌ no   |
| Own `this`                  | ✅ yes       | ✅ yes       | ❌ no   |
| TDZ for const/let           | ❌           | ✅           | ✅      |
| Short syntax                | ❌           | ❌           | ✅      |
| Constructor allowed (`new`) | ✅           | ✅           | ❌      |
| Good for object methods     | ✅           | 🤏 not much | ❌ no   |
| Good for callbacks          | 😐          | 😐          | ✅ best |

---

# 🧨 **6. Hoisting Differences**

### Function Declaration

```js
walk(); // works

function walk() {
  console.log("walking...");
}
```

### Function Expression

```js
run(); // ❌ TDZ error

const run = function() {
  console.log("running...");
}
```

### Arrow

```js
fly(); // ❌ TDZ error

const fly = () => console.log("flying...");
```

---

# 🧠 **7. `this` Differences (VERY IMPORTANT)**

### Normal Function → Dynamic `this`

```js
const person = {
  name: "Usman",
  sayHi() {
    console.log(this.name);
  }
};

person.sayHi(); // Usman
```

### Arrow Function → Lexical `this`

```js
const person = {
  name: "Usman",
  sayHi: () => {
    console.log(this.name);
  }
};

person.sayHi(); // undefined
```

Arrow functions **are NOT for methods**.

---

# ⚙️ **8. When to Use What? (Professional Guidance)**

### ✅ Use **Function Declaration** when:

* You want hoisting
* You want clean, readable API
* You want normal `this` behavior

### ✅ Use **Function Expression** when:

* You need to store a function in a variable
* You want a clear loading order
* More control (React, async handlers, etc.)

### ✅ Use **Arrow Function** when:

* Writing short, inline functions
* Writing callbacks:

  * `map`
  * `filter`
  * `reduce`
  * `addEventListener`
* When you want lexical `this`
* React components (function body only, not methods)

---

# 🧩 **9. Interview-Level Gotchas**

### ❗ Arrow functions cannot be constructors

```js
const A = () => {};
new A(); // ❌ TypeError
```

### ❗ No `arguments`

```js
const test = () => {
  console.log(arguments); // ❌ error
};
```

### ❗ Arrow functions can't be used as methods

```js
const obj = {
  x: 10,
  getX: () => this.x
};

obj.getX(); // undefined
```

---

# 🎯 **10. Summary Table**

```
Function Declaration → Hoisted + own this
Function Expression → No hoisting + own this
Arrow Function      → No hoisting + lexical this + short syntax
```

---

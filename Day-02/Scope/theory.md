# **JS-MASTERY: Day — Scope (Global / Function / Block)**

### 🚀 **Why Scope Matters?**

Scope decides **where a variable is accessible** in your code.
If you master scope → you avoid bugs, write cleaner logic, and understand closures, hoisting, modules… *everything advanced relies on scope.*

---

# **1️⃣ Global Scope**

Variables available **everywhere** in your code.

### **Where do globals come from?**

* Declared outside any function/block
* In browsers, global variables attach to the `window` object (except `let/const`)

### **Example**

```js
let name = "Usman"; // global

function sayHi() {
  console.log(name); // accessible
}

sayHi(); // Usman
console.log(name); // Usman
```

---

# **2️⃣ Function Scope (Only var-based)**

Variables declared using **var** are function-scoped.

Meaning → `var` is only accessible **inside the function it’s declared in**.

### Example:

```js
function test() {
  var a = 10;
  console.log(a); // 10
}

console.log(a); // ❌ ReferenceError
```

---

# **3️⃣ Block Scope (let & const)**

`let` and `const` stay limited to `{}` blocks.

Blocks include:

* if
* for
* while
* functions
* switch cases
* standalone `{}`

### Example:

```js
if (true) {
  let x = 5;
  const y = 10;
}

console.log(x); // ❌
console.log(y); // ❌
```

---

# **4️⃣ Global vs Function vs Block — Key Table**

| Keyword | Scope    | Re-declare | Re-assign | Hoisting                           |
| ------- | -------- | ---------- | --------- | ---------------------------------- |
| var     | Function | ✔️ yes     | ✔️ yes    | hoisted (initialized as undefined) |
| let     | Block    | ❌ no       | ✔️ yes    | hoisted but TDZ                    |
| const   | Block    | ❌ no       | ❌ no      | hoisted but TDZ                    |

TDZ = Temporal Dead Zone

---

# **5️⃣ Scope Chain (MOST IMPORTANT 🔥)**

When JS needs a variable, it looks:

1. In the current scope
2. If not found → parent scope
3. If still not found → global scope
4. If not found anywhere → `ReferenceError`

### Example:

```js
let a = 5;

function outer() {
  let b = 10;

  function inner() {
    let c = 20;
    console.log(a, b, c);
  }

  inner();
}

outer();
```

Flow: `inner → outer → global`

---

# **6️⃣ Lexical Scope (static scope)**

A function’s scope is determined by **where it is written**, NOT where it is called.
A function can access variables based on where it is written in the code, not where it is called.

### Example:

```js
function outer() {
  let message = "Hello";

  function inner() {
    console.log(message);
  }

  return inner;
}

const fn = outer();  
fn();  // "Hello"
```

Even though `fn()` is called outside, it remembers the scope where it was **defined**.

This is the concept that leads to **closures**.

---

# **7️⃣ Real World Examples**

## ✔ Example 1: Avoiding Global Pollution

Bad:

```js
var count = 0;

function increment() {
  count++;
}
```

Better:

```js
function counter() {
  let count = 0;
  return () => ++count;
}
```

---

## ✔ Example 2: Loops & var bug

```js
for (var i = 1; i <= 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

Output:

```
4
4
4
```

Because `var` is function scoped.

Fix:

```js
for (let i = 1; i <= 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

---

# **8️⃣ Hoisting & Scope**

Hoisting + scope interaction is crucial:

### Example:

```js
console.log(a); // undefined
var a = 10;
```

But:

```js
console.log(b); // ❌ TDZ error
let b = 10;
```

---

# **9️⃣ Summary Cheat Sheet**

* **var → function scope**
* **let/const → block scope**
* **Functions → create new scopes**
* **Scope chain → inner can access outer**
* **Lexical scope → location defines access**
* **Globals → avoid unless necessary**

---

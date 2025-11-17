# 🚀 **JS MASTERCLASS — HOISTING (Var / Let / Const / Functions)**

We’ll cover:

1. What hoisting ACTUALLY is (not the common myth)
2. JS Execution Context (Memory + Execution phases)
3. How `var` is hoisted
4. How `let` and `const` are hoisted
5. What TDZ actually means
6. Function hoisting (Function Declaration vs Expression)
7. Hoisting in block scope
8. Hoisting inside functions
9. Real-world pitfalls & examples

---

# 🧠 **1. What Hoisting ACTUALLY is**

Most people say:

> “Hoisting means JS moves your code to the top.”

❌ Not true.
Nothing moves.

The REAL definition is:

> **Hoisting is JavaScript’s behavior of setting up memory for variables and functions before execution begins.**

So JS reads your file TWICE:

### ✔ Phase 1: Memory Creation

* Create memory for variables & functions
* Assign initial values (or not)

### ✔ Phase 2: Execution

* Run your code line-by-line
* Assign actual values

---

# 🏗 **2. Execution Context — the brain of hoisting**

Every time JS runs:

* a **Global Execution Context** is created
* inside functions, separate **Function Execution Contexts** are created

Each context has two parts:

### 1. **Memory Component (Hoisting phase)**

Stores:

* variables (`var/let/const`)
* functions
* function arguments

### 2. **Code Component (Execution phase)**

Executes your code line-by-line.

---

# 🔥 **3. Hoisting of `var` — fully hoisted and initialized**

During memory phase:

```
var a ➝ allocated memory, initialized with undefined
```

This is why:

```js
console.log(a); 
var a = 10;
```

Output:

```
undefined
```

Because JS does:

### Memory phase:

```
a = undefined
```

### Execution phase:

* console.log(a) → undefined
* a = 10

---

# 🚫 **4. Hoisting of `let` and `const` — hoisted but NOT initialized**

During memory phase:

```
let b ➝ allocated memory, NOT initialized  
const c ➝ allocated memory, NOT initialized
```

They stay in the **TDZ (Temporal Dead Zone)** until the actual line is executed.

Example:

```js
console.log(b);
let b = 20;
```

Error:

```
ReferenceError: Cannot access 'b' before initialization
```

Because:

### Memory Phase:

```
b = <uninitialized>  // cannot be touched
```

### Execution Phase:

* line 1 → accessing an uninitialized variable → ❌ error
* line 2 → only here b is initialized with 20

---

# 🔒 **5. TDZ (Temporal Dead Zone) — the missing piece**

TDZ is the time between:

* The variable being hoisted (memory created)
* The variable being initialized (actual line executed)

Inside TDZ → **any access is illegal**.

It protects the variable from being used incorrectly.

---

# 🧩 **6. Function Hoisting (VERY IMPORTANT)**

There are two types of functions:

---

## ✔ **Function Declarations**

```js
function greet() {
  console.log("hello");
}
```

These are **fully hoisted** — including their body.

You can call them before they appear:

```js
greet(); // works
function greet() {
  console.log("hello");
}
```

---

## ❌ **Function Expressions**

```js
var greet = function() { ... }
let greet = function() { ... }
const greet = function() { ... }
```

These behave like variables.

### If declared with `var`:

* hoisted with `undefined`

```js
greet();  // ❌ TypeError: greet is not a function
var greet = function() { console.log("hi"); }
```

Because:

* greet = undefined during hoisting
* greet() → undefined is not callable

---

### If declared with `let` or `const`:

They are inside TDZ.

```js
greet();  // ❌ ReferenceError
const greet = function() {};
```

---

# 🧱 **7. Hoisting inside Block Scope**

Example:

```js
{
  console.log(x);
  let x = 10;
}
```

Block creates its own hoisting:

* memory created for x inside block
* but uninitialized → TDZ

Exactly same rules as global.

---

# 📦 **8. Hoisting inside Functions**

Example:

```js
function test() {
  console.log(a);
  var a = 5;
  console.log(a);
}
```

Works because function has its own hoisting:

### Memory Phase:

```
a: undefined
```

### Execution:

* log(a) → undefined
* a = 5
* log(a) → 5

---

Another example:

```js
function test() {
  console.log(x);
  let x = 5;
}
test();
```

ReferenceError — because of TDZ.

---

# 💣 **9. Real-World Pitfalls (Interview Level)**

### ❗ Using var inside loops is dangerous:

```js
for (var i = 1; i <= 3; i++) {
  setTimeout(() => console.log(i), 0);
}
```

Output:

```
4
4
4
```

Because `var` ignores block and leaks into global scope.

### ✔ Correct version:

```js
for (let i = 1; i <= 3; i++) {
  setTimeout(() => console.log(i), 0);
}
```

Output:

```
1
2
3
```

Because `let` creates a new block-scope binding for each iteration.

---

# 🎯 **HOISTING CHEAT TABLE (print this in your mind)**

| Type                            | Hoisted? | Initialized?    | TDZ? | Can use before definition? |
| ------------------------------- | -------- | --------------- | ---- | -------------------------- |
| var                             | ✔        | ✔ undefined     | ❌    | ✔ prints undefined         |
| let                             | ✔        | ❌               | ✔    | ❌ ReferenceError           |
| const                           | ✔        | ❌               | ✔    | ❌ ReferenceError           |
| function declaration            | ✔        | ✔ full function | ❌    | ✔ fully callable           |
| function expression (var)       | ✔        | ✔ undefined     | ❌    | ❌ TypeError                |
| function expression (let/const) | ✔        | ❌               | ✔    | ❌ ReferenceError           |

---

# 🔥 FINAL SUMMARY (Ultra Clean)

```
Hoisting = JS allocates memory before execution.

var → hoisted & initialized with undefined  
let → hoisted but NOT initialized (TDZ)  
const → same as let but must have initializer  
function declarations → fully hoisted  
function expressions → hoisted like variables
```

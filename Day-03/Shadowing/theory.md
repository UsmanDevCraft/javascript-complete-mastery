# 🎯 **JavaScript Shadowing — Complete Lesson**

---

# ✅ **1. What is Shadowing? (Simple Definition)**

**Shadowing** is when a **local variable** has the **same name** as a variable in the **outer scope**, and the local variable *hides/shadows* the outer one inside that scope.

➡️ Inner variable **overrides** the outer variable *within its block/function*.

---

# ✅ **2. Basic Example**

```js
let a = 10;

function demo() {
  let a = 20;  // shadows outer 'a'
  console.log(a);
}

demo();
console.log(a);
```

### Output:

```
20
10
```

Inside the function, the `a = 20` variable shadows the outer one.

---

# 🧠 **3. Visual “Shadow” Mental Model**

```
Global a = 10
   |
   |  function creates its own a = 20
   ↓
Function scope doesn't see the outer a.
The inner variable casts a "shadow" over it.
```

---

# ✅ **4. Shadowing with Block Scope (let, const)**

```js
let x = 5;

{
  let x = 100; // block scoped shadowing
  console.log(x);
}

console.log(x);
```

### Output:

```
100
5
```

Block-scoped variables shadow outer variables *inside that specific block*.

---

# 🔥 **5. Shadowing vs Re-declaring — VERY important difference**

### ❌ Redeclaring with `var`

`var` does **not** respect block scope:

```js
var x = 10;

{
  var x = 20; // same scope!
}

console.log(x);
```

### Output:

```
20
```

This is NOT shadowing…
This is **re-declaration in the same scope**, because `var` is function-scoped.

---

# ⚠️ **6. Illegal Shadowing (must know!)**

Illegal shadowing happens when a `let` or `const` variable tries to shadow a `var` in the **same function scope**.

```js
var a = 10;

{
  let a = 20; // ❌ Illegal shadowing
}
```

This throws an error:

```
SyntaxError: Identifier 'a' has already been declared
```

### Why?

Because:

* `var a` is **function scoped**
* `let a` is **block scoped**
* But since both are declared inside **the same functional scope**, JS disallows it (to avoid accidental bugs)

---

# 🔥 **7. Legal Shadowing Example**

```js
let a = 10;

function test() {
  let a = 20;  // ✔ allowed
  console.log(a);
}
```

Different scopes → allowed.

---

# 🧨 **8. Shadowing + TDZ (Tricky!)**

```js
let x = 100;

{
  console.log(x); // ❌ ReferenceError (TDZ)
  let x = 20;
}
```

### Why error?

Because the inner `let x` shadows the outer `x`,
and the inner `x` is in the **Temporal Dead Zone** until its declaration line.

Inside the block, JS behaves like:

```
There is an x here.
But you can't use it until its declaration.
```

---

# 🔁 **9. Function Parameter Shadowing**

```js
let x = 50;

function f(x) {  // parameter shadows outer x
  console.log(x);
}

f(200);
console.log(x);
```

### Output:

```
200
50
```

The parameter has higher priority inside the function.

---

# 🧱 **10. Nested Shadowing Example**

```js
let a = 1;

function outer() {
  let a = 2;

  function inner() {
    let a = 3;
    console.log(a);
  }

  inner();
}

outer();
console.log(a);
```

### Output:

```
3
1
```

The innermost variable wins.

---

# ⚙️ **11. Shadowing with var inside functions**

```js
var a = 10;

function test() {
  console.log(a); // undefined → because var a (hoisted)
  var a = 20;
}

test();
```

Hoisting plays a role:

Inside the function:

* `var a` gets hoisted
* So it shadows the global `a`
* But its value is `undefined` until assign

---

# 📌 **12. Shadowing in Strict Mode vs Non-Strict Mode**

Strict mode **does NOT affect shadowing rules**.

Shadowing works the same.
What strict mode DOES affect is accidental global creation, duplication, silent errors — but not shadowing.

---

# 🧪 **13. Interview Trick Questions**

### ❓**Q1: Output?**

```js
let a = 10;

function test() {
  console.log(a);
  let a = 20;
}

test();
```

### ✔ Answer:

```
ReferenceError (TDZ)
```

Because `let a` shadowed outer `a` but is in TDZ.

---

### ❓**Q2: Output?**

```js
var x = 1;

{
  var x = 2;
}

console.log(x);
```

### ✔ Answer:

```
2
```

Not shadowing — just redeclared in same scope.

---

### ❓**Q3: Output?**

```js
let a = 10;

{
  const a = 20;
  {
    let a = 30;
    console.log(a);
  }
}
```

### ✔ Answer:

```
30
```

---

# 🎯 Final Summary (Shadowing in 7 Seconds)

* Shadowing = inner variable hides outer variable
* `let` + `const` → block scope (clean shadowing)
* `var` → function scope (accidental overwrites)
* Illegal shadowing: `let` cannot shadow a `var` in same function scope
* Parameters shadow outer values
* Shadowing + TDZ = ReferenceErrors
* Shadowing is a core part of how lexical scope works

---

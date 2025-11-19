# ✅ **HARD (Scope — 4 Problems)**

---

### **Problem 7 — Hoisting + Function Scope Output?**

```js
console.log(a);
var a = 20;

function show() {
  console.log(a);
  var a = 10;
  console.log(a);
}

show();
console.log(a);
```

### **Solution:**

```
undefined
undefined
10
20
```

Inside `show()`, `var a` is hoisted and initialized as `undefined`.

---

### **Problem 8 — let + Closures Output?**

```js
let funcs = [];

for (let i = 0; i < 3; i++) {
  funcs.push(function () {
    console.log(i);
  });
}

funcs[0]();
funcs[1]();
funcs[2]();
```

### **Solution:**

```
0
1
2
```

Each loop iteration creates a new `i` because of block-scoped `let`.

---

### **Problem 9 — Shadowing + TDZ Output?**

```js
let value = 100;

function calc() {
  console.log(value);

  let value = 50;

  console.log(value);
}

calc();
```

### **Solution:**

Error:

```
ReferenceError: Cannot access 'value' before initialization
```

Inner `value` shadows global `value`, but it's in TDZ before initialization.

---

### **Problem 10 — Scope Chain Output?**

```js
let x = 1;

function a() {
  let x = 2;

  function b() {
    let x = 3;

    function c() {
      console.log(x);
    }

    c();
  }

  b();
}

a();
```

### **Solution:**

```
3
```

Function `c` finds `x` in its nearest lexical scope (inside `b()`).

---

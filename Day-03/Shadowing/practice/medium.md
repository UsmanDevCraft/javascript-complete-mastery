# 🟦 **MEDIUM (Shadowing — 3 Problems)**

---

### **Problem 4 — Output?**

```js
var a = 1;

{
  var a = 2;
  console.log(a);
}

console.log(a);
```

### **Solution:**

```
2
2
```

This is NOT shadowing — it’s re-declaration because `var` is **function scoped**, not block scoped.

---

### **Problem 5 — Output?**

```js
let x = 100;

function demo() {
  console.log(x);
  let x = 50;
}

demo();
```

### **Solution:**

```
ReferenceError: Cannot access 'x' before initialization
```

Inner `let x` shadows outer one, and because it is hoisted into TDZ → accessing before declaration causes error.

---

### **Problem 6 — Output?**

```js
let a = 10;

function outer() {
  let a = 20;

  function inner() {
    console.log(a);
  }

  inner();
}

outer();
```

### **Solution:**

```
20
```

Inner function sees nearest `a` (lexical scope).

---

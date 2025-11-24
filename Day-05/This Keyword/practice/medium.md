# ⚡ **MEDIUM (3 Problems)**

---

### **Problem 1 — Output?**

```js
const obj = {
  a: 10,
  b: () => console.log(this.a)
};

obj.b();
```

### **Solution**

`undefined`
**Explanation:** Arrow functions do NOT have their own `this`; they inherit from parent (global).

---

### **Problem 2 — Output?**

```js
"use strict";

function x() {
  console.log(this);
}

x();
```

### **Solution**

`undefined`
**Explanation:** In strict mode, regular functions do NOT default to global; `this` stays undefined.

---

### **Problem 3 — Output?**

```js
const user = {
  name: "Ali",
  greet() {
    setTimeout(function() {
      console.log(this.name);
    }, 0);
  }
};

user.greet();
```

### **Solution**

`undefined`
**Explanation:** Inside setTimeout’s regular function, `this` becomes global, not the object.

---

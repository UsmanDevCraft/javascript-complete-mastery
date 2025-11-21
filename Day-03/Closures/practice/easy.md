# ✅ **EASY (Closures — 3 Problems)**

---

### **Problem 1 — Output?**

```js
function outer() {
  let a = 5;
  return function () {
    console.log(a);
  };
}

const fn = outer();
fn();
```

### **Solution:**

```
5
```

The inner function remembers `a`.

---

### **Problem 2 — Output?**

```js
function make() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const c = make();
console.log(c());
console.log(c());
```

### **Solution:**

```
1
2
```

`count` is preserved inside the closure.

---

### **Problem 3 — Output?**

```js
function x() {
  var a = 10;
  function y() {
    console.log(a);
  }
  a = 20;
  return y;
}

const z = x();
z();
```

### **Solution:**

```
20
```

Closures capture **reference**, not value.

---

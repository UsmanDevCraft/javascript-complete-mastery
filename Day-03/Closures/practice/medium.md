# 🟦 **MEDIUM (Closures — 3 Problems)**

---

### **Problem 4 — Fix the code so output is 0, 1, 2**

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

### **Solution:**

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

`let` creates block scope → each iteration gets its own closure.

---

### **Problem 5 — What will be printed?**

```js
function greet(name) {
  return function () {
    return "Hello " + name;
  };
}

const g = greet("Usman");
console.log(g());
```

### **Solution:**

```
Hello Usman
```

Inner function uses `name` from outer scope.

---

### **Problem 6 — Predict output**

```js
function counter() {
  let c = 10;

  return {
    inc() { c++; },
    dec() { c--; },
    get() { return c; }
  };
}

const ctr = counter();
ctr.inc();
ctr.dec();
ctr.dec();
console.log(ctr.get());
```

### **Solution:**

```
9
```

10 → inc (11) → dec (10) → dec (9)

---

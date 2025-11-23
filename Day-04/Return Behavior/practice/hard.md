# 🔥 **HARD (Return — 4 Problems)**

---

### **Problem 1 — Arrow function with braces but no return**

```js
const fn = () => {
  10;
};

console.log(fn());
```

### **Solution:**

```
undefined
```

Braces block implicit return; needs `return`.

---

### **Problem 2 — Return inside callback does NOT exit outer function**

```js
function test() {
  [1, 2, 3].forEach(n => {
    return n;
  });

  return "done";
}

console.log(test());
```

### **Solution:**

```
done
```

Return exits callback, NOT outer function.

---

### **Problem 3 — Return in constructor**

```js
function Person() {
  this.name = "Ali";
  return 100;
}

console.log(new Person());
```

### **Solution:**

```
{ name: 'Ali' }
```

Primitive returns are ignored in constructors.

---

### **Problem 4 — Async return behavior**

```js
async function x() {
  return 7;
}

console.log(x());
```

### **Solution:**

```
Promise { 7 }
```

Async functions always return a Promise.

---

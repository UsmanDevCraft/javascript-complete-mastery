# ✅ **EASY (Return — 3 Problems)**

---

### **Problem 1 — What is the output?**

```js
function test() {
  return 5;
}

console.log(test());
```

### **Solution:**

```
5
```

Return sends a value back to the caller.

---

### **Problem 2 — Missing return**

```js
function greet() {
  console.log("Hello");
}

console.log(greet());
```

### **Solution:**

```
Hello
undefined
```

Function logs `"Hello"` but returns nothing → `undefined`.

---

### **Problem 3 — Implicit return (arrow)**

```js
const add = (a, b) => a + b;

console.log(add(2, 3));
```

### **Solution:**

```
5
```

Arrow without `{}` returns implicitly.

---

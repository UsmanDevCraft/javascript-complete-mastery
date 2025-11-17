# ✅ **EASY (Hoisting — 3 Problems)**

---

### **Problem 1**

```js
console.log(a);
var a = 10;
```

### **Solution:**

```
undefined
```

`var` is hoisted + initialized with undefined.

---

### **Problem 2**

```js
console.log(b);
let b = 20;
```

### **Solution:**

❌ ReferenceError
Because `let` is hoisted but **not initialized** → TDZ.

---

### **Problem 3**

```js
greet();
function greet() {
  console.log("Hi");
}
```

### **Solution:**

```
Hi
```

Function declarations are fully hoisted.

---

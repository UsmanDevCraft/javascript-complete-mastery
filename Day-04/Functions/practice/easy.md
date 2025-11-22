# ✅ **EASY (Functions — 3 Problems)**

---

### **Problem 1 — Output? (Declaration Hoisting)**

```js
sayHi();

function sayHi() {
  console.log("Hi");
}
```

### **Solution:**

```
Hi
```

Function declarations are fully hoisted.

---

### **Problem 2 — Output? (Expression TDZ)**

```js
greet();

const greet = function () {
  console.log("Hello");
};
```

### **Solution:**

```
ReferenceError (TDZ)
```

Function expressions are not hoisted; the variable is in TDZ.

---

### **Problem 3 — Output? (Arrow Implicit Return)**

```js
const sum = (a, b) => a + b;

console.log(sum(2, 3));
```

### **Solution:**

```
5
```

Arrow functions can return implicitly.

---

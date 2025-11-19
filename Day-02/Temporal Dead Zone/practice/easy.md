# ✅ **EASY (3 Problems)**

---

### **Problem 1 — Output?**

```js
console.log(a);
let a = 5;
```

### **Solution:**

```
ReferenceError: Cannot access 'a' before initialization
```

`a` is in the TDZ from the start of the scope until the line `let a = 5`.

---

### **Problem 2 — Output?**

```js
{
  console.log(msg);
  let msg = "hello";
}
```

### **Solution:**

```
ReferenceError
```

TDZ starts at the beginning of the block, so `msg` is not accessible before initialization.

---

### **Problem 3 — Output?**

```js
const x = 10;

{
  console.log(x);
  const x = 20;
}
```

### **Solution:**

```
ReferenceError
```

The inner `x` shadows the outer `x`. Inside the block, the new `x` is in TDZ.

---

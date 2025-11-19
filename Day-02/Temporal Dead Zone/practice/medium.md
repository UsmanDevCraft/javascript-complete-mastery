# 🟡 **MEDIUM (3 Problems)**

---

### **Problem 4 — Output?**

```js
let num = 1;

function test() {
  console.log(num);
  let num = 2;
}

test();
```

### **Solution:**

```
ReferenceError
```

Inside `test()`, the inner `num` creates a new variable in the function scope.
TDZ applies — so `console.log(num)` hits the inner variable, not the outer one.

---

### **Problem 5 — Output?**

```js
{
  let a = 10;

  {
    console.log(a);
    let a = 20;
  }
}
```

### **Solution:**

```
ReferenceError
```

Inner block creates its own `a` → TDZ begins at start of that block → accessing it before initialization triggers error.

---

### **Problem 6 — Output?**

```js
console.log(typeof myVar);

let myVar = "OK";
```

### **Solution:**

```
ReferenceError
```

`typeof` normally returns `"undefined"` for undeclared variables,
**but TDZ variables break that rule**.

Since `myVar` is in the TDZ, `typeof` cannot access it.

---

# 🔥 **MEDIUM (Variables — 3 Problems)**

---

### **Problem 4 — What prints?**

```js
let a = 10;

{
  let a = 20;
  console.log(a);
}

console.log(a);
```

### **Solution:**

```
20
10
```

Block-scope shadowing.

---

### **Problem 5 — Output?**

```js
const user = { name: "usman" };
user.name = "awan";
console.log(user.name);
```

### **Solution:**

```
awan
```

`const` locks reference, not inner values.

---

### **Problem 6 — Valid or Error?**

```js
var a = 10;

{
  let a = 20;
}
```

### **Solution:**

✔ Valid
`var` is in global scope.
`let` is in block scope.
Different scopes → no conflict.

---

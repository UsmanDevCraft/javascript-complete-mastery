# 🟨 **MEDIUM (Return — 3 Problems)**

---

### **Problem 1 — Return inside block**

```js
function check(n) {
  if (n > 5) return "big";
  return "small";
}

console.log(check(10));
```

### **Solution:**

```
big
```

First return stops function.

---

### **Problem 2 — Return inside loop**

```js
function loop() {
  for (let i = 1; i <= 3; i++) {
    return i;
  }
}

console.log(loop());
```

### **Solution:**

```
1
```

Return ends the whole function on first iteration.

---

### **Problem 3 — Arrow function object return**

```js
const makeUser = () => ({ name: "Usman" });

console.log(makeUser().name);
```

### **Solution:**

```
Usman
```

Object must be wrapped in `()` for implicit return.

---

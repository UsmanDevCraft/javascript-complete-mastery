# ✅ **EASY (Scope — 3 Problems)**

---

### **Problem 1 — Global Scope Output?**

```js
let x = 10;

function print() {
  console.log(x);
}

print();
console.log(x);
```

### **Solution:**

```
10
10
```

Because `x` is global, accessible everywhere.

---

### **Problem 2 — Block Scope Output?**

```js
if (true) {
  let a = 5;
}

console.log(a);
```

### **Solution:**

Error:

```
ReferenceError: a is not defined
```

`let` is block-scoped; `a` exists only inside `{}`.

---

### **Problem 3 — var Loop Output?**

```js
for (var i = 1; i <= 3; i++) {}
console.log(i);
```

### **Solution:**

```
4
```

`var` is function-scoped, not block-scoped.

---

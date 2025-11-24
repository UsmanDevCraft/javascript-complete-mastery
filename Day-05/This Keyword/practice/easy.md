# ✅ **EASY (3 Problems)**

---

### **Problem 1 — Output?**

```js
console.log(this);
```

### **Solution**

**Browser:** `window`
**Node:** `{}`
**Explanation:** Top-level `this` = global object (browser) or module object (Node).

---

### **Problem 2 — Output?**

```js
function test() {
  console.log(this);
}
test();
```

### **Solution**

Browser → `window`
Node → `global`
**Explanation:** Regular function call defaults to global context in non-strict mode.

---

### **Problem 3 — Output?**

```js
const obj = {
  a: 5,
  show() {
    console.log(this.a);
  }
};

obj.show();
```

### **Solution**

`5`
**Explanation:** Method call → `this` refers to the object before dot (`obj`).

---

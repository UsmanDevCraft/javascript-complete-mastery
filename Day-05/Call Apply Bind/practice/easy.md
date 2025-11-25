# ✅ **EASY (3 Problems)**

---

### **Problem 1 — Output?**

```js
function say() {
  console.log(this.x);
}

const obj = { x: 10 };

say.call(obj);
```

### **Solution**

`10`
**Explanation:** `call` sets `this` to the object passed → `obj`.

---

### **Problem 2 — Output?**

```js
function sum(a, b) {
  console.log(a + b);
}

sum.apply(null, [5, 7]);
```

### **Solution**

`12`
**Explanation:** `apply` calls the function using an array of arguments.

---

### **Problem 3 — Output?**

```js
function greet(name) {
  console.log("Hi " + name);
}

const g = greet.bind(null, "Usman");
g();
```

### **Solution**

`Hi Usman`
**Explanation:** `bind` creates a new function with preset argument `"Usman"`.

---

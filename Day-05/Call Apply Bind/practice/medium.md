# ⚡ **MEDIUM (3 Problems)**

---

### **Problem 1 — Output?**

```js
const user = {
  name: "Ali",
  say() {
    console.log(this.name);
  }
};

const fn = user.say;
fn.call(user);
```

### **Solution**

`Ali`
**Explanation:** Losing method reference loses `this`, but `call(user)` restores it.

---

### **Problem 2 — Output?**

```js
function add(a, b) {
  console.log(this.x + a + b);
}

const obj = { x: 5 };

add.call(obj, 10, 15);
```

### **Solution**

`30`
**Explanation:** `this.x = 5`, so `5 + 10 + 15`.

---

### **Problem 3 — Output?**

```js
function intro(age, country) {
  console.log(this.name, age, country);
}

const p = { name: "Usman" };

intro.apply(p, [22, "PK"]);
```

### **Solution**

`Usman 22 PK`
**Explanation:** `apply` passes arguments as array and sets `this = p`.

---

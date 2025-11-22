# 🟨 **MEDIUM (Functions — 3 Problems)**

---

### **Problem 1 — `this` in Arrow vs Normal Function**

```js
const user = {
  name: "Usman",
  show1() {
    console.log(this.name);
  },
  show2: () => {
    console.log(this.name);
  }
};

user.show1();
user.show2();
```

### **Solution:**

```
Usman
undefined
```

Normal functions use object as `this`.
Arrow functions take `this` from outer/global scope → undefined.

---

### **Problem 2 — Function Expression vs Declaration**

```js
console.log(typeof a);
console.log(typeof b);

function a() {}

const b = function () {};
```

### **Solution:**

```
function
undefined
```

Declarations exist at creation phase.
Expressions don’t assign value until execution.

---

### **Problem 3 — Arrow Function + Object Return**

```js
const makeUser = () => ({ name: "Ali" });

console.log(makeUser().name);
```

### **Solution:**

```
Ali
```

Objects require parentheses in arrow implicit return.

---

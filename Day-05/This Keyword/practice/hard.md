# 🔥 **HARD (4 Problems)**

---

### **Problem 1 — Output?**

```js
const obj = {
  name: "Usman",
  greet() {
    return () => console.log(this.name);
  }
};

const x = obj.greet();
x();
```

### **Solution**

`Usman`
**Explanation:** Arrow function captures lexical `this` from `greet()`, which is `obj`.

---

### **Problem 2 — Output?**

```js
class A {
  constructor() {
    this.num = 100;
  }

  show() {
    console.log(this.num);
  }
}

const a = new A();
const s = a.show;
s();
```

### **Solution**

`undefined`
**Explanation:** Extracting method into variable loses object context; becomes regular function call.

---

### **Problem 3 — Output?**

```js
const obj = {
  x: 15,
  y: {
    z: function() {
      console.log(this.x);
    }
  }
};

obj.y.z();
```

### **Solution**

`undefined`
**Explanation:** `this` refers to `y` object, and `y.x` does not exist, so undefined.

---

### **Problem 4 — Output?**

```js
let a = {
  value: 50,
  print: function() {
    (function() {
      console.log(this.value);
    })();
  }
};

a.print();
```

### **Solution**

`undefined`
**Explanation:** IIFE runs as a regular function → `this` becomes global, not `a`.

---

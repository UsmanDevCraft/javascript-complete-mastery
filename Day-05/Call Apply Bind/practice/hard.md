# 🔥 **HARD (4 Problems)**

---

### **Problem 1 — Output?**

```js
const a = { value: 50 };

function print() {
  console.log(this.value);
}

const b = print.bind(a);
b.call({ value: 100 });
```

### **Solution**

`50`
**Explanation:** `bind` permanently fixes `this = a`; `call` cannot override it.

---

### **Problem 2 — Output?**

```js
const obj = {
  x: 10,
  y: function() {
    console.log(this.x);
  }
};

const z = obj.y.bind({ x: 99 });
z();
```

### **Solution**

`99`
**Explanation:** `bind` forces `this` to `{ x: 99 }`, ignoring obj.

---

### **Problem 3 — Output?**

```js
function show() {
  console.log(this.a);
}

const o1 = { a: 1 };
const o2 = { a: 2 };

const f = show.bind(o1);
f.call(o2);
```

### **Solution**

`1`
**Explanation:** Once bound, `this` cannot be changed again.

---

### **Problem 4 — Output?**

```js
function multiply(a, b, c) {
  console.log(a * b * c);
}

const f = multiply.bind(null, 2);
f.apply(null, [3, 4]);
```

### **Solution**

`24`
**Explanation:** `bind(null, 2)` sets first argument = 2; remaining args come from apply → `2 * 3 * 4`.

---

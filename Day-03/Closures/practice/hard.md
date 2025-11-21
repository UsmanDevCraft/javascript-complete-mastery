# 🔥 **HARD (Closures — 4 Problems)**

---

### **Problem 7 — Create a function that runs only once**

```js
function once(fn) {
  // write code here
}

const hello = once(() => console.log("Hello"));
hello();
hello();
```

### **Solution:**

```js
function once(fn) {
  let ran = false;

  return function () {
    if (!ran) {
      ran = true;
      return fn();
    }
  };
}
```

Second call does nothing.

---

### **Problem 8 — Build a memoize function**

```js
function memoize(fn) {
  // your code
}

const square = memoize(n => n * n);

console.log(square(5)); 
console.log(square(5)); 
```

### **Solution:**

```js
function memoize(fn) {
  const cache = {};

  return function (n) {
    if (cache[n]) return cache[n];
    const result = fn(n);
    cache[n] = result;
    return result;
  };
}
```

Second call comes from cache.

---

### **Problem 9 — Output? (Tricky)**

```js
function outer() {
  let arr = [];

  for (var i = 0; i < 3; i++) {
    arr.push(function () {
      console.log(i);
    });
  }

  return arr;
}

const funcs = outer();
funcs[0]();
funcs[1]();
funcs[2]();
```

### **Solution:**

```
3
3
3
```

Because all functions share the same `i` (var → function scoped).

---

### **Problem 10 — Fix above code to print 0, 1, 2**

```js
function outer() {
  let arr = [];

  for (var i = 0; i < 3; i++) {
    // fix here
    arr.push(/* something */);
  }

  return arr;
}
```

### **Solution 1 — Using let**

```js
for (let i = 0; i < 3; i++) {
  arr.push(() => console.log(i));
}
```

### **Solution 2 — IIFE**

```js
for (var i = 0; i < 3; i++) {
  (function (x) {
    arr.push(() => console.log(x));
  })(i);
}
```

---

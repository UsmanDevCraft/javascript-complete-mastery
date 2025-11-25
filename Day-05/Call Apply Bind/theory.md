# 🚀 **THE ULTIMATE JS LESSON — `call()`, `apply()`, `bind()`**

These three methods are used to **manually control the value of `this`** inside a function.

---

# 🔥 **1. Why do we need call/apply/bind?**

Because sometimes, we want to run a function with:

* **a specific object as `this`**
* **custom arguments**

Example problem:

```js
function greet() {
  console.log(this.name);
}

const user = { name: "Usman" };

greet();          // ❌ undefined (global `this`)
```

We want:
👉 "Run greet, but set `this` to user"

Here enter **call, apply, bind**.

---

# 🧠 **2. `call()` — immediately calls the function with custom this**

```js
func.call(thisValue, arg1, arg2, ...)
```

### Example:

```js
function greet(age) {
  console.log(this.name, age);
}

const user = { name: "Usman" };

greet.call(user, 22);
```

✔ Sets `this = user`
✔ Immediately executes greet
✔ Arguments are passed **one-by-one**

---

# 🧠 **3. `apply()` — same as call but arguments in array**

```js
func.apply(thisValue, [arg1, arg2])
```

### Example:

```js
greet.apply(user, [22]);
```

✔ Same output as `call()`
✔ Just different argument format

---

# 🧠 **4. `bind()` — returns a NEW function with `this` fixed**

```js
const newFn = func.bind(thisValue, arg1, arg2...)
```

### Example:

```js
const greetUser = greet.bind(user, 22);
greetUser();
```

✔ Does NOT run immediately
✔ Returns a new function with permanent `this = user`

---

# 🔑 **5. The Three in One Line**

```
call  → call immediately (args individually)
apply → call immediately (args in array)
bind  → return new function (does NOT call)
```

---

# 📦 **6. Why use call/apply/bind? Real-world Uses**

### 1. Borrowing methods from other objects

```js
let obj1 = { name: "Ali" };
let obj2 = { name: "Usman" };

function sayHi() {
  console.log("Hi " + this.name);
}

sayHi.call(obj2);
```

---

### 2. Using array methods on non-array objects

```js
const nums = {
  0: 4,
  1: 8,
  length: 2
};

console.log(Array.prototype.join.call(nums, "-"));
```

---

### 3. Fixing context in event handlers (browser)

```js
button.addEventListener("click", obj.method.bind(obj));
```

---

### 4. Function currying with `bind`

```js
function multiply(x, y) {
  return x * y;
}

const double = multiply.bind(null, 2);
console.log(double(5)); // 10
```

---

# 🧨 **7. Tricky & IMPORTANT Behavior**

---

## ⚠ Arrow functions IGNORE call/apply/bind

```js
const obj = { a: 10 };

const x = () => console.log(this.a);
x.call(obj);  // ❌ does not change `this`
```

Because arrow functions have **lexical `this`**.

---

## ⚠ bind returns a new function → NOT change original

```js
function a() {}
const b = a.bind(obj);

a !== b  // true
```

---

## ⚠ Multiple binds = first one wins

```js
const x = greet.bind(obj1).bind(obj2);

x();  // uses obj1
```

---

# ⚡ **8. Browser vs Node Behavior?**

NO DIFFERENCE ✔
`call`, `apply`, `bind` behave exactly the same in both environments.

Only difference is WHAT `this` resolves to in global context — but the methods behave the same.

---

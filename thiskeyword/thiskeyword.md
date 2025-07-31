# JavaScript `this` Keyword

The `this` keyword in JavaScript is one of the trickiest concepts because its value depends on the context in which a function is called. Simply put, **`this` refers to the object that is executing the current function**.

---

## What Does `this` Refer To?

- **In the global scope:** `this` refers to the global object (`window` in browsers, `global` in Node.js).
- **Inside an object method:** `this` refers to the object that owns the method.
- **Inside a regular function:** `this` depends on how the function is called — it can be `undefined` in strict mode or the global object otherwise.
- **Inside arrow functions:** Arrow functions don’t have their own `this`; they inherit `this` from the surrounding lexical scope.

---

## Simple Examples

```javascript
console.log(this); // In global scope, refers to window (in browsers)

const obj = {
  name: "Ali",
  introduce: function() {
    console.log(this.name); // "Ali" — this refers to the object
  }
};

obj.introduce();

const arrowFunc = () => {
  console.log(this);
};

arrowFunc(); // Refers to lexical this, usually window in global scope

```

## this in Classes

In JavaScript classes, `this` refers to the current instance (object) of the class.

When you create a new object from a class using `new`, `this` inside the class methods points to that specific object.

### Example:

```javascript
class Person {
  constructor(name) {
    this.name = name; // 'this' refers to the new object being created
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const person1 = new Person("Ali");
person1.greet(); // Hello, my name is Ali

```

## Arrow Functions and `this`

Arrow functions do not create their own `this` context. Instead:

The `this` inside an arrow function is the same as the `this` in its surrounding scope.

Using arrow functions as object methods usually causes unexpected `this` behavior.

---

## Example: Regular Function vs Arrow Function

```javascript
const obj = {
  name: "Ayşe",
  introduce1: function() {
    console.log(this.name); // "Ayşe"
  },
  introduce2: () => {
    console.log(this.name); // undefined, because arrow uses global this
  }
};

obj.introduce1(); // "Ayşe"
obj.introduce2(); // undefined

```

## Why Do We Use this?

- To write dynamic and reusable code where functions can operate on the object that calls them.

- To know which object a function belongs to at runtime.

- To handle events and callbacks where the calling object might change.

---

## ✅ Summary

- this refers to the object that calls the function.

- Arrow functions do not have their own this; they inherit it from the lexical scope.

- In the global scope, this refers to the global object (window or global).

- In regular functions, the value of this is dynamic depending on the caller.

---

## 💡 Next Steps

- [Prototype & Inheritance](../prototype-inheritance/prototype_inheritance.md)

---

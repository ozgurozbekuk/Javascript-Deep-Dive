# JavaScript Prototype & Inheritance

Understanding **prototype** and **inheritance** in JavaScript is essential for working with objects and object-oriented programming. These concepts help us share and reuse code efficiently.

---

## What is a Prototype?

- In JavaScript, every function (used as a constructor) has a special property called `prototype`.
- This `prototype` object contains properties and methods that will be shared across all instances created from the constructor.
- When you access a property or method on an object, JavaScript first checks the object itself. If not found, it checks the object's prototype chain.

---

### Basic Example:

```js
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log("Hello, my name is " + this.name);
};

const alice = new Person("Alice");
alice.greet(); // Hello, my name is Alice
```

In this example, the `greet` method is defined on `Person.prototype`, not directly on `alice`. JavaScript finds it via the prototype chain.

---

## What is Inheritance?

- Inheritance allows one object to use properties and methods from another object.
- JavaScript uses **prototypal inheritance** via the prototype chain.
- This enables reuse of logic and cleaner code structure.

---

### Inheritance Example:

```js
function Animal(type) {
  this.type = type;
}

Animal.prototype.makeSound = function() {
  console.log(this.type + " makes a sound.");
};

function Dog(name) {
  this.name = name;
  this.type = "Dog";
}

// Inherit from Animal
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Add Dog-specific method
Dog.prototype.bark = function() {
  console.log(this.name + " barks.");
};

const rex = new Dog("Rex");
rex.makeSound();  // Dog makes a sound.
rex.bark();       // Rex barks.
```

Here, `Dog` inherits the `makeSound` method from `Animal`, and also has its own method `bark`.

---

## ✅ Summary

- **Prototype**: An object that provides shared properties/methods to instances.
- **Inheritance**: A mechanism to use features from another object.
- Prototypal inheritance allows objects to inherit from other objects via the prototype chain.
- Use `Object.create()` to set up inheritance manually.

---

## 💡 Next Steps

- [Strict Mode](../strict-mode/strictmode.md)

---

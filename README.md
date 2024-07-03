# JavascriptOOPS

# 📘 OOP in JavaScript

Welcome to the guide on Object-Oriented Programming (OOP) in JavaScript! This documentation will cover all the key concepts of OOP, including examples to help you understand and implement them in your projects. 

## Table of Contents
- [Introduction to OOP](#introduction-to-oop)
- [Classes and Objects](#classes-and-objects)
- [Constructors](#constructors)
- [Inheritance](#inheritance)
- [Encapsulation](#encapsulation)
- [Polymorphism](#polymorphism)
- [Abstraction](#abstraction)

## Introduction to OOP 🧑‍💻

Object-Oriented Programming (OOP) is a programming paradigm that uses objects and classes to structure and organize code. It helps in making the code more modular, reusable, and easier to maintain.

## Classes and Objects 🏛️

- **Class**: A blueprint for creating objects (a particular data structure).
- **Object**: An instance of a class.

### Example:

```javascript
// Define a class
class Car {
  constructor(brand, model) {
    this.brand = brand;
    this.model = model;
  }

  displayInfo() {
    return `🚗 ${this.brand} ${this.model}`;
  }
}

// Create an object
const myCar = new Car('Toyota', 'Corolla');
console.log(myCar.displayInfo()); // 🚗 Toyota Corolla
```

## Constructors 🛠️

- A constructor is a special method used to initialize objects.
- It is called automatically when an object is created.

### Example:

```javascript
class Animal {
  constructor(name, type) {
    this.name = name;
    this.type = type;
  }

  sound() {
    return `${this.name} makes a sound!`;
  }
}

const dog = new Animal('Dog', 'Mammal');
console.log(dog.sound()); // Dog makes a sound!
```

## Inheritance 🧬

- Inheritance allows a class to inherit properties and methods from another class.
- The class that inherits is called the **subclass** or **derived class**.
- The class being inherited from is called the **superclass** or **base class**.

### Example:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  move() {
    return `${this.name} is moving.`;
  }
}

class Bird extends Animal {
  fly() {
    return `${this.name} is flying! 🕊️`;
  }
}

const sparrow = new Bird('Sparrow');
console.log(sparrow.move()); // Sparrow is moving.
console.log(sparrow.fly()); // Sparrow is flying! 🕊️
```

## Encapsulation 🔒

- Encapsulation is the bundling of data and methods that operate on the data within one unit, e.g., a class.
- It restricts direct access to some of an object's components, which is a means of preventing accidental interference and misuse.

### Example:

```javascript
class Person {
  constructor(name, age) {
    this._name = name; // Private property conventionally marked with _
    this._age = age;
  }

  getName() {
    return this._name;
  }

  getAge() {
    return this._age;
  }

  setAge(newAge) {
    if (newAge > 0) {
      this._age = newAge;
    } else {
      console.log('Invalid age');
    }
  }
}

const john = new Person('John', 30);
console.log(john.getName()); // John
john.setAge(32);
console.log(john.getAge()); // 32
```

## Polymorphism 🔄

- Polymorphism means "many shapes" and allows methods to do different things based on the object it is acting upon.
- It is achieved through method overriding and method overloading.

### Example:

```javascript
class Animal {
  speak() {
    return 'Animal makes a sound';
  }
}

class Dog extends Animal {
  speak() {
    return 'Dog barks 🐶';
  }
}

class Cat extends Animal {
  speak() {
    return 'Cat meows 🐱';
  }
}

const animals = [new Animal(), new Dog(), new Cat()];
animals.forEach(animal => {
  console.log(animal.speak());
});
// Animal makes a sound
// Dog barks 🐶
// Cat meows 🐱
```

## Abstraction 🎭

- Abstraction hides the complex reality while exposing only the necessary parts.
- It can be achieved using abstract classes or interfaces (though JavaScript doesn’t have built-in support for interfaces like TypeScript).

### Example:

```javascript
class Vehicle {
  constructor(type) {
    if (this.constructor === Vehicle) {
      throw new Error('Cannot instantiate abstract class');
    }
    this.type = type;
  }

  move() {
    throw new Error('Abstract method must be implemented');
  }
}

class Car extends Vehicle {
  move() {
    return `The ${this.type} drives on the road 🛣️`;
  }
}

const myCar = new Car('Car');
console.log(myCar.move()); // The Car drives on the road 🛣️
```

## Conclusion 🏁

OOP is a powerful way to structure your JavaScript code, making it more modular and maintainable. By understanding and using these OOP principles, you can write cleaner and more efficient code. Happy coding! 🎉

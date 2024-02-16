### Relationship using JS

1. **Is a:**
   Inheritance example:
   ```javascript
   // Parent class
   class Animal {
       eat() {
           console.log("Animal is eating");
       }
   }

   // Child class inheriting from Animal
   class Dog extends Animal {
       bark() {
           console.log("Dog is barking");
       }
   }

   // Creating an instance of Dog
   const myDog = new Dog();
   myDog.eat(); // Output: Animal is eating
   myDog.bark(); // Output: Dog is barking
   ```

2. **Has a:**
   Composition example:
   ```javascript
   // Engine class
   class Engine {
       start() {
           console.log("Engine started");
       }
   }

   // Car class containing an Engine
   class Car {
       constructor() {
           this.engine = new Engine(); // Car has an Engine
       }

       startCar() {
           this.engine.start(); // Car uses the Engine to start
       }
   }

   // Creating an instance of Car
   const myCar = new Car();
   myCar.startCar(); // Output: Engine started
   ```

3. **Uses a:**
   Dependency example:
   ```javascript
   // Printer class
   class Printer {
       print(document) {
           console.log("Printing: " + document);
       }
   }

   // Office class using Printer to print documents
   class Office {
       constructor(printer) {
           this.printer = printer; // Office uses a Printer
       }

       printDocument(document) {
           this.printer.print(document); // Office uses the Printer to print
       }
   }

   // Creating an instance of Printer and Office
   const myPrinter = new Printer();
   const myOffice = new Office(myPrinter);
   myOffice.printDocument("Report"); // Output: Printing: Report
   ```

These examples demonstrate the concepts of "is a" (inheritance), "has a" (composition), and "uses a" (dependency) in JavaScript programming.

### Relationship using Java

- **Is a:** In Java, "is a" typically refers to inheritance, where one class can inherit properties and behaviors from another class. This is achieved using the "extends" keyword. For example, if class B extends class A, you could say "B is a type of A."

```java
class A {
    // Properties and methods of class A
}

class B extends A {
    // Additional properties and methods specific to class B
}
```

- **Has a:** "Has a" in Java often refers to composition, where one class contains an instance of another class as a member. This is sometimes achieved through instance variables or by passing instances through constructors. For example, if a Car class "has a" Engine, you could say "Car has an Engine."

```java
class Engine {
    // Properties and methods of Engine
}

class Car {
    private Engine engine; // Car has an Engine

    public Car(Engine engine) {
        this.engine = engine;
    }
}
```

- **Uses a:** "Uses a" in Java generally implies dependency, where one class utilizes the functionality of another class. This could be through method calls, parameter passing, or object instantiation. For example, if a class Printer "uses a" Paper object to print, you could say "Printer uses a Paper."

```java
class Paper {
    // Properties and methods of Paper
}

class Printer {
    public void print(Paper paper) {
        // Logic to print using the Paper object
    }
}
```

These concepts are fundamental to object-oriented programming and design in Java.

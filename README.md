### Relationship using JS

1. **Is a:**
   Inheritance example:
   ```javascript
   class Device {
    constructor(brand, model) {
        this.brand = brand;
        this.model = model;
    }
   }

   class Smartphone {
       constructor(brand, model, processor) {
           this.brand = brand;
           this.model = model;
           this.processor = processor;
       }
       getProcessor() {
           return this.processor;
       }
   }
   
   const processor = new Device("Intel", "Core i7");
   const smartphone = new Smartphone("Phone", "xyz model", processor);
   const smartphoneProcessor = smartphone.getProcessor();
   console.log(smartphone);
   
   ```

2. **Has a:**
   Composition example:
   ```javascript
   class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
   }
   class Employee extends Person {
       constructor(id,salary,name,age) {
           super(name, age);
           this.id = id;
           this.salary = salary;
       }
   }
   
   const emp1 = new Employee(1046,35000,'John',22);
   const emp2 = new Employee(1047,40000,'Rajesh',27);
   
   console.log(emp1);
   console.log(emp2);
   ```

3. **Uses a:**
   Dependency example:
   ```javascript
   class Section {
    constructor(id, name) {
        this.id = id;
        this.name = name;
    }
   }

   class College {
        constructor() {
            this.sections = [];
         }

   addSection(id, name) {
        const section = new Section(id, name);
        this.sections.push(section);
   }

   displaySections() {
        console.log("Sections in the college:");
        this.sections.forEach(section => {
            console.log(`ID: ${section.id}, Name: ${section.name}`);
        });
    }
   }
      
      
   const college = new College();
   college.addSection(1, "Computer Science");
   college.addSection(2, "Electrical Engineering");
   college.displaySections();
   ```

### Relationship using Java

1. **Is a:** In Java, "is a" typically refers to inheritance, where one class can inherit properties and behaviors from another class. This is achieved using the "extends" keyword. For example, if class B extends class A, you could say "B is a type of A."

```java
class Person {
    protected String name;
    protected int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Employee extends Person {
    private int id;
    private double salary;

    public Employee(int id, double salary, String name, int age) {
        super(name, age);
        this.id = id;
        this.salary = salary;
    }

    @Override
    public String toString() {
        return "id "+id+" salary "+salary+" name "+name+" age "+age;
    }
}

public class Is_A {
    public static void main(String[] args) {
        Employee emp1 = new Employee(1046, 35000, "John", 22);
        Employee emp2 = new Employee(1047, 40000, "Rajesh", 27);

        System.out.println(emp1);
        System.out.println(emp2);
    }
}
```

2. **Has a:** "Has a" in Java often refers to composition, where one class contains an instance of another class as a member. This is sometimes achieved through instance variables or by passing instances through constructors. For example, if a Car class "has a" Engine, you could say "Car has an Engine."

```java
class Processor {
    private String brand;
    private String model;

    public Processor(String brand, String model) {
        this.brand = brand;
        this.model = model;
    }

    @Override
    public String toString() {
        return "Processor{" +
                "brand='" + brand + '\'' +
                ", model='" + model + '\'' +
                '}';
    }
}

class Mobile {
    private String brand;
    private String model;
    private Processor processor;

    public Mobile(String brand, String model, Processor processor) {
        this.brand = brand;
        this.model = model;
        this.processor = processor;
    }

    public Processor getProcessor() {
        return this.processor;
    }

    @Override
    public String toString() {
        return "Brand "+brand+" Model "+brand+" Processor "+processor;
    }
}

public class Has_A {
    public static void main(String[] args) {
        Processor processor = new Processor("Intel", "Core i7");
        Mobile mobile = new Mobile("Phone", "xyz model", processor);
        Processor mobileProcessor = mobile.getProcessor();
        System.out.println(mobile);
    }
}
```

3. **Uses a:** "Uses a" in Java generally implies dependency, where one class utilizes the functionality of another class. This could be through method calls, parameter passing, or object instantiation. For example, if a class Printer "uses a" Paper object to print, you could say "Printer uses a Paper."

```java
import java.util.*;

class Department{
    int id;
    String name;
    Department(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public String toString() {
        return "id = "+id+" name = "+name;
    }
}
class University {
    List<Department> dept = new ArrayList<>();
    String name;
    University(String name, List<Department> dept) {
        this.name = name;
        this.dept = dept;
    }
    public void getDepartments() {
        dept.stream().forEach(ele-> System.out.println(ele));
    }

}
public class Uses_A {
    public static void main(String[] args) {
        Department cs = new Department(1,"CS");
        Department eee = new Department(2,"EEE");
        List<Department> depts = Arrays.asList(cs,eee);
        University uni = new University("XYZ",depts);
        uni.getDepartments();
    }
}
```

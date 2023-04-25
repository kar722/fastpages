---
toc: true
layout: post
description: Unit 9 Teaching
categories: [markdown]
title: Unit 9 APCSA - Inheritance
---

# Unit 9 Java Inheritance

## Superclass and Subclass
- Inheritance defines a relationship between objects that share characteristics. Specifically it is the mechanism whereby a new class, called a subclass, is created from an existing class, called a superclass, by absorbing its state and behavior and augmenting these with features unique to the new class. We say that the subclass inherits characteristics of its superclass.
- Don’t get confused by the names: a subclass is bigger than a superclass—it contains more data and more methods!
- Inheritance provides an effective mechanism for code reuse. Suppose the code for a superclass has been tested and debugged. Since a subclass object shares features of a superclass object, the only new code required is for the additional characteristics of the subclass.

## Inheritance Heirarchy
- A subclass can itself be a superclass for another subclass, leading to an inheritance hierarchy of classes.
- For example, consider the relationship between these objects: Person, Employee, Student, GradStudent, and UnderGrad.
   - ![image](https://user-images.githubusercontent.com/72475804/232651246-d72c0371-3e02-48fe-8836-66322c3dd89a.png)
   - For any of these classes, an arrow points to its superclass. The arrow designates an inheritance relationship between classes, or, informally, an is-a relationship. Thus, an Employee is-a Person; a Student is-a Person; a GradStudent is-a Student; an UnderGrad is-a Student. Notice that the opposite is not necessarily true: A Person may not be a Student, nor is a Student necessarily an UnderGrad. Note that the is-a relationship is transitive: If a GradStudent is-a Student and a Student is-a Person, then a GradStudent is-a Person.

## Implementing Subclasses
The inheritance relationship between a subclass and a superclass is specified in the declaration of the subclass, using the keyword extends. The general format looks like this:
```
public class Superclass {
  //private instance variables
  //other data members
  //constructors
  //public methods
  //private methods
}

public class Subclass extends Superclass {
  //additional private instance variables
  //additional data members
  //constructors (Not inherited!)
  //additional public methods
  //inherited public methods whose implementation is overridden
  //additional private methods
}
```

### Inheriting Instance Methods and Variables
- The semantics of talking about inheritance is tricky. Subclasses do not inherit the private instance variables or private methods of their superclasses. However, objects of subclasses contain memory for those private instance variables, even though they can’t directly access them. 
- A subclass inherits all the public and protected data members of its parent.
- Classes on the same level in a hierarchy diagram do not inherit anything from eachother. All they have in common is the identical code they inherit from their superclass.

### Method Overriding and the ```super``` Keyword
- Any public method in a superclass can be overridden in a subclass by defining a method with the same return type and signature (name and parameter types).
- By using super we can call the overridden method as shown in the example below:
```
class ABC{
   public void myMethod()
   {
    System.out.println("Overridden method");
   }	   
}
class Demo extends ABC{
   public void myMethod(){
    //This will call the myMethod() of parent class
    super.myMethod();
    System.out.println("Overriding method");
   }
   public static void main( String args[]) {
    Demo obj = new Demo();
    obj.myMethod();
   }
}
```
Output:
```
Class ABC: mymethod()
Class Test: mymethod()
```
- As you see using super keyword, we can access the overriden method.

### Constructor and ```super```
- Constructors are never inherited! If no constructor is written for a subclass, the superclass default constructor with no parameters is generated. 
- If the superclass does not have a default (zero-parameter) constructor, but only a constructor with parameters, a compiler error will occur.
- If there is a default constructor in the superclass, inherited data members will be initialized as for the superclass.
- Additional instance variables in the subclass will get a default initialization—0 for primitive types and null for reference types. 
- A subclass constructor can be implemented with a call to the ```super``` method, which invokes the superclass constructor.
- Be sure to provide at least one constructor when you write a subclass. Constructors are never inherited from the superclass.

1. If super is used in the implementation of a subclass constructor, it must be used in the first line of the constructor body.
2. If no constructor is provided in a subclass, the compiler provides the following default constructor:
```
public SubClass(){
  super(); //calls default constructor of superclass
}
```

## Rules for Subclasses
- A subclass can add new private instance variables.
- A subclass can add new public, private, or static methods.
- A subclass can override inherited methods.
- A subclass may not redefine a public method as private.
- A subclass may not override static methods of the superclass.
- A subclass should define its own constructors.
- A subclass cannot directly access the private members of its superclass. It must use accessor or mutator methods.

# Polymorphism
- A method that has been overridden in at least one subclass is said to be polymorphic.
- Polymorphism is the mechanism of selecting the appropriate method for a particular object in a class hierarchy. The correct method is chosen because, in Java, method calls are always determined by the type of the actual object, not the type of the object reference.
-  In Java, the selection of the correct method occurs during the run of the program.

## Polymorphism in Java Example
A superclass named “Shapes” has a method called “area()”. Subclasses of “Shapes” can be “Triangle”, “circle”, “Rectangle”, etc. Each subclass has its way of calculating area. Using Inheritance and Polymorphism means, the subclasses can use the “area()” method to find the area’s formula for that shape.
```
class Shapes {
  public void area() {
    System.out.println("The formula for area of ");
  }
}
class Triangle extends Shapes {
  public void area() {
    System.out.println("Triangle is 0.5 * base * height ");
  }
}
class Circle extends Shapes {
  public void area() {
    System.out.println("Circle is 3.14 * radius * radius ");
  }
}
class Main {
  public static void main(String[] args) {
    Shapes myShape = new Shapes();  // Create a Shapes object
    Shapes myTriangle = new Triangle();  // Create a Triangle object
    Shapes myCircle = new Circle();  // Create a Circle object
    myShape.area();
    myTriangle.area();
    myShape.area();
    myCircle.area();
  }
}
```
Output:
```
The formula for the area of the Triangle is 0.5 * base * height
The formula for the area of the Circle is 3.14 * radius * radius
```

### Ex 3
```
class Shape {
    public void draw() {
        System.out.println("Drawing a shape");
    }
}

class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }
}

class Main {
    public static void main(String[] args) {
        Shape s1 = new Circle();
        Shape s2 = new Square();

        s1.draw(); // Output: "Drawing a circle"
        s2.draw(); // Output: "Drawing a square"
    }
}
```
In this example, we have a base class Shape with a single method draw() that prints “Drawing a shape” to the console. We then create two subclasses, Circle and Square, that override the draw() method to print “Drawing a circle” and “Drawing a square” respectively.

In the main method, we create two instances of the Shape class, s1 and s2, which are actually instances of the Circle and Square subclasses. When we call the draw() method on these objects, the correct implementation is called based on the actual type of the object, this is run-time polymorphism. The program will output: “Drawing a circle” and “Drawing a square”

In this example, the draw() method is overridden in the subclasses, and this allows for the program to determine which method to use at runtime. This is known as runtime polymorphism or dynamic polymorphism, Because at runtime the JVM determines the actual type of the object and calls the corresponding method.

### Types of Polymorphism
You can perform Polymorphism in Java via two different methods:
1. Method Overloading
2. Method Overriding

### What is Method Overloading in Java?
- Method overloading is the process that can create multiple methods of the same name in the same class, and all the methods work in different ways. Method overloading occurs when there is more than one method of the same name in the class.

### Example of Method Overloading in Java
```
class Shapes {
  public void area() {
    System.out.println("Find area ");
  }
public void area(int r) {
    System.out.println("Circle area = "+3.14*r*r);
  }

public void area(double b, double h) {
    System.out.println("Triangle area="+0.5*b*h);
  }
public void area(int l, int b) {
    System.out.println("Rectangle area="+l*b);
  }


}

class Main {
  public static void main(String[] args) {
    Shapes myShape = new Shapes();  // Create a Shapes object
    
    myShape.area();
    myShape.area(5);
    myShape.area(6.0,1.2);
    myShape.area(6,2);
    
  }
}
```
Output:
```
Find area
Circle area = 78.5
Triangle area=3.60
Rectangle area=12
```
### What is Method Overriding in Java?
- Method overriding is the process when the subclass or a child class has the same method as declared in the parent class.

### Example of Method Overriding in Java
```
class Vehicle{  
  //defining a method  
  void run(){System.out.println("Vehicle is moving");}  
}  
//Creating a child class  
class Car2 extends Vehicle{  
  //defining the same method as in the parent class  
  void run(){System.out.println("car is running safely");}  
  
  public static void main(String args[]){  
  Car2 obj = new Car2();//creating object  
  obj.run();//calling method  
  }  
}
```
Output:
```
Car is running safely
```

# Quizzez

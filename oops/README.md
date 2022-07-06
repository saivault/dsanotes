<h1 style="font-size:35px">Object-Oriented Programming</h1>
Object-oriented programming (OOP) has been around for decades. As the original object-oriented language, <b>Java</b> is a mainstay in the world of computer programming.<br><br>
Having a foundation in OOP Java concepts will allow you to write cleaner, more modular, and more reusable code, as well as make it easier for you to understand the codebases of different companies you might be interested in joining. <br><br><br>
<h2>Procedural Programming</h2>
It is a programming paradigm. In this, a program is divided into smaller parts called methods. These methods are the basic entities used in this technique.<br><br>
The focal point of procedural programming technique is to <b>use methods for code reusability</b>. However, the implementation of a complex real-world scenario becomes a difficult task using this paradigm.<br><br><br>
<h2>Back to OOP !!</h2>
Object-oriented programming, also referred to as OOP is a programming paradigm that includes or relies on the concept of <b>classes and objects</b>. <br>
The basic entities in object-oriented programming are classes and objects.<br><br>
Programming won’t make much sense if one can’t model real-world scenarios using programming languages right? <br>
This is where Object-Oriented Programming comes into play!<br><br>
Used to structure a software program into simple, reusable pieces of code blueprints (usually called classes), which are used to create individual instances of objects. <br><br><br>
<div align="center"><b>
The basic idea of OOP is to <br> divide a complex program into <br>a bunch of objects talking to each other.
</b></div>
<br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1>Objects</h1>
Objects in a program frequently represent real-world objects. <br>
<b>Eg:- </b> Bicycle object, Person object, Bulb object etc ...<br><br>
Many other objects serve application logic and have no direct real-world parallel objects that manage authentication, templating, request handling, or any of the other myriad features needed for a working application.<br><br><br><br>
<h2>Anatomy of Objects and Classes</h2>
Objects may contain data in the form of fields (variables) and methods to operate on that data. For a while, think about the real-world objects around you."What are the characteristics of these objects? Take the example of a light bulb. It has a state i.e. either it is on or off. It also has a behavior i.e. when you turn it on it lights up and when turned off, it stops spreading light. <br><br>
To conclude this one can say:
<blockquote><b>Objects have state and behavior.</b></blockquote><br>
Interesting! isn’t it? <br>
But the question is “where do these objects come from?”<br>
Well, the answer to the above question is classes.<br><br>
<blockquote><b>A Class can be thought of as a blueprint for creating objects.</b></blockquote><br><br>
<h1>Classes</h1>
A class is an abstract blueprint used to create more specific, concrete objects. Classes often represent broad categories, like Car or Dog that <b>share attributes</b>. These classes define what attributes an instance of this type will have, like color, but not the value of those attributes for a specific object.<br><br>
Classes can <b>also contain functions, called methods</b> available only to objects of that type. These functions are defined within the class and perform some action helpful to that specific type of object.
<br><br><br><br><br><br><br><br><br><br>
The below illustration shows what a LightBulb class should look like.
<div align="center">
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/classintro.png" height="220" width="500">
</div><br>
LightBulb class has methods turnOn() and turnOff() that changes the onOff attribute of our bulb. This function is only helpful to objects of type LightBulb, so we declare it within the LightBulb class thus making it a method.
<br><br><div align="center">
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/bulbon.png" height="220" width="500">
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/bulboff.png" height="220" width="500">
</div><br><br>
From the above illustration, it can be concluded that 
<ul>
<li>the state of the objects is generally modeled using variables in a class and </li>
<li>the behavior is modeled by implementing the methods. </li>
</ul><br>
It can be inferred from the discussion above that <b>classes are user-defined data types</b> implemented using the primitive data types e.g. boolean, int, char etc. <br><br><br>
<h2>Creation of objects from classes</h2>
We can use a class to represent any number of objects.<br>
Each object can have unique values to the properties defined in the class. We can set the value of the properties defined in the class to describe a particular object, without affecting other objects or the class template.<br><br>
<div align="center">
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/classblueprint.png" height="450" width="500">
</div><br>
The concept of classes allows us to create complex objects and applications in Java. This is why classes are the basic <b>building blocks behind all of the OOP’s principles</b>.<br><br><br><br><br><br>
<h2>DECLARATION AND IMPLEMENTATION OF CLASSES</h2>
The written code of a class and its attributes are known as the definition or implementation of the class.<br><br>
In Java, we define classes in the following way:

```java
class ClassName { // Class name
    /* All member variables
    and methods*/
}
```
The <b>'class'</b> keyword tells the compiler that we are creating our custom class. All the members of the class will be defined within the class scope.<br><br>
Sample structure of a java class is as follows : <br>

```java
class Car { // Class name
  
      // Class Data members
      int topSpeed;
      int totalSeats;
      int fuelCapacity;
      String manufacturer;
      
      // Class Methods
      void refuel(){
        ...
      }
      void park(){
        ...
      }
      void drive(){
        ...
      }
}
```
<br><br><h2>Creating a class object</h2>
The name of the class, (ClassName) will be used to create an instance of the class. We can create an object of a class by using the keyword <b>new</b><br>

```java
// className object
ClassName obj = new ClassName(); 
```
<br><br><br><br><br>
<h1>Access Modifiers</h1>
In Java, we can <b>impose access restrictions</b> on different data members and member functions. The restrictions are specified through access modifiers. Access modifiers are tags we can associate with each member to define <b> which parts of the program can access it directly</b>.<br><br><br>
<h2>Private</h2>
A private member <b>cannot be accessed directly from outside the class</b>. The aim is to keep it hidden from the users and other classes. It is a popular practice to keep the data members private since we do not want anyone manipulating our data directly.<br>We can make members private using the keyword private as follows : 

```java
private int gun; 
```
<br><br>
<h2>Public</h2>
This tag indicates that the members can be <b>directly accessed by anything</b> which is in the same scope as the class object. Member functions are usually public as they provide the interface through which the application can communicate with our private members. Public members can be declared using the keyword public.<br><br>
Public members of a class can be accessed by a class object using the <b>. operator</b>. 

```java
class Cop {
    private int gun; // Private variable
  
    public int getGun(){
        return gun;  // The private variable is directly accessible over here!
    }
}

class Main{
    public static void main(String args[]){
        Cop c = new Cop(); // Object created
        c.getGun(); // Can access the gun
        c.gun = 0; // This would cause an error since gun is private
    }
}
```
<br><br><br><br><br><br>
<h2>Protected</h2>
The protected category is unique. The access level to the protected members lies somewhere between private and public. The primary use of the protected tag can be found when using inheritance, which is the process of creating classes out of other classes.<br><br>
The protected data members can be accessed inside a Java package. However, outside the package, they can only be referred to through an inherited class.
<br><br><br><br>
<h2>Default</h2>
If we do not mention any access modifier, then it is considered to be default access. The default access is similar to the protected. It also has package-level access, but it also applies to inherited classes as well, unlike protected. So, you can say that its access is more limited.<br><br>
<table style="padding-left:160px">
<tr><td>Public</td><td>global access</td></tr>
<tr><td>Default</td><td>package level access</td></tr>
<tr><td>Private</td><td>class level access</td></tr>
</table>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1>Fields in java</h1>
Java supports static and non-static fields. <br>
<h2>STATIC FIELD</h2>
A static field resides in a class. <b>All the objects we create will share this field and its value</b>. <br>
You can define a static field by using the static keyword. <br><br>
We don’t need an instance of the class to access static fields. We can access the static fields of a class by just writing the class name before the field:

```java
class Car {
    // static fields
    static int topSpeed = 100;
    static int maxCapacity = 4;  
}

class Demo {
    public static void main(String args[]){
    // Static fields are accessible in the main
    System.out.println(Car.topSpeed);
    System.out.println(Car.maxCapacity);   
  }
}
``` 
<br>
<h2>NON-STATIC FIELD</h2>
Non-static fields are located in the instances of the class. <b>Each instance of the class can have its own values for these fields</b>.<br>
You can define a non-static field just by not using the static keyword. <br><br>
As non-static fields doesn’t reside in the class, So we need an instance of the class to access non-static fields.

```java
class Car {
    // non-static fields
    int speed = 100;
    int capacity = 4;  
}

class Demo {
    public static void main(String args[]){
        Car obj1 = new Car();
        System.out.println(obj1.speed);
        System.out.println(obj1.capacity);   
    }
}
```
<br>
<h2>FINAL FIELD</h2>
A final field cannot have its value changed once it is assigned. We can make a field final by using the keyword final.

```java
final int capacity = 4;
```
<br><br><h1>Methods in java</h1>
<h2>Getters and setters</h2>
These two types of methods are very popular in OOP. A get method retrieves the value of a particular data field, whereas a set method sets its value. <br><br>
It is a common convention to write the name of the corresponding member fields with the get or set command.

```java
class Car {

    private int speed; // member field speed

    // Setter method to set the speed of the car
    public void setSpeed(int x) {
        speed = x; 
    }

    // Getter method to get the speed of the car
    public int getSpeed() {
        return speed; 
    }
  
}

class Demo {
  
   public static void main(String args[]) {
     Car car = new Car();
     car.setSpeed(100); // calling the setter method
     System.out.println(car.getSpeed()); // calling the getter method
   } 
  
}
```
<br><br><br><br><h1>Method Overloading</h1>
<div align="center"><b>
Overloading refers to making a<br>method perform different operations<br>based on the nature of its arguments.
</b></div><br><br>
Methods can be overloaded in Java. <br>
We could redefine a method several times and give it different arguments and method types. When the method is called, the appropriate definition will be selected by the compiler!<br><br>

```java
class Calculator {

    public double product(double x, double y) {
        return x * y;
    }
    // Overloading the function to handle three arguments
    public double product(double x, double y, double z) {
        return x * y * z;
    }
    // Overloading the function to handle int
    public int product(int x, int y){
        return x * y;
    }

}

class Demo {
    public static void  main(String args[]) {
        Calculator cal = new Calculator();
    
        double x = 10;
        double y = 20;
        double z = 5;
    
        int a = 12;
        int b = 4;
        
        System.out.println(cal.product(x, y));
        System.out.println(cal.product(x, y, z));
        System.out.println(cal.product(a, b));
    }
}
```
<br><b>Note:- </b> Methods that have no arguments and differ only in the return types cannot be overloaded since the compiler won’t be able to differentiate between their calls.<br><br>
<h2>Advantages</h2>
One might wonder if we could simply create new methods to perform different jobs rather than overloading the same method.
<ul>
<li>The code becomes simple and clean. We don’t have to keep track of different methods.</li>
<li>Polymorphism is a very important concept in object-oriented programming, and method overloading plays a vital role in its implementation.</li>
</ul><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1 "font-size:30px">Constructors</h1>
As the name suggests, the constructor is used to <b>construct the object of a class</b>. It is a special method that outlines the steps that are performed when an instance of a class is created in the program. <br>
<b>Note:-</b> A constructor’s name must be exactly the same as the name of its class.<br><br>
The constructor is a special method because it <b>does not have a return type</b>. We do not even need to write void as the return type. It is a good practice to declare/define it as the <b>first member method</b>.<br><br>
So, let’s study the different types of constructors and use them to create class objects.<br><br><br>
<h2>Default constructor</h2>
The default constructor is the most basic form of a constructor. In a default constructor, we define the default values for the data members of the class.<br><br>
Hence, the constructor creates an object in which the <b>data members are initialized to their default values</b>. The default constructor does not need to be explicitly defined. Even if we don’t create it, the JVM will call a default constructor and set data members to null or 0 as given in the below table. <br><br>
<table style="padding-left:210px">
<tr><td>int</td><td>0</td></tr>
<tr><td>float</td><td>0.0</td></tr>
<tr><td>boolean</td><td>false</td></tr>
<tr><td>string</td><td>null</td></tr>
</table><br>
If you don’t define any constructor, the Java compiler will insert a default constructor for you. Thus, once the class is compiled it will always at least have a no-argument constructor.<br><br>

```java
class Date {

    private int day;
    private int month;
    private int year;
    
    // Default constructor
    public Date() {
        // We must define the default values for day, month, and year
        day = 0;
        month = 0;
        year = 0;
    }
    
    // A simple print function
    public void printDate(){ 
        System.out.println("Date: " + day + "/" + month + "/" + year);
    }
  
}

class Demo {
    public static void main(String args[]) {
        // Call the Date constructor to create its object;
        Date date = new Date(); // Object created with default values!
        date.printDate();
    }
}
```
<br>
Notice that when we created a Date object, we don’t treat the constructor as a method and write this: <b><i>date.Date()</i></b><br>
We create the object just like we create an integer or string object. It’s that easy!<br><br><br>
<h2>Parameterized constructor</h2>
The default constructor isn’t all that impressive. Sure, we could use set methods to set the values for day, month and year ourselves, but this step can be avoided using a parameterized constructor.<br><br>
In a parameterized constructor, we pass arguments to the constructor and set them as the values of our data members.
We are basically <b>overloading the default constructor</b> to accommodate our preferred values for the data members.
<br><br><br>

```java
// Parameterized constructor
public Date(int d, int m, int y){
    // The arguments are used as values
    day = d;
    month = m;
    year = y;
}

class Demo {
    public static void main(String args[]) {
        Date date = new Date(1, 8, 2018); // Object created with specified values! 
        date.printDate();
    }
}
```
<br>This is much more convenient than the default constructor!<br>
<h1>"this"</h1>
The "this" reference variable exists for every class. It <b>refers to the class object itself</b>. We use "this" when we have an argument which has the same name as a data member. this.memberName specifies that we are accessing the memberName variable of the particular class. <br><br>
Let’s see it in action:

```java
// Default constructor
public Date() {
    this.day = 0;
    this.month = 0;
    this.year = 0;
}

// Parameterized constructor
public Date(int day, int month, int year){
    this.day = day;
    this.month = month;
    this.year = year;
}
```
<br><br><h2>Calling a constructor from a constructor</h2>
In Java, we can call a constructor from a constructor.<br>
Calling another constrcutor in the same java class from a constrcutor can be done by using "this" keyword followed by parentheses.

```java
public Date(int day, int month, int year){
    // The arguments are used as values
    this.day = day;
    this.month = month;
    this.year = year;
}

public Date(int day, int month, int year, String event){
    this(day, month, year); // calling the constructor
    this.event = event;
}
```
<br><br><br><br>
<h1 style="font-size:32px">Data hiding</h1>
Objects are created using classes. One can observe that classes contain data members and objects are created to manipulate and access this data. To make this object-oriented system more reliable and error free, it is a good practice to limit access to the class members.<br><br>
<blockquote><b>In layman’s terms, data hiding refers to the concept of hiding the inner workings of a class and simply providing an interface through which the outside world can interact with the class without knowing what’s going on inside.</b></blockquote><br>
The purpose is to implement classes in such a way that the instances (objects) of these classes should not be able to cause any unauthorized access or change in the original contents of a class. One class does not need to know anything about the underlying algorithms of another class. However, the two can still communicate.<br><br><br>
<h2>A Real Life Example</h2>
Let’s apply this to a real-world scenario. Take the doctor-patient model. In case of an illness, the patient consults the doctor, after which he or she is prescribed the appropriate medicine.<br><br>
The patient only knows the process of going to the doctor. The logic and reasoning behind the doctor’s prescription of a certain medicine are unknown to the patient. A patient will not understand the medical details the doctor uses to reach his/her decision on the treatment.<br><br>
This is a classic example of the patient class interacting with the doctor class without knowing the inner workings of the doctor class.<br><br><br>
<h2>Components of Data Hiding</h2>
Data hiding can be divided into two primary components: <br><br>
<ul>
<li>Encapsulation</li>
<li>Abstraction</li>
</ul>
<br><br><br><br><br><br><br>
<h1 style="font-size:36px">Inheritance</h1>
Inheritance provides a way to create a new class from an existing class. The new class is a specialized version of the existing class such that it inherits all the <b>non-private fields (variables) and methods</b> of the existing class. The existing class is used as a starting point or as a base to create the new class.<br><br><br>
<h2>Where to use it ?</h2>
wherever we come across an <b>IS A</b> relationship between objects, we can use inheritance.
Some examples are as follows :<br>
<ul style="padding-top:7px">
<li>Car IS A vehicle</li>
<li>Dentist IS A doctor</li>
</ul>
which implies,<br> if we have an existing class "Vehicle", we can create a new class "Car" out of it.<br><br><br>
<h3>Some Terminology</h3>
> As its similar to a child inheriting the traits of his/her parents, the new class is called as <b>child class</b> and the existing class is called <b>parent class</b>.

<br>
<div style="border-style:solid;width:350px;margin-left:120px;height:60px;padding-left:43px;padding-top:11px;border-width:2px;margin-top:8px">
Parent class / Base class / SuperClass <br>
Child class / derived class / SubClass
</div>
<br>
In Java, we have to use the keyword <b>extends</b> to implement inheritance:

```java
SubClass extends SuperClass{
    //contents of SubClass
}
```
<br><br>
<h2>Some important points</h2>
<ul>
<li>In Java whenever we create a class, it inherits all the non-private methods and fields from the builtin <b>Java Object class</b> by default which makes it a very <b>good example of inheritance</b> in Java. The methods defined in the Object class come in very handy when you create new classes.</li>
<li>Some classes <b>cannot be inherited</b>. Such classes are defined with the <b>keyword, final</b>. An example of such a class is the built-in Integer class - this class cannot have derived classes.</li>
<li>In Java, a class can extend from only one other class at a time and a class cannot extend itself.</li>
</ul>
<br><br>
Example of inheritance is as follows : 

```java
// Base Class Vehicle
class Vehicle {
    // Private Fields
    private String make; 
    private String color; 
    private int year;      
    private String model;   

    // Parameterized Constructor
    public Vehicle(String make, String color, int year, String model) {
        this.make = make;
        this.color = color;
        this.year = year;  
        this.model = model; 
    }

    // public method to print details
    public void printDetails() {
        System.out.println("Manufacturer: " + make);
        System.out.println("Color: " + color);
        System.out.println("Year: " + year);
        System.out.println("Model: " + model);
    }
}

// Derived Class Car
class Car extends Vehicle {
    // Private field
    private String bodyStyle;
    
    // Parameterized Constructor
    public Car(String make, String color, int year, String model, String bodyStyle) {
        super(make, color, year, model);  //calling parent class constructor
        this.bodyStyle = bodyStyle;       
    }
    
    public void carDetails() {  //details of car
        printDetails();         //calling method from parent class
        System.out.println("Body Style: " + bodyStyle);
    }
}

class Main {
    public static void main(String[] args) {
        Car elantraSedan = new Car("Hyundai", "Red", 2019, "Elantra", "Sedan"); 
        //creation of car Object
        elantraSedan.carDetails(); //calling method to print details
    }
}
```
<h1>"super" keyword</h1>
As you already know that this keyword in Java is used to refer to the instance of the current class. <br><br>
In a similar fashion, the super keyword in Java is used to refer to the SuperClass members from inside the immediate Subclass. The use of super comes into play when we implement inheritance.<br><br>
The super keyword is used in three major contexts:<br>
<ul>
<li>Accessing parent class fields</li>
<li>Calling a parent class method</li>
<li>Using with constructors</li>
</ul>
<br>
<h2>1. Accessing parent class fields</h2>
Whenever a SuperClass and the immediate SubClass have any fields with the same name, we use super to access the fields from the SuperClass inside the SubClass.

```java
class Vehicle { //Base class vehicle  
    int fuelCap = 90; //fuelCap field inside SuperClass
} 

class Car extends Vehicle { // sub class Car extending from Vehicle
    int fuelCap = 50; //fuelCap field inside SubClass
    public void display() { 
        //accessing the field of parent class using super*
        System.out.println("Fuel Capacity from the Vehicle class: " + super.fuelCap); 
        //without using super the field of current class shadows the field of 
        //parent class
        System.out.println("Fuel Capacity from the Car class: " + fuelCap); 
    } 
} 

class Main {
    public static void main(String[] args) { 
        Car corolla = new Car(); 
        corolla.display(); 
    } 
}
```
<blockquote>
Fuel Capacity from the Vehicle class: 90<br>
Fuel Capacity from the Car class: 50
</blockquote>
<br><br><br><br><br><br>
<h2>2. Calling a parent class method</h2>
Just like the fields, super is also used with the methods. Whenever a SuperClass and the immediate SubClass have any methods with the same name we use super to access the methods from the SuperClass inside the SubClass.

```java
class Vehicle {          //Base class vehicle 
    public void display() {   //display method inside SuperClass
        System.out.println("I am from the Vehicle Class");
    }
} 

class Car extends Vehicle { // sub class Car extending from Vehicle
    public void display() { //display method inside SubClass
        System.out.println("I am from the Car Class");
    } 
    
    public void printOut(){
        System.out.println("The display() call with super:");
        super.display();  //calling the display() of Vehicle(SuperClass)
        System.out.println("The display() call without super:");
        display();        //calling the display() of the Car(SubClass)
    }
} 

class Main {
    public static void main(String[] args) {
        Car corolla = new Car(); 
        corolla.printOut(); 
    }
}
```
<blockquote>
The display() call with super: <br>
I am from the Vehicle Class<br>
The display() call without super:<br>
I am from the Car Class
</blockquote><br><br>
<h2>3. Using constructors</h2>
Another very important use of the keyword super is to call the constructor of the SuperClass from inside of the constructor of the SubClass.<br>
<b>Note:</b> When you create an Object of a SubClass type at the same time, an Object of SuperClass type is created by calling implicitly the constructor of SuperClass.<br><br>
The syntax of the constructor call is as follows:

```java
super();  //calls the (no argument) constructor if a no-argument constructor is defined in the SuperClass
super(parameters); //calls the parameterized constructor of the SuperClass with matching parameters from the SubClass constructor
```

The call to the SuperClass constructor using super() is usually the first line of code inside the constructor of the SubClass. If we do not call super() in the SubClass constructor, the default no-argument constructor of SuperClass is called automatically. The super(parameters) call has to be used if we want to call a parameterized constructor of the SuperClass.<br><br><br><br><br><br><br><br>
<h1>Types of Inheritance</h1>
Based upon superclasses and subclasses, there are the following five types of inheritance in general:<br>
1. Single <br>
2. Multi-level <br>
3. Hierarchical <br>
4. Multiple <br>
5. Hybrid <br>

<br><div style="display:flex">
<div>
<h2>Single Inheritance</h2>
In single inheritance, there is only a single class<br> extending from another class. We can take the example of the Vehicle class (Super class) and the Car class (Sub class).<br><br>
A car <b>IS A</b> vehicle
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/singleinherit.png" height="150" width="150">
</div>
<br><div style="display:flex">
<div>
<h2>Multi-level Inheritance</h2>
When a class is derived from such a class which itself is derived from another class, this type of inheritance is<br> called Multilevel Inheritance. Classes can be extended to<br> any further levels as per the requirement of the model.<br><br>
A car <b>IS A</b> vehicle<br>
A prius <b>IS A</b> car
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/multilevelinherit.png" height="180" width="150">
</div>
<br><br><br><br><br><div style="display:flex">
<div>
<h2>Hierarchical Inheritance</h2>
When more than one classes inherit from the same class, it is referred to as hierarchical inheritance. In hierarchical inheritance, more than one classes extend, as per the requirement of the design, from the same base class. The common attributes of these child classes are implemented inside the base class..<br><br>
A car <b>IS A</b> vehicle<br>
A truck <b>IS A</b> vehicle
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/hierainherit.png" height="180" width="220">
</div>
<br><br><br><div style="display:flex">
<div>
<h2>Multiple Inheritance</h2>
When a class is derived from more than one base class, i.e. when a class has more than one immediate parent classes, this type of inheritance is called Multiple Inheritance.<br><br>
A hyundai elantra <b>IS A</b> car.<br>
A hyundai elantra <b>IS A</b> sedan also.
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/multipleinherit.png" height="150" width="180">
</div>
<br><br><br><div style="display:flex">
<div>
<h2>Hybrid Inheritance</h2>
A type of inheritance which is a combination of Multiple and Multi-level inheritance is called hybrid inheritance.<br><br>
A combustion engine is an engine<br>
An electric motors engine is an engine<br>
A Hybrid engine combines both combustion engine and electric motors.
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/hybridinherit.png" height="150" width="180">
</div><br><br><br>
<b>Note:</b> In Java, Multiple and Hybrid inheritance are applicable using interfaces only. <br><br><br><br><br><br><br><br><br><br>
<h1>Redundancy vs Duplication</h1>
<h2>in code</h2>
Duplication is a repetition of form. <br>
Redundancy is not a repetition of form, but rather a repetition of intent. We are trying to do the same thing in multiple places and that makes it redundant.<br><br>
Duplication ofcourse, is the most obvious form of redundancy but redundancy can take many other forms that are far more subtle and harder to detect.<br><br>
<h3>Q) Can non-identical code be redundant ?</h3>
Yes, Think of a “for” loop and a “for each” loop iterating through the same collection. <br><br>
<h3>Q) Can identical code be non-redundant ?</h3>
Also, Yes. For example, a line of code that reads “index++;” can be used to iterate through a list of names in one part of the code and a list of numbers in another part of the code.<br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1>Advantages of Inheritance</h1>
Inheritance makes the code reusable. <br><br>
Consider that you are up for designing a banking system using classes. Your model might have these: <br>&nbsp;
- A base <i>BankAccount</i> class<br>&nbsp;
- A derived class named <i>SavingsAccount</i><br>&nbsp;
- A derived class named <i>CheckingAccount</i><br><br><br>

<h2>Re-usability</h2>
On a later point, you realize that you have to diversify this banking application by adding another class for <i>MoneyMarketAccount</i>. So, <b>rather than implementing this class from scratch</b> you can extend from the existing <i>BankAccount</i> class as a starting point and <b>reuse its attributes</b> that are common with <i>MoneyMarketAccount</i>.<br><br>
From this, we can examine that we can implement inheritance which will result in avoiding redundant coding and will also save the programmer’s time and effort.<br><br>
<h2>Avoiding Duplication of Code</h2>
Considering the above example, you don’t need to duplicate the code for the deposit() and withdraw() methods inside the child classes namely <i>SavingsAccount</i> and <i>CheckingAccount</i> as they are the same for any kind of account and it can be implemented in the base class <i>BankAccount</i>. In this way, you can avoid the duplication of code.<br><br>
<h2>Extensibility</h2>
Using inheritance, one can extend the base class logic as per the business logic of the derived class. This is an easy way to upgrade or <b>enhance specific parts of a product without changing the core attributes</b>. An existing class can act as a base class to derive a new class having upgraded features.<br><br>
<h2>Data Hiding</h2>
The base class can decide to keep some data private so that it cannot be altered by the derived class. <br><br><br><br><br><br><br><br><br><br><br>
<h1>Polymorphism</h1>
The word Polymorphism is a combination of two Greek words, Poly means many and Morph means forms. In programming, polymorphism refers to the <b>same object exhibiting different forms and behaviors</b>.<br><br>
For example, take the Shape Class. The exact shape you choose can be anything. It can be a rectangle, a circle, a polygon or a diamond. So, these are all shapes but their properties are different. This is called Polymorphism.
<br><br><br><h2>A brief introduction</h2>
Assume there is a base class named Shape from which the subclasses Rectangle, Circle, Polygon, and Diamond are derived. Also consider that the Shape class has a method called calculateArea(), which is inherited by all subclasses mentioned. With polymorphism, each subclass may have its way of implementing the method.<br><br>
So, for example, when the calculateArea() method is called in an object of the Rectangle class, the method might respond by displaying the area of the rectangle. On the other hand, when the same method is called in an object of the Circle class, the circle’s area might be calculated and displayed on the screen.<br><br>
In effect, polymorphism cuts down the work of the developer because when the time comes to create more specific subclasses with certain unique attributes and behaviors, the developer can alter the code in the particular portions where the responses differ. All other pieces of the code can be left untouched.<br><br><br>
<h3>What if we want our derived class to inherit a method from the base class and have a different implementation for it?</h3> That is when polymorphism, a fundamental concept in the OOP paradigm, comes into play.<br><br><br>
<h3>Example</h3>
Here we consider the example of a Shape class, which is the base class while many shapes like Rectangle and Circle extending from the base class are derived classes. These classes contain the getArea() method which calculates the area for the respective shape.<br><br>
In the main function, we have declared a Shape class array of size 2 and declared the Circle and the Rectangle class objects at index 0 and 1 respectively. Now the getArea() method returns the area of the respective shape. This is Polymorphism.<br><br><br><br><br><br>

```java
// A sample class Shape which provides a method to get the Shape's area
class Shape {
    public double getArea() {
        return 0;
    }
}

// A Rectangle is a Shape with a specific width and height
class Rectangle extends Shape {   // extended form the Shape class
    private double width;
    private double height;
    
    public Rectangle(double width, double heigh) {
        this.width = width;
        this.height = height;
    }
    
    public double getArea() {
        return width * height; 
    }
}

// A Circle is a Shape with a specific radius
class Circle extends Shape {
    private double radius;
    
    public Circle(double radius) {
        this.radius = radius; 
    }
    
    public double getArea() {
        return 3.14 * radius * radius; 
    }
}


class driver {
    public static void main(String args[]) {
        Shape[] shape = new Shape[2]; // Creating shape array of size 2
        
        shape[0] = new Circle(2); // creating circle object at index 0
        shape[1] = new Rectangle(2, 2); // creating rectangle object at index 1
        
        System.out.println("Area of the Circle: " + shape[0].getArea());
        System.out.println("Area of the Rectangle: " + shape[1].getArea());
    }
}
```
<br><br><h1>Method Overriding</h1>
<blockquote><b>
process of redefining a parent class’s method in a subclass.
</b></blockquote>
In other words, if a subclass provides the specific implementation of a method that has been defined by one of its parent classes, it is known as method overriding.<br>
In the previous example, the Rectangle and Circle classes were overriding the getArea() method from the Shape class.
<br><br>Overriding is done so that a child class can give its own implementation to a method which is already provided by the parent class.<br><br>
In this case: <br>
- The method in the parent class is called overridden method.<br>
- The methods in the child classes are called overriding methods.<br><br><br>

<h2>Advantages</h2>
<ol>
<li>The derived classes can give their own specific implementations to inherited methods without modifying the parent class methods.</li>
<li>For any method, a child class can use the implementation in the parent class or make its own implementation.</li>
</ol><br><br><br>
<h2>Key features</h2>
- Method overriding needs inheritance and there should be at least one derived class.<br>
- Derived class(es) must have the same declaration, i.e., access modifier, name, same parameters and same return type as the method as of the base class.<br>
- The method in the derived class(es) must have different implementations from each other.<br>
- The method in the base class must be overridden in the derived class.<br>
- Base class/method must not be declared as a final class.<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<br><br><table style="padding-left:10px">
<tr><th style="width:300px">Method Overloading</th><th style="width:300px">Method Overriding</th></tr>
<tr><td>Overloading happens at compile time.</td><td>Overriding happens at runtime</td></tr>
<tr><td>Gives better performance because the binding is being done at compile time.</td><td>Gives less performance because the binding is being done at run time.</td></tr>
<tr><td>Private and final methods can be overloaded.</td><td>Private and final methods can not be overridden.</td></tr>
<tr><td>Return type of method does not matter in case of method overloading.</td><td>Return type of method must be the same in the case of overriding.</td></tr>
<tr><td>Arguments must be different in the case of overloading.</td><td>Arguments must be the same in the case of overriding.</td></tr>
<tr><td>It is being done in the same class.</td><td>Base and derived classes are required here.</td></tr>
<tr><td>Mostly used to increase the readability of the code.</td><td>Mostly used to provide the implementation of the method that is already provided by its base class.</td></tr>
</table><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><h1>Static Polymorphism</h1>
Also known as compile time polymorphism.<br><br>
Polymorphism that is resolved during compile time is known as static polymorphism.<br>
Method overloading is used here.<br><br>
<b>Example:-</b>

```java
class Calculator {
    int add(int num1, int num2) {
        return num1 + num2;
    }
    
    int add(int num1, int num2, int num3) {
        return num1 + num2 + num3;
    }
    
    public static void main(String args[]) {
        Calculator obj = new Calculator();
        System.out.println("10 + 20 = " + obj.add(10, 20));
        System.out.println("10 + 20 + 30 = " + obj.add(10, 20, 30));
    }
}
```

<br>Here, we have two definitions of the same method add() in the Calculator class. Which add() method would be called is determined by the parameter list at the compile time. This is the reason this is also known as compile time polymorphism.<br><br><br>
<h1>Dynamic Polymorphism</h1>
Also known as runtime polymorphism.<br>
Dynamic polymorphism is the mechanism by which methods can be defined with the same name, return type, and parameters in the base class and derived classes.<br><br>
Polymorphism that is resolved during run time is known as dynamic polymorphism.<br>
Method overriding is used here.<br><br>
<b>Example:-</b> In our shape class example, <br>
the child classes are overriding the method getArea() of the parent class. We have child classes objects assigned to the parent class reference. So to determine which method would be called, the type of the object would be determined at runtime. This is the reason it is also known as runtime polymorphism.

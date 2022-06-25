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
<br><br><br><br><h2>Method Overloading</h2>
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
</ul>

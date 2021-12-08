# Object Oriented Programming Concepts

## Fundamental of Classes
-------------------------
A class is a user defined blueprint or prototype from which objects are created.  It represents the set of properties or methods that are common to all objects of one type. In general, class declarations can include these components, in order:

* **Modifiers:** A class can be public or has default access
.
* **``class`` keyword:** class keyword is used to create a class.

* **Class name:** The name should begin with an initial letter (capitalized by convention).

* **Superclass(if any):** The name of the class’s parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.

* **Interfaces(if any):** A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.

* **Body:** The class body surrounded by braces, ``{ }``.

Syntax to declare a class:

```java
class <class_name>
{  
    field;  
    method;  
}  
```
Example:

```java
class Bicycle 
{
  // state or field
  private int gear = 5;
  // behavior or method
  public void braking() 
  {
    System.out.println("Working of Braking");
  }
}
```
## Object
---------

An object is called an instance of a class. For example, suppose Bicycle is a class then MountainBicycle, SportsBicycle, TouringBicycle, etc can be considered as objects of the class.

An object has three characteristics:

* **State:** It is represented by attributes of an object. It also reflects the properties of an object.
* **Behavior:** It is represented by methods of an object. It also reflects the response of an object with other objects.
* **Identity:** It gives a unique name to an object and enables one object to interact with other objects.

Here is how we can create an object of a class.

Syntax:

```java
className object = new className();
```

Example:

```java
Bicycle sportsBicycle = new Bicycle();
Bicycle touringBicycle = new Bicycle();
```
We have used the ``new`` keyword along with the constructor of the class to create an object.

Here, ``sportsBicycle`` and ``touringBicycle`` are the names of objects. We can use them to access fields and methods of the class.

As you can see, we have created two objects of the class. We can create multiple objects of a single class in Java.

## Instance variable in Java
----------------------------

A variable which is created inside the class but outside the method is known as an instance variable. Instance variable doesn't get memory at compile time. It gets memory at runtime when an object or instance is created. That is why it is known as an instance variable.

## Access Members of a Class
-----------------------------
We can use the name of objects along with the . operator to access members of a class. For example,

```Java
class Bicycle 
{
  // field of class
  int gear = 5;
  // method of class
  void braking() 
  {
      System.out.println("Working of Braking");
  }
}

// create object
Bicycle sportsBicycle = new Bicycle();
// access field and method
sportsBicycle.gear;
sportsBicycle.braking();
```
In the above example, we have created a class named ``Bicycle``. It includes a field named ``gear`` and a method named ``braking()``. Notice the statement,

```Java
Bicycle sportsBicycle = new Bicycle();
```

Here, we have created an object of ``Bicycle`` named ``sportsBicycle``. We then use the object to access the field and method of the class.

* ``sportsBicycle.gear`` - access the field ``gear``
* ``sportsBicycle.braking()`` - access the method ``braking()``

## Abstraction
---------------
In OOP, abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it.

There are two ways to achieve abstraction in java:

* Abstract class (0 to 100%)
* Interface (100%)

### **Abstract class in Java**
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated.

**Syntax of declaring an abstract class:**

To declare an abstract class we use the keyword ``abstract``. The syntax is given below:

```Java
abstract class ClassName
{
    //class body
}
```

**Example:**

```Java
abstract class A{}  
```

### **Abstract method in Java**
A method which is declared as abstract and does not have implementation is known as an abstract method. 

**Syntax of declaring abstract methods:**

```Java
access_specifier abstract return_type method_name();
```

**Example:**

```Java
abstract void printStatus(); //no method body and abstract  
```

## Encapsulation
-----------------
Encapsulation is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates. Another way to think about encapsulation is, it is a protective shield that prevents the data from being accessed by the code outside this shield. 

Advantages of Encapsulation:  

* **Data Hiding:** The user will have no idea about the inner implementation of the class. It will not be visible to the user how the class is storing values in the variables. The user will only know that we are passing the values to a setter method and variables are getting initialized with that value.

* **Increased Flexibility:** We can make the variables of the class read-only or write-only depending on our requirement. If we wish to make the variables read-only then we have to omit the setter methods like setName(), setAge(), etc.  or if we wish to make the variables as write-only then we have to omit the get methods like getName(), getAge(), etc.

* **Reusability:** Encapsulation also improves the re-usability and is easy to change with new requirements.

* **Testing code is easy:** Encapsulated code is easy to test for unit testing.

### **Get and Set**

``private`` variables can only be accessed within the same class (an outside class has no access to it). However, it is possible to access them if we provide public ``get`` and ``set`` methods.

The ``get`` method returns the variable value, and the ``set`` method sets the value.

Syntax for both is that they start with either get or set, followed by the name of the variable, with the first letter in upper case:`

```Java
public class Person 
{
  private String name; // private = restricted access
  // Getter
  public String getName() 
  {
    return name;
  }
  // Setter
  public void setName(String newName) 
  {
    this.name = newName;
  }
}
```

Example explained

* The ``get`` method returns the value of the variable name.

* The ``set`` method takes a parameter ``(newName)`` and assigns it to the name variable. The ``this`` keyword is used to refer to the current object.

## Using ``this`` keyword
--------------------------
``this`` keyword in Java is a reference variable that refers to the current object of a method or a constructor. The main purpose of using this keyword in Java is to remove the confusion between class attributes and parameters that have same names.

Following are various uses of ``this`` keyword in Java:

* It can be used to refer instance variable of current class
* It can be used to invoke or initiate current class constructor
* It can be passed as an argument in the method call
* It can be passed as argument in the constructor call
* It can be used to return the current class instance

## Constructors 
----------------
In Java, a constructor is a block of codes similar to the method. It is called when an instance of the class is created. At the time of calling constructor, memory for the object is allocated in the memory.

It is a special type of method which is used to initialize the object.

Every time an object is created using the ``new()`` keyword, at least one constructor is called.

It calls a default constructor if there is no constructor available in the class. In such case, Java compiler provides a default constructor by default.

>It is called constructor because it constructs the values at the time of object creation. It is not necessary to write a constructor for a class. It is because java compiler creates a default constructor if your class doesn't have any.

Rules for creating constructor:

* Constructor name must be the same as its class name.
* A Constructor must have no explicit return type.
* A Java constructor cannot be abstract, static, final, and synchronized.

There are two types of constructors in Java:

* Default constructor (no-arg constructor)
* Parameterized constructor

### **Default constructor**

A constructor is called "Default Constructor" when it doesn't have any parameter.The default constructor is used to provide the default values to the object like 0, null, etc., depending on the type.

Syntax of default constructor:

```Java
<class_name>()
{
  //body
}  
```

Example:

```Java
//Java Program to create and call a default constructor  
class Bike1
{  
//creating a default constructor  
  Bike1()
  {
    System.out.println("Bike is created");
  }  
//main method  
public static void main(String args[])
{  
  //calling a default constructor  
  Bike1 b=new Bike1();  
}  
}  
```
### **Parameterized constructor**

A constructor which has a specific number of parameters is called a parameterized constructor. The parameterized constructor is used to provide different values to distinct objects. However, you can provide the same values also.

Example:

```Java
//Java Program to demonstrate the use of the parameterized constructor.  
class Student4
{  
  int id;  
  String name;  
  //creating a parameterized constructor  
  Student4(int i,String n)
  {  
    id = i;  
    name = n;  
  }  
  //method to display the values  
  void display()
  {
    System.out.println(id+" "+name);
  }  
  public static void main(String args[])
  {  
    //creating objects and passing values  
    Student4 s1 = new Student4(111,"Karan");  
    Student4 s2 = new Student4(222,"Aryan");  
    //calling method to display the values of object  
    s1.display();  
    s2.display();  
  }  
}   
```
## Java Methods
------------------------
A method is a collection of statements that perform some specific task and return the result to the caller. A method can perform some specific task without returning anything. Methods allow us to reuse the code without retyping the code.

### **Creating Method:**

Considering the following example to explain the syntax of a method

Syntax:

```Java
public static int methodName(int a, int b) 
{
   // body
}
```
Here,

* **public static** − modifier

* **int** − return type

* **methodName** − name of the method

* **a, b** − formal parameters

* **int a, int b** − list of parameters

### **Pass by Value and Pass by Reference in Java**

Pass by Value and Pass by reference is the two ways by which we can pass a value to the variable in a function.

* Pass by Value: It is a process in which the function parameter values are copied to another variable and instead this object copied is passed. This is known as call by Value.

* Pass by Reference: It is a process in which the actual copy of reference is passed to the function. This is called by Reference.

Talking about Java, we can say that Java is Pass by Value and not pass by reference.

### **Access Control**

Access specifier or modifier is the access type of the method. It specifies the visibility of the method. Java provides four types of access specifier:

* **Public**: The method is accessible by all classes when we use public specifier in our application.

* **Private**: When we use a private access specifier, the method is accessible only in the classes in which it is defined.

* **Protected**: When we use protected access specifier, the method is accessible within the same package or subclasses in a different package.

* **Default**: When we do not use any access specifier in the method declaration, Java uses default access specifier by default. It is visible only from the same package only.

### **Methods that Rerurns value**

A Java method may or may not return a value to the function call. We use the ``return`` statement to return any value. For example,

```Java
int addNumbers() 
{
  ...
  return (sum);
}
```

Here, we are returning the variable ``sum``. Since the return type of the function is ``int``. The sum variable should be of ``int`` type. Otherwise, it will generate an error.

>Note: If the method does not return any value, we use the ``void`` keyword as the return type of the method. For example:

```Java
public void square(int a) 
{
  int square = a * a;
  System.out.println("Square is: " + a);
}
```
## Polymorphism
--------------------------
The word polymorphism means having many forms.Polymorphism is considered one of the important features of Object-Oriented Programming. Polymorphism allows us to perform a single action in different ways. In other words, polymorphism allows you to define one interface and have multiple implementations. The word “poly” means many and “morphs” means forms, So it means many forms.

In Java polymorphism is mainly divided into two types:

* Compile time Polymorphism
* Runtime Polymorphism

### **(1) Compiled time Polymorphism:**
It is also known as static polymorphism. This type of polymorphism is achieved by function overloading or operator overloading. But **``Java doesn’t support the Operator Overloading``**.

**Method Overloading:** When there are multiple functions with same name but different parameters then these functions are said to be overloaded. Functions can be overloaded by ``change in number of arguments`` or/and ``change in type of arguments``.

Example:

```Java
// Java program for Method overloading
class MultiplyFun 
{
	// Method with 2 parameter
	static int Multiply(int a, int b)
	{
		return a * b;
	}
  // Method with the same name but 3 parameter
  static int Multiply(int a, int b, int c)
  {
        return a * b * c;
  }
	// Method with the same name but 2 double parameter
	static double Multiply(double a, double b)
	{
		return a * b;
	}
}
class Main 
{
	public static void main(String[] args)
	{
      System.out.println(MultiplyFun.Multiply(2, 4));
      System.out.println(MultiplyFun.Multiply(5.5, 6.3));
      System.out.println(MultiplyFun.Multiply(2, 7, 3));
	}
}
```

### **(2) Runtime Polymorphism:**
It is also known as Dynamic Method Dispatch. It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by Method Overriding.

Method overriding, on the other hand, occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.

Examnple:

```Java
// Java program for Method overriding
class Parent 
{
	void Print()
	{
		System.out.println("parent class");
	}
}
class subclass1 extends Parent 
{
	void Print()
	{
		System.out.println("subclass1");
	}
}
class subclass2 extends Parent 
{
	void Print()
	{
		System.out.println("subclass2");
	}
}
class TestPolymorphism3 
{
	public static void main(String[] args)
	{

		Parent a;
		a = new subclass1();
		a.Print();
		a = new subclass2();
		a.Print();
	}
}
```
Output:

```
subclass1
subclass2
```

## Nested and Inner Classes:
----------------------------
Java inner class or nested class is a class that is declared inside the class or interface.

We use inner classes to logically group classes and interfaces in one place to be more readable and maintainable.

Additionally, it can access all the members of the outer class, including private data members and methods.

```Java
class OuterClass 
{
  // ...
  class NestedClass 
  {
    // ...
  }
}
```

There are two types of nested classes you can create in Java.

* Static Nested Class
* Non-Static Nested Class

### **Static Nested Class**

* We Can define an inner class as static, so such type of classes is called a ``static nested class.``
* The ``nested class`` is defined with the ``static`` keyword, so this type of nested classes doesn’t share any relationship with the instance of an ``outer class``.
* A ``static nested class`` can able to access the ``static members`` of our class.

Example:

```Java
class Car 
{
  static class Wheel 
  {
    public void rotate() 
    {
      System.out.println("The wheel is rotating");
    }
  }
}
public class Test 
{
  public static void main(String args[]) 
  {
    Car.Wheel wheel = new Car.Wheel();
    wheel.rotate();
  }
}
```
Output:
```
The wheel is rotating
```

### **Non-Static Nested Class**

* A ``non-static nested class`` is indirectly known as an ``inner class`` in Java.
* The ``inner class`` is associated with the ``object of the outer class``. So the inner class is treated like other variables and methods of the outer class.
* The ``inner class`` is associated with the outer class object or instance, so we ``can’t declare static variables`` inside the inner class.

Example:
```Java
public class OuterClassTest 
{
  private int a = 10;
  public void innerClassInstance() 
  {
    InnerClassTest inner = new InnerClassTest();
    inner.outerObject();
  }
  public static void main(String args[]) 
  {
    OuterClassTest outer = new OuterClassTest();
    outer.innerClassInstance();
  }
  class InnerClassTest 
  {
    public void outerObject() 
    {
      System.out.println("Outer Value of a is: " + a);
    }
   }
}
```

Output:
```
Outer Value of a is: 10
```

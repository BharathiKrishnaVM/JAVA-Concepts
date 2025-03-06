# JAVA-Concepts
This repo contains basic concepts of OOPS and other things related to spring boot


# JDBC 
JDBC is a connection between database and java

Steps 
1. Import the package  (java.sql.*)
2. Load and Register the driver (forName("com.mysql.jdbc.driver"))
	a. forName is a method to load the driver
3. Establish the connection
	a. Connection is an interface. getConnection is a static method which will connect the connection
	b. getConnection("URL", "Username", "Password");
4. Create the statement
	a. Statement
	b. Prepared Statement (
	c. Callable Statement (stored procedures)
5. Execute the Query
6. Process Result
7. Close

```java
Import java.sql.*;
Main (){
}
Class forName("com.mysql.jdbcDriver");
Connection con = DriverManager getConnection("url", "un", "p");
Statement st = cn.createStatement();
ResultSet rs = st.executeQuery("select * from student").
Rs.next();
```


# JAVA

Table name is class name
Columns are the properties in java  - create variables 
Generate setters and getters
To print data we need toString method
Generate to string

Every class is a package

Spring framework to manage into bean then I need to add @component

By default the component of the class is Singleton in order to change to prototype we need to use @Scope

@Scope("prototype")  - For different request it will create new objects 

Java code is platform independent 
To run Java code we need JVM 
JVM is dependent with OS

Java code is compiled into byte code and that goes into JVM
It uses java compiler

The execution has rooted to only one file which has main method (public static void main) -> main will accept arguments which is string []args

To run the files we need JRE JAVA run time environment

JVM is a  part of JRE

**Write Once Run Anywhere**

ARRAYS

JAGGED ARRRAYS are rows and columns are not equal
Columns size are different



**CREATION of OBJECTS**

```java
class Students {
	
	int marks;
	String name;
	int id;
}

public class coreJava {

	public static void main(String[] args) {
		
		//creation of objects
		Students s1 = new Students();
		s1.id = 1;
		s1.marks = 90;
		s1.name = "Krishna";
		
		Students s2 = new Students();
		s2.id = 3;
		s2.marks = 50;
		s2.name = "Ram";
		
		Students s3 = new Students();
		s3.id = 2;
		s3.marks = 90;
		s3.name = "Lakshman";
		
		Students[] students = new Students[3];
		students[0] = s1;
		students[1] = s2;
		students[2] = s3;
		
//		for(int i=0; i<students.length; i++) {
//			System.out.println(students[i].name + " : "+students[i].marks);
//		}
//		
		//Enhanced for loop
		
		for(Students stud: students) {
			System.out.println(stud.name + " : "+stud.marks);
		}
	}

}
```

**STRINGS**

Strings are immutable in nature once the value is assigned for a string we can't reassingn the value because the address will change
```java
String str = new String("Name");
Or
String str  = "NAME";
```
String buffers are mutable which will give a capacity of 16Bytes- even if we increase the size of the string it will allocates the memory.

Append to
```java
StringBuffer sb = new StringBuffer(str: "BHARATHI KRISHNA");
Sb.append(" VM ");
```
String Buffer is THREAD SAFE but String Builder is not

**ENCAPSULATION**

Every time u create a instance variable make it private

How to access the data from a class in main --- using methods 

Assign the data with methods and access the data with methods which are setters and getters

```java
class Employee{
	private String name;
	private double salary;
	private String designation;
	//getters 
	public String getName() {
		return name;
	}
	
	public double getSalary() {
		return salary;
	}
	
	public String getDesignation() {
		return designation;
	}
	//setters
	public void setName(String name) {
		this.name = name;
	}
	
	public void setSalary(double sal) {
		this.salary = sal;
	}
	
	public void setDesignation(String designation) {
		this.designation = designation;
	}
}

public class encapsulation {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Employee employee = new Employee();
		employee.setName("Bharathi Krishna");
		employee.setSalary(1000);
		employee.setDesignation("Software Engineer");
		
	}

}
```

**CONSTRUCTORS**

Once the object is created I need the default values which is assigned for objects then constructors is used

We don't mention return type of a constructor and name of the constructor is same as class name

Everytime the object is called then always constructor will be called.



```java
package JavaBasics;

class Employees{
	private String name;
	private double salary;
	private String designation;
	//getters 
	
//Default constructor
	public Employees() {
		this.name = "Bharathi";
		this.salary = 1000;
		this.designation="Software engineer";
	}
	
	public String getName() {
		return name;
	}
	
	public double getSalary() {
		return salary;
	}
	
	public String getDesignation() {
		return designation;
	}
	//setters
	public void setName(String name) {
		this.name = name;
	}
	
	public void setSalary(double sal) {
		this.salary = sal;
	}
	
	public void setDesignation(String designation) {
		this.designation = designation;
	}
}

public class constructorExample {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Employees emp = new Employees();
		System.out.println("emp name is "+emp.getName());
	}

}
```

**PARAMETERIZED CONSTRUCTOR**

Which takes values for the constructor

**/*STATIC KEYWORD*/**

**STATIC VARIABLES:**

STATIC will be shared for all the objects which are referred. To use static variables we have to call by class

Students.marks = 89;
 Value is same for all objects


```java
class Students {
	
	static int marks;
	String name;
	int id;
}

public class coreJava {

	public static void main(String[] args) {
		
		//creation of objects
		Students s1 = new Students();
		s1.id = 1;
		Students.marks = 90;
		s1.name = "Krishna";
		
		Students s2 = new Students();
		s2.id = 3;
		Students.marks = 90;
		s2.name = "Ram";
		
		Students s3 = new Students();
		s3.id = 2;
		Students.marks = 90;
		s3.name = "Lakshman";
		
		Students[] students = new Students[3];
		students[0] = s1;
		students[1] = s2;
		students[2] = s3;
		
//		for(int i=0; i<students.length; i++) {
//			System.out.println(students[i].name + " : "+students[i].marks);
//		}
//		
		//Enhanced for loop
		
		for(Students stud: students) {
			System.out.println(stud.name + " : "+stud.marks);
		}
}
}
```

**STATIC METHOD:**

Static variables can be used inside the static method. But non static variables cannot be used directly inside the static method

```java
package JavaBasics;

class Students {
	
	static int marks;
	String name;
	int id;
	
	//non static method
	public void printValues() {
		System.out.println("Values of a students are : "+ name+ " : "+marks);
	}
	
	//static method needs the object to be sent as argument in order to print non static variables
	public static void staticPrintValues(Students obj) {
		System.out.println("Values of a students are : "+ obj.name+ " : "+marks);
	}
}

public class coreJava {

	public static void main(String[] args) {
		
		//creation of objects
		Students s1 = new Students();
		s1.id = 1;
		Students.marks = 90;
		s1.name = "Krishna";
		
		Students s2 = new Students();
		s2.id = 3;
		Students.marks = 90;
		s2.name = "Ram";
		
		Students s3 = new Students();
		s3.id = 2;
		Students.marks = 90;
		s3.name = "Lakshman";
		
		s1.printValues();
		s2.printValues();
		s3.printValues();
	
		//Static method calling -- pass the object as an argument
		Students.staticPrintValues(s1);
	
	}

}
```

**STATIC BLOCK:** is used to initialize the static variables

Irrespective of how many times the object reference is created and called this static block will call only ONCE

FIRST 
CLASS LOADS AND OBJECT LOADS

CLASS Loads only once from JVM once this class loads it calls the static block only once when the object is created for this class

```java
package JavaBasics;

class Mobile {
	int price;
	//Static variable which is common for all the objects so we create it using static block which will be called only one once when the class loads
	static String name;
	String brand;
	//Static block
	static {
		System.out.println("Static block");
		name = "Smart Phone";
	}
	//constructor
	public Mobile(){
		System.out.println("Constructor");
	}
}


public class staticBlock {

	public static void main(String[] args) throws ClassNotFoundException {
		// TODO Auto-generated method stub
		Mobile m1 = new Mobile();
		m1.price = 1500;
		m1.brand = "Samsung";
		
	
		Mobile m2 = new Mobile();
		
		//HAve two instances of class objects we can see that static block is called once irrespective of the object references how many times we called. 
	}

}
```

**Anonymous object:**
It can't be reused.

New A();![image](https://github.com/user-attachments/assets/19e09ae0-4e92-411e-9ef3-6e53a3a85e47)

**INHERITANCE**

When u repeat same code then it is redudancy

Keyword: extends


Super Class
```java
package JavaBasics.inheritance;

public class Calculator {
	
	public int add(int n1, int n2) {
		return n1+n2;
	}
	
	public int sub(int n1, int n2) {
		return n1-n2;
	}

}



SUB CLASS - ADVANCED CALC
SUPER CLASS -  CALCULATOR
package JavaBasics.inheritance;

//Advanced calculator contains few methods but i want to get all the methods from Calc also using extends
public class AdvancedCalc extends Calculator {

	public int multi(int n1, int n2) {
		return n1 * n2;
	}

	public int div(int n1, int n2) {
		return n1 / n2;
	}

}
```


```java
package JavaBasics.inheritance;

public class mainMethod {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		AdvancedCalc advcalc = new AdvancedCalc();
		int r1 = advcalc.add(5, 4);
		int r2 = advcalc.sub(10,30);
		int r3 = advcalc.multi(5, 2);
		int r4 = advcalc.div(15,6);
		
		System.out.println("results are "+r1+" " +r2+" "+r3+" "+r4);
		
	}

}
```

**MULTIPLE INHERITANCE WILL NOT WORK**

Class A{}
Class B{}
Class C extendes A, B{} --------- Will not work because what if A and B has same methods then it is difficult to get methods from A or B so it will not support

**CONSTRUCTOR**
EVERY CONSTRUCTOR IN JAVA HAS A METHOD WHICH IS SUPER
By default in every constructor has a method called super()

Super() method - Calls the constructor of a super class

EVERY CLASS IN JAVA EXTENDS "THIS" CLASS

This() methods executes the default constructor of the same class

```java
package JavaBasics;
 
class SuperClass {
	public SuperClass() {
		System.out.println("DEFAULT CONSTRUCTOR OF A SUPER CLASS ");
	}
	
	public SuperClass(int a) {
		System.out.println("PARAMETERIZED CONSTRUCTOR "+a);
	}
	
}

class SubClass extends SuperClass {
	public SubClass() {
		System.out.println("DEFAULT CONSTRUCTOR OF A SUB CLASS ");
	}
	
	public SubClass(int a) {
		//To call parameterized super class use super method with parameters
		//super(4);
		//TO call all the constructors of a super class use this method. 
		this();
		System.out.println("PARAMETERIZED CONSTRUCTOR of a SUB CLASS "+a);
	}
	
}


public class superAndThis {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

	//	SubClass sub = new SubClass(); // EXECUTES DEFAULT CONSTRUCTORS OF BOTH CLASSES
	//	SubClass sub1 = new SubClass(2); // EXECUTES PARAMETERIZED CONSTRUCTORS OF SUB CLASS and DEFAULT OF SUPER
		
		 /* EXECUTES PARAMETERIZED CONSTRUCTORS OF SUB CLASS and SUPER CLASS
		  * we have to call super class with parameters in SUB CLASS
		  */
		SubClass sub1 = new SubClass(2);
		
	}

}
```

**METHOD OVERRIDING**
```java
SuperClass


package JavaBasics.inheritance;

public class Calculator {
	
	public int add(int n1, int n2) {
		return n1+n2;
	}
	
	public int sub(int n1, int n2) {
		return n1-n2;
	}

}

Base class

package JavaBasics.inheritance;

//Advanced calculator contains few methods but i want to get all the methods from Calc also using extends
public class AdvancedCalc extends Calculator {

	// method overriding will have same method name and same arguments but the logic
	// is different in that the priority is given to same class instead of
	// inheritance Base class will over ride with super class
	public int add(int n1, int n2) {
		return n1 + n2 + 1;
	}

	public int multi(int n1, int n2) {
		return n1 * n2;
	}

	public int div(int n1, int n2) {
		return n1 / n2;
	}

}



package JavaBasics.inheritance;

public class mainMethod {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		AdvancedCalc advcalc = new AdvancedCalc ();
		int r1 = advcalc.add(5, 4);
		int r2 = advcalc.sub(10,30);
		int r3 = advcalc.multi(5, 2);
		int r4 = advcalc.div(15,6);

		
		System.out.println("results are "+r1+" " +r2+" "+r3+" "+r4);
		
	}

}
```

**ACCESS MODIFIERS**

	Private	Protected	Public	Default
Same Class	Yes	Yes	Yes	Yes
Same package
Subclass	No	Yes	Yes	Yes
Same package
Non-Subclass	No	Yes	Yes	Yes
Different package
subclass	No	Yes	Yes	No
Different package
Non-subclass	No	No	Yes	No




Try to make your class PUBLIC, make a each class in one file
Instance Variables are created as PRIVATE
Methods can be given as PUBLIC

There is a method / variables which should be accessed by only subclass then make it as PROTECTED

**PACKAGES:**

Move files common functionality files into a package 
Call the relevant file in main method using

import packageName.className;

Inbuilt class we use in java is a package
Example
ArrayList, System.out.println-> System is a package

Mvnrepository contains libraries

How to create a unique package name
	1.  Reversing the domain
	2. Example com.google.calculator

**FINAL KEYWORD**

Can be used with a 
Variable
Method
Class

Final keyword works same as const variable

We can't re assign the value of a variable



Anyone can inherits the properties or methods from any other class. To stop this make the class as final (Basically stopping the inheritance)

If I don’t want to override the method then make it final

**POLYMORPHISM**
--- It works with only inheritance

Many behaviors 

Two types of ploy morphism

Compile time polymorphism (early binding)
	Behavior is defined at compile time then it is compile time
	Example : over-loading
Run time Polymorphism (Late binding)
	When the behavior is compiled at run time then it late binding
	Example: Over riding
	
	

DYNAMIC METHOD DISPATCH:

Irrespective of what type of object we has It always depends what object we have

Run time polymorphism example

```java
package JavaBasics.inheritance;

 class A{
	public void show() {
		System.out.println("In A show ");
	}
}

 class B extends A{
	public void show() {
		System.out.println("In B Show");
	}
}

 class C extends A{
	public void show() {
		System.out.println("In C Show");
	}
}

public class mainMethod {	

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		//A is the reference class 
		A obj = new A();
		obj.show(); //In A Show;
		
		obj = new B();
		obj.show(); //In B Show;
		
		obj = new C();
		obj.show(); //In C Show

		//REFERENCE OF A AND OBJECT OF B - It is possible to have this kind of objects
		   A obj = new B();
			Obj.show();
		
	}

}
```


PACKAGES:

Move files common functionality files into a package 
Call the relevant file in main method using

import packageName.className;

Inbuilt class we use in java is a package
Example
ArrayList, System.out.println-> System is a package

Mvnrepository contains libraries

How to create a unique package name
	1.  Reversing the domain
	2. Example com.google.calculator

Final keyword

Can be used with a 
Variable
Method
Class

Final keyword works same as const variable

We can't re assign the value of a variable



Anyone can inherits the properties or methods from any other class. To stop this make the class as final (Basically stopping the inheritance)

If I don’t want to override the method then make it final

**OBJECTS AND METHODS USAGE:**
Every time I call the object in behind the scenes it returns as obj.toString() - which returns a string

HASHCODE

```java
package JavaBasics.inheritance;

import java.util.Objects;

class Laptop{
	int price;
	String model;
	
	public String toString() {
		return "model : "+model+" and price is "+price; 
	}
	//Generated from source code conversion of toString and hashcode
	@Override
	public int hashCode() {
		return Objects.hash(model, price);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Laptop other = (Laptop) obj;
		return Objects.equals(model, other.model) && price == other.price;
	}
	
	
}

public class objectMethods {

	public static void main (String[]args) {
		
		Laptop obj = new Laptop();
		obj.model = "MACBook Air";
	    obj.price = 1000;
	    //the below toString method overrides the super class which is a inbuilt method.
	    System.out.println(obj.toString());
	    
	    Laptop obj2 = new Laptop();
	    obj2.model = "MacBook Air";
	    obj2.price = 2000;
	    System.out.println(obj.equals(obj2));
	}
}
```
**TypeCasting**

UP Casting and Down Casting:

Double d = 4.5;
Int I = (double)d;


UpCasting:
A-> super class
B-> subclass

A obj = new B();
obj.show1();

DownCasting:
B obj1 = (A)obj;
obj1.show2()

```java
package JavaBasics.inheritance;

class A{
	public void show1() {
		System.out.println("In A Show");
	}
}

class B extends A{
	public void show2() {
		System.out.println("In B Show");
	}
}
public class Typecasting {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		//upCasting - has Reference of superclass but subclass of object
		A obj = new B();
		obj.show1();
		
		//Downcasting - has reference of subclass and typecasting of obj
		B obj1 = (B) obj;
		obj1.show2();
		
	}

}
```



abstract class Car{ //ABSTRACT CLASS
	//method declaration using abstract- If i don't now what functionality this drive method contains then declare it
	public abstract void drive();
	public abstract void fly();
	
	public void playMusic() {
		System.out.println("Play music for the car");
	}
}

abstract class BMW extends Car{ //ABSTRACT CLASS

	@Override
	public void drive() {
		System.out.println("Drive from BMW");
		
	}
	
}

class FinalCar extends BMW{   //CONCERETE CLASS
	@Override
	public void fly() {
		// TODO Auto-generated method stub
		System.out.println("Fly from final car");
	}
	
}


public class AbstractKeyword {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		//OBJECT Reference is from parent class but the object is from concerete class
		Car obj = new FinalCar();
		obj.playMusic();
		obj.drive();
		obj.fly();
	}

}


***Wrapper classes:***

int -> Integer
double -> Double

Boxing
Taking a primitive value and storing it in a wrapper object, it automatically converts to wrapper is called autoboxing



Auto - unboxing

Str to Integer - Integer.parseInt(str)
```java
package JavaBasics.inheritance;

public class WrapperClasses {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int num1 = 7;
		
		Integer num2 = num1; //auto boxing
		System.out.println(num2);
		
		int num3 = num2; //auto unboxing
		System.out.println(num3);
		
		String str = "35";
		int stringToNumber = Integer.parseInt(str);
		System.out.println(stringToNumber);
		
	}

}
```

**Abstract keyword:**

IF we want to declare a method then use abstract keywords.
******WE can't create a object of a abstract class. But can create a reference of obj 

Is it compulsory to have a abstract method in a abstract class??

A Abstract method should have a abstract class//
But a abstract class can either or can have abstract method or public methods..

```java
package JavaBasics.inheritance;


abstract class Car{ //ABSTRACT CLASS
	//method declaration using abstract- If i don't now what functionality this drive method contains then declare it
	public abstract void drive();
	public abstract void fly();
	
	public void playMusic() {
		System.out.println("Play music for the car");
	}
}

abstract class BMW extends Car{ //ABSTRACT CLASS

	@Override
	public void drive() {
		System.out.println("Drive from BMW");
		
	}
	
}

class FinalCar extends BMW{   //CONCERETE CLASS
	@Override
	public void fly() {
		// TODO Auto-generated method stub
		System.out.println("Fly from final car");
	}
	
}


public class AbstractKeyword {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		//OBJECT Reference is from parent class but the object is from concerete class
		Car obj = new FinalCar();
		obj.playMusic();
		obj.drive();
		obj.fly();
	}

}
```

**INNER CLASS:**

Only inner class can have a static keyword.

```java
package JavaBasics.inheritance;

class Parent{
	int price;
	public void show() {
		System.out.println("A class");
		
	}
	
	class B{
		public void show2() {
			System.out.println("Inner class");
		}
		
	}
}

public class InnerClass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		//Creating object reference of A
		
		Parent obj = new Parent();
		obj.show();
		
		//to create object reference of B which is inner class we need parent class as well.
		
		// B obj1 = new B(); // will throw an error because for inner class we cannot directly create an object
		
		Parent.B obj1 = obj.new B(); //Creating the object based on parent class which is obj;
		obj1.show2();
		
		
		
	}

}
```

//To avoid creating the reference of parent class then make the inner class to static

```java
package JavaBasics.inheritance;

class Parent{
	int price;
	public void show() {
		System.out.println("A class");
		
	}
	
	static class SubClass{
		public void show2() {
			System.out.println("Inner class");
		}
		
	}
}

public class InnerClass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		//Creating object reference of A
		
		Parent obj = new Parent();
		obj.show();
		
		
		SubClass obj1 = new SubClass(); //Creating the object directly because inner class is static
		obj1.show2();
		
	}

}
```


//ANONYMOUS INNER CLASS
```java
package JavaBasics.inheritance;


class ParentClass{
	public void show() {
		System.out.println("In parent class");
	}
}

public class AnonymousClass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		//creating a anonymous class beside the object declaration
		ParentClass obj = new ParentClass(){
			public void show() {
				System.out.println("In Anonymous class of same method ");
			}
		};
		
		obj.show();
		
	}

}
```

Abstract class and anonymous class

```java
package JavaBasics.inheritance;

abstract class parentClass{
	public abstract void show();
}

public class AnonymousClass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub		
		//We are creating an object for the anonymous class with reference of abstract class...
		parentClass obj = new parentClass() {
			public void show() {
				System.out.println("In Anonymous abstract class of same method ");
			}
		};
		obj.show();
	}

}
```
**INTERFACES:**

Using in class

Public class sampleClass implements interface_name{}

Interface to interface - use extends


By default the variables in interface are final and static.
By default the methods in interface is a public abstract

Interfaces don't have memory for object

```java
package JavaBasics.interface_;

//-----first way
/*
class Laptop extends Computer{
	public void devlop() {
		System.out.println("Develop an app in laptop");
	}
}

class Desktop extends Computer {
	public void devlop() {
		System.out.println("Develop an app in Desktop");
	}
}

abstract class Computer{
	public abstract void devlop();
}
*/
```

```java
//Make a interface instead of abstract class
class Laptop implements Computer{
	public void devlop() {
		System.out.println("Develop an app in laptop");
	}
}

class Desktop implements Computer {
	public void devlop() {
		System.out.println("Develop an app in Desktop");
	}
}
interface Computer{
	 void devlop();
}

public class interfaceClass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Laptop obj1 = new Laptop();
		obj1.devlop();
		
		Computer obj2 = new Desktop();
		obj2.devlop();
		//if i use reference of abstract computer ---first way solution
		/*
		Computer obj2 = new Laptop();
		obj2.devlop();
		*/
	}

}
```
```java
// More on interface variables

package JavaBasics.interface_;

interface Laptop1{
	public static final String brand = "Lenovo";
	public static final int price = 25000;
	void specifications();
}

class BuyNewLaptop implements Laptop1{

	@Override
	public void specifications() {
		// TODO Auto-generated method stub
		System.out.println("I want to buy Dell laptop with 16gb ram and 8gb ssd cards");
	}
	
}

public class InterfaceVariables {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		Laptop1 obj;
		obj = new BuyNewLaptop();
		Laptop1.brand="DEll";
		Laptop1.price = 30;
		//throws an error for final static variables
		obj.specifications();
		
	}

}
```
A class can have more than one interface 

**Multiple interfaces**
```java
package JavaBasics.interface_;

interface X{
	void employee();
	void sample();
}

interface Y extends X{
	void getDetails();
}

class Sample implements Y{

	@Override
	public void employee() {
		// TODO Auto-generated method stub
		System.out.println("GET EMPLOYEE");
	}

	@Override
	public void sample() {
		// TODO Auto-generated method stub
		System.out.println("GET SAMPLE");
	}

	@Override
	public void getDetails() {
		// TODO Auto-generated method stub
		System.out.println("GET DETAILS");
	}
	
}

public class InheritanceInterface {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Sample obj = new Sample();
		obj.employee();
		obj.sample();
		obj.getDetails();

	}

}
```

**ENUM:**

Constants which we create:

We cannot extend enum in class

By default ENUM extends a class called ENUM java.lang.enum


```java
package JavaBasics.interface_;

enum Status{
	Running, Failed, Success, Pending;
}

// ENUM is class which contains objects array
public class EnumClass {

	public static void main(String[]args) {
		
		Status s = Status.Running;
		
		switch(s) {
		case Running:
			System.out.println("All good");
			break;
		case Pending:
			System.out.println("Please wait");
			break;
		case Success:
			System.out.println("Done");
			break;
		case Failed:
			System.out.println("Try again");
			break;
			
		}
	}
}
```

**ENUM MORE INFO**

```java
package JavaBasics.interface_;

enum LaptopPrices{
	MacBook(2500), Dell(1500), Lenovo(1000), HP(2000), ACER(960), DEFAULTPRICE();
	
	private int price;

	//default constructor of laptop which accepts price 
	private LaptopPrices() {
		// TODO Auto-generated constructor stub
		price = 800;
//		System.out.println("In constructor of Enum class ");
	}
	//parameterised constructor
	private LaptopPrices(int price) {
		this.price = price;
//		System.out.println("in laptop "+this.name());
	}
	
	
	public int getPrice() {
		return this.price;
	}

	public void setPrice(int price) {
		this.price = price;
	}
	
}

public class EnumMoreInfo {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
//		LaptopPrices p = LaptopPrices.ACER;
//		System.out.println(p+" "+ p.getPrice());
		
		for(LaptopPrices p1 : LaptopPrices.values()) {
			System.out.println("Laptop is "+ p1+ " : "+p1.getPrice());
		}
	}

}
```

**Functional Interface**
In Interface we can only declare methods all the methods are public and abstract

Different types of interfaces

Normal Interface - which has two or more methods
Functional Interface or SAM - Single Abstract method ***Important


Marker interface: which has no methods
Interface Abc{}


Serialization and Deserialisation

We can use lamda expressions only with functional interfaces
```java
()-> {
Public void show(){
System.out.println("In show");
}
}

A obj = new A(){
Public void show(){
System.out.println("In show");
}
}
```
The above code replaces with (I,j)-> i+j

LAMDA EXPRESSIONS ONLY Works with Functional Interface

```java
package JavaBasics.interface_;

@FunctionalInterface
interface addNumbers {
	int add(int i, int j);
}
public class FunctionalInterface_1 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		addNumbers obj = (i, j) -> i+j; //lamda expressions
		System.out.println(obj.add(5,4));
		
	}

}
```

**Exceptions:**

Compile time errors - > syntax errors 
Run time errors -> exception handling
Logical Errors

Exception:

```java
package exception;


public class ExceptionHandling {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		int i = 4; // change the value to see the exception
		int j = 18;
		try {
			j=	j/i;
		}
		catch(Exception e){
			System.out.printf("Exception Handling ", e);
		}
		System.out.println(j);
	 
	}

}
```

Multiple catch blocks can be written to catch the expressions
Exception is a parent class it can handle all the classes

Object
|
Throwable is are two types error and exception

Errors example

ThreadDeath

IOError

VirtualMachineError

OutOfMemory

Exceptions

Run time exception are called as unchecked exceptions

	ArrayOutOfBoundException
 
	Arithematic
 
	NullPointer
 
SQL Exception are called as checked exceptions

IO Execution

**THREADS**

Threads: Multi tasking can be done using threads

In same task we can have multiple threads that has to perform the tasks

How to make normal objects into threads 
Then extends the class called thread

Behind the scenes it will have schedulers

Range of priorities goes from 1-10 1(highest), 10-least

```java
package threads;


class A extends Thread{
	public void run() {
		for(int i=1; i<=100; i++) {
			System.out.println("Hello");
		}
	}
}

class B extends Thread{
	public void run() {
		for(int i=1; i<=100; i++) {
			System.out.println("Hi");
		}
	}
}

public class ThreadsExample {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		A obj = new A();
		B obj1 = new B();
		System.out.println(obj.getPriority());
		obj.start();
		obj1.start();
		

	}

}
```
Thread Safe: Only one thread can work with the one method.

Thread Status

1. New
2. Runnable
3. Running
4. Waiting
5. Dead


**Collections**

Collections API: Concept 
We can work with all types of data structures using inbuilt classes.


Collection : it is an interface
Collections: It is a Class

LIF O - Stack
FIFO - Queue

Collection 

List -> ArrayList, LinkedList
Queue -> DeQueue
Set -> HashSet, LinkedHashSet
ArrayList:
We can directly print the Arraylist no need of for loop

We can use generics to get the values from Collections
<String>
Why type is Important?

ArrayList does'nt give index value

To support index value use list
Collection will have a unique value
But list supports duplicate Values


Set is a collection of unique value it doesn't contain index as well,
TreeSet gives an sorted value of an array

Maps will have key value pairs
Map is an interface which has HashMap as a class
.put

Keys are unique it cannot be repeated
Hashtable and Hashmap ->
Hashtable is synchronised data 

Comparable is a interface

```java
package CollectionInJava;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.Comparator;
import java.util.Iterator;
import java.util.List;

public class CollectionInterface {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		
		Collection<Integer> col = new ArrayList<Integer>();
		//List supports duplicate values
		List <Integer> list = new ArrayList<Integer>();
		
		col.add(1); //the values are objects they are not strings
		col.add(2);
		col.add(1);
		col.add(3);
		
		list.add(1);
		list.add(2);
		list.add(3);
		list.add(4);
		
		
		
		for(Integer c: col) {
			System.out.println(c);
		}
		System.out.println("List output values");
		//get index value
		System.out.println("Index value is "+list.get(2));
		for(Integer li: list) {
			System.out.println(li);
		}
		
		//Instead of For loop use Iterator
		Iterator<Integer> values = col.iterator();
	
		while(values.hasNext()) {
			System.out.println("Values from Iterator "+values.next());
		}
		
		
		//Comparator Operator
		
		
		List<String> names = new ArrayList<String>();
		
		names.add("Bharathi");
		names.add("Vishnu");
		names.add("Neekshita Sree");
		names.add("Krishna");
		names.add("Velu");
		
		//lamda expressions
		Comparator<String> com = (str1, str2) -> str1.length() > str2.length() ?  1 :  -1;
		
		Collections.sort(names, com);
		System.out.println(names);
	}

}
```


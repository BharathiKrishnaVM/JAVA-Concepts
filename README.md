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



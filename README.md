# psa-notes-22april
This is my first Repository.
<br>
Satendra


https://us02web.zoom.us/rec/share/fJWCkJJ3PsXmGdurCP_wsv3bYZhD9PDSf44utoK-gYdKdGh4lC8UPiOI33xhXkw2.OGDk298l7Gcklzuy



################################
Core Java - Pankaj Sir Academy
###############################

What is a class?
-> Class helps us to create object in java
-> In java we use class keyword to create class.
-> Keyword should be in lower case
Example :

class A {

}
-> We define the boundary of class using flower brackets

Class Naming Convention
#######################
-> Class name should always start with upper case
-> If the class has more than one work then use camel casing. that is
first letter of every word should be in upper case

Example: Correct
-------
class Bank {

}
Example: Correct
-------
class BankAccountNumber {

}
Example: InCorrect
-------
class Bank Account Number {

}

Example:
----------
-> Snake Casing-->Should not use for java
-> Will Execute without any error

public class Bank_Account_Number {
 
}

Example: Class name cannot start with a number
----------------------------------------------
-> Will give error
public class 1Bank {
  public static void main(String[] args){
     
  }
}

Example:Class name can start with a character follwed by Number
---------
public class Bank1 {
  public static void main(String[] args){
     
  }
}

Note:
1. Donot use specials characters like #,@ % & etc while creating class
2. $Class name will execute. But never create a class with special character $

Example:Correct, but not recommended
___________
public class $A {
	public static void main(String[] args) {
	
	}
}

Example: For Creating objects in java
---------------------------------------

public class A {
  public static void main(String[] args){
     A a1 = new A();
     A a2 = new A();
     System.out.println(a1);
     System.out.println(a2);
  }
}

new keyword:
##############

-> Using new keyword we send request to class to create object
-> Once object is created new keyword will get objects's address and stores that in a reference variable

Syntax to create object:
-------------------------
ClassName variableName = new ClassName();

Note:
-----------------------------------
Two types of camel casing:

a. Upper Case Camel Casing: Used for naming class, interface, abtract class etc
b. Lower Case Camel Casing: Used for creating method, variables etc
_______________________________________________________________________

Non-static Variable/ Instance Variable /Object Variables
#####################
1. We should create non static variable inside class outside method without using static keyword
2. Without creating object we cannot access non static variable
Example 1:
-----------
public class A {
	int x = 10;
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
	}
}
Output: 10
--------------------------------------------------------------------------------
Example 2:
----------

public class A {
	int x = 10;
	int y = 20;
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		System.out.println(a1.y);
	}
}
Output:
10
20

-----------------------------------------------------------------
3. Every time we create object non-static variable copy is loaded to that object
4. Copy of variable in these object's are different. That is if you change the value of variable in one object, those changes cannot be seen in another object

Example:
---------

public class A {
	int x = 10;
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);//10
		a1.x = 20;
		System.out.println(a1.x);//20
		
		A a2 = new A();
		System.out.println(a2.x);//10
	}
}
Output
10
20
10


5. It is not mandatory to initialize non-static variable. Depending on data type automatically default value will get stored in it.
Example:
---------
public class A {
	int x ;
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		
	}
}

Ouput: 0
-----------------------------------------------------------

Static variables:
#################

1. We should create static variables inside class but outsiude method with static keyword
2. To access static variable we will use below Options
a. ClassName.variableName
b. variableName (Contraints)
c. objectAddress.variableName (Wrong Appraoch but will work)

Example:
---------------
public class A {
	static int x=10 ;
	public static void main(String[] args) {
		System.out.println(A.x);
		System.out.println(x);
		
		//Wrong
		A a1 = new A();
		System.out.println(a1.x);//A.x
	}
	
}
Output
10
10
10
--------------------------------------------------------------------------
Example:
--------
public class A {
	static int x=10 ;
	public static void main(String[] args) {
		System.out.println(A.x);//10
		A.x=20;
		System.out.println(A.x);
		System.out.println(A.x);
		A.x = 30;
		System.out.println(A.x);
		System.out.println(A.x);
		
		
	}
	
}
-----------------------------------------------------------------------

Types of variables in java
############################

1. Local Variable
######################
a. Local vaiables should be created inside methods
b. We should use local variable within the created method only
Example 1:
---------
public class A {
	
	public static void main(String[] args) {
		int x = 100;//Created
		System.out.println(x);//Using
	}
	
}
Output: 100

Example 2:
-----------
public class A {
	public static void main(String[] args) {
		int x = 100;//Created
		System.out.println(x);//Using
		A a1 = new A();
		a1.test();
	}
	public void test() {
		System.out.println(x);//Error
	}
}
Output: Error

Example 3:
----------
public class A {
	public static void main(String[] args) {
		A a1 = new A();
		a1.test();
	}
		
	public void test() {
		int x = 100;//Created
		System.out.println(x);//Correct
	}
}

Example 4:
------------
public class A {
	public static void main(String[] args) {
		A a1 = new A();
		a1.test();
		System.out.println(x);//Error
	}
		
	public void test() {
		int x = 100;//Created
		System.out.println(x);//Correct
	}
}

c. Without initializing if you are using local variable then you will get an error
Example 5:
----------
public class A {
	public static void main(String[] args) {
		int x;
		System.out.println(x);//Error
	}
}

Note: Static variable has global access
Example:
---------
public class A {
	static int y = 10;
	public static void main(String[] args) {
		System.out.println(A.y);
		int x=10;
		System.out.println(x);
	}
	public void test() {
		System.out.println(A.y);
		System.out.println(x);
	}
}

2. Static variable
3. Non-static variable / instance variable

4. Reference Variable
#####################
a. Can hold either Object address or null value
Example 1:
----------
public class A {
	
	public static void main(String[] args) {
		A a1 = null;
		A a2 = new A();
	}
	
}

b. Datatype of reference variable is class name
Example 2: A x;

Example 3:
In the below example "a1" is created inside main and hence it is a local variable. We cannot access that outside main method

public class A {
	
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1);
	}
	public void test() {
		System.out.println(a1);//Error
	}
	
}

Example 4:
Error because "a1" is local variable and not initialized

public class A {
	
	public static void main(String[] args) {
		A a1;
		System.out.println(a1);//Error
	}
	
	
}
Example 5: If we donot initialize static reference variable then by default null value will get stored in it

Example:
public class A {
	static A a1;
	public static void main(String[] args) {
		System.out.println(a1);
	}
	
	
}

Example:
public class A {
	static A a1;
	public static void main(String[] args) {
		System.out.println(a1);
		a1 = new A();
		a1.test();
	}
	public void test() {
		System.out.println(a1);
	}
	
	
}

Note:
Stack - > LIFO (Last In First Out)
Heap - > Objects are created inside heap memory
Garbage Collector - > Manages Memory to avoid overflow of memory by constantly removing objects that is not is use from heap memory

Heap and stack memory
#####################


###############
methods in java
###############
1. void keyword: A void method cannot return any value

Example 1:
----------
public class C {
	public static void main(String[] args) {
		
	}
	
	public void test() {
		return 100;//Error
	}
}

Example :
-----------
public class C {
	public static void main(String[] args) {
		C c1 = new C();
		int x = c1.test();
		System.out.println(x);
	}
	
	public int test() {
		return 100;
	}
}
Output: 100

Example:
----------
public class C {
	public static void main(String[] args) {
		C c1 = new C();
		String x = c1.test();
		System.out.println(x);
	}
	
	public String test() {
		return "mike";
	}
}

return keyword versus return "value"
#####################################

return keyword:
-> A method has to be void
-> It is optional
-> it will return control to method calling statement

Example:
-------

public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test();
	}
	
	public void test() {
		System.out.println(100);
		return;
	}
}
Output: 100

Note: if we write code after return keyword, then that code will 100% not run. This error is called as unreachable code error

Example:
public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test();
	}
	
	public void test() {
		System.out.println(100);
		return;
		System.out.println(200);
	}
}
Output: unreachable code error

return "value"
---------------
-> The method has to be not a void method
-> It is mandatory to use return "value" statement inside not a void method
-> It will return control and value to method calling statement

Example:
public class C {
	public static void main(String[] args) {
	 
	}
	
	public int test() {//Error
		
	}
}
Output: Error because return "value" statement is missing inside test method


Example:
public class C {
	public static void main(String[] args) {
	 
	}
	
	public int test() {
		return 100;
		System.out.println(300);
	}
}
Output: Unreachable code error

Method Arguments
##################
-> Using method arguments we supply values to method when we are calling it
-> The method argument is a local variable
-> arguments inside the method values that you supply to the method should match

Example:
-------
public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test(100);
	}
	
	public void test(int x) {
		System.out.println(x);
	}
}

Example:
--------
public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test(100,"mike");
	}
	
	public void test(int x,String y) {
		System.out.println(x);
	}
}

Note: When method argument type is Object, then we can supply any kind of value to it

Example:
--------
public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test('a');
	}
	
	public void test(Object x) {
		System.out.println(x);
	}
}

Example:
public class C {
	public static void main(String[] args) {
	  C c1 = new C();
	  c1.test("mike",100,200,300,400);
	}
	
	public void test(String y, int... x) {
		System.out.println(x[0]);
		System.out.println(x[1]);
		System.out.println(x[2]);
		System.out.println(x[3]);
		System.out.println(y);
	}
}
Output:
100
200
300
400
mike

Static Methods
###############

Example 1:
public class C {
	public static void main(String[] args) {
	    C.test();
	}
	public static void test() {
		System.out.println(599);
	}
	
}

Example 2:
---------
public class C {
	public static void main(String[] args) {
	   int x =  C.test();
	   System.out.println(x);
	}
	public static int test() {
		return 100;
	}
	
}

Example 3:
-----------
public class C {
	public static void main(String[] args) {
	   int x =  C.test(100,200);
	   System.out.println(x);
	}
	public static int test(int a, int b) {
		return a+b;
	}
	
}
Example 4:
----------
public class C {
	public static void main(String[] args) {
	   C.test();
	   C.test();
	   C.test();
	}
	public static void test() {
		System.out.println(500);
	}
	
}

Datatypes in java
##################
Storing integer Values:
------------------------------------
1. byte - 1 byte - default value: 0
2. short - 2 bytes - default value: 0
3. int - 4 bytes - default value: 0
4. long - 8 byte - default value: 0

Floating Value
-------------------------------
1. float - 4 bytes - default value: 0.0
2. double - 8 bytes - default value: 0.0

boolean(true/false)
----------------------------
1. boolean - NA - default: false

character values
-----------------------
1. char - 2 bytes - default: blank space

String - Class
---------------
String - NA - dynamic - default: null

Note:
byte: -128 to 127 (8-bit signed two's complement integer)
short: -32,768 to 32,767 (16-bit signed two's complement integer)
int: -2,147,483,648 to 2,147,483,647 (32-bit signed two's complement integer)
long: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 (64-bit signed two's complement integer)
float: Approximately ±3.40282347E+38F (32-bit IEEE 754 single-precision floating-point)
double: Approximately ±1.79769313486231570E+308 (64-bit IEEE 754 double-precision floating-point)
char: 0 to 65,535 (16-bit unsigned Unicode character)
boolean: true or false (size is not precisely defined, often considered 1 bit)

Datatypes example:
---------------------
public class C {
	static byte x1 ;
	static short x2 ;
	static int x3 = 23_567 ;
	static long x4=9632629033L ;
	static float x5=10.3F ;
	static double x6 ;
	static char x7 ;
	static boolean x8 ;
	static String x9;
	
	public static void main(String[] args) {
		System.out.println(x1);
		System.out.println(x2);
		System.out.println(x3);
		System.out.println(x4);
		System.out.println(x5);
		System.out.println(x6);
		System.out.println(x7);
		System.out.println(x8);
		System.out.println(x9);
	}
	
}

New type introduced in java version 10
---------------------------------------
var type
#########
-> This was introduced in java version 10
-> It gives dynamic datatype concept. Depending on the value stored inside variable, dataype is allocated to it internally

Example:
public class C {
	
	public static void main(String[] args) {
		var x1 =100;
		var x2 =100.3;
		var x3 ='a';
		var x4 ="mike";
		var x5 =new C();
		System.out.println(x1);
		System.out.println(x2);
		System.out.println(x3);
		System.out.println(x4);
		System.out.println(x5);
	}
	
}
-> var type can only be local variable
-> It cannot be static / non-static variable
-> It cannot be method argument
-> It cannot be method return type
Example:
--------
public class C {
	var x1;//Error
	static var x2;//Error
	public static void main(String[] args) {
		var x5 = 100;//Correct
	}
	public var test(var x3) {//Error
		
	}
	
}

######################
Constructors in java
######################

-> Should have same name as that of class
-> It is always void by default
Example 1:
----------
public class C {
	C(){
		return 100;//Error
	}
	public static void main(String[] args) {
		C c1 = new C();
	}
	
}
-> To call a constructor we have to create object.

Example 2:
--------
public class C {
	C(){
		System.out.println(100);
	}
	public static void main(String[] args) {
		C c1 = new C();
	}
	
}

-> Whenever we creat object constructor is being called

Example 3:
---------
public class C {
	C(){
		System.out.println(100);
	}
	public static void main(String[] args) {
		C c1 = new C();
		C c2 = new C();
		C c3 = new C();
	}
	
}
Ouput:
100
100
100

-> If you mention return type for a constructor. Then it is treated as a method

Example 4:
----------
public class C {
	void C(){
		System.out.println(100);
	}
	public static void main(String[] args) {
		C c1 = new C();
	}
	
}

Ouput: No Output, because void C() is a method

Example 5: 
Note :
-> Method name can be same as class name
-> Variable name can be same as class name

public class C {
        int C = 1000;
	void C(){
		System.out.println(100);
	}
	public static void main(String[] args) {
		C c1 = new C();
		c1.C();
		System.out.println(c1.C);
	}

}

Contructor Overloading:
-------------------------
Here we create more than one constructor in same class provided they have different number of arguments or different type of arguments

Example:
--------
public class A {
	A(){//NoofArgs=0
		System.out.println("A");
	}
	A(int x){//NoofArgs=1
		System.out.println(x);
	}
	A(int x,int y){//NoofArgs=2
		System.out.println(x);
		System.out.println(y);
	}
	public static void main(String[] args) {
		A a1 = new A();
		A a2  = new A(100);
		A a3 = new A(200,300);
	}
}

Example:
--------------
public class A {
	A(int x){//noOfArgs=1, type=int
		System.out.println(x);
	}
	A(float y){//noOfArgs=1, type=float
		System.out.println(y);
	}
	public static void main(String[] args) {
		A a1 = new A(100);
		A a2 = new A(10.3F);
	}
}

Example:
---------
public class A {
	A(int x){//noOfArgs=1, type=int
		System.out.println(x);
	}
	A(String x, int y){//noOfArgs=2, type=String, int
		System.out.println(x);
		System.out.println(y);
	}
	public static void main(String[] args) {
		A a1 = new A("mike",100);
		A a2 = new A(500);
		
	}
}

############
this keyword
#############
-> this keyword is a special reference variable tha hold's object's address
Example:
----------
public class A {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1);
		a1.test();
	}
	public void test() {
		System.out.println(this);
	}
}

-> Using this keyword we can access non-static members of the class
Example:
--------

public class A {
	int x = 10;
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
	public void test() {
		System.out.println(this.x);
	}
}

-> We cannot use this keyword inside "static method"
public class A {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(this);//Error
	}
	public static void test() {
		System.out.println(this);//Error
	}
}
Example:
-------
public class A {
	int x = 10;
	int y = 10;
	public static void main(String[] args) {
		A a1 = new A();
		a1.test();
	}
	public void test() {
		System.out.println(this.x);
		System.out.println(this.y);
	}
}
#################################################
Note: PeerUp App start Communication here......
#################################################

-> this keyword hold's current object address that is executing

Example:
--------
public class A {
	public static void main(String[] args) {
		A a1 = new A();
		a1.test();
		A a2 = new A();
		a2.test();
		a1.test();
		
	}
	public void test() {
		System.out.println(this);
	}
}

this()- This syntax is used to call constructor
--------------------------------------------
-> Using this() keyword we can call a constructor

Example:
-------
public class A {
	A(){
		System.out.println("A");
	}
	A(int x){
		this();
	}
	public static void main(String[] args) {
	   A a1 = new A(100);
	}
	
}

-> While calling a constructor using this() keyword, ensure calling is done from anothe constructor

Example:
--------
public class A {
	A(){
		System.out.println("A");
	}
	A(int x){
		this();
	}
	public static void main(String[] args) {
	   A a1 = new A(100);
	}
	public void test() {
		this();//Error, we cannot call constructor from method
	}
	
}

Example:
---------
public class A {
	A(int x){
		System.out.println(x);
	}
	A(){
		this(100);
	}
	public static void main(String[] args) {
	   A a1 = new A();
	}
	
	
}

-> While calling a constructor using this() keyword ensure it is always first statement inside another constructor

Example:
---------
public class A {
	A(int x){
		System.out.println(x);
	}
	A(){
		System.out.println(200);
		this(100);//Error because it cannot be second statement while calling constructor
		
	}
	public static void main(String[] args) {
	   A a1 = new A();
	}
	
	
}

Example:
---------
public class A {
	int x;//-->0
	A(int x){////Step 4-->x=100
		this.x=x;//Step 5
		System.out.println(this.x);//Step 6===>100
	}
	A(){//Step 2
		this(100);//Step 3
	}
	public static void main(String[] args) {
	   A a1 = new A();//Step 1
	}
	
	
}

Constructor Chaining
---------------------
-> When we call one constructor from another constructor it will form chain like flow structure. This is called as constructor chaining
-> This can be achieved by using this() keyword or Creating Object in another constructor

Example 1:
----------
public class A {
	A(){
		System.out.println("A");
	}
	A(int x){
		this();
	}
	public static void main(String[] args) {
		A a1 = new A(100);
	}
}

Example 2:
-----------
public class A {
	A(){
		System.out.println("A");
	}
	A(int x){
		A a2 = new A();
	}
	public static void main(String[] args) {
		A a1 = new A(100);
	}
}

###############################
Important Shortcuts in eclipse
################################
1. Ctrl + Space
⚡ Content Assist — suggests code completions.

Example: 
a. syso  (do control+ space bar)
b. main (do control+ space bar)

2. Ctrl + 1
💡 Quick fix — suggests solutions for errors or warnings.

Example: String x = 100; (Press control + 1 to get solutions to fix problem) 

3. Ctrl + O
🧭 Quick outline — shows methods/fields of the current class.

Example:
public class Animal {

    private String name;
    private int age;
   
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }

    public void sleep() {
    	
        System.out.println(name + " is sleeping.");
    }

    private void breathe() {
    	System.out.println(name + " is breathing.");
    }
}

-> in the above file when pressed Control + O we will get soo all  content of like like shown below:

Animal 
-> name
-> age
-> Animal(String name, int age)
-> eat()
-> sleep() etc.....

4. F3
🔄 Go to the declaration of a variable, method, or class.

Example: 
public class Animal {

    private String name;// Will show this step, as variable is declared here
    private int age;
   
    public Animal(String name, int age) {
        this.name = name; // When placed cusor on this.name, and pressed f3
        this.age = age;
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }

    public void sleep() {
    	
        System.out.println(name + " is sleeping.");
    }

    private void breathe() {
    	System.out.println(name + " is breathing.");
    }
}

5. Ctrl + .
➡️ Jump to the next error or warning in the file.
public class Dog {
	
	int x//This is your first error. When pressed control + .
	
	public static void main(String[] args) {
		int y//It will take you to this error
	}

}

##########################
Packages in java
###########################
a. Packages are folders created in java to store programs in organized manner
b. This will make maintainance of the project easy
c. Naming Convention for packages
-> Package name cannot be keyword like - new , static, public , in etc...
-> Donot start package name with capital letters
-> Package name not to be given as java

d. When you create a class inside package, we have to define package keyword in our program as shown below:

Example:
package p1;
public class A {

}

e. Create 2 classes in same package and perform inheritance. Import is not required
Example:
package p1;
public class A {

}

package p1;
public class B extends A {

}

f. Create 2 classes in different package and perform inheritance. "Import required"

Example:
package p1;
public class A {

}

package p2;
import p1.A;
public class C extends A{

}
------------------------------------------------------
Example :
package p1;
public class A {

}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
----------------------------------------------------------
Example:
package p1;
public class A {

}

package p2;
public class C {

}

package p1;
import p2.C;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		C c1 = new C();
	}
}
---------------------------------------
Example:
package p1;
public class A {

}

package p1;
public class B {
	
}

package p2;
import p1.*;
public class C {
	public static void main(String[] args) {
		A a1 = new A();
		B b1 = new B();
	}
}

--------------------------------
Example:
package p1;
public class A {

}

package p2;
public class A {
	
}

package p3;
public class B {
	public static void main(String[] args) {
		p1.A a1 = new p1.A();//---> p2
		p2.A a2 = new p2.A();//---> p1
	}
}

---------------------------------------
Example:

package p1;
public class A {

}

package p2;
public class A {
	
}

package p3;
import p2.A;
public class B {
	public static void main(String[] args) {
		p1.A a1 = new p1.A();//---> p2
		A a2 = new A();//---> p1
	}
}
-------------------------------------------------

Example:

package com.tcs.service;
public class EmailService {
	//Logic To Send Email
	public void sendEmail() {
		System.out.println("Email Sending");
	}
}
EmailService.java
---------------------------------------------------
package com.tcs.auth;
import com.tcs.service.EmailService;
public class Auth {
	//Registration Logic
	
	public void register() {
		//Logic to register user
		EmailService emailService = new EmailService();
		emailService.sendEmail();
	}
	
	public static void main(String[] args) {
		Auth a = new Auth();
		a.register();
	}
}

#######################################
Object Oriented Programming -  Pillars
########################################

a. inheritance
b. polymorphism
c. encapsulation
d. abstraction

a. inheritance
######################
-> Here we inherit the members of parent class to child class so that we can re-use those members
Example 1:
---------
package app_java_1;
public class Animal {
	public void eat() {
		System.out.println("Eating");
	}
	public void sleep() {
		System.out.println("sleeping");
	}
}

package app_java_1;
public class Dog extends Animal{
	public static void main(String[] args) {
		Dog d = new Dog();
		d.eat();
		d.sleep();
	}
}
Output:
------
Eating
sleeping

Example 2:
package app_java_1;
public class Animal {
	public void eat() {
		System.out.println("Eating");
	}
	public void sleep() {
		System.out.println("sleeping");
	}
}
Animal.java

package app_java_1;
public class Dog extends Animal{
	//eat(),sleep()--->Animal
}
Dog.java

package app_java_1;
public class Cat extends Animal{
	//eat(),sleep()--->Animal
}
Cat.java

package app_java_1;
public class Cow extends Animal{
	//eat(),sleep()--->Animal
}
Cow.java

package app_java_1;
public class Root {
	public static void main(String[] args) {
		Dog d = new Dog();
		d.eat();
		d.sleep();
		System.out.println("_______");
		Cat cat = new Cat();
		cat.eat();
		cat.sleep();
		System.out.println("_______");
		Cow cow = new Cow();
		cow.eat();
		cow.sleep();
	}
}
Root.java

Example 3: Multilevel inheritance
-----------------------------------

package app_java_1;
public class A {
	public void test1() {
		System.out.println(1);
	}
}

package app_java_1;
//test1, test2
public class B extends A{
	public void test2() {
		System.out.println(2);
	}
}
package app_java_1;

public class C extends B{
	public static void main(String[] args) {
		C c1 = new C();
		c1.test1();
		c1.test2();
	}
}
output:
1
2
------------------------------------------------------------------------------

################################################################################################
What is mulitlpe inheritance?
Answer: When a child class has more than one parent class, it is called as mulitple inheritance
#################################################################################################

Note: Java classes does not support mulitple inheritance because of diamond problem
diamond problem: Suppose we inherit a method from A->B->D  and Same method is inherited from A->C->D, then confusion from which parent class method is inherited to child class D. This is called as DIAMOND PROBLEM. Hence in java classes does not support multiple inheritance.

Note: We can do mulitple inheritance on interface. But will explain this during interfaces concept

Example 4:Mulitple inheritance error
------------------------------------------
package app_java_1;
public class A {
	
}

package app_java_1;
public class B{
	
}
package app_java_1;
public class C extends A,B{//Error
	
}

Example 4: Inheritance between classes present inside different packages
----------------------------------------
package p1;
public class A {
	public void test() {
		System.out.println(1);
	}
}
package p2;
import p1.A;
public class B extends A{
	public static void main(String[] args) {
		B b1 = new B();
		b1.test();
	}
}

Example on non sub class: When in your project we have two class and no inheritance is happening between them then it is called as non-sub class
--------------------------------------------------------------------------------------------------------
package p1;
public class A {
	public void test() {
		System.out.println(1);
	}
}
package p2;
import p1.A;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		a1.test();
	}
}
------------------------------------------------------------
Output: 1

###############################
Access Specifiers in java
###############################
--------------------------------------------------------------------
Questions:
1. What happens when a variable is  private/default/protected/public
2. What happens when a constructor is  private/default/protected/public
3. What happens when a class is  private/default/protected/public
4. What happens when a interface is  private/default/protected/public
----------------------------------------------------------------------

-> They define the visibility of variables, methods, class & interface.

------------------------------------------------------------------------------
a. private: When a variable / method is made private then we can access that in same class but not outside class
----------------------------------------------------------------------------------
Example 1:
package p1;
public class A {
	private int x=10;
	private void test() {
		System.out.println(1);
	}
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
Output:
10
1

Example 2:
package p1;
public class A {
	private int x=10;
	private void test() {
		System.out.println(1);
	}
}
package p1;
public class B extends A{
	public static void main(String[] args) {
		B b1 = new B();
		System.out.println(b1.x);//Error
		b1.test();//Error
	}
}

Example 3:
package p1;
public class A {
	private int x=10;
	private void test() {
		System.out.println(1);
	}
	
}
package p1;

public class B {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);//Error
		a1.test();//Error
	}
}

Example 4:
package p1;
public class A {
	private int x=10;
	private void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C extends A {
	public static void main(String[] args) {
		C c1 = new C();
		System.out.println(c1.x);//-->Error
		c1.test();//-->Error
	}
}
Example 5:
package p1;
public class A {
	private int x=10;
	private void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C  {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);//-->Error
		a1.test();//-->Error
	}
}


------------------------------------------------------------------------
b. default: A variable/method with default access specifier can work only inside same class or same package, but cannot be accessed in different package

Example 1:
------------

package p1;
public class A {
	int x=10;
	void test() {
		System.out.println(1);
	}
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
	
}

Example 2:
---------------------------------------------
package p1;
public class A {
	int x=10;
	void test() {
		System.out.println(1);
	}
	
}
package p1;
public class B extends A{
	public static void main(String[] args) {
		B b1 = new B();
		System.out.println(b1.x);
		b1.test();
	}
}
Output:
10
1
-----------------------------------------------------------------------
Example 4:
------------
package p1;
public class A {
	int x=10;
	void test() {
		System.out.println(1);
	}
	
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
-----------------------------------------------------------------
Example 5:
------------------------
package p1;
public class A {
	int x=10;
	void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C  extends A{
	public static void main(String[] args) {
		C c1 = new C();
		System.out.println(c1.x);//-->Error
		c1.test();//-->Error
	}
}
--------------------------------------------------------
Example 6:
----------------
package p1;
public class A {
	int x=10;
	void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);//--->Error
		a1.test();//--->Error
	}
}
-------------------------------------------

c. protected: We can access variables/methods in same class/same package and inside different package only when inheritance is done

Example 1:
-------------
package p1;
public class A {
	protected int x=10;
	protected void test() {
		System.out.println(1);
	}
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
	
}
Ouput:
10
1

Example 2:
------------------
package p1;
public class A {
	protected int x=10;
	protected void test() {
		System.out.println(1);
	}
}
package p1;
public class B extends A{
	public static void main(String[] args) {
		B b1 = new B();
		System.out.println(b1.x);
		b1.test();
	}
}
Output:
10
1

Example 3:
----------
package p1;
public class A {
	protected int x=10;
	protected void test() {
		System.out.println(1);
	}
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
Ouput:
10
1

Example 4: 
-----------
package p1;
public class A {
	protected int x=10;
	protected void test() {
		System.out.println(1);
	}
}
package p2;
import p1.A;
public class C extends A{
	public static void main(String[] args) {
		C c1 = new C();
		System.out.println(c1.x);
		c1.test();
	}
}
Ouput:
10
1

Example 5:
--------------
package p1;
public class A {
	protected int x=10;
	protected void test() {
		System.out.println(1);
	}
}
package p2;
import p1.A;
public class C {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);//----> Error
		a1.test();//----> Error
	}
}
------------------------------------------------------

d. public: When we make variable/method public then we can access that in sam class/same package/different package

Example 1:
package p1;
public class A {
	public int x=10;
	public void test() {
		System.out.println(1);
	}
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
Ouput:
10
1

Example 2:
-----------
package p1;
public class A {
	public int x=10;
	public void test() {
		System.out.println(1);
	}
	
}
package p1;
public class B extends A{
	public static void main(String[] args) {
		B b1 = new B();
		System.out.println(b1.x);
		b1.test();
	}
}
Ouput:
10
1

Example 3:
-------------------------------------------

package p1;
public class A {
	public int x=10;
	public void test() {
		System.out.println(1);
	}
	
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
Output:
10
1

Example 4:
--------------
package p1;
public class A {
	public int x=10;
	public void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C extends A {
	public static void main(String[] args) {
		C c1 = new C();
		System.out.println(c1.x);
		c1.test();
	}
}
Output:
10
1

Example 5:
------------
package p1;
public class A {
	public int x=10;
	public void test() {
		System.out.println(1);
	}
	
}
package p2;
import p1.A;
public class C {
	public static void main(String[] args) {
		A a1 = new A();
		System.out.println(a1.x);
		a1.test();
	}
}
Output:
10
1

########################################################
Access Specifier on Constructors
#######################################################

Can we Inherit Constructor?
Answer: We cannot inherit constructor

a. private Constructor
----------------------------
-> If a constructor is made private then its object cannot be created outside the class

Example 1:
package p1;
public class A {
	private A() {
		
	}
	public static void main(String[] args) {
		A a1 = new A();
	}
	
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();//--->Error
	}
}
package p2;
import p1.A;
public class C {
	public static void main(String[] args) {
		A a1 = new A();//-->Error
	}
}

-> When a constructor is made private then inheritance of that class is not allowed
(Note: Construct re not inherit)

Example 2:
----------
package p1;
public class A {
	private A() {
		
	}
	
}
package p1;
public class B extends A{//-->Error
	
}
package p2;
import p1.A;
public class C extends A{//-->Error
	
}

b. default Constructor
-------------------------
-> If a constructor is made default then its object can be created in same class/same package but not outside the package

Example 1:
----------
package p1;
public class A {
	A() {
		
	}
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p2;
import p1.A;
public class C{
	public static void main(String[] args) {
		A a1 = new A();//-->Error
	}
}


-> When a constructor is made default then inheritance of that class is  allowed only in same package but not outside the package
(Note: Construct re not inherit)

Example 2:
----------
package p1;
public class A {
	A() {
		
	}
	
}
package p1;
public class B extends A {
	
}
package p2;
import p1.A;
public class C extends A{//-->Error
	
}

e. protected Constructor
--------------------------
-> If a constructor is made protected then its object can be created in same class/same package but not outside the package 

Example 1:
---------
package p1;
public class A {
	protected A() {
		
	}
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p1;
public class B  {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p2;
import p1.A;
public class C {
	public static void main(String[] args) {
		A a1 = new A();//-->Error
	}
}

-> When a constructor is made protected then inheritance of that class is  allowed in same package / outside the package (both)
(Note: Construct re not inherit)

Example 2:
----------
package p1;
public class A {
	protected A() {
		
	}
	
}
package p1;
public class B extends A {
	
}
package p2;
import p1.A;
public class C extends A {
	
}

e. public Constructor
------------------------
-> If a constructor is made public then its object can be created in same class/same package and outside the package also

Example 1:
---------
package p1;
public class A {
	public A() {
		
	}
	public static void main(String[] args) {
		 A a1 = new A();
	}
}
package p1;
public class B  {
	public static void main(String[] args) {
		 A a1 = new A();
	}
}
package p2;
import p1.A;
public class C  {
	public static void main(String[] args) {
		 A a1 = new A();
	}
}

-> When a constructor is made public then inheritance of that class is  allowed in same package / outside the package (both)
(Note: Construct re not inherit)

Example 2:
----------
package p1;
public class A {
	public A() {
		
	}
	
}
package p1;
public class B extends A {
	
}
package p2;
import p1.A;
public class C extends A {
	
}

########################################
Access Specifier on Class
########################################
-> A class can be only public / default
-> A class cannot be private / protected

What happens when a class is made default?
Answer:
->  It's object can be created in same class/same package but not inside different package
-> Inheritance is allowed in same package

Example 1:
package p1;
class A {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p1;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p2;
import p1.A;//--->Error
public class C {
	public static void main(String[] args) {
		A a1 = new A();//--->Error
	}
}

Example 2:
package p1;
class A {
	
}
package p1;
public class B extends A{
	
}
package p2;
import p1.A;//-->Error
public class C extends A{//-->Error
	
}

--------------------------------------------------------------]
What happens when a class is made public?
Answer:
->  It's object can be created in same class/same package & inside different package
-> Inheritance is allowed in same package & inside different package

Example 1:
----------
package p1;
public class A {
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p1;
public class B{
	public static void main(String[] args) {
		A a1 = new A();
	}
}
package p2;
import p1.A;
public class C{
	public static void main(String[] args) {
		A a1 = new A();
	}
}

Example 2:
-----------------

package p1;
public class A {
	
}
package p1;
public class B extends A{
	
}
package p2;
import p1.A;
public class C extends A{
	
}

Note: A class cannot be made private
---------------------------------------
Example :
package p1;
private class A {//-->Error
	
}

Note: A class cannot be made protected
---------------------------------------
Example :
package p1;
protected class A {//-->Error
	
}

###################################
Note: 
a. Compile Time: Here our java compiler converts .java files to .class files(byte code)
b. Run Time: Here we run .class file(byte code using Java Runtime Environment.


########################################
Polymorphism in java
#########################################

Here we develop a feature such that it can take more than one form depending on the situation
Note: Polymorphism is applicable only on methods and not variables

------------------------------------------------------------------------------------
Two types of polymorphism

a. Overriding (Run time polymorphism): 
-> Here we modify the logic of inherited method in child class
Example 1:
-----------
package p1;
public class GoldAccount {
	public void onlineBanking() {
		System.out.println("yes");
	}
	public void rateOfInterest() {
		System.out.println("nill");
	}
}
GoldAccount.java

package p1;
public class PlatinumAccount extends GoldAccount {
	public void rateOfInterest() {
		System.out.println("6% PA");
	}
	public static void main(String[] args) {
		PlatinumAccount p = new PlatinumAccount();
		p.onlineBanking();
		p.rateOfInterest();//-->6% PA
		System.out.println("--------");
		GoldAccount g = new GoldAccount();
		g.onlineBanking();
		g.rateOfInterest();//-->nill
	}
}
PlatinumAccount.java

Output:
yes
6% PA
--------
yes
nill

Example 2:
-> In version java 5 , A concept of annotations was introduced
-> Annotations can instruct compiler to perform a specific task
-> @AnnotationName
-> @Override: This annotation instructs compiler to check whether overriding is happening or not

	package p1;
	public class GoldAccount {
		
		public void rateOfInterest() {
			System.out.println("nill");
		}
	}
GoldAccount.java

package p1;
public class PlatinumAccount extends GoldAccount {
	@Override
	public void rateOfInterests() {//-->Error because method name mismatch
		System.out.println("6% PA");
	}
	
}
PlatinumAccount.java

Example 3:
---------
Question: Access Specifier should it be same or can be different during Overriding?
Answer: During Overriding we can increase the scope of access specifier but we cannot reduce the scope of access specifier

package p1;
public class GoldAccount {

	void rateOfInterest() {
		System.out.println("nill");
	}
}
GoldAccount.java

package p1;
public class PlatinumAccount extends GoldAccount {
//No Error Because default scope is increase to public	
	@Override
	public void rateOfInterest() {
		System.out.println("6% PA");
	}

}
PlatinumAccount.java

-------------------------------------------------------------------

Example 4:
----------
package p1;
public class GoldAccount {

	public void rateOfInterest() {
		System.out.println("nill");
	}
}

package p1;
public class PlatinumAccount extends GoldAccount {
//Error Because public scope is reduced to 	default
	@Override
	void rateOfInterest() {
		System.out.println("6% PA");
	}

}

Example 5:
-----------
package p1;
public class GoldAccount {

	void rateOfInterest() {
		System.out.println("nill");
	}
}

package p1;
public class PlatinumAccount extends GoldAccount {
//No Error Because default scope is increased to protected
	@Override
	protected void rateOfInterest() {
		System.out.println("6% PA");
	}
}

Example 6:
-----------
package p1;
public class GoldAccount {

	private void rateOfInterest() {
		System.out.println("nill");
	}
}

package p1;
public class PlatinumAccount extends GoldAccount {
//Error Because private methods we cannot inherit
//Without inheritance Overriding cannot be done
	
	@Override
	protected void rateOfInterest() {
		System.out.println("6% PA");
	}

}

####################################
Note: 
-> Static members cannot be inherited
Example :
package p1;
public class GoldAccount {
	static int x = 100;
	public static void rateOfInterest() {
		System.out.println("nill");
	}
}
package p1;

public class PlatinumAccount extends GoldAccount {
	
	public static void main(String[] args) {
		PlatinumAccount.rateOfInterest();
		System.out.println(PlatinumAccount.x);
		//GoldAccount.rateOfInterest();
		//GoldAccount.x
	}

}
//PlatinumAccount.rateOfInterest()---->Converted to ------>GoldAccount.rateOfInterest();
//PlatinumAccount.x--->Converted---->GoldAccount.x
//Hence we are geeting output

################################################
Question : Can we Override static methods?
-> We cannot override static methods, as we cannot inherit static methods
########################################

Example 1:
package p1;
public class GoldAccount {
	
	public static void test() {
		System.out.println(100);
	}
}
package p1;

public class PlatinumAccount extends GoldAccount {
	
	@Override
	public static void test() {//--->Error, cannot override static methods
		System.out.println(100);
	}

}

Example 2: During Overriding method return type should match
package p1;
public class GoldAccount {
	
	public int test() {
		return 100;
	}
}
package p1;

public class PlatinumAccount extends GoldAccount {
	
	@Override
	public void test() {//-> Error because method return type is not matching 
		System.out.println(100);
	}

}


b. Overloading (Compile time polymorphism)
-> Here we develop more than one method with same name in same class provided they have different number of arguments or different type of arguments

Example:
-> I want to send email with attachment & Also an email to be sent without attachment
-> Email feature is taking more than one form

package p1;

public class EmailService {
	public void sendEmail(String to, String subject, String message) {
		System.out.println("Email sending....");
	}
	public void sendEmail(String to, String subject, String message, String filePath) {
		System.out.println("Email sending with attachment.....");
	}
	public static void main(String[] args) {
		EmailService service = new EmailService();
		service.sendEmail("mike@gmail.com", "Welcome", "Some Message","G:\\image.png");
	}
}

################################
Final Keyword
################################
-> If you make a variable final then we cannot change it's value(Just like constant variables)
-> If you make static/non-static variable final then initialization is mandatory
-> If you make a method final then overriding is not allowed
-> If you make a class final then inheritance is not allowed

Example 1: 
----------
package p1;

public class A {
	public static void main(String[] args) {
		final int x = 10;
		x=20;//-->Cannot change the value of final variable
		System.out.println(x);
	}
}

Example 2:
----------
package p1;

public class A {
	final int x;//->final mandatory to be initialized
	final static int y;//->final mandatory to be initialized
	//These above erros are called as blank field errors
	public static void main(String[] args) {
		
	}
}

Example 3:
----------
package p1;

public class A {
	final public void test() {
		System.out.println(100);
	}
}
package p1;

public class B extends A{
	@Override
	public void test() {//--> Error because we cannot override final methods
		System.out.println(100);
	}
}

Example 4:
----------
package p1;

final public class A {
	
}
package p1;

public class B extends A{//---> Error because we cannot inherit final class
	
}

#####################################
interfaces in java - abstraction
#######################################
-> An interface can consist of only incomplete methods/abstract methods in it ( Java Version 7)
-> All Variables in an interface by default are final & static
-> Interfaces defines what needs to be developed and not how it is to be developed
-> Interfaces are like contract that a class follows, and the class has to implements these methods
-> An Object of interface cannot be created. Because objects cannot have incomplete methods in it
-> loosely coupled
-> It forces all the implementation classes to have same method same resulting in good design

Example 1:
---------
package p1;

public interface A {

	public void test1() {//-->Error because complete methods are not allowed in an interface
		
	}
}

Example 2:
-----------
package p1;

public interface A {
	public void test1() ;
}

Example 3:
----------
package p1;

public interface NotificationService {

	//What needs to be implemented
	public void emailService();
	public void whatsAppService();
	public void smsService();
}

package p1;

public class NotificationServiceImpl 
implements NotificationService
{
	//How it will be implemented
	@Override
	public void emailService() {
		System.out.println("Email Sending");
	}
	@Override
	public void whatsAppService() {
		System.out.println("Whats app Sending");
	}
	@Override
	public void smsService() {
		System.out.println("SMS Sending");
	}
	public static void main(String[] args) {
		NotificationServiceImpl impl = new NotificationServiceImpl();
		impl.emailService();
		impl.smsService();
		impl.whatsAppService();
	}
}

Example 4:
----------
package p1;

public interface PropertyService {

	public void addProperty();
	public void updateProperty();
	public void deleteProperty();
	public void searchProperty();
}
package p1;

public class PropertyServiceImpl 
implements PropertyService
{
	@Override
	public void addProperty() {
		System.out.println("Added Property");
	}
	@Override
	public void updateProperty() {
		System.out.println("Updated Property");
	}
	@Override
	public void deleteProperty() {
		System.out.println("Deleted Property");
	}
	@Override
	public void searchProperty() {
		System.out.println("Search Property");
	}
	public static void main(String[] args) {
		PropertyServiceImpl service = new PropertyServiceImpl();
		service.addProperty();
		service.updateProperty();
		service.deleteProperty();
		service.searchProperty();
	}
	
}

#############################
Note: Drawback of inheritance
#############################
-> Inheritance results in tightly couple programming.

Example 5:
----------
package p1;

public interface Calculator {
	public void add(int x, int y);
	public void mul(int x, int y);
}

package p1;
public class OrdinaryCalc implements Calculator{

	@Override
	public void add(int x, int y) {
		System.out.println(x+y);
	}
	
	@Override
	public void mul(int x, int y) {
		System.out.println(x*y);
	}

}

package p1;

public class SciCalc implements Calculator{

	@Override
	public void add(int x, int y) {
		System.out.println(x*x+y*y);
	}
	
	@Override
	public void mul(int x, int y) {
		int num1 = x*x;
		int num2 = y*y;
		System.out.println(num1*num2);
	}

}
package p1;

public class MainCalc {
	public static void main(String[] args) {
		OrdinaryCalc oc = new OrdinaryCalc();
		oc.add(10, 20);
		oc.mul(10, 20);
		
		SciCalc sc = new SciCalc();
		sc.add(10, 20);
		sc.mul(10, 20);
		
		
	}
}


Advantages of interfaces
---------------------------


1. abstraction: hiding of implementation details. That is we define what needs to be developed and not how it needs to be developed
2. It imposes contract on a class to implement all methods of an interface
3. Results in good design
4. loosely coupled

-> All Variables by default in an interface are final and static
----------------------------------------------------------------
package p1;

//-> All variables in the given program are final & static
//-> Hence intialization is mandatory
public interface A {
	int MAX_VAL=100;
	static final int MIN_VAL=0;
}
package p1;

public class B {
	public static void main(String[] args) {
		System.out.println(A.MAX_VAL);
		System.out.println(A.MIN_VAL);
	}
}
Output:
100
0
#################################################
Note:
-> Class to Class Inheritance --> extends
-> interface to interface Inheritance --> extends
-> interface to class Inheritance --> implements
#################################################

Example 1:
---------
package p1;

public interface A {
	public void test1();
}
package p1;

public interface B extends A{
	public void test2();
}
package p1;

public class C implements B {

	@Override
	public void test1() {
		System.out.println("From test1");
	}

	@Override
	public void test2() {
		System.out.println("From test2");
	}
	public static void main(String[] args) {
		C c1 = new C();
		c1.test1();
		c1.test2();
	}

}

Example 2:
-----------
package p1;

public interface A {
	public void test2();
}
package p1;

public interface B {
	public void test1();
}
package p1;

public interface C extends  A,B {

	
}

Example 3:
----------
-> If you do mulitple inheritance on a class then it's parent should be interfaces only

package p1;
public interface A {
	public void test2();
}

package p1;
public interface B {
	public void test1();
}

package p1;
public class C implements  A,B {

	@Override
	public void test1() {
		System.out.println("From test1");
	}

	@Override
	public void test2() {
		System.out.println("From test2");		
	}
	public static void main(String[] args) {
		C c1 = new C();
		c1.test1();
		c1.test2();
	}
	
}

Example 4:
----------
-> On class can we perform extends implements together
-> But ensure extends is used first and then implements

package p1;
public interface A {
	public void test2();
}

package p1;
public class B {
	public void test1() {
		System.out.println("From test1");
	}
}

package p1;
public class C extends B  implements  A {
	@Override
	public void test2() {
		System.out.println("From test2");		
	}
	public static void main(String[] args) {
		C c1 = new C();
		c1.test1();
		c1.test2();
	}
}

###############################################################
Question: Can i develop incomplete static method in an interface?
Answer: We cannot inherit static method & override, hence incomplete static methods are not allowed in an interface

Example:
package p1;
public interface A {
	public static void test2();//-------> Error
}

###############################################################

Java 8 Features
###################
1. default keyword:
-> Using default keyword we can create complete methods inside interface. This was introduced in java version 8

Example 1:
--------
package p1;
public interface A {
	default public void test1() {
		System.out.println("From test1");
	}
}

package p1;
public class B implements A {
	public static void main(String[] args) {
		B b1 = new B();
		b1.test1();
	}		
}
Output:
From test1

Example 2:
----------
package p1;
public interface A {
	default public void test1() {
		System.out.println("From test1");
	}
	public void test2();
}

package p1;
public class B implements A {
	public static void main(String[] args) {
		B b1 = new B();
		b1.test1();
		b1.test2();
	}
	@Override
	public void test2() {
		System.out.println("From test2");
	}		
}
Output:
-------
From test1
From test2

Note: 

2. Functional Interface:
---------------------------
-> A functional interface should consist of exactly one incomplete method inside it
-> Inside functional interface we can develop any number of complete methods using default keyword
-> During inheritance/multiple inheritance if more than one method is inherited to Functional Interface then you will get error. As shown in below examples 

Example 1:
--------------------
@FunctionalInterface
public interface A {//Error-> Because cannot have ZERO incomplete method
}

Example 2:
----------
@FunctionalInterface
public interface A {
	public void test1();
}

Output: 
No Error because it has exactly one incomplete method

Example 3:
----------
@FunctionalInterface
public interface A {//Error->A functional interface should consist of exactly one //incomplete method inside it
	public void test1();
	public void test2();
}

Example 4:
----------
package p1;
@FunctionalInterface
public interface A {
	public void test1();
	default public void test2() {
		System.out.println("From Test 2");
	}
	default public void test3() {
		System.out.println("From Test 3");
	}
	default public void test4() {
		System.out.println("From Test 4");
	}
}
package p1;
public class B implements A {
	public static void main(String[] args) {
		B b1 = new B();
		b1.test1();
		b1.test2();
		b1.test3();
		b1.test4();
	}

	@Override
	public void test1() {
		System.out.println("From test 1");
	}
		
}
Output:
---------
From test 1
From Test 2
From Test 3
From Test 4

Example 5:
-----------
package p1;
public interface A {
	public void test1();
}
package p1;
@FunctionalInterface
public interface B extends A{
	
}
Output: No Error

Example 2:
----------
package p1;
public interface A {
	public void test1();
	public void test2();
}
package p1;
@FunctionalInterface
public interface B extends A{
	
}
Output: Error because we are inheriting 2 method to functional interface

Example 6:
---------
package p1;
public interface A {
	public void test1();
	
}

package p1;
@FunctionalInterface
public interface B extends A{
	public void test2();
}
Output: Output: Error because we are inheriting 1 method to functional interface  and functional interface has a method which totals to 2 methods in an interface

3. lambdas expression - 
-------------------------
-> It was introduced in java 8
-> Reduces number of lines of code
-> Works with functional interfaces
-> We can use lambdas expression in stream API

How Lambdas Expression Works?

Note: Fuctional Programming defines you say "what you want, not how to do it step-by-step"

-> Its creates Annonymous class behind the scene. A class without any name is called Annonymous .
-> Then lambdas expression creates an object and load the method by implementing inside object.
-> Then we use object reference to call that implemented method

Example 1:
------------
package p1;
@FunctionalInterface
public interface A {
	public void test1();
	
}
package p1;
public class B{

	public static void main(String[] args) {
		A a1 = ()->{
			System.out.println(100);
		};
		a1.test1();
	}
}

Example 2:
-----------
package p1;
@FunctionalInterface
public interface A {
	public void test1(int x);
	
}
package p1;
public class B{
	public static void main(String[] args) {
		A a1 = (int x)->{
			System.out.println(x);
		};
		a1.test1(100);
	}
}

Example 3:
----------
package p1;
@FunctionalInterface
public interface A {
	public void test1(int x);
	default public void test2() {
		System.out.println(2);
	}
	default public void test3() {
		System.out.println(3);
	}
}
package p1;
public class B{

	public static void main(String[] args) {
		A a1 = (int y) -> {
			System.out.println(y);
		};
		a1.test1(100);
		a1.test2();
		a1.test3();
	}
}

4. stream API
---------------------
Note: to learn Stream API Complete the following first
a. Collection (Data Structure)
b. Functional Programming

5. Optional class - We have to learn exception concept in java first
--------------------------------------------
Note:
What are marker interfaces in java?
-> Empty interfaces in java are called as marker interface

Example: For marker interface
package p1;
public interface A {
	
}

---------------------------------------------------
Abstract class in java
----------------------------
-> We can create both complete / incomplete non static methods
-> To define incomplete method, it mandatory to use abstract keyword
-> In an abstract class we can create both static / non static members
-> We cannot create static incomplete methods here but we can create complete static methods
-> We can create main method inside abstract class
-> We cannot create object of abstract class because abstract class can consist of incomplete methods
-> We cannot perform multiple inheritance

Example 1:
----------
package p1;
abstract public class A {
	public void test1() {
		
	}
	abstract public void test2();
	public static void test3() {
		
	}
	public static void test4();//Error
	public static void main(String[] args) {
		A a1 = new A();//Error
	}
}

Example 2: Error because multiple inheritance cannot be done
-------------------------------------------------------------
package p1;
abstract public class A {
	
}
package p1;
abstract public class B{

	
}
package p1;
public abstract class C extends A,B{//Error

}

Difference between interface & abstract class
-------------------------------------------------
a. interface supports mulitple inheritance but abstract class does not support multiple inheritance
b. All variables in an interface by default are final & static whereas inside abstract class we can create static/non static/final variables

Example:
-------
package p1;
abstract public class A {
	static int x = 10;
	public static void test() {
		System.out.println(100);
	}
	public static void main(String[] args) {
		System.out.println(A.x);
		A.test();
	}
}
Output:
10
100

Example :
---------
package p1;
abstract public class A {
	int x = 10;
	public void test() {
		System.out.println(100);
	}
}
package p1;
public class B extends A {
	public static void main(String[] args) {
		B b1 = new B();
		System.out.println(b1.x);
		b1.test();
	}

}
Output:
10
100

Example:inheritance from interface-->abstract class-->class
----------------------------------------------------------------
package p1;
public interface A {
	public void test1();
}
package p1;
abstract public class B implements A {
	abstract public void test2();
}
package p1;
public class C extends B{
	@Override
	public void test1() {
		System.out.println("From test1");
	}
	@Override
	public void test2() {
		System.out.println("From test2");
	}
	public static void main(String[] args) {
		C c1 = new C();
		c1.test1();
		c1.test2();
	}

}
#############################################################################
Note:In java 8 we can develop complete static methods & main method in an interface
#################################################################################

Example:
package p1;
public interface A {
	static int x = 100;
	public static void test1() {
		System.out.println("From test1");
	}
	public static void main(String[] args) {
		System.out.println(A.x);
		A.test1();
	}
}
Output:
100
From test1

Exception and Exception Handling In Java
-------------------------------
-> Unexpected events are called exceptions.
-> Exceptions will hault your program execution.
-> Exceptions will Occur when bad user input is given

Example 1:
package p1;

public class A {
	public static void main(String[] args) {
		int x = 10;
		int y = 0;
		int z = x / y;//Stop Program Here
		System.out.println(z);
		System.out.println("Welcome");
	}
}
Output:
Exception in thread "main" java.lang.ArithmeticException: / by zero
	at app_java_1/p1.A.main(A.java:7)

#######################
Exception handling
#######################
-> To handle exception we will use "try & catch" block in java
-> When exception occurs in try block, it will create exception object and that object's address is given to catch block. Catch block will suppress that exception and further code will continue to execute

Example :
----------
package p1;
public class A {
	public static void main(String[] args) {
		try {
			int x = 10;
			int y = 0;
			int z = x/y;
			System.out.println(z);
		} catch (Exception e) {
			e.printStackTrace();
		}
		System.out.println("Welcome");
	}
}

Types of Exception in java
##########################

There are two types of exception in java

a. Compiletime / Checked Exception - These Exception will occur when .java file is compiled to .class file. That is during compilation we will get this exception

b. Runtime / Unchecked Exception - These Exception will occur when we run .class file. That is during runtime

###############################
Runtime / unchecked Exceptions
###############################

1. ArithmeticException: This exception will occur when invalid mathematical operations are performed

package p1;
public class A {
	public static void main(String[] args) {
		try {
			int x = 10;
			int y = 0;
			int z = x/y;
			System.out.println(z);
		} catch (ArithmeticException a) {
			a.printStackTrace();
		}
		System.out.println("Welcome");
	}
}
Output:
java.lang.ArithmeticException: / by zero
	at app_java_1/p1.A.main(A.java:7)
Welcome

Example 2: %ZERO
----------
package p1;
public class A {
	public static void main(String[] args) {
		try {
			int x = 11;
			int y = 0;
			int z = x%y;
			System.out.println(z);
		} catch (ArithmeticException a) {
			a.printStackTrace();
		}
		System.out.println("Welcome");
	}
}

Output:
-------
java.lang.ArithmeticException: / by zero
	at app_java_1/p1.A.main(A.java:7)
Welcome

2. Null PointerException: This exception will occur when with null reference variable we try to access non static members of the class
Example:
--------
package p1;
public class A {
	int x = 10;
	public static void main(String[] args) {
		try {
			A a1 = null;
			System.out.println(a1.x);
		} catch (NullPointerException e) {
			e.printStackTrace();
		}
		System.out.println("Welcome");
	}
}
Output:
java.lang.NullPointerException: Cannot read field "x" because "a1" is null
	at app_java_1/p1.A.main(A.java:7)
Welcome

Example 
----------
package p1;
public class A {
	static int x = 10;
	public static void main(String[] args) {
		try {
			A a1 = null;
			System.out.println(a1.x);//A.x
		} catch (NullPointerException e) {
			e.printStackTrace();
		}
		System.out.println("Welcome");
	}
}
Output:
10
Welcome


Note:

Primitive    Wrapper Class
byte		Byte
short		Short
int		Integer
long		Long
float		Float
double		Double
char		Character

Example 1: I want to convert String to Integer

public class A {
	public static void main(String[] args) {
		String x = "100";
		int  y = Integer.parseInt(x);
		System.out.println(y);
	}
}

Example 2:I want to convert String to Float

public class A {
	public static void main(String[] args) {
		String x = "10.3";
		float  y = Float.parseFloat(x);
		System.out.println(y);
	}
}

Example 3:I want to convert String to Double

public class A {
	public static void main(String[] args) {
		String x = "10.3";
		double  y = Double.parseDouble(x);
		System.out.println(y);
		
	}
}

Example 4:
-----------
package p1;

public class A {
	public static void main(String[] args) {
		try {
			String x = "10.3dasdsd";
			double  y = Double.parseDouble(x);
			System.out.println(y);
		} catch (NumberFormatException e) {
			e.printStackTrace();
		}
		System.out.println("Welcome");
		
	}
}
Output:
java.lang.NumberFormatException: For input string: "10.3dasdsd"
	at java.base/jdk.internal.math.FloatingDecimal.readJavaFormatString(FloatingDecimal.java:2054)
	at java.base/jdk.internal.math.FloatingDecimal.parseDouble(FloatingDecimal.java:110)
	at java.base/java.lang.Double.parseDouble(Double.java:792)
	at app_java_1/p1.A.main(A.java:7)
Welcome

######################
What is class upcasting?
########################
-> Here we store child class object address into parent class reference variable, so that reference variable becomes re-usable

Example: Reusing reference variable

public class A {
	
}

public class B extends A{

}

public class C extends A{
	public static void main(String[] args) {
		A a1 = new B();
		System.out.println(a1);
		a1 = new C();
		System.out.println(a1);
	}
}

Example 2: How we can implement polymorphism for multiple child classes by using same reference variable

public class A {
	void display() {
        System.out.println("Inside class A");
    }
}

public class B extends A{
	 @Override
	    void display() {
	        System.out.println("Inside class B");
	    }
}

public class C extends A{
	  @Override
	    void display() {
	        System.out.println("Inside class C");
	    }
	public static void main(String[] args) {
				
		A a1 = new B();
		a1.display();    // Calls B's version => "Inside class B"
		a1 = new C();
		a1.display();    // Calls C's version => "Inside class C"
	}
}

Note:

🧠 Why do we do it?
1. To reuse the parent class reference for multiple child class objects.
2. To enable polymorphism on mulitple child classes.
3. To write generic, flexible code that works with different subclasses.

Note:
instanceof - It will check which class object address is present inside the reference variable

Example:

public class A {
	
}

public class B extends A{
	
}

public class C extends A{
	 
	public static void main(String[] args) {
				
	  A a1 = new B();
	  System.out.println(a1 instanceof B);
	}
}

Output:
true

What is class downcasting?
##########################
-> Here we store parent class object address into child class reference variable
-> To perform downcasting, firstly do upcasting and then perform downcasting
Example:
---------
public class A {
	
}
public class B extends A{
	
}
public class C extends A{
	 
	public static void main(String[] args) {
		
		A a1 = new B();
		if(a1 instanceof B) {
			B b1 = (B)a1;
			System.out.println("Downcasting successful!");
		}
	}
}

Example:
--------
public class A {
	public void display() {
		System.out.println("Inside class A");
	}
}
public class B extends A{
	public void showB() {
        System.out.println("Inside class B");
        }
}
public class C extends A {
	public void showC() {
		System.out.println("Inside class C");
	}
}
public class MainClass {
	public static void processObject(A obj) {
        if (obj instanceof B) {
            B b = (B) obj;  // Downcasting to B
            b.showB();
        } else if (obj instanceof C) {
            C c = (C) obj;  // Downcasting to C
            c.showC();
        } else {
            obj.display();
        }
    }
    public static void main(String[] args) {
    	processObject(new B());
	}
}

Note:
-Using upcasting we can access only parent class members, you cannot access child class members
-After upcating to access child class members we have to perform downcasting

Example:
---------
package p1;

public class A {
	public void display() {
		System.out.println("Inside class A");
	}
}
public class B extends A{
	public void showB() {
       	 System.out.println("Inside class B");
        }
	public static void main(String[] args) {
		A a1 = new B();
		if(a1 instanceof B) {
			B b1 = (B)a1;
			b1.showB();
		}
		
	}
}


Arrays in java:
###############
-> In java arrays holds collection of value
-> Anything that holds colection of values is called as a data struture
-> Array in java is treated as an object
-> Arrays starts with index zero
-> To store and read values we use this formula in arrays - start_address + index*memory_size
-> Memory allocation happens to be in sequence(Continuous).

Example 1:
----------
package p1;
public class A {
	public static void main(String[] args) {
		int[] age = new int[4];
		age[0] = 90;
		age[1] = 89;
		age[2] = 67;
		age[3] = 97;
	
		System.out.println(age[0]);
		System.out.println(age[1]);
		System.out.println(age[2]);
		System.out.println(age[3]);
	} 
	
}

-> To find size of an array dynamically we will use  public final field "length". When array is created this variable will get initiliazed
Example : age.length


Example 2:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int[] age = new int[40];
		System.out.println(age.length);
	} 
	
}
Ouput: 40

##########################
Unary Operators in java
##############################

Types:
1. Increment Operator
   1.1 Post Increment
   1.2 Pre Increment

2. Decrement Operator
   2.1 Post Decrement
   2.2 Pre Decrement

1.1 Post Increment -  Increment the value of the variable next time you see the same variable

Example 1:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=0;
		int j = i++;
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Output:
1
0

Example 2:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
		int j = i++ + i++ + i++;
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Ouput:
13
33

Example 3:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = i++ + i++ + i++ + i++ + i++;
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Ouput:
15
60

 1.2 Pre Increment - Increment the value of variable in same step

Example 1:
-----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = ++i;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Ouput:
11
11

Example 2:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = ++i + ++i + ++i;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Ouput:
13
36

Example 3:
---------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = ++i + i++ + ++i + i++ + ++i;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Output:
15
63

 2.1 Post Decrement - Here we decrement the value of i by 1 when we next time see the same variable:

Example 1:
---------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = i-- + i--;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Output:
------
8
19

Example 2:
-----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = i-- + i++ + i-- + i--;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}
Output:
8
38

 2.2 Pre Decrement -  Here we decrement the value of the variable in same step by 1

Example 1:
----------
package p1;

public class A {
	public static void main(String[] args) {
		int i=10;
				
		int j = --i + --i;
		
		System.out.println(i);
		System.out.println(j);
	} 
	
}

#################
Scanner class - Is used to provide user input
################

Example 1:
----------
package p1;
import java.util.Scanner;
public class A {
	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		System.out.println("Enter your name:");
		String name = scan.next();//Can read one String word only
		System.out.println("Your name is "+name);
		System.out.println("Enter your age:");
		int age = scan.nextInt();//Can read on Integer value only
		System.out.println("Your age is "+age);
		System.out.println("Enter your weight:");
		float weight = scan.nextFloat();//Can read on float values
		System.out.println("Your weight is "+weight);
		System.out.println("Enter your Answer:");
		boolean ans = scan.nextBoolean();//Can read on float values
		System.out.println("Your ans is "+ans);
		scan.close();
		
	} 
	
}
Output:
Enter your name:
mike
Your name is mike
Enter your age:
100
Your age is 100
Enter your weight:
98.34
Your weight is 98.34
Enter your Answer:
true
Your ans is true

Example 2: How to read multiple String words using nextLine() method
--------------------------------------------------------------------------
package p1;
import java.util.Scanner;
public class A {
	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		System.out.println("Enter your name:");
		String name = scan.nextLine();//Can read Multiple String words
		System.out.println(name);
		scan.close();
	} 
	
}

##############
Loops in java
##############
1. for loop
Example 1;
---------
public class A {
	public static void main(String[] args) {
		
		for (int i = 0; i < 4; i++) {//0 to 3
			System.out.println(i);
		}
	} 
	
}
Example 2:
a. User will enter the pin number 1234
b. If the entered pin number is valid , then program should print welcome and stop
c. If pin number is invalid, user can attempt to enter pin maximum 3 times.
d. If All 3 times pin number is invalid then card blocked message we should get

Code:
package p1;
import java.util.Scanner;
//break
//1. Can be used only inside loops and switch case statements
//2. It stops the for loop execution
public class A {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		
		for(int i=0;i<3;i++) {//0 to 2
			System.out.println("Enter the pin number");
			int pinNumber = scan.nextInt();
			if(pinNumber==1234) {
				System.out.println("Welcome");
				break;
			}else {
				System.out.println("Invalid Pin number");
				if(i==2) {
					System.out.println("Card is blocked");
				}
			}
		}
		scan.close();
	} 
	
}




2. while loop
Example 1:
----------
package p1;
public class A {
	public static void main(String[] args) {
		int i=0;
		while(i<3) {//If condition true will enter while loop
			System.out.println(i);
			i++;
		}
	}
	
}

Example 2:
--------
a. Enter the amount, and we should get message please collect cash
b. Then prompt a message do you want to continue(yes or no)
c. If yes again enter the amount and we should get message please collect cash
d. If enter no program should stop

Code:
import java.util.Scanner;

public class A {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		String i="yes";
		while(i.equals("yes")) {//If condition true will enter while loop
			System.out.println("Enter the amount");
			int amount = scan.nextInt();
			System.out.println("Please collect the cash: rs. "+amount);
			System.out.println("Do you want to continue(yes/no)?");
			i = scan.next();
			
			if(i.equals("no")) {
				System.out.println("Thank you. Visit again");
			}
		}
	}
	
}

3. do while loop -  Will run first time without condition check. For second iteration condition will be evaluated

Example 1:
---------
package p1;
public class A {
	public static void main(String[] args) {
		int i=100;
		do {
			System.out.println(i);
			i++;
		}while(i<3);
	}
	
}
Example 2:
----------
package p1;
public class A {
	public static void main(String[] args) {
		int i=0;
		do {
			System.out.println(i);
			i++;
		}while(i<3);
	}
	
}


4. for each loop - 
-> Works only with data structure
-> Can only read value of data structure one by one
-> Loop will run until all values reading is not completed in the given data structure

Example:
package p1;
public class A {
	public static void main(String[] args) {
		int[] age = new int[3];
		age[0] = 100;
		age[1] = 101;
		age[2] = 120;
		
		for(int x:age) {
			System.out.println(x);
		}
	}
	
}

####################
Continuation of Arrays:
######################

Example 1:
----------
package p1;
public class A {
	public static void main(String[] args) {
		int[] age = new int[3];
		age[0] = 100;
		age[1] = 101;
		age[2] = 120;
		
		for (int i = 0; i < age.length; i++) {//0 to 2
			System.out.println(age[i]);
		}
	}
	
}

#####################################
ArrayIndexOutOfBoundsException
#####################################

-> When we exceed array size we get this exception

Example:
------
package p1;
public class A {
	public static void main(String[] args) {
		try {
			int[] age = new int[3];
			age[0] = 100;
			age[1] = 101;
			age[2] = 120;
			age[3] = 103;
		} catch (Exception e) {
			e.printStackTrace();
		}
		System.out.println("Welcome");
		
	}
	
}
Output:
java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 3
	at app_java_1/p1.A.main(A.java:9)
Welcome

####################
Continue Keyword in java
#####################

The continue keyword is used inside loops (for, while, or do-while) to skip the current iteration and jump to the next one.

package p1;
public class A {
	public static void main(String[] args) {
		for (int i = 0; i < 5; i++) {
			
			if(i==3) {
				continue;
			}
			System.out.println(i);//0 1 2 4
		}
		
	}
	
}
Output:
0
1
2
4


######################
else-if ladder statement
######################
-> If the user enters yes, it should print pass
-> If the user enters no, it should print fail
-> If the user enters something else, it should print invalid input

Example:
-------------
package p1;

import java.util.Scanner;

public class A {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		System.out.println("Enter the input(yes/no)");
		String value = scan.next();
		if(value.equals("yes")) {
			System.out.println("Pass");
		} else if(value.equals("no")) {
			System.out.println("Fail");
		} else {
			System.out.println("Invalid Input");
		}
	}
	
}

############################
Swicth Case
############################

package p1;

import java.util.Scanner;

public class A {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		System.out.println("Enter the floor number");
		int key=scan.nextInt();
		switch (key) {
		case 1:
			System.out.println("1st Floor");
			break;
		case 2:
			System.out.println("2nd Floor");
			break;
		case 3:
			System.out.println("3rd Floor");
			break;
		default:
			System.out.println("Invalid input");
			break;
		}
	}
	
}


###########################################
Removing Duplicate elements from an array
###########################################
-> For the below logic array should be sorted

Steps
------
1. Create a temp array which same size as that of x
int[] x = {3,3,4,5,6,6,7};
int[] temp = new int[x.length];

2. Compare i with i+1 of array x, if not equal copy the value from x[i] to temp[j] and increment j by 1

3. When you reach last index of array x, copy that value directly to temp[j];

Code:
package p1;
public class A {
	public static void main(String[] args) {
		int[] x = {3,3,4,5,6,6};
		int[] temp = new int[x.length];
		int j=0;
		for(int i=0;i<x.length-1;i++) {//i=5
			if(x[i]!=x[i+1]) {//with index 5 to 6
				temp[j] = x[i];
				j++;
			}
		}
		temp[j] = x[x.length-1];
		
		for(int arr:temp) {
			System.out.println(arr);
		}
	}
	
}

##########################
Logic For Swapping
##########################
package p1;
public class A {
	public static void main(String[] args) {
		int x = 10;
		int y = 20;
		int temp;
		
		temp=y;
		y=x;
		x=temp;
		
		System.out.println(x);
		System.out.println(y);
	}
	
}

######################################
Array Sorting
###################################

-> Compare x[i] > x[i+1], if true swap the element
-> End of first round of comparision heavy element will go to the botton of the array
-> Compare x[i] > x[i+1], array length-1 times maximum

Code:
----
package p1;
public class A {
	public static void main(String[] args) {
		int[] x = {35,21,22,14};
		//x[i]->x
		//x[i+1]-> y
		int temp;
		for(int j=0;j<x.length-1;j++) {//j=0, 1, 2
			for(int i=0;i<x.length-1;i++) {//i=0 1 2 , 0 1 2, 0 1 2
				if(x[i]>x[i+1]) {
					temp = x[i+1];
					x[i+1] = x[i];
					x[i]= temp;
				}
			}
		}
		
		for(int arr:x) {
			System.out.println(arr);
		}
	}
	
}

#################
1. Sort and remove duplicate elements
2. Get Highest & Lowest Value in an array
#################

######################
File Handling in Java
#######################

a. File
-----------
Note: Special Characters
               System.out.print(200);
		System.out.print("\n");
		System.out.print(300);
		System.out.print("\n");
		System.out.print(200);
		System.out.print("\t");
		System.out.print(300);
Example 1:It holds the given path in variable "f" without check the file exist
----------------------------------------------------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
		File f = new File("E:\\april\\t1.txt");
		System.out.println(f);
	}
}

1. exists() - 
------------
a. It is a non static method present inside File class
b. Return type of this method is boolean
c. It checks whether the file exists in the given path.
d. If file exists, it will return true or else false

Example:
---------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
		File f = new File("G:\\april\\t100.txt");
		boolean val = f.exists();
		System.out.println(val);
	}
}

2. delete() - 
------------
a. It is a non static method present inside File class
b. Return type of this method is boolean
c. It deletes the file exists in the given path.
d. If file is deleted, it will return true or else false

Example:
--------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
		File f = new File("G:\\april\\t1.txt");
		boolean val = f.delete();
		System.out.println(val);
	}
}

3.mkdir() - 
------------
a. It is a non static method present inside File class
b. Return type of this method is boolean
c. It creates folder  in the given path.
d. If folder is created, it will return true or else false
e. It will not replace existing folder

Example:
-------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
		File f = new File("G:\\april\\p2");
		boolean val = f.mkdir();
		System.out.println(val);
	}
}

Example: To delete Folder using delete() method
------------------------------------------------
public class A {
	public static void main(String[] args) {
		File f = new File("G:\\april\\p2");
		boolean val = f.delete();
		System.out.println(val);
	}
}

Note: delete() method can delete folder/file both

4.length() - 
------------
a. It is a non static method present inside File class
b. Return type of this method is long
c. It counts characters with white spaces in the given file.

Example:
--------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
		File f = new File("G:\\april\\t1.txt");
		long val = f.length();
		System.out.println(val);
	}
}

Note:
Compiletime Exception/ Checkedc Exception
_____________________________________________
-> These exceptions will occur even when the program is correct/Incorrect
-> Handling exception becomes mandatory when it is compile time

5. createNewFile()-
-------------------
a. It is non static method present inside File Class
b. It's return type is boolean
c. It Throws Compiletime exception. So should be handled before executing the program
d. If file is created, it will return true or else false
e. Will not replace exisiting file

Example:
------
package p1;
import java.io.File;
import java.io.IOException;
public class A {
	public static void main(String[] args) {
		try {
			File f = new File("G:\\april\\t1.txt");
			boolean val = f.createNewFile();
			System.out.println(val);
		} catch (IOException e) {
			e.printStackTrace();
		}
	
	}
}

##################
IOException in Java
############
The IOException is a checked exception in Java, part of the java.io package. It is thrown when an Input/Output operation fails or is interrupted.

Scenario			Example
File not found			Reading a file that doesn't exist
File not readable		Permission denied or locked file
Network I/O failure		Socket disconnected unexpectedly
Stream closed unexpectedly	Trying to read from a closed stream
Writing to a full disk		OutputStream write failure


6. list()-
-------------------
a. It is non static method present inside File Class
b. It's return type is String[] array
c. It gets all files/folders names from a given path

Example:
-------
package p1;
import java.io.File;
public class A {
	public static void main(String[] args) {
			File f = new File("G:\\april\\");
			String[] val = f.list();
			for(String x: val) {
				System.out.println(x);
			}
			System.out.println(val.length);
	}
}


2. FileReader:
#######################
-> It can read text file content
->read(): int

Example 1:
-----------
package app_java_3;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			FileReader fr = new FileReader("G:\\april\\t1.txt");
			System.out.println((char)fr.read());
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Example 2:
----------

package app_java_3;
import java.io.File;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			File f = new File("G:\\april\\t1.txt");
			FileReader fr = new FileReader(f);
			for (int i = 0; i < f.length(); i++) {//0 to 3
				System.out.print((char)fr.read());
			}
			fr.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

-> read(char[] ch)
Example
-------
package app_java_3;
import java.io.File;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			File f = new File("G:\\april\\t1.txt");
			FileReader fr = new FileReader(f);
			char[] ch = new char[(int)f.length()];
			fr.read(ch);
			
			for(char c:ch) {
				System.out.print(c);
			}
			
			fr.close();
			
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}



#####################
FileWriter class
#####################
1. It will write content to text file
2. If File is not present in given path, it will create a new file
3. If the file is present in the given path, then it will replace the existing file by default
4. During FileWriter object creation if true is given, then it will not replace existing content of the file. But will create new file if file was not present in given path
Example: FileWriter fw = new FileWriter("G:\\april\\t4.txt",true);
5. During FileWriter object creation if fale/ no boolean value is given, then it will replace existing content of the file and  will create new file if file was not present in given path
Example: FileWriter fw = new FileWriter("G:\\april\\t4.txt",false);
Example: FileWriter fw = new FileWriter("G:\\april\\t4.txt");

Example:
---------
package app_java_3;

import java.io.FileWriter;

public class A {
	public static void main(String[] args) {
		try {
			FileWriter fw = new FileWriter("G:\\april\\t4.txt",false);
			fw.write(97);//write(int x)
			fw.write("100");//write(String x)
			
			char[] ch = {'a','b','c'};
			fw.write(ch);//write(char[] x)
			
			fw.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Example 2:
----------
package app_java_3;

import java.io.FileWriter;

public class A {
	public static void main(String[] args) {
		try {
			FileWriter fw = new FileWriter("G://april//t1.txt");
			fw.write("mike");
			fw.write("\n");
			fw.write("stallin");
			fw.write("\n");
			fw.write("adam");
			fw.close();//Save the file content and closes the file
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}


########################
BufferedReader
#######################
1. This will improve file reading performance
2. This should be used with FileReader class, If we use only BufferedReader then FileReading cannot be done
3. It has readLine() method. Using this method we can read the entire line from the file

Example 1:
----------
package p1;
import java.io.BufferedReader;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			FileReader fr = new FileReader("G://april//t1.txt");
			BufferedReader br = new BufferedReader(fr);
			System.out.println((char)br.read());
			br.close();
			fr.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Example 2:
----------
package p1;
import java.io.BufferedReader;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			FileReader fr = new FileReader("G://f1//t1.txt");
			BufferedReader br = new BufferedReader(fr);
			char[] ch = new char[4];
			br.read(ch);
			for(char c: ch) {
				System.out.print(c);
			}
			br.close();
			fr.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Example 3:
-----------
package p1;
import java.io.BufferedReader;
import java.io.FileReader;
public class A {
	public static void main(String[] args) {
		try {
			FileReader fr = new FileReader("G://f1//t1.txt");
			BufferedReader br = new BufferedReader(fr);
			for(int i=0;i<3;i++) {
				System.out.println(br.readLine());
			}
			br.close();
			fr.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}


#####################
BufferedWriter
#####################
-> It improves file writing performance
-> This should be used with FileWriter class, If we use only BufferedWriter then FileWriting cannot be done
-> BufferedWriter class has newline() method

Example 1:
----------
import java.io.BufferedWriter;
import java.io.FileWriter;
public class A {
	public static void main(String[] args) {
		try {
			FileWriter fw = new FileWriter("G://april//t1.txt",true);
			BufferedWriter bw = new BufferedWriter(fw);
			bw.write("mike");
			bw.newLine();
			bw.write(97);
			char[] ch = {'b','c','d'};
			bw.newLine();
			bw.write(ch);
			
			bw.close();
			fw.close();
			
			
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

################################
Serialization & Deserialization
################################

-> Serialization is a process of converting object to byte code and storing that in a file system
-> De-Serialization is a process of reading byte code from the file and form Object based on byte code
-> To skip writing certain content to object during serialization we can use transient keyword

Example:
--------
package p1;
import java.io.Serializable;
public class A implements Serializable{
	String name="mike";
	transient String password = "testing";
}

package p1;
import java.io.FileOutputStream;
import java.io.ObjectOutputStream;
public class B {
	public static void main(String[] args) {
		A a1 = new A();
		try {
			FileOutputStream fos = new FileOutputStream("G:\\april\\file.ser");
			ObjectOutputStream oos = new ObjectOutputStream(fos);
			oos.writeObject(a1);
		
			oos.close();
			fos.close();
		} catch (Exception e) {
			
			e.printStackTrace();
		}
		
	}
}

package p1;
import java.io.FileInputStream;
import java.io.ObjectInputStream;
public class C {
	public static void main(String[] args) {
		try {
			FileInputStream fis = new FileInputStream("G:\\april\\file.ser");
			ObjectInputStream ois = new ObjectInputStream(fis);
			A a1 = (A)ois.readObject();
			System.out.println(a1.name);
			System.out.println(a1.password);
			
			ois.close();
		
			
		} catch (Exception e) {
			
			e.printStackTrace();
		}
		
	}
}

##########################################
JDBC - Java Database Connnectivity
##########################################
-> Database: Here we store data in the form of tables permanently
-> Popular Databases: MySQl, Postgres, Oracle, SQlServer, MongoDB, Derby, h2Database
-> Install MySql Database
Download from here: https://dev.mysql.com/downloads/windows/installer/8.0.html
-> When you download MySql Workbench you will get the following
a. IDE - To Write SQl Query (Structured Query Language)
(SQl query is use to interact with the database)
b. MySQl Server

Installation Doc: https://www.prowesstics.com/blogs/mysql-workbench-installation/


-> Launch Mysqlworkbench
-> Create psaDB connection
-> Crate Database: Create Database psaDB
-> Connect to Database: use psaDB
-> Create Table Student: 
Create table student(
	name varchar(45),
    email varchar(128),
    mobile varchar(10)
)
-> Read Table Content: Select * from student
-> Insert data to table: insert into student values('mike','mike@gmail.com','9632629033')
-> Read Table Content: Select * from student


Assignment: Complete SQL Recorded Classes. Access will be given in PSA App. Nearly covered 250+ examples

After Installing MySQl Workbench, We can now start with JDBC Concept
------------------------------------------------------------------------
-> Interacting with database using java program
-> Download Connector File for MySql: https://dev.mysql.com/downloads/file/?id=538917
-> Create a folder with name lib inside root path of your java project & paste the connector jar file inside it
-> Right click on project>>Go to properties>>select java build path>> click on libraries tab>>Click on add jar>>navigate to lib folder and select mysql connector j jar>> click apply + close

Example 1: JDBC code to insert data
-----------------------------------
package jdbc_examples;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class A {
	public static void main(String[] args) {
		try {
//Connect to database - use psaDB (SQL)
			
Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/psadb1","root","test");

//Write & execute SQl query
Statement stmnt =  con.createStatement();
stmnt.executeUpdate("insert into student values('adam','adam@gmail.com','9632629555')");
			
//Close database connection
con.close();
} catch (Exception e) {
	e.printStackTrace();
}
}

}
 
Example 2: JDBC Code to delete a record
---------------------------------------
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class B {
	public static void main(String[] args) {
		try {
			//Connect to database - use psaDB (SQL)
		Connection con = 
					DriverManager.
	getConnection("jdbc:mysql://localhost:3306/psadb1","root","test");
					
			//Write & execute SQl query
			
			Statement stmnt =  con.createStatement();
			stmnt.executeUpdate("Delete from student where email='adam@gmail.com'");
			
			//Close database connection
			con.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}

}

Example 3: JDBC Code to update Record
-------------------------------------
import java.sql.*;

public class C {
	public static void main(String[] args) {
		try {
			//Step Connect to Database
			Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/psadb1", "root", "test");
			
			//Step 2: Execute SQl Query
			Statement stmnt = con.createStatement();
			stmnt.executeUpdate("Update student set mobile='9632882052' where email='mike@gmail.com'");
			
			//Step 3: Close Database Connection
			con.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Example 4: JDBC Code to read data from database
-----------------------------------------------
package p1;

import java.sql.*;

public class D {
	public static void main(String[] args) {
		try {
			//Step Connect to Database
			Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/psadb1", "root", "test");
			
			//Step 2: Execute SQl Query
			Statement stmnt = con.createStatement();
			ResultSet result = stmnt.executeQuery("Select * from student");
			
			while(result.next()) {
				System.out.println(result.getString(1));
				System.out.println(result.getString(2));
				System.out.println(result.getString(3));
			}
			
			//Step 3: Close Database Connection
			con.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

Multi catch blocks:
---------------------

-> We can create multiple catch block.
-> Always start with child exception class followed by parent exception class

Example:
---------
package p1;

public class E {
	int x = 10;
	public static void main(String[] args) {
		try {
			Integer.parseInt("ahsjkdhas687");
			E a1 = null;
			System.out.println(a1.x);
			int x = 10/0;
		}catch (ArithmeticException e) {
			System.out.println(1);
		}catch (NullPointerException e) {
			System.out.println(2);
		}catch (Exception e) {
			System.out.println(3);
		}
		
	}
}

finally block in java
###########################

-> this is extension of try catch block
-> The code that we write in finally block will run 100%, regardless of exception


Example:
--------
public class E {
	int x = 10;
	public static void main(String[] args) {
		try {
			int x = 100/0;
		}catch (Exception e) {
			e.printStackTrace();
		}finally {
			System.out.println("Finally");
		}
		
	}
}
Output: Finally

Example:
--------
public class E {
	int x = 10;
	public static void main(String[] args) {
		try {
			int x = 100/2;
		}catch (Exception e) {
			e.printStackTrace();
		}finally {
			System.out.println("Finally");
		}
		
	}
}
Output: Finally

Example: Can we write only try & catch block: yes
--------
public class E {
	int x = 10;
	public static void main(String[] args) {
		try {
			int x = 100/0;
		}finally {
			System.out.println("Finally");
		}
		
		System.out.println("Welcome");
		
	}
}
Output:
Finally
Exception in thread "main" java.lang.ArithmeticException: / by zero
	at jdbc_examples.E.main(E.java:7)


Note: Can u give practical example where finally block can be used?
Ans: 
a. We can perform database closing operation
b. We can peform file closing operation / Database closing Operation

Example :
package p1;

import java.sql.*;

public class A {
	public static void main(String[] args) {
		Connection con = null;
		try {
			//Step Connect to Database
			con = DriverManager.getConnection("jdbc:mysql://localhost:3306/psadb1", "root", "test");
			
			//Step 2: Execute SQl Query
			Statement stmnt = con.createStatement();
			stmnt.executeUpdate("insert into student values('adam','adam@gmail.com','9632629455')");
			
			
		} catch (Exception e) {
			e.printStackTrace();
		}finally {
			try {
				//Step 3: Close Database Connection
				con.close();
			} catch (Exception e2) {
				e2.printStackTrace();
			}
		}
	}
}


Interview Question:
a. Difference between final versus finally versus finalize
=============================================================
final
--------
-> final makes variable contant
-> final prevents overriding
-> final on class stops inhertiance

finally
-------
-> this is extension of try catch block
-> The code that we write in finally block will run 100%, regardless of exception

finalize():
----------
-> This is a method inside Object class and here Garbage collection logic is implemented
-> We can try calling garbage collector using System.gc(). But will not guarantee 100% execution.






Q 1. Explain the general subprogram characteristics and define the basic terms associated with subprograms.
- A sub program has a single entry point
- Only one subprogram can be ran at a time
- When the subprogram’s execution terminates control is returned back to the caller
- Terms
	- Subprogram: self contained code block that can be called elsewhere
Q 2. Explain the terms actual parameters, formal parameters, positional parameters and keyword parameters with examples.
- actual parameters: 
- formal parameters: parameters in the subprogram header
- positional parameters: a list of parameters to be bound to the formal parameters of the subprogram
- keyword parameters: formal parameter that the caller binds by naming it in the call of it
```cpp
#include <iostream>

#include <string>

Using namespace std;
void printMessage(string& msg, int times = 1) {
    for (int i = 0; i < times; ++i) {
        std::cout << msg << "\n";
    }
}
Void printNumber(int numInput = 1){
    cout << numInput << endl;
}
int main() {
    printMessage("test!");
    printMessage("print 3 times", 3);
    printNumber(5);
}
```

Program prints by default 1 time but we can specify an exact amount as the second parameter. It also prints 1 or if specified it will print that number.

Q 3. What are the different semantic models of parameter passing? Explain with examples.
- Data can be received from the actual parameter
```cpp
Func increment(int x)
    x = x + 1
a = 5
increment(a) 
print(a)           
```
- Data can be transferred to the actual parameter
```cpp
Func setToTen(int y)
  y = 10
a = 5
setToTen(a)        
print(a)
```
- Or both
```cpp
Func addOne(int z)
	z = z + 1
a = 5
addOne(a)         
print(a)           
```

Q 4. What are the implementation models of parameter passing? How are they related to the semantic models? Explain.
Pass by value:
- Caller evaluates the actual expression
- Value is copied in to memory
- Function uses the copy
- Nothing is copied back on return

Pass by result
- Function allocated space for the formal but isn’t initialized
- Function compute and stores into that space
- When returned the slot value is copied back to the original variable

pass  by value result
- Copy the actual’s value into the formal 
- Function works with that copy
- On return the final copy is copied to the actual

Q 5. Explain the design issues for functions.
- Side effects
- Can a function change things outside itself: like global variables, parameters, or I/O or must it be “pure” and only return a value?
- Return types
- What kinds of data may a function give back? Only basic types (ints, floats), or any user-defined type (objects, arrays, even other functions)?
- Number of results
- Is a function limited to a single return value, or can it return several values at once? ​

Q 6. Chapter 9 Problem set: Question 6
6. Present one argument against providing both static and dynamic local variables in subprograms.
- If a program could be done with static local variables only at the cost of the time required to allocate, initialize (when necessary), and deallocate such variables for each call to the subprogram of dynamic local variables.

Q 7. Chapter 11 Review Questions: 1 – 6, 21, 24, 26, 28, 29.
1. What are the two kinds of abstractions in programming languages?
	- Process abstraction
	- Data abstraction
2. Define abstract data type
	- A data type that satisfies the following conditions: 
	-  The representation of objects of the type is hidden from the program units that use the type, so the only direct operations possible on those objects are those provided in the type’s definition. 
	- The declarations of the type and the protocols of the operations on objects of the type, which provide the type’s interface, are contained in a single syntactic unit. The type’s interface does not depend on the representation of the objects or the implementation of the operations. Also, other program units are allowed to create variables of the defined type.

3. What are the advantages of the two parts of the definition of abstract data type?
	- increased reliability
	- Internal names don’t pollute the global scope
	- Ability to swap one data structure for another without changing the client code

4. What are the language design requirements for a language that supports abstract data types?
	- provide a syntactic unit that encloses the declaration of the type and the prototypes of the subprograms that implement the operations on objects of the type
5. What are the language design issues for abstract data types?
	- they are not universal
	- can be parameterized?
	- If the language supports parameterized abstract data types, one could design an abstract data type for some structure that could store elements of any type

6. From where are C++ objects allocated?    
	- Static storage
	- Objects with static duration—globals, namespace-scope variables, static members—are allocated before main begins and live until the program ends.
	- Stack-dynamic (automatic) storage
	- Local (non-static) variables—including objects declared inside functions—are allocated on the call stack when their declaration is reached and destroyed when the scope exits.
	- Heap-dynamic (free-store) storage
	- Objects created via new are allocated on the heap at run time and remain until you explicitly delete them (C++ has no built-in garbage collection for these) 
	​
7. Explain the three reasons accessors to private types ae better than making the types public.
	- Read-only access can be provided by having a getter method but no corresponding setter method.
	- Constraints can be included in setters. For example, if the data value should be restricted to a particular range, the setter can enforce that. 
	- The actual implementation of the data member can be changed without affecting the clients if getters and setters are the only access
8. What is the fundamental difference between the classes of Ruby and those of C++ and Java?
	- Ruby’s classes are dynamic and open while C++ and Java classes are static and closed
9. Describe the two problems that appear in the construction of large programs that led to the development of encapsulation constructs.
10. What is a Java package, and what is its purpose?
	- a naming‐encapsulation construct that groups related classes and interfaces into a single logical unit
	- package mypkg;
	- members without explicit public or protected modifiers have package scope, making them visible throughout their own package but hidden from outsiders
	- Organization
Q 8. How are Interfaces and Abstract classes defined in Java? Why are they useful? How are these related to the concept of data abstractions, and how are they different from concrete classes?
- Interfaces definition
```cpp
public interface StudentList {
	public void add(Student student);
	public void delete(String name);
	public void print();
}
```
- The keyword “interface” is what makes it an interface
- Abstract classes definition:
	```cpp
public abstract class Shape {
    private double area;
    public abstract void computeArea();
    public double getArea() { return area; }
}
	```

- Abstract keyword allows this to become a abstract class
- They are useful because they are great for reusing code
- They also are useful for polymorphism and decoupling
- Both use abstract data type principles
- They encapsulate details and only expose them under specific conditions
- Interfaces are pure ADT
- Abstract classes are partial ADT 
- Concrete classes provides the full implementations and can actually be used
- Concrete classes though, expose their methods and data structures

Q 9. Explain with an example how Java deals with run-time errors.
```cpp
public class Except0 { 
	public static void main(String[] s) {
		Student s1 = null; 
		s1.toString(); 
	}
}
```

- If we were to implement we would run into this error if there is a null reference
- Exception in thread "main" java.lang.NullPointerException at Except0.main(Except0.java:4) 
- We then would use try-catch blocks and handle the exceptions
```cpp
public class Except1 { 

	public static void main(String[] s) { 

		Student s1 = null; 
try { 

	s1.toString(); 

} catch (NullPointerException ne) { 

	System.out.println(" Null Pointer Exception on s1. \n Continue(yes/no)?"); 
	
	Scanner myScanner = new Scanner(System.in); 
	
	String answer = myScanner.next(); 

	if (answer.equals("no")) { 

	System.exit(0); 

} 

myScanner.close(); 

} 

System.out.println("continuing \n"); 

  } 

} 
```


  

Q 10. Explain the terms Inheritance, Polymorphism and Dynamic Binding with examples.
- Inheritance:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe0g1boLq4PmUMoCM6yKbMNEXoEdcLqVjCHG-oMXSOQQx5qfhPX0zgRwhORRUk7KEaCz6PQeS3Bh1ErJWOVZiq3gJMYTCJdSbLHt5Cr0c6G_kMTAFQFPCyBAv76_Gl22NOxuR3Gug?key=yHZo9R0lPCE1hXzBH-auy5GP)
- Inheritance is easiest to explain with this picture.     
- We have a base class that has some common methods and attributes that the derived classes will inherit while adding their own unique attributes and methods
- For example if we have a person base class, it would make sense to inherit that and have the derived class be a student since it is a more specific person
- Polymorphism: 
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdxA-j-Eoa06M67azgcJviW0Db9ACkyaDiQPMdx-vyyVFymPz1NdFFy6V5ZJDazIa5Au_b3dQ_dHIYtCHiy_q0mJS7f2C53Ige2x8lKxv_koOIpVcG-y9_yjXgkOA6P1aFR9tsd2g?key=yHZo9R0lPCE1hXzBH-auy5GP)
- objects of type GraduateStudent and UndergraduateStudent are stored in student1 and student2
- For assignment of them it would be written as so:
```java
Student student1; 
student1 = new GraduateStudent(); 
```
    
```java
graduateStudent student2 = (GraduateStudent) student1; // O.K.
```
- Dynamic Binding: 
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfSKTm1gyws-ZEYinot-a6QS5VgCezrfi_qBF9mUWWTHEc13skF4wNBPfK5l18baK1H6HiWD1c1elKSj_VQPjR4xuwczRRYuLbjUTsIkjtTvRCa4l_e2CtnJKLKTbWqlL_BnsdA8g?key=yHZo9R0lPCE1hXzBH-auy5GP)
- allows us to invoke methods on members of a class hierarchy without knowing what kind of specific object we are dealing with

Q 11. Explain why polymorphic assignments result in a loss of information. In spite of this loss of
information, why are they useful, and what language features enable their usefulness. Explain with examples.
```java
Student student1 = new GraduateStudent();
```

```java
student1.getThesisTitle();
```
- Student doesn't have this method so a compile time error occurs
- Even with the loss of information, we can write generic code that works with any subclass
- Subtype polymorphism
- Declared variables of a base type allows them to be rendered to a derived object
- Dynamic binding 
- Overriding methods in the actual object’s class at run time
- “virtual” 

Q 12. What is the Object class in Java? Why is it useful? From your experience with C++, do you feel that such a class would be useful in C++? Explain
- Object can be declared and be referred to any object instance
- Unifying the methods that java calls
- Comparing this to c++ it would allow for more flexibility in using classes
- A side note the inheritance for java is a lot easier to follow then c++ increasing readability for the programmer
Q 13. Explain with a simple example how Java provides support for generic classes.
```java
Box<String>  stringBox = new Obj1<>(); 
    
Box<Integer> intBox    = new Obj2<>(); 
```
- This is very similar to C++’s templates, which allows you to input the objects types allowing for a generic class that can be used in different ways elsewhere
Q 14. What is the Java event model? How is it used to deal with mouseclicks and button clicks?
- It handles user-generated events like mouse presses, keyboard buttons, etc.
- If we have a java GUI a user mouse input will create an event object like MouseEvent
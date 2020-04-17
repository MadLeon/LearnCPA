# Welcome to Object-Oriented



### ADDRESSING COMPLEXITY

**Three Relationship**

- *has-a* relationship
- *uses-a* relationship
- *is-a-king-of* relationship



**Switching from**	

activities in the structure chart		

procedural description of the problem

**To**	

objects in the relationship diagram

object-oriented description



---



### PROGRAMMING LANGUAGES

**The Five Most Popular Languages**

- Java
- C
- C++
- Python
- C#

**The Distinguishing Features of C, C++ and Java**

- C 
	- has NO object-oriented support
	- activity-oriented structures

- C++
	- hybrid
	- arguments C with object-oriented features
	- partly activities & partly objects
	- stresses compile-time logic

- Java
	- purely object-oriented
	- object-oriented structures
	
	

### Features of C++

- superset of C
- multi-paradigm language
	- procedural
	- object-oriented
- realistic, efficient, and flexible
	- large apps
	- game
	- OS
- clean
- comprehensive



### Type Safety

- C compilers are more tolerant of type errors than C++ compilers
- In C++, all prototypes must list their parameter types



---



### NAMESPACES

**Purpose**:		To avoid naming conflicts

**Definition**:	A scope for the entities that it encloses



**Syntax**

```C++
namespace identifier {

}
```

`::`																			 the scope resolution operator	

`using identifier::x;`		 							  expose an identifier to the current namespace

`using namespace identifier::variable;`	expose all identifiers of a namespace



**Common Usage**

- struct-like types
- function types



---



### FIRST EXAMPLES

### C++ Procedural Code

```C++
#include <cstdio>
using namespace std;

int main() {
	printf("Welcome to Object-Oriented\n");
}
```

`.cpp`				  file extension										
`<csdio>`			standard input/output library
`std`					namespace in header						



### C++ Hybrid Code

```C++
#include <iostream>
using namespace std;

int main(){
	cout << "Welcome to Object-Oriented" << endl;
}
```

`<iostream>`		provides access to the std input/output objects
`cout`					the std output device
`<<`						inserts from RIGHT to LEFT
`endl`					manipulator - end of line character w/ a flushing of the output buffer



### First I/O Example

```C++
#include <iostream>
using namespace std;

int main(){
	int i;
	cout << "Enter an integer : ";
	cin >> i;
	cout << "You enterd " << i << endl;
}
```

`cin`				std input device
`>>`				  extracts and stores

**NOTE**: There is NO conversion specifier & address operator in C++

---

# Object Terminology

**Object**
Manageable chunks from problems broken down

**Class**
The shared structure of a set of similar objects

### ABSTRACTION

> We distinguish the most important features of the object, identify them publicly and hide the less important details within the object itself.

### CLASSES

Objects of the same class have:

- the same structure
- possibly different states

> Each object is an instance of its class.

### UML (The Unified Modelling Language)

**UML Connectors**

- filled circle
- empty circle
- arrow

**The Class Diagram**

A rectangular box with three compartments

| Compartments | Identifies                                        |
|--------------|---------------------------------------------------|
| upper        | class name                                        |
| middle       | attributes names & types                          |
| lower        | operations' names, return types & parameter types |

**Terminology**

Equivalent terms

- attributes (UML) - fields, data members, properties, member variables
- operations (UML) - methods (Java), procedures, messages, member functions

> C++ uses the terms *data members* & *member functions*


### ENCAPSULATION

> refers to the integration of data and logic within a class' implementation that establishes the crisp interface between the implementation and any client
> maintains high cohesion within a class and low coupling between the class' implementation and any one of its clients
> A well-encapsulated class hides all implementation details within itself.


### INHERITANCE AND POLYMORPHISM

**Relationship Between Classes**

- Inheritance  - one class inherits the structure of another class
- Polymorphism - a single interface provides multiple implementations

**Inheritance**

> Classes that share the same structure

> We only provide the code that implements additional structure

**Polymorphism**

> The implementation for an object based on its type

> Allows us to minimize the duplication of code amongst objects that belong to the same inheritance hierarchy

**The Three Musketeers**

- Encapsulation
- Inheritance
- Polymorphism



# Modular Programming

### Modules

> The module addresses one aspect of the programming solution and hides as much detail as practically possible.

We store the source code for each module in two separate files

- header file -         define the class and declares the function prototypes
- implementation file - defines the functions and contains all of the logic

> An implementation file can include several header files but DOES NOT include any other implementation file.



### STAGES OF COMPILATION

Three independent but sequential stages

- preprocessor
- compiler
- linker



### Command Line Compilation

**Linux**

`g++ -o accounting main.cpp Transaction.cpp`

| Item           | Description                      |
|----------------|----------------------------------|
| -o             | identifies the name of the exe   |
| two files name | specify the implementation files |

**Legacy Linux**

`g++ -o accounting -std=c++0x main.cpp Transaction.cpp`

specify the std option to compile an app that includes a C++ 11 feature on a legacy Linux installation

**Visual Studio**

`cl /Fe accounting main.cpp Transaction.cpp`

`/Fe`    identifies the name of the exe



### IDE Compilation

Already know



### UNIT TESTS

> It is good programming practice to write the suite of unit tests for the work units in a module as soon as we have defined the header file and before coding the bodies of the work units.





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

`.cpp`			file extension

`<csdio>`		standard input/output library

`std`			namespace in header						



### C++ Hybrid Code

```C++
#include <iostream>
using namespace std;

int main(){
	cout << "Welcome to Object-Oriented" << endl;
}
```

`<iostream>`		provides access to the std input/output objects

`cout`			the std output device

`<<`			inserts from RIGHT to LEFT

`endl`			manipulator - end of line character w/ a flushing of the output buffer



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

`cin`		std input device

`>>`		extracts and stores

**NOTE**: There is NO conversion specifier & address operator in C++



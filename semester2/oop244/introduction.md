# Welcome to Object-Oriented

### ADDRESSING COMPLEXITY

>We express the features in terms of *data* & *activities*
>We identify the data objects & the activities on those objects as complementary tasks

The three relationship

- *has-a* relationship

- *use-a* relationship

- *is-a-kind-of* relationship

### PROGRAMMING LANGUAGE

**TOP Five Language**

- JAVA
- C
- Python
- C++
- C#

**The distinguishing features of C, C++ & Java**

- C has no o-o support.

- C++ is hybrid.

- Java is purely o-o.

### Features of C++

See the website.

### Type Safety

In C++, all prototypes list their parameter types, which has forced all compilers to check for argument/ parameter type mismatches at compile-time.

### NAMESPACES

>A **namespace** is a scope for the entities that it encloses.
>Scoping rules avoid identifier confilicts across different namespaces.

**Definition**

```c++
namespace identifier {

}
```

`identifier`    the name of the scope
`{}`			encolses & defines the scope

**Access**

To access a variable defined within a namespace, we procede its identifier with the identifier and separate them with `::`. This is called **scope resolution oerator**

**Expose**

expose one variable to the current namespace:

`using *identifier*::variable;`

expose all of a namespace's identifiers:

`using namespace *identifier*::variable;`

**Common Usage**

- struct-like types
- function types

### FIRST EXAMPLE

**C++ procedural code**

```c++
#include <cstdio>
using namespace std;

int main(){
	printf("Hello World!")
}
```

Note:

- `<cstdio.h>` - C++ version
- it declares the prototype for printf() within the `std` namespace
- `std` denotes standard

`using namespace std;`

- expose all identifiers declared within the std namespace to the global namespace.
- the libraries of standard C++ declare most of their identifiers within the std namespace.

**C++ hybrid code**

```c++
#include <iostream>
using namespace std;

int main(){
	cout << "Hello World!" << endl;
}
```

Note:

- `<iostream>` 	provides access to the standard io objects
- `cout`		the standard output device
- `<<` 			inserts whatever is on its right side into whatever is on its left side
- `endl` 		end of line character & a flushing of the output buffer
- NO formatting string

### First I/O Example

```c++
#include <iostream>
using namespace std;

int main(){
	cout << "Enter an integer: ";
	cin >> i;
	cout << "You entered: " << i << endl;
}
```

Note:

- `cin` the standard input devide
- `>>`  assign input value to variable
- NO "&" get involved

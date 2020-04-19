# Types, Overloading and References

## TYPES

*Fundamental Type*    built-in type

*Struct Type*

- C   - derived type
- C++ - compound type

### Fundamental Types

- Integral Types
	- *bool*
	- char
	- int - short, long, long long

- Floating Point Types
	- float
	- double - long double

**bool**

`true` or `false`

`!` self-invert

1    <=>     0
true <=> false

**bool to int**

bool  | int
------|
true  | 1
false | 0

### Compound Types

- struct
- class

> C++ DOES NOT require the keyword struct or class in a **function prototype** or an **object definition**

### auto Keyword

> This keyword deduces the object's type directly from its initializer's type

`auto x = 4;`    x is an int
`auto y = 3.5;`  y is a double




## DECLARATIONS AND DEFINITIONS

### Declarations

> associates an entity with a type, telling the compiler how to interpret the entity's identifier.



### Definitions

> a declaration that associates a meaning with an identifier.

> In C++, each definition is an executable statement. We may embed it amongst other executable statements.

`for (int i = 0; i < n; i++)`

**One Definition Rule**

In C++, a definition may only appear once within its scope.



### Designing Away Multiple Definitions

See example in the online notes

**Forward Declaration Solution**

> provides the compiler with just enough info to accept the identifier, without exposing the type details.

**Compact Solution**

> localized all declarations related within the same header file

**Helper Function**

functions that support a compound type

**Proper Header File Inclusion**

Include header files in the order:

- <...> - system header files
- "..." - other system header files
- "..." - your own header files

> insert namespace declarations and directives after all header file inclusions.



## SCOPE

- global
- file
- function
- class
- block

local = non-global



### Going Out of Scope

**Iteration**

```C++
for (int i = 0; i < 4; i++) {
int j;
}
```

Note:
`i` goes out of scope immediately *after* the closing brace
`j` goes out of scope immediately *before* the closing brace, means each iteration

### Shadowing

mentioned in last semester



## FUNCTION OVERLOADING

### Function Signature

- identifier
- parameter types
- the order of the parameter types

`type identifier (type identifier [, ...., type identifier])`

> The square brackets enclose optional info. The return type and the parameter identifiers are not part of a function's signature.



### Prototypes

function prototype = function signiture + return type

> The declaration may be either a prototype or the function definition itself.



### Default Parameter Values

`type identifier(type[, ...], type = value);`



## REFERENCES

> A *reference* is an alias for a variable or obj.

> A reference is an alternative to the pass by address mechanism

`type identifier(type& identifier, ...)`

NOTE: The feature of referencing

- only specify '&' in prototype
- do NOT specify in function call
- use '&' in definition, instead of '*'



## ARRAY OF POINTERS

> Array of pointers contain addresses rather than values.



## KEYWORDS

There are 84 keywords in C++. C programs without using those keywords as identifiers are called clean C programs.



---



# Dynamic Memory

## STATIC AND DYNAMIC MEMORY

### Static Memory

> The memory that the operating system allocates for the application at load time.

Static memory includes the memory allocated for

- program instructions
- program data

The *compiler* determines    the amount of static memory that each translation unit requires
The *linker* determines      the amount of static memory that the entire app requires

- determined at compile-link time 
- do NOT change during execution
- fast
- fixed in its amount
- allocated at load time



### Dynamic Memory (DM)

> The memory that an app obtains from the OS during execution.

- system reserves DM
- allocated & deallocated at run-time

**Scope Considerations**

> To keep track of an app's DM, we store the address of each allocated region in a pointer variable. We allocate memory for this pointer itself in static memory. This pointer variable must remain in scope as long as wee need access to the data in the allocated region of DM.



### Lifetime

- The lifetime of any DM ends when the address holder (pointer) goes out of scope.

- The programmer MUST manage DMs' deallocation explicitly.



## DYNAMIC ALLOCATION

**Syntax**

`pointer = new type[size];`

Note: `new` return the address of the array's first element

```C++
int n;
Student* student = nullptr;

cout << "How many students in this section? ";
cin >> n;

student = new Student[n];
```

`nullptr`    identifies the address pointed to as the null address



## DYNAMIC DEALLOCATION

**Syntax**

`delete [] pointer`

```C++
delete [] student;
student = nullptr;
```

> The second line is optional, it eliminates the possibility of deleting the original address a second time, which is a serious run-time error.

> Omitting '[]' only deallocates the first element, leaving the other elements inaccessible.

> Deallocation does not return DM to OS until app ends.



## MEMORY ISSUES

- memory leaks
- insufficient memory



### Memory Leak

> an app loses the address of DM before it has been deallocated.

> One of the important bugs in oo programming.

**Reasons**

- the pointer to DM goes out of scope *before* deallocation
- the pointer to DM changes its value *before* the app deallocates the memory starting at the address stored in that pointer

**Appearance**

- subsequently incorrect results
- progressively slower execution



### Insufficient Memory

Will be discussed later



## SINGLE INSTANCES (OPTIONAL)

### Allocation

**Syntax**

`pointer = new type;`

Note: removing the '[]'



### Deallocation

**Syntax**

`delete pointer;`
`pointer = nullptr;`



# Member Functions and Privacy



## MEMBER FUNCTIONS

Communication Link between client code and objects of the class.

**Mutually Exclusive Categories**

| Categories  | Methods          | Function                             |
| ----------- | ---------------- | ------------------------------------ |
| *queries*   | accessor methods | report the state of the object       |
| *modifiers* | mutator methods  | change the state of the object       |
| *special*   | manager methods  | create, assign and destroy an object |

### Adding a Member Function

**Function Declaration**

> To declare a member function to a class, we insert its prototype into the class definition.

```C++
struct Student {
	int no;
	float grade[NG];
	int ng;

	void display() const;
}
```

`const`    identifies the member function as a query, it cannot change the value of `no` and `grade`

> Member function has direct access to the data members.



**Function Definition**

```C++
void Student::display() const {
	// statements
}
```

| Items             | Description                                              |
| ----------------- | -------------------------------------------------------- |
| *Student::*       | identifies it as a member of Student                     |
| *empty parameter* | it does not receive / return value from / to client code |
| *const*           | it cannot change other members' value                    |
| data members      | directly access other members' values                    |

**Calling a Member Function**

`student.display();`



### Scope of a Member Function

> The scope lies within the scope of its class.

**Accessing Global Functions**

```C++
void Student::displayNo() const {
	::display(); // calls the global function
	display();   // calls the member function
}
```



## PRIVACY

### Accessibility Labels

`private:`    identifies all subsequent members listed in the class definition as inaccessible

`public:`     identifies all subsequent members listed in the class definition as accessible

`struct`    identifies a class that is public by default

`class`     identifies a class that is private by default

### Modifying Private Data

Using member function to help initializing such as set()

### Communications Links

> Member functions are only communication liks to client code.



## EMPTY STATE 

Verify data by using member functions

- accept valid
- reject invalid

**Design Tip**

> Select one data member to hold the special value that identifies an empty state. Then, to determine if an obj is in an empty state, we only need to interrogate that data member.



## INPUT AND OUTPUT EXAMPLES

### cin

`cin >> identifier`

- an instance of the `istream` type
- skip leading whitespace with numeric, string and character types
- treat whitespace as delimiter for numeric and string 
- add '\0' after the non-whitespace character

`istream` type member functions

| Functions | Description                                         |
| --------- | --------------------------------------------------- |
| ignore()  | ignores/discards character(s) from the input buffer |
| get()     | extracts a character / string from the input buffer |
| getline() | extracts a line of characters from the input buffer |

**ignore()**

- does NOT skip leading whitespace

`cin.ignore();`            

- discards a single character

`cin.ignore(2000, '\n')`   

- removes and discards up to the specified number of characters 
- or up to the specified delimiting character, whichever occurs first
- discards the delimiting character
- the default delimiter is EOF (not end of line)



### cout

`cout << identifier`

- an instance of the ostream type
- copies data from system memory into an output stream
- converts the data in system memory into a sequence of characters

**cascading**

> Combine expressions into a single statement that specifies multiple insertions.

`ostream` type public member functions

| Functions      | Description                                          |
| -------------- | ---------------------------------------------------- |
| width(int)     | sets the fields width to the integer received        |
| fill(char)     | sets the padding character to the character received |
| setf()         | sets a formatting flag for the flag received         |
| unsetf()       | unsets a formatting flag for the flag received       |
| precision(int) | sets the decimal precision to the integer received   |

`width()`

- applies only to the next field

`fill()`

- define the padding character
- the default fill character is ' ' (space)
- the padding character remains unchanged until reset

`setf()`, `unsetf()`

- control formatting and alignment
- the default format in C++ is *general format*

| Control Flag    | Result      |
| --------------- | ----------- |
| ios::fixed      | ddd.ddd     |
| ios::scientific | d.ddddddEdd |
| ios::left       | align left  |
| ios::right      | align right |

Note: the scope resolution (ios::) identifies them as part of the `ios` class

- format settings persist until change
- pass the format that want to change to `unset()`

**precision**

- sets the precision of subsequent floating-point fields
- the default precision is 6 units
- applies to the output of all subsequent floating-point values until change

Note: 
general, fixed, and scientific formats implement precision differently

- general format counts the number of significant digits
- scientific and fixed formats count the number of digits following the decimal point




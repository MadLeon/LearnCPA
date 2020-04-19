# Workshop 3



### Copy Structure

Using dereference rather than directly address matching

```c++
(*cargo) = goods;	// right

cargo = &goods;		// wrong
```



### Namespace

Function definitions in .cpp file can be encapsulated by namespace.

Using `class::FunctionName` to point to the class



### String Copy

Remember to add `'\0'` manually

```c++
for (i = 0; i < strlen(str); i++)
{
	name[i] = str[i];
}
name[i] = '\0';
id = num;		
```

Instead of `name[i + 1]` , using `name[i]` to represent the last position because it has already increment when `i++`.



### Privacy

Though a pointer of class Cargo is included in Train, the values of members cannot be access by public functions in Train class.

The only way to access members' value is to add function in class Cargo



### Function Naming

`setMemberName()` , `getMemberName()` are both useful function as seen before.


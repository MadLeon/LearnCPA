# Compiling Modules

### Using External File To Test The Program

**Visual Studio**

Properties => Debugging => Command Arguments: `< Filename`

### Compilation Safeguard

```C++
#ifndef NAMESPACE_HEADERFILENAME_H
#define NAMESPACE_HEADERFILENAME_H

// headerfile content

#endif
```

### Namespace Definition

- insert namespace below #include in the header file

- put the rest things in the header file into the namespace

- the definition in .cpp file should be something like below:

`void namespace::specifier () {};`





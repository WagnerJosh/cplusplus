# Qualifiers

## The `const` qualifier

The `const` qualifier specifies that the object is constant and therefore cannot be changed.

**Examples**:

```c++
    const int x = 42 ; 
    x 13 ;              // ERROR : x is const 
    const int& x1 =  x; // OK 
    const int* p1 = &x; // OK 
    int& x2 = x ;       // ERROR : x const , x2 not const 
    // The above would create THIS SHOULD BE 
    const int& x2 = x; 
    int* p2 = &x ;      // ERROR : x const , * p2 not const 
```

```c++
    int x 0 ; 
    const int & y = x;
    x = 42; // OK 
            // y also changed to 42 since y refers to x 
            // y cannot be used to change x, however 
            // the following would cause compile error:
            // y = 24 ; - ERROR : y is const
```

with types that are not pointer or reference types, `const` can only be applied to object itself (i.e.top level)
that is, object itself may be const or non-const

**Example**:

```c++
int i = 0 ;         // object i is modifiable 
i = 42 ;            // OK : i can be modified 
const int ci = 0 ;  // object ci is not modifiable 
ci 42 ;             // ERROR : ci cannot be modified
```

**Example**: Const and non-pointer/non-reference types

```c++

/*  with types that are not pointer or reference types , const
    can only be applied to object itself ( i.e. , top level ) 
    object itself may be const or non - const 
*/
    
    int i = 0;      // non const int object 
    const int ci=0; // const int object 
    i = 42;         // OK: can modify non -const object 
    ci = 42;        // ERROR: cannot modify const object 
    i =  ci;        // OK: can modify non - const object 
    ci = i;         // ERROR: cannot modify const object 
```

## The `volatile` qualifier

The `volatile` qualifier is used to indicate that the object can change due to agents external to  the program (such as a *memory-mapped device* or *signal handler*)

The compiler cannot optimize away read and write operations on volatile objects (e.g. repeated reads without intervening writes cannot be optimized away)

volatile qualifiers are typically used when the object:

* Corresponds to a register of memory-mapped device
* May be modified by a signal handler (namely, object of type `volatile std :: sig_atomic_t`)

**Example**:

```c++
    volatile int x;
    volatile unsigned chart deviceStatus;
```

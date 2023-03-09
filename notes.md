# C++

.cpp = C++ file
.hpp = Header C++ file

## GNU Compiler Collection ( GCC ) C++ Compiler

* `g++` command provides both compiling and linking functionality
* command-line usage `g++ [options] input_file ...`
* [web site](http://www.gnu.org/software/gcc )
* [C++ standards support in GCC](https://gcc.gnu.org/projects/cxx-status.html)

Many command-line options are supported and particularly useful command-line options are listed below:

* compile C++ source file file.cpp to produce object code file file.o: `g++ -c file.cpp`
* link object `files` `file_1.o`, `file_2.o`, ... to produce executable file executable: `g++ -o executable file_1.o file_2.o ...`
* `-c`: compile only ( i.e. , do not link )
* `-o file`: use file file for output
* `-g`:include debugging information
* `-On`: set optimization level to n (`0` almost none ; `3` full)
* `-std=c++20`: conform to C++20 standard
* `-Idir`: specify additional directory dir to search for include files
* `-Ldir`:specify additional directory dir to search for libraries
* `-llib`:link with library lib
* `-pthread`: enable concurrency support ( via pthreads library ) I
* `-pedantic-errors`: strictly enforce compliance with standard

The `W` means warning

* `-Wall`: enable most warning messages
* `-Wextra`: enable some extra warning messages not enabled by -Wall
* `-Wpedantic`: warn about deviations from strict standard compliance
* `-Werror`: treat all warnings as errors
* `-fno-elide-constructors`: in contexts where standard allows (but does not require) optimization that omits creation of temporary , do not attempt to perform this optimization
* `-fconstexpr-loop-limit=n`: set maximum number of iterations for loop in constexpr functions to n
* `-fconstexpr-depth=n`: set maximum nested evaluation depth for constexpr functions to n

## C++ Syntax

Comments are as follow single line `//` or multi-line `/* */`

Identifiers:

* Name entities such as `types`, `objects(i.e. variables)`,`functions`
* Can be any sequence of letter, digits or underscores but **CANNOT start with a digit**
* Are Case Sensitive so `counter` and `CoUnTER` are different!
* Cannot be a reserved keyword such as `delete`, `do`, `assign` ...

## The Basics

### Objects, Types  and Values

The basic types are also know as "Fundamental Types" and consist of Boolean, Character and Integer types as follows:

Boolean Types

|  Name             | Notes                     |
|---                | ---                       |
| `bool`            | Either `True` or `False`  |  

Character Types

|  Name             | Notes                     |
|---                | ---                       |
| `char`            |                           |
| `signed char`     |                           |
| `unsigned char`   |                           |
| `char16_t`        |                           |
| `char32_t`        |                           |
| `wchar_t`         |                           |

> **📝 NOTE:**  **`char`**  is distinct from  `unsigned char` and `signed char`

Integer Types

|  Name                     | Notes                     |
|---                        | ---                       |
| `signed char`             |                           |
| `signed short int`        |                           |
| `signed int`              |                           |
| `signed long int`         |                           |
| `signed long long int`    |                           |
| `unsigned char`           |                           |
| `unsigned short int`      |                           |
| `unsigned int`            |                           |
| `unsigned long int`       |                           |
| `unsigned long long int`  |                           |

> **📝 NOTE:**
>
> * **`int`** may be omitted from names of non-character integer types (e.g. **`unsigned`** is equivalent to **`unsigned int`** and **`signed`** is equivalent to **`signed int`**)
> * **`signed`** may be omitted from names of signed integer types excluding **`signed char`**

Floating point types

|  Name                     | Notes                     |
|---                        | ---                       |
| `float`                   |                           |
| `double`                  |                           |
| `long double`             |                           |

Void Type
|  Name                     | Notes                     |
|---                        | ---                       |
| `void`                    | incomplete/valueless type:void (placeholder for nothing) |

null pointer

|  Name                     | Notes                     |
|---                        | ---                       |
| `null pointer`            | std::nulllptr_t           |

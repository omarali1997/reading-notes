# Read 02 - Testing and Modules

> # Testing
* ## What is Unit Testing?
### Unit testing is a technique to test a small block of independent code. The small-block code will be a function in most cases. The word independent means it doesn’t depend on other pieces of code in the project.

> ## Importance of Unit Testing
### In general, the independent blocks code can be used across the project. So, it must be well written and tested. Unit tests are the tests used to test those types of independent blocks of code. 

* ## What happens if we don’t use unit tests for our project?

### Let’s assume we didn’t test small blocks of code that are used across the project. All other tests like integration tests, end-to-end tests, etc., using the other small blocks of code may fail. This breaks the application. That’s why the basic building blocks of the code must be tested well.

### Now, we know the importance of unit testing and written unit tests for all independent code blocks. Since we have performed unit tests, other tests like integration tests, end-to-end tests, etc., won’t fail because of the independent block of codes.
#
> # Modules

* ## What are modules in Python?
### Modules refer to a file containing Python statements and definitions.

### A file containing Python code, for example: `example.py`, is called a module, and its module name would be `example`.


* ## Why we need to use modules

### We use modules to break down large programs into small manageable and organized files. Furthermore, modules provide reusability of code.
#
#### Let us create a module. Type the following and save it as `example.py`.

```
# Python Module example

def add(a, b):
   """This program adds two
   numbers and return the result"""

   result = a + b
   return result
```
### Here, we have defined a function add() inside a module named example. The function takes in two numbers and returns their sum.
#

* ## How to import modules in Python?

### We can import the definitions inside a module to another module or the interactive interpreter in Python.

### We use the `import` keyword to do this. To import our previously defined module `example`, we type the following in the Python prompt.

```
>>> import example
```

### This does not import the names of the functions defined in `example` directly in the current symbol table. It only imports the module name `example` there.

* ### Using the module name we can access the function using the dot `"."` operator. For example:

```
>>> example.add(4,5.5)
9.5
```

### Python has tons of standard modules. You can check out the full list of Python standard modules and their use cases. These files are in the Lib directory inside the location where you installed Python.

### Standard modules can be imported the same way as we import our user-defined modules.

* ## Python import statement
### We can import a module using the import statement and access the definitions inside it using the dot operator as described above. Here is an example.

```
# import statement example
# to import standard module math

import math
print("The value of pi is", math.pi)
```
### When you run the program, the output will be:
```
The value of pi is 3.141592653589793
```

#
Resources

* [geekflare](https://geekflare.com/unit-testing-with-python-unittest/)
* [programiz](https://www.programiz.com/python-programming/modules)
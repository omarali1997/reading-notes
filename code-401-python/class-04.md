# Read 04 - FileIO & Exceptions
>## Files
* ### Files are named locations on disk to store related information. They are used to permanently store data in a non-volatile memory (e.g. hard disk).

* ### Since Random Access Memory (RAM) is volatile (which loses its data when the computer is turned off), we use files for future use of the data by permanently storing them.

* ### When we want to read from or write to a file, we need to open it first. When we are done, it needs to be closed so that the resources that are tied with the file are freed.

* ### Hence, in Python, a file operation takes place in the following order:

1. Open a file
2. Read or write (perform operation)
3. Close the file

>## Opening Files in Python

* ### Python has a built-in `open()` function to open a file. This function returns a file object, also called a handle, as it is used to read or modify the file accordingly.

```
>>> f = open("test.txt")    # open file in current directory
>>> f = open("C:/Python38/README.txt")  # specifying full path
```

* ### We can specify the mode while opening a file. In mode, we specify whether we want to read `r`, write `w` or append `a` to the file. We can also specify if we want to open the file in text mode or binary mode.

* ### The default is reading in text mode. In this mode, we get strings when reading from the file.

* ### On the other hand, binary mode returns bytes and this is the mode to be used when dealing with non-text files like images or executable files.

| Mode | Description                                                                                                       | 
| ----------------------------- | ---------------------------------------------------------------------------------------- |
|   `r`  | Opens a file for reading. (default)                                                                               |
|   `w`  | Opens a file for writing. Creates a new file if it does not exist or truncates the file if it exists.             |
|   `x`  | Opens a file for exclusive creation. If the file already exists, the operation fails.                             |
|   `a`  | Opens a file for appending at the end of the file without truncating it. Creates a new file if it does not exist. |
|   `t`  | Opens in text mode. (default)                                                                                     |
|   `b`  | Opens in binary mode.                                                                                             |
|   `+`  | Opens a file for updating (reading and writing)                                                                   |

```
f = open("test.txt")      # equivalent to 'r' or 'rt'
f = open("test.txt",'w')  # write in text mode
f = open("img.bmp",'r+b') # read and write in binary mode
```
* ### Unlike other languages, the character a does not imply the number 97 until it is encoded using ASCII (or other equivalent encodings).

* ### Moreover, the default encoding is platform dependent. In windows, it is cp1252 but utf-8 in Linux.

* ### So, we must not also rely on the default encoding or else our code will behave differently in different platforms.

* ### Hence, when working with files in text mode, it is highly recommended to specify the encoding type.
```
f = open("test.txt", mode='r', encoding='utf-8')
```

>## Closing Files in Python
### When we are done with performing operations on the file, we need to properly close the file.

### Closing a file will free up the resources that were tied with the file. It is done using the `close()` method available in Python.

### Python has a garbage collector to clean up unreferenced objects but we must not rely on it to close the file.

```
f = open("test.txt", encoding = 'utf-8')
# perform file operations
f.close()
```

>## Exceptions 

### Exception handling is an essential part of any Python developer's job. If you know how to handle exceptions, you can execute any code you write flawlessly, without any interruption. A detailed guide for handling exceptions in Python can help refresh and revise your Python programming knowledge and suggest some ideas for exception handling. In this article, we define exception handling in Python, discuss different types of errors that can occur, explore five unique Python keywords for exception handling, provide relevant examples and list 20 built-in Python exceptions.
#
### When the code is syntactically correct, but it still results in an error because of some internal events, it is called an exception. It does not stop the execution, but it changes the normal flow of the program. These are usually logical errors that are non-fatal and recoverable by user programs. Programmers can handle exceptions at the run time through exception handling methods.

#

* ## What does handling exceptions in Python mean?
### The requirement for handling exceptions in Python arises when an error occurs that can cause the program to terminate. Errors interrupt the flow of the program at the point where they appear, so any further code stops executing. This error is called an exception. The exception has to be handled so that the interpreter can execute all the code that exists after the exception.

### Some common examples of such errors are dividing a number by zero, adding two incompatible types, trying to access a non-existent index of a sequence or accessing a file that does not exist. These scenarios are called exceptions. When the method cannot handle the exception, it gets thrown out of the main function, causing the program to terminate abruptly. It is necessary to prevent all such unexpected errors so that the program keeps running. Programmers write a special block of code that triggers automatically on detecting such errors. This is called exception handling in Python.
# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Python Exception Handling

| Title                     | Type   | Duration | Author               |
|---------------------------|--------|----------|-----------------------
| Python Exception Handling | Lesson | 2:00     | Suresh Melvin Sigera |

### Objectives

*After this lesson, students will be able to:*

- Describe what an exception is
- Find errors and debug code
- Handle multiple exception during the runtime

## What are exceptions?

There may be times when, while executing a Python program, an issue arises that prevents the program from executing at
all, or if it does execute, the program generates unexpected output or behaves abnormally. This type of error is caused
by syntax errors, runtime errors, or logical errors in the code. In Python, exceptions are errors that get triggered
automatically. There is however the possibility that exceptions can be forcedly triggered and handled through the code
of the program. As part of this lesson, we will learn about how to handle exceptions in Python programs.

The first error that programmers (even experienced ones) are confronted with is when the code has incorrect syntax,
meaning that the code instructions are not correctly formatted.

Consider this example of a syntax error:

```text
>>> for i in range(10)
  File “<stdin>”, line 1
    for i in range(10)
                      ^
SyntaxError: invalid syntax
```

In the case of the `for` declaration, there is an error that occurs due to the fact that there is no colon at the end of
the statement. As you can see, this is an example of an exception being thrown. It is important to remember that
`SyntaxError` is an error that not only informs the programmer that there is an error with the syntax of the code, but
also prints the line where the error occurred with an arrow that indicates where the error is located in that line.

## Types of Exceptions

There are various exceptions in Python that are derived (inherited) from a base class called the `Exception` class.
Exceptions are a significant part of Python, and they come with a number of built-in features.

As per Python's [documentation](https://docs.python.org/3/library/exceptions.html), the following is a list of the
built-in exceptions and what they mean.

| Exception | Cause |
|-------|-------|
| AssertionError | Raised when assert statement fails |
| AttributeError | Raised when attribute assignment or reference fails |
| EOFError | Raised when the input() function hits end-of-file condition |
| FileNotFoundError | Raised when a file or directory is requested but doesn’t exist. Corresponds to errno ENOENT |
| FloatingPointError | Raised when a floating point operation fails |
| GeneratorExit | Raised when a generator's close() method is called |
| ImportError | Raised when the imported module is not found |
| IndexError | Raised when index of a sequence is out of range |
| KeyError | Raised when a key is not found in a dictionary |
| KeyboardInterrupt | Raised when the user hits interrupt key (Ctrl+C or delete) |
| MemoryError | Raised when an operation runs out of memory |
| NameError | Raised when a variable is not found in local or global scope |
| NotImplementedError | Raised by abstract methods|
| OSError | Raised when system operation causes system-related error|
| OverflowError | Raised when result of an arithmetic operation is too large to be represented|
| ReferenceError | Raised when a weak reference proxy is used to access a garbage collected referent|
| RuntimeError | Raised when an error does not fall under any other category|
| StopIteration | Raised by next() function to indicate that there is no further item to be returned by iterator|
| SyntaxError | Raised by parser when syntax error is encountered|
| IndentationError | Raised when there is incorrect indentation|
| TabError | Raised when indentation consists of inconsistent tabs and spaces|
| SystemError | Raised when interpreter detects internal error|
| SystemExit | Raised by sys.exit() function|
| TypeError | Raised when a function or operation is applied to an object of incorrect type|
| UnboundLocalError | Raised when a reference is made to a local variable in a function or method, but no value has been
bound to that  variable |
| UnicodeError | Raised when a Unicode-related encoding or decoding error occurs|
| UnicodeEncodeError | Raised when a Unicode-related error occurs during encoding |
| UnicodeDecodeError | Raised when a Unicode-related error occurs during decoding |
| UnicodeTranslateError | Raised when a Unicode-related error occurs during translating |
| ValueError | Raised when a function gets argument of correct type but improper value |
| ZeroDivisionError | Raised when second operand of division or modulo operation is zero | 

As shown in the table above, every time an exception occurs and an exception error is raised in the interpreter, the
execution of a program is halted.

You can use the `try` keyword to catch exceptions thrown by the code, and when an exception occurs, you can use
the `except` keyword to provide code to handle the error when it occurs.

## Process of Handling Exception

When an error occurs, Python interpreter creates an object called the **_exception object_**. This object contains
information about the error like its type, file name and position in the program where the error has occurred.
The object is handed over to the runtime system so that it can find an appropriate code to handle this particular
exception. This process of creating an exception object and handing it over to the runtime system is called throwing an
exception. It is important to note that when an exception occurs while executing a particular program statement, the
control jumps to an exception handler, abandoning execution of the remaining program statements.

The runtime system searches the entire program for a block of code, called the _exception handler_ that can handle the
raised exception. It first searches for the method in which the error has occurred and the exception has been raised. If
not found, then it searches the method from which this method (in which exception was raised) was called. This
hierarchical search in reverse order continues till the exception handler is found. This entire list of methods is known
as _call stack_.

When a suitable handler is found in the call stack, it is executed by the runtime process. This process of executing a
suitable handler is known as catching the exception. If the runtime system is not able to find an appropriate exception
after searching all the methods in the call stack, then the program execution stops.

Note: A programmer can also create custom exceptions to suit one’s requirements. These are called _user-defined
exceptions_. We will learn how to handle exceptions in the next section.

## Catching Exceptions

An exception is said to be caught when a code that is designed to handle a particular exception is executed. Exceptions,
if any, are caught in the try block and handled in the except block. While writing or debugging a program, a user might
doubt an exception to occur in a particular part of the code. Such suspicious lines of codes are put inside a `try`
block.
**Every `try` block is followed by an `except` block**. The appropriate code to handle each of the possible exceptions (
in the code inside the try block) are written inside the except clause.

- The `try` block lets you test a block of code for errors.
- The `except` block lets you handle the error.
- The `else` block lets you execute code when there is no error.
- The `finally` block lets you execute code, regardless of the result of the `try` and `except` blocks.

While executing the program, if an exception is encountered, further execution of the code inside the `try` block is
stopped and the control is transferred to the `except` block. The syntax of `try` … `except` clause is as follows:

```text
try:
    [program statements where exceptions might occur]
except [exception-name]:
    [code for exception handling if the exception-name error is encountered]
```

Consider the Program 1-2 given below:

```python
import sys

file_object = open("/user/ecommerce/data.csv", "r")
```

Based on the analysis of the above code, which type of error is likely going to occur during the execution of the code
as a result of analyzing its structure?
<details>
  <summary>Answer</summary>

```text
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    file_object = open("/user/ecommerce/data.csv", "r")
FileNotFoundError: [Errno 2] No such file or directory: '/user/ecommerce/data.csv'    
```

</details>

<hr>

```python
a = 5
b = 0
print(a / b)
```

Based on the analysis of the above code, which type of error is likely going to occur during the execution of the code
as a result of analyzing its structure?
<details>
  <summary>Answer</summary>

```text
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    print (a/b)
ZeroDivisionError: division by zero
```

</details>
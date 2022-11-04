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

An exception is an error that occurs during execution of a program, sometimes called a runtime error.

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

In the case of the for declaration, there is an error that occurs due to the fact that there is no colon at the end of
the statement. As you can see, this is an example of an exception being thrown. It is important to remember that
SyntaxError is an error that not only informs the programmer that there is an error with the syntax of the code, but
also prints the line where the error occurred with an arrow that indicates where the error is located in that line.

There are various exceptions in Python that are derived (inherited) from a base class called the Exception class.
Exceptions are a significant part of Python, and they come with a number of built-in features.

As per Python's documentation, the following is a list of the built-in exceptions and what they mean.

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

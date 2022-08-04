

# Fundamentals of Python - Importing and Commenting

## Goal

Understanding the importance of code commenting and how to use external code

## Learning objectives

After going through this chapter, students should be able to:

* Clearly annotate their code
* Load external code into their scripts

## Commenting

While it may seem like extra work, adding context to  code is **crucial**. It's helpful to remind you as a programmer when you look back at an old script what you intended as well as making it much easier for someone else reading the code to follow your logic.

### Adding comments to code

We can add comments to our code to explain what we are doing or what we want to do using a pound sign or the hash (`#`). You can either start a line with this or put it at the end of the line. Everything on the line after the pound sign (`#`) will be ignored by python and not executed, but allows readers of code to better understand what is happening. 

## Importing packages (AKA libraries or modules)

Finally, sometimes in Python we'll use the `import` keyword to import packages that have pre-built functions that aren't built-in Python functions, but nonetheless allow us to do specific things. A very common package that we'll be using in this prep work is `sys` which allows us to take in commandline arguments when calling a bash script on Python. For plotting we would use a package called `matplotlib.pyplot`.

### Importing specific functions and variables

Often you will not need to import an entire library or module, but rather a specific function or variable. For example, if we wanted to have access to the `log` function which is in the `math` library, we could either


```python
import math
a = math.log(5)
```

But we could also just get the `log` function using the `from` keyword.


```python
from math import log
a = log(5)
```

This is much easier to read and write. However this should be used with caution as some functions in different libraries have the same name and importing one will replace another function of the same name. But if we import and reference the module (i.e. using `math.log`), that problem is alleviated.

We can also import multiple functions/variables in a single line.


```python
from math import log, exp, sin
```

### Aliasing packages or modules

Sometimes it is too bulky to type out the complete name of the module and function that you have imported each time you wish to use it. Instead, Python has the `as` keyword which allows us to given modules or even individual functions alternate names. One that we will use repeatedly in this class is


```python
import matplotlib.pyplot as plt
```

Anytime we type `plt`, Python interprets this as `matplotlib.pyplot`. So if we want to call the `subplots` function from this imported module, we can simply type `plt.subplots()`.

Note that you should use this aliasing with caution. As with importing functions without reference to their module, aliases will replace another function or variable of the same name in your script.



# Applied Python Exercise 2

## Goal -- Print the first line in a file

Write Python code that works towards recreating the Bash tool `head`, displaying only the first line in a file: `random_snippet.vcf`

## Learning Objectives

After going through this module, students should be able to:

* State the sub-steps needed to meet the coding goal
* Use the following datatypes, structures, and fundamentals to meet the coding goal:
  * variable assignment
  * strings
  * opening a file
  * for loop
  * integers
  * logical expression
  * conditional statement
  * printing output

## Coding Blueprint

Let's start with and edit the pseudocode from the last module to meet the needs of this module.

Last module's pseudocode:

First, we need to SET the input file
Second, FOR every line in the open file
  PRINT the line
END FOR

In this module, we want to only print the line if it's the first line of the file. Keeping the for loop, edit the pseudocode, inserting a step that asks which line position it is numerically in the file.

ANSWER:

First, we need to SET the input file
Second, FOR every line in the open file
  IF the first line
    PRINT the line
  END IF
END FOR

### SET the input file

Much like how we reused the pseudocode of the last module, we'll be able to reuse much of the code from the last module. Do you think that defining a variable with the input file name is one of those reusable steps? 

ANSWER: Yes, it is

### FOR every line in the open file

Let's again focus on building the `for` loop structure by considering the 2 components of the loop used in the first module

1. The `for` statement

  Do you think that the `for` statement from the last module is the best pattern for this problem? Consider that the `for` statement in the last module only provided you access to each line (or item) in the file (or collection of items), but did not provide you any information on which line position numerically it was in the file.
  
  ANSWER: We should use the third `for` statement pattern instead which provides both the item and the item's position or index.

### IF the first line and PRINT the line

2. The body of the `for` loop
  
  Considering that the body of the for loop is where the pseudocode was added, we also need to add to the body of the `for` loop. However, does the code that we already have from the first module still work well for this module?
  
  ANSWER: Yes, it does.
  
  What can we use to see if the index or position of the line is the first line in the file? 
  
  ANSWER: We can use a conditional and logical expression such that we'll PRINT the line, but only if it's the first line in the file.
  

## Building the code

**Create a new Python script**

### SET the input file

To SET what the input file is, we will use the variable assignment code from the first module. Within your Python script, write that variable assignment expression. 

ANSWER:

```python
filename = "random_snippet.vcf"
```

### FOR every line in the open file

Consult the notes on the third pattern of the `for` statement and edit the first modules `for` statement code to meet the needs of this module. Within your python script, write the revised `for` statement.

ANSWER

```python
for i, line in enumerate(open(filename)):
```


### IF the first line

Next, edit the body of the `for` loop from the first module such that it asks if the line is the first line. Consult your notes on indexing to see what integer you want the index to be equal to (e.g., 0 or 1). Write the conditional and logical expression code within your Python script within the `for` loop body.

ANSWER:

```python
  if i == 0:
```

### PRINT the line

Finally, reuse the code from the first module to print the line (when it is the first line). Add this `print()` statement to your Python script, indenting correctly under the conditional statement.

ANSWER:

```python
    print(line.strip('\r\n'))
```

Within your Python script, you should have the four lines of code together which makes our complete indended goal code -- code that prints just the first line in a file.

**Use the command line to run the Python script and look at the output.**

## Complete Intended Goal Code


```python
filename = "random_snippet.vcf" #SET the input filename
for i, line in enumerate(open(filename)): #FOR every line in the open file
  if i == 0: #IF the first line
    print(line.strip('\r\n')) #PRINT the line
```

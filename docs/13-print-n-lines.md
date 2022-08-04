

# Applied Python Exercise 5

## Goal -- print a default number of lines from the beginning of an input file if another number isn't specified as an additional input

Write Python code that recreates the Bash tool `head`, displaying a default number of lines in an input file if a specific number of lines isn't specified.

## Learning Objectives

After going through this chapter, students should be able to:

* State the sub-steps needed to meet the coding goal
* Use the following datatypes, structures, and fundamentals to meet the coding goal:
  * importing modules
  * variable assignment
  * list indexing
  * list length
  * integer conversion
  * opening a file
  * for loop
  * logical expression
  * conditional statement
  * printing output
  
## Coding Blueprint

Let's again start with and edit the pseudocode from the previous chapter to meet the needs of this chapter

Previous chapter's pseudocode:

First, we need to SET the input file <br />
Next, we need to SET the desired number of displayed lines <br />
Then, FOR every line in the open file <br />
&nbsp;&nbsp;  IF a desired line (by its numerical position) <br />
&nbsp;&nbsp;&nbsp;&nbsp;    PRINT the line <br />
&nbsp;&nbsp;  END IF <br />
END FOR <br />

We do want to edit this past pseudocode, adding some clarity to how we're going to SET the desired number of displayed lines. Specifically, we're either setting the desired number as a user-specified input, or as a default number if no user-input is given. Edit that line of the pseudocode, expanding it with conditional expression language to reflect this change in the program behavior.

***
<details><summary> ANSWER: </summary>

First, we need to SET the input file <br />
Next, IF the user-specified a desired number of lines to display <br />
&nbsp;&nbsp;  THEN we need to SET the desired number of displayed lines <br />
END IF <br />
OTHERWISE <br />
&nbsp;&nbsp;  THEN we need to SET the desired number of displayed lines to a default <br />
END OTHERWISE <br />
Then, FOR every line in the open file <br />
&nbsp;&nbsp;  IF a desired line (by its numerical position) <br />
&nbsp;&nbsp;&nbsp;&nbsp;    PRINT the line <br />
&nbsp;&nbsp;  END IF <br />
END FOR <br />

</details>
***

## Building the code

**Create a new Python script**

### Usage statement and module importing

We again want to import the `sys` module so that users specify the input file and can specify the desired number of lines (if they want). Within your new Python script, import the module. 

We'll want to update our usage statement comment to reflect that only the filename is required. Adding brackets (`[`, `]`) around an argument description in the usage statement is the preferred way to say that the argument is not required as input. Within your Python script, update your previous usage statement from the fourth Applied Python Exercise chapter to show that the number of lines to display is no longer a required argument.

***
<details><summary> ANSWER: </summary>


```python
#USAGE: python scriptname.py input_filename [number_lines_to_display]
import sys
```

</details>
***

### SET the input filename

Within your Python script, set the filename variable to be equal to the first command line argument like you did in fourth Applied Python Exercise chapter.

***
<details><summary> ANSWER: </summary>


```python
filename = sys.argv[1]
```

</details>
***

### IF the user-specified a desired number of lines to display

In the previous Applied Python Exercise chapter, we wanted the second command line argument to be the number of lines that would be displayed by the program. In this chapter, we want to see if the user provided a desired number of lines as a command line argument. To do this, let's consider what information we know and what variables/objects/functions are available to us.

Command-line arguments are stored in the `sys.argv` object which we already said is a list. We've discussed previously that lists have a length associated with them where their length is equal to the number of elements in the list. Given that `sys.argv[0]` is always the name of the script, if no arguments are passed to a script when calling it from the command line, the length of the list would be 1. If only one argument is passed, then the length would be 2. And finally, if two arguments are passed, then the length would be 3. Consult the notes on the `len()` Python built-in function, and write code in your Python script that checks if the length of the `sys.argv` list suggests that the user specified a number of lines to display.

***
<details><summary> ANSWER: </summary>


```python
if len(sys.argv) > 2:
```

</details>
***

### THEN SET the desired number of lines

If the user did specify the number of desired lines, we want define the variable for the desired number of lines to equal this value. Within your Python script and indented under the conditional you've just written, follow the method we used in the fourth Applied Python Exercise chapter to define this variable.

***
<details><summary> ANSWER: </summary>


```python
  n_lines = int(sys.argv[2])
```

</details>
***

### OTHERWISE 

If the user didn't provide a specified number of lines, then we want alternate behavior in how we define the desired number of lines variable. Consult the notes on conditionals to see how to specify what structure should be used to specify behavior for when the `if` conditional evaluates to False. Within your Python script, aligned with the `if`, add the appropriate conditional statement.

***
<details><summary> ANSWER: </summary>


```python
else:
```

</details>
***

### THEN SET the desired number of lines to a default

In the third Applied Python Exercise chapter, we previously hardcoded the number of lines we wanted to display. Within your Python script, indented under the `else` statement, write code that defines the default number of lines as 10.

***
<details><summary> ANSWER: </summary>


```python
  n_lines = 10
```

</details>
***

Now that we've managed to set the input file and the desired number of lines to values that are specified by the user or a default value, we can reuse the rest of the code for the next three steps that we used in the previous two Applied Python Exercise chapters. 

### FOR every line in the open file

To loop through every line in the open file, use the `for` statement structure from the second, third, and fourth Applied Python Exercise chapters. Write this line of code within your Python script.

***
<details><summary> ANSWER: </summary>


```python
for i, line in enumerate(open(filename)):
```

</details>
***

### IF a desired line (by its numerial position)

To ask if the line is one of the desired beginning lines, use the conditional statement structure from the third and fourth Applied Python Exercise chapters. Write this line of code within your Python script, indenting correctly under the `for` loop statement.

***
<details><summary> ANSWER: </summary>


```python
  if i < n_lines:
```

</details>
***

### PRINT the line

Finally, reuse the code from the first four Applied Python Exercise chapters to print the line, adding this `print()` statement indented correctly under the conditional within your Python script.

***
<details><summary> ANSWER: </summary>


```python
    print(line.strip('\r\n'))
```

</details>
***

Within your Python script, you should have the ten lines of code together which makes our complete intended goal code -- code that recreates the Bash tool `head` -- a program that prints a user specified number of lines from the beginning a user-specified input file, unless no specific number of lines is specified, then it prints a default of 10 lines.

**Use the command line or the Run button in the online interface to run the Python script and look at the output.**
  
## Complete Intended Goal Code

***
<details><summary> ANSWER: </summary>


```python
#USAGE: python scriptname.py input_filename [number_lines_to_display]
import sys #import module
filename = sys.argv[1] #SET input filename
if len(sys.argv) > 2: #IF user-specified number of lines provided
  n_lines = int(sys.argv[2]) #SET the desired number of lines
else: #OTHERWISE
  n_lines = 10 #SET the desired number of lines to a default
for i, line in enumerate(open(filename)): #FOR every line in the open file
  if i < n_lines: #IF a desired line by its numerical position
    print(line.strip('\r\n')) #PRINT the line
```

</details>
***

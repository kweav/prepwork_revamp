

# Applied Python Exercise 6

## Goal -- recreate the Bash tool `head` in Python; adding some new functionality that skips header lines

Write Python code that recreates the Bash tool `head`, displaying a default number of lines in an input file if a specific number of lines isn't specified; but extend the tool so that it skips header lines (specifically, for this example, lines that start with a pound sign (`#`)).

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
  * initializing a counter variable before a for loop
  * updating a counter variable within a the body of a for loop
  * for loop
  * chaining logical expressions
  * looking at the character a line starts with
  * conditional statement
  * printing output
  
## Coding Blueprint

Let's again start with and edit the pseudocode from the previous chapter to meet the needs of this chapter.

Previous chapter's pseudocode:

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

We do want to edit this past pseudocode, adding a condition that should be true before we print a line. Edit that line of the pseudocode, expanding it with logical expression language to reflect this change in the program behavior.

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
&nbsp;&nbsp;  IF a desired line (by its numerical position) AND NOT a header line (line doesn't start with a pound sign `#`) <br />
&nbsp;&nbsp;&nbsp;&nbsp;    PRINT the line <br />
&nbsp;&nbsp;  END IF <br />
END FOR <br />

</details>
***

We also can no longer assume that the numerical position of the line within the file corresponds to the number of lines that have been printed since we're filtering out the header. Therefore, we need to track the number of lines that have been printed. Add two lines to the pseudocode that will help you do this, and further edit the conditional that we check before printing a line. As a hint for those, this is the first time we'll be using the third optional component of a `for` loop: initializing a variable before the `for` loop (and then subsequently) updating it within the body of the loop.

***
<details><summary> ANSWER: </summary>

First, we need to SET the input file <br />
Next, IF the user-specified a desired number of lines to display <br />
&nbsp;&nbsp;  THEN we need to SET the desired number of displayed lines <br />
END IF <br />
OTHERWISE <br />
&nbsp;&nbsp;  THEN we need to SET the desired number of displayed lines to a default <br />
END OTHERWISE <br />
SET counter of number of lines that have been displayed to 0 <br />
Then, FOR every line in the open file <br />
&nbsp;&nbsp;  IF a desired line (counter hasn't reached desired number of lines) AND NOT a header line <br />
&nbsp;&nbsp;&nbsp;&nbsp;    PRINT the line <br />
&nbsp;&nbsp;&nbsp;&nbsp;    SET counter to ADD one <br />
&nbsp;&nbsp;  END IF <br />
END FOR <br />

</details>
***

## Building the code

**Create a new Python script**

### Usage statement and module importing

The usage statement and module importing from the previous Applied Python Exercise chapter are still accurate for this chapter, so go ahead and reuse the usage and import statements from the fifth Applied Python Exercise chapter within your new Python script.

***
<details><summary> ANSWER: </summary>


```python
#USAGE: python scriptname.py input_filename [number_lines_to_display]
import sys
```

</details>
***

### SET the input filename

Within your Python script, set the filename variable to be equal to the first command line argument like you did in fourth and fifth Applied Python Exercise chapters.

***
<details><summary> ANSWER: </summary>


```python
filename = sys.argv[1]
```

</details>
***

### IF the user-specified a desired number of lines to display

Within your Python script, set up the conditional statement structure like you did in the fifth Applied Python Exercise chapter to check if the user has provided a desired number of lines to display.

***
<details><summary> ANSWER: </summary>


```python
if len(sys.argv) > 2:
```

</details>
***

### THEN SET the desired number of lines

Within your Python script, use the variable assignment statement from the fourth and fifth Applied Python exercise chapters to define the desired number of lines as specified by the user, indenting under the conditional statement.

***
<details><summary> ANSWER: </summary>


```python
  n_lines = int(sys.argv[2])
```

</details>
***

### OTHERWISE 

Use the alternate conditional statement structure from the fifth Applied Python Exercise chapter to start defining the alternate behavior we will want (in how we define the desired number of lines variable in cases where the user didn't specify a specific value). Put this statement in your Python script.

***
<details><summary> ANSWER: </summary>


```python
else:
```

</details>
***

### THEN SET the desired number of lines to a default

Use the alternate variable assignment statement from the fifth Applied Python Exercise chapter to define the desired number of lines variable if the user didn't specify a specific value. Put this statement in your Python script, indented correctly.

***
<details><summary> ANSWER: </summary>


```python
  n_lines = 10
```

</details>
***

### SET counter of number of lines that have been displayed to 0

Because we no longer assume that the numerical position of the line within the file corresponds to the number of lines that are  printed, since we're filtering out the header lines, we need to define a counter variable we can use to track the number of lines that we print. When first initializing this variable, we haven't printed any lines. Therefore, you want to set the counter variable equal to the value of zero. Do this within your Python script.

***
<details><summary> ANSWER: </summary>


```python
counter = 0
```

</details>
***

### FOR every line in the open file

Next, we no longer need to track the position of the line in the file. We only want to work with each line line-by-line in the open file. Therefore, we can go back to the `for` loop statement that we used in the first Applied Python Exercise chapter. Add the appropriate `for` loop statement to your Python script.

***
<details><summary> ANSWER: </summary>


```python
for line in open(filename):
```

</details>
***

### IF a desired line (because counter hasn't reached the desired number of lines) and NOT a header line

Let's break this task down into two separate conditions and then chain the conditions together into one conditional expression.

First, we want to check if the value of the counter is less than the number of desired lines. Write an expression that will evaluate to a boolean variable answering whether an integer is less than another integer. Use the appropriate variable names that refer to the integer variable we're interested in.

***
<details><summary> ANSWER: </summary>


```python
counter < n_lines
```

</details>
***

Next, we want to verify that the specific line we're working with is not a header line. Specifically, does the line not start with a pound sign (`"#"`)? Consult the Python notes on negating a boolean expression and checking if a string variable starts with a specific character. Then write an expression that will evaluate to a boolean variable answering whether the line does not start with the pound sign (`"#"`). Make sure to use the appropriate variable name in the expression.

***
<details><summary> ANSWER: </summary>


```python
not line.startswith("#")
```

</details>
***

Now, chain the expressions together within your Python script to form a chained conditional expression, within the body of the `for` loop, indented correctly under your `for` loop statement. Recall that you want both booleans to be True for the conditional's body (printing the line) to be executed.

***
<details><summary> ANSWER: </summary>


```python
  if counter < n_lines and not line.startswith("#"):
```

</details>
***

### PRINT the line

Finally, reuse the code from the first five Applied Python Exercise chapters to print the line, adding this `print()` statement indented correctly under the conditional within your Python script.

***
<details><summary> ANSWER: </summary>


```python
    print(line.strip('\r\n'))
```

</details>
***

### SET counter to ADD one

If we were to end writing the program now, our script would print every line in the file that wasn't a header line. What can we do to avoid this and only print the specific number of lines we want?

***
<details><summary> ANSWER: </summary>

To avoid this, we have to update the counter every time we print a line so we have an accurate count of the number of lines we've printed.
</details>
***

Write a variable assignment statement within your Python script that updates the value of the counter variable, adding one to it. Make sure it is appropriately indented in line with the print statement under the conditional statement.

***
<details><summary> ANSWER: </summary>


```python
    counter = counter + 1
```

</details>
***

Within your Python script, you should now have the twelve lines of code together which makes our complete intended goal code -- code that prints a user specified number of lines from the beginning of a user specified input file, skipping header lines that begin with a pound sign (`#`).

**Use the command line or the Run button in the online interface to run the Python script and look at the output.**

## Complete Intended Goal Code

***
<details><summary> ANSWER: </summary>


```python
#USAGE: #USAGE: python scriptname.py input_filename [number_lines_to_display]
import sys #import module
filename = sys.argv[1] #SET the input filename
if len(sys.argv) > 2: #IF user-specified number of lines provided
  n_lines = int(sys.argv[2]) #SET the desired number of lines
else: #OTHERWISE
  n_lines = 10 #SET the desired number of lines to a default
counter = 0 #SET counter of number of lines that have been displayed ot 0
for line in open(filename): #FOR every line in the open file
  if counter < n_lines and not line.startswith("#"): #IF the counter hasn't reached the max number of desired lines AND NOT a header line
    print(line.strip('\r\n')) #PRINT the line
    counter = counter + 1 #SET counter to add one
```

</details>
***

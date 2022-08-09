

# Applied Python Exercise 1

## Goal -- Print every line in a file

Write Python code that works towards recreating the Bash tool `head`, displaying every line in a file: `random_snippet.vcf`

## Learning Objectives

After going through this chapter, students should be able to: 

* State the sub-steps needed to meet the coding goal
* Use the following datatypes, structures, and fundamentals to meet the coding goal:
  * variable assignment
  * strings
  * opening a file
  * for loop
  * printing output

## Coding Blueprint

Within this chapter, you will write code that displays every line in an input file. To complete this goal, consider the most basic tasks that would be required.

First, we need to SET the input file<br />
Second, FOR every line in the open file<br />
&nbsp;&nbsp;PRINT the line<br />
END FOR<br />

### SET the input file

Let's focus on that first step: SET the input file. One important thing when breaking down tasks into smaller, manageable steps is asking yourself what information is available in your script, and what information you need to define or store in variables. The filename is something that will need to be assigned to a variable so that it is available information. 

### FOR every line in the open file ...

Let's focus on the FOR portion of the pseudocode now, specifically building the `for` loop structure by considering each of the 3 components discussed earlier:

1. The `for` statement

  Which `for` statement pattern best fits the task you want to accomplish of printing every line in the file? We'll see as we build the code that the first pattern, `for line in file`, will work very well for this task because all we need is to work with the items (lines) contained in a collection (the file) item-by-item.
  
  However, we will have to slightly edit this pattern to make sure we're working with the contents of the file, and not the contents of the string variable storing the filename. If we don't open the file and the `file` variable refers to the string of the filename, then `line` will just be the letters of the filename one at a time. Therefore, we'll want to make sure that `file` refers to the open file.

### PRINT the line

2. The body of the `for` loop

  We've already defined this well - we want to PRINT the line.

3. Any variable initialization before the `for` statement

  Is there any need to initialize a variable before the `for` loop that you will edit within the body of the loop? In this case, because we're printing every line in the file, there's no need to initilalize a variable beforehand.

## Building the code

**Create a new Python script**

### SET the input file

To SET what the input file is, we will create a variable which stores the string of the filename for the input file.

Consult the notes from earlier, specifically variable assignment, to SET a variable equal to the input file. Within your Python script, write a line of code that does this. 

***
<details><summary> ANSWER: </summary>


```python
filename = "random_snippet.vcf"
```

</details>
***

### FOR every line in the open file

Then, that variable is just storing the name of the file. The actual file contents, or the lines of the file, aren't available to Python until the file is opened. Consult the notes on the built-in Python function `open()` and use the determined structure of the `for` statement from the pseudocode section above to open the file and begin the `for` loop architecture. Within your Python script, write a line of code that does this.

***
<details><summary> ANSWER: </summary>


```python
for line in open(filename):
```

</details>
***

### PRINT the line

Now that we have the first component of the `for` loop, we can write the body of the `for` loop so that each line is printed as output. Consult the notes on the `print()` function indenting the body of the `for` loop under the `for` statement. Within your Python script, write a line of code that does this.

***
<details><summary> ANSWER: </summary>


```python
  print(line)
```

</details>
***

If we were just to use the code above, there would be a blank line printed at the end of each line from the file. We can remove the blank lines from the output by using another built-in Python function specifically `strip()`. Newline characters which apepar as blank lines in the output are either `"\n"` or `"\r"` within bioinformatic files.  Since we're not certain which of these our input file has, we'll strip both of these characters off the end of each line using `strip("\r\n")`, specifically telling the `strip` function to remove both of those characters. We can tell the `strip` function to remove those characters from each line using the following syntax: `line.strip("\r\n")`. Use of this function with this syntax will remove or suppress those blank lines in the output. Edit the line of code within your Python script to do this.

***
<details><summary> ANSWER: </summary>


```python
  print(line.strip('\r\n'))
```

</details>
***

Finally, within your Python script, you should have the three lines of code together which makes our complete intended goal code -- code that prints every line in a file.

**Use the command line or the Run button in the online interface to run the Python script and look at the output.**

## Complete Intended Goal Code

***
<details><summary> ANSWER: </summary>


```python
filename = "random_snippet.vcf" #SET the input filename
for line in open(filename): #FOR every line in the open file
  print(line.strip('\r\n')) #PRINT the line
```

</details>
***

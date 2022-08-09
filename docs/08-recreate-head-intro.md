

# Applied Python Exercise Outline

## Goal

Outline recreating and extending the bash tool `head` in Python

## Learning Objectives

After going through this chapter, students should be able to:

* Explain what the tool `head` does
* List the different tasks that make up `head`'s main function
* State what the assignment is following these chapters

## Intro

One of the strengths of Python that was previously mentioned is its versatility and how it can be used to extend and visualize the results of analyses performed with the command line. Therefore, the overarching goal of these prepwork chapters is to recreate and extend the functionality of a common bash tool using Python. These chapters will guide you through recreating `head`, adding some functionality outside of the tool's basic behavior.

As a reminder, `head` is used to display the first n number of lines in a file. If no number is specified, the tools defaults to displaying 10 lines.

## Coding Blueprint

In these chapters, you will be guided through writing code that does each of the following to recreate `head`:

1. displaying every line in an input file
2. displaying just the first line in an input file
3. displaying a specified number of lines from the beginning of an input file
4. displaying a specific number of lines from the beginning of an input file, specifying the number outside of the code itself as an additional input
5. displaying a default number of lines from the beginning of an input file if another number isn't specified as an additional input

Then, you will be guided through writing code that extends the recreated `head` program such that additionally it can

6. skip a file header before displaying the output

## Final Assignment

Finally, you will be asked to take your recreated `head` program and edit it such that it would `tail` an input file instead.

Each of these 7 tasks will focus on using a specific python fundamental or data type like for loops, conditionals, or lists. Each guided chapter will help you to break the task into small manageable pieces, write pseudocode for these smaller tasks, and then build the code. For the final task, you will be asked to both pseudocode and code on your own.

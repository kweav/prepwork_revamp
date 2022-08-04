

# Pseudo-code

## Goal

Understanding how to break a problem down into basic steps that can be translated into code

## Learning Objectives

After going through this chapter, students should be able to:

* Explain the purpose of pseudocode
* Dissect a problem into basic building blocks
* Verbalize the goal of each step

## What is pseudocoding?

Pseudocoding is a way of informally describing the logic behind solving a potentially complicated task by breaking it down into individual steps and explaing the steps in plain language.

An example of pseudocode for the task of assigning pass/fail grades to students in a class:

```
SET students          ## Add students to a variable
SET grades            ## Add student grades to a variable
INITIALIZE outcomes   ## We also need somewhere to store the results
SET cutoff            ## We need some passing criteria
FOR each student in students ## We need to take the same action for each student
    IF student's grade is greater than or equal to cutoff
        then ADD 'pass' to outcomes  ## Update the outcomes
    OTHERWISE
        add 'fail' to outcomes
    END IF
END FOR
```

You'll notice that all of the code that is to be repeated for each student is indented to indicate what is included in the repeated block. The same is true under the conditional statement. This helps us keep track of what steps constitute a subtask when code is repeated or run only under certain conditions. There is also the challenge of matching up the grade with the student. This can be accomplished in many different ways and will vary with what language is being used. Here, we keep it language-agnostic.

## Why pseudocode instead of just writing a script?

The advantage of writing pseudocode first rather than just writing a script in your programming language of choice is that it is

* Helps transition novice programmers into thinking through the logic needed to solve a task
* Easier to breakdown and express tasks in natural language
* Not dependent on language-specific syntax

Even once you become a proficient programmer and feel comfortable writing code directly, more complex tasks can be facilitated by pseudocoding the task. This also makes breaking code into discrete parts for collaborative coding much easier and can be used to talk about expected outputs and inputs for each subtask.

## Good practices

While there is no set of standards for pseudocoding, there are ways to make it more effective. The most important thing you can do is to be consistent. When you pick a term (e.g. repeat or set), make sure that it has the same meaning each time you use it. It can be helpful to put these action words in all caps to highlight them. Some general rules for effective pseudocoding are:

* Make the first word the key action for the step and capitalize
* Only list one step per line
* Indent to show hierarchy of actions and improve readability
* End multiline blocks of code with `END`
* Make your pseudocode programming language independent
* Keep it simple, concise, and readable

## Exercise

Let's try a more complicated example to practice. Let's say our task is to take a text file and return the line number of any line that contains a keyword. However, we want to ignore any comment line in the file, denoted by a "#" as the first character.

First, we'll need a way to keep track of the line numbers

```
SET counter to 0
```

Next, we need step line by line through the file

```
FOR each line in the file
```

Then we need to check if the line is not a comment

```
    IF the line does not begin with #
```

Next, we need to know if the keyword appears in the line

```
        IF the line contains the keyword
```

Finally, if both conditions are true, we need to report the line number

```
            PRINT counter
```

Now we can close the conditional statements

```
        END IF
    END IF
```

Now we need to advance our counter since we're about to move to the next line

```
    INCREMENT counter by 1
```

Finally let's close the for loop

```
END FOR
```

Putting it all together, we have the following pseudocode

```
SET counter to 0
FOR each line in the file
    IF the line does not begin with #
        IF the line contains the keyword
            PRINT counter
        END IF
    END IF
END FOR
```

And we're done!

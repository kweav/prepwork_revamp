

# Basic bash

## Goal

A basic grasp of navigating bash and executing a python script

## Learning Objectives

After going through this module, students should be able to:

* Move between directories in bash
* Run a python script from within bash
* Open a "man page"
* Explain what the tool `head` does

## Resources

* [Bash syntax cheatsheet](http://bxlab.github.io/cmdb-bootcamp/cheatsheet/unix.html)

## Navigation

In order to move around the filesystem, you only need the command `cd`, short for change directory. There are also 3 special notations for navigation, `~`, `.`, and `..`. These represent your home directory, your current directory, and you current parent directory, respectively. So,assume the following directory structure.

```
/
	Users/
		cmdb/
			Documents/
			Movies/
		guest/
	Lib/
		Some/
		Stuff/
```

If we were in the folder "cmdb", we would use `cd Documents` to move to the Documents folder. To get to the Users folder, we would use `cd ../`. You can also chain multiple moves together. To move from the cmdb to the Stuff folder, you would use `cd ../../Lib/Stuff`. We can also see where we are with the `pwd` command, short for "print working directory".

## Running a python script

In order to run a python script in bash (i.e. locally on your own machine), you need to use the python interpreter, the name of the script, and any arguments (additional information) being passed to the script.


```bash
python myscript.py
python myscript.py arg1 arg2
```

This does not apply if you are using the online Python resources.

## The head tool

There are many bash tools, but right now we will focus on one, `head`. This tool takes reads through a text file, printing out the first *n* lines, where *n* is an arbitrary number passed as an argument with `-n`. If *n* is not specified, `head` defaults to 10.

If you were to forget the default number of lines or need more information about `head`, you can look at the manual page for it, aka its "man" page. To do this, type `man head`. You will get a text manual with a general description of the tool, an explanation of all of the possible arguments, and more. You can navigate with the up and down arrows. To move more quickly, hold down *fn*. To exit, push *q*. 

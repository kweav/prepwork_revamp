

# Logistics

## Goal

Below we describe two ways you can complete these exercises:

* Online -- Work "on the Cloud" using your laptop, browser, and internet connection
* Your Own Computer -- Work "locally" with your own Python, text editor, and 

During your first year in the CMDB program, you will be provided with a laptop with everything you will need preloaded and configured already for you. So there is no need to use online interface resources in the actual class and by the end of the actual course, you will be able to run Bash commands and Python scripts from whatever machine you are working on, including accessing local files. 

Before the course, rather than expecting you to install or configure any software or Python on your local machine (which is a hassle), we are recommending specific online interfaces that will be useful for these prepwork chapters as you are introduced to and learning bash and Python fundamentals.

If you would like to practice creating and running scripts to most closely mirror the experience you will have during the bootcamp, then we recommend that you use the local option for the Python chapters as much as possible.

## Online

### Online Bash

There is [an online bash interface resource](https://sandbox.bio/playground) which you will have to use for Chapter 4. It will not help you in running Python scripts for the later chapters.

This online interface contains a black window which is the bash interface with which you will be interacting.

### Online Python

There is [an online Python interpreter](https://www.online-python.com) which we recommend you use in Chapters 7-10 to interact with examples For Chapters 12-18, if you are not familiar with navigating your filesystem from the command line (which we would expect you may not be), we highly recommend making use of the online interface. 

The online interface includes both a text editing interface to write your scripts in. You can create a new script for each example (Chapters 7-10) and each exercise (Chapters 12-18) by clicking the plus sign (`+`) next to the tab with the filename "main.py". 

You can save any script using the "disk" icon above the editor.

Below the editor is a "Run" button that executes your code, printing any output in the window below the editor. 

You will need to load the external file `random_snippet.vcf` to make it accessible to your script with the "folder" icon above the editor. 
Finally, there is a text field to the right of the "Run" button that says "Command Line Arguments" that you can use to pass arguments to your script. You will need this for Chapters 15-18.


## Local

### Macs

If you are using a Mac to complete the prepwork, you should be in good shape. Python should be already installed on your computer. You can verify this using Terminal which should also already be installed on your Mac. Open Terminal by typing "Terminal" in the Spotlight search. This will bring up a command line terminal. You can verify that Python is installed by typing `which python` in the opened command line terminal, then hit `<return>`. If the result is a filepath ending with some version of 'python', you are all set. 

You will also need a plain text editor such as TextEdit, TextMate, Sublime, etc. (NOT a wordprocessor like Word, Pages, etc.). TextEdit should already be installed. You will want to type Python code within files from the plain text editor of choice. 

You will then save those files and run them from terminal. Navigating to the folder where you saved the file (see Basic Bash Chapter 4 for more details), you then run the script like so:


```bash
python scriptname.py
```

If the script has any input files or arguments specific to it (more details in the Python Fundamentals Chapter 11 and Applied Python Exercise Chapters), you would run the script like so:


```bash
python scriptname.py inputfile argument
```

If for some reason Python is not installed or for any reason you would prefer to work with the online resources, jump back to the [Online Python](#Online-Python) section.

### Windows

Unfortunately, Python does not come pre-installed on the Windows OS. You have a couple of options. First, you can install it by downloading the installer from [here](https://www.python.org/downloads/windows/). Select whatever Python3 version you want (I would go with 3.10). Then follow the instructions when you run the downloaded installer. Finally, verify that Python was successfully installed by opening `Command Prompt`, typing `python -V`, and hitting `<Enter>`. This should tell you what version of Python is installed on your system. In addition to Python and Command Prompt, you will also need a plain text editor like Notepad, Sublime, etc. (Not a wordprocessor like Word.)

If you would prefer not to install Python, or for any reason you would prefer to work with the online resources, jump back to the [Online Python](#Online-Python) section.

### Unix

If you are on a Unix system, Python should be pre-installed. If not, chances are that you are comfortable installing it yourself using `apt-get`, `dnf`, or whatever the appropriate package manager is for your distro. You will also need a terminal and plain text editor.

If for some reason Python is not installed or for any reason you would prefer to work with the online resources, jump back to the [Online Python](#Online-Python) section.


## When do you need to use Bash and Python in this prepwork?

### Bash

Chapter 4 requires that you use the [online bash sandbox](https://sandbox.bio/playground) resource discussed above. 

### Python

Chapters 7-10 will describe fundamentals of working with Python to code. You are welcome, but not required, to use Python for any of the examples in those sections. If you choose to follow along using Python, you will want to copy and paste or type examples within a Python script or the Python text editor available in the [online Python interface](https://www.online-python.com) (described earlier). Then you will want to run the code to see the output (either with Terminal, if working locally, or with the Run button in the online interface). Additionally, you may want to edit/remix/rewrite the code to see how changes affect the behavior and output. 

Chapters 12-18 will require you to use Python as you work through guided examples of pseudocoding and writing code in Python. Specifically, you will be asked to create a new Python script every single chapter. Chapters 12-18 will also require you to run your script to verify that it works as intended. You will run the script either with Terminal or with the Run button in the online interface. 
We recommend using the online Python editor if you are at all uncomfortable with creating, saving, and running Python scripts locally.

Even though you are creating a new script every chapter, you will only be asked to turn in the final script (from Chapter 18). You are not required to turn in any pseudocode from any chapter.   

## Submitting your final script

Once you have completed the last Applied Python Exercise Chapter (Chapter 18) of this prep work, you will need to submit the script you have produced (the tail script). To do this, please save it, naming it LASTNAME_tail.py, and then email it to Kate Weaver at kweave23@jhu.edu.

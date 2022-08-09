

# Fundamentals of Bash

## Goal

A fundamental grasp of navigating bash and using some common commands

## Learning Objectives

After going through this chapter, students should be able to:

* Move between directories in bash
* Examine folder contents
* Move and copy files
* Run the `head` and `tail` commands
* Describe what a usage statement is and print it for `head` and `tail`
* Explain what a "man page" is
<!--
cd, pwd, ls, mv, cp, head, tail, --help, man
-->

## Resources

<div class = "notice">

This chapter will be performed online. 

UPDATE based on issue reported by students. In order to load the sample data from the Terminal Basics tutorial provided by this website, please follow these steps before beginning this chapter:

  1. [Load this link](https://sandbox.bio/playground)
  2. Click on "Tutorials" at the top right of the screen, followed by "Terminal Basics" in the dropdown menu.
  3. In the black window with the prompt `guest@sandbox$`, type `ls`
  3. Hit `<Enter>` or `<return>`.
  4. Click on "Playgrounds" at the top right of the screen, followed by "Command Line" in the dropdown menu.

</div>
    
* Use of this online resource avoids issues that can arise from people using different operating systems and having trouble finding the terminal on their own computers. Once you have loaded the Command Line Playground, you should see a black window with the prompt `guest@sandbox$`. This is the bash interface.
* The [Bash syntax cheatsheet](http://bxlab.github.io/cmdb-bootcamp/cheatsheet/unix.html) may be useful to refer to, especially throughout the course.

## Navigation

When you use bash, your system is located or working within a single folder (which we refer to as a directory) at any given time. Whatever directory you are in is known as the "working directory". You can always see what directory you are working in with the command `pwd`, which stands for "print working directory". To run the command, simply type "pwd" into the terminal window and press `<Enter>` or `<return>`.

What directory name was printed out?

***
<details><summary> ANSWER: </summary>

```
/shared/data/
```
</details>
***

You can see that not only the name of the working directory was printed but also the name of every parent directory all the way up to the **root**, the left-hand "/", that contains all files and directories on the computer. This nested list of directories is called the "path". In this case, it is an **absolute** path because it tells us how to get to this directory from the root. 

In order to move to another directory, we can use the command `cd`, which stands for "change directory". If we wanted to move to the "shared" directory, we could type the `cd` command and the path to that directory.


```bash
cd /shared
```

Once you have done this, verify that you are in the "shared" directory using the `pwd` command. In this case, "shared" is the **parent** directory of "data".

If we had to type a long directory path every time we wanted to change directories, it would be very tedious, especially with highly nested directories. Luckily, there is another way to navigate using **relative** paths. This means giving directions based on your current working directory. So, to move back to the "data" directory, instead of typing out the full path, we will simply give the directory name since it is located in our working directory.


```bash
cd data
```

But what about going back to the "shared" directory? To do that, we need to use the special notation ".." which means the parent of a directory. So, to go back to the "shared" directory, use the following command.


```bash
cd ..
```

Use `pwd` to make sure that you are working in the "shared" directory now. If you are in the "shared" directory, you don't need to do anything until the paragraph "You can also give longer relative ...". If you aren't in the "shared" directory, review what commands you used by pressing the up arrow and compare your history of commands to the directions above. Pressing the up arrow will show you a command you used, most recent first. Pressing it again will show you the command you used before that. You can keep hitting the up arrow to see previous commands up to the number saved by bash, which defaults to 500. Pressing the down arrow will take you back through down the history back to the most recent command and finally the prompt with anything you have typed without pressing enter. Now use an absolute path to move back into the "shared" directory: `cd /shared`


```bash
cd /shared
```

You can also give longer relative paths by combining directions. To demonstrate this, let's move to a directory a little further down the file structure: `/shared/data/tutorials`


```bash
cd data/tutorials/
```
The directory "shared" which contains "data" also contains a directory named "home". To move there from the "tutorials" directory, use the relative path "../../home".


```bash
cd ../../home
```

Now, using a relative path, how can you get from `/shared/home` to a directory with files we will explore as we continue this lesson: `/shared/data/tutorials/terminal-basics`?

***
<details><summary> ANSWER: </summary>


```bash
cd ../data/tutorials/terminal-basics
```
</details>
***

Finally, one other special notation that you can use is **~** which stands for your home directory. You can always use `cd ~` to return to your home directory. You can also use relative paths from your home directory, like `cd ~/mystuff`, assuming that the "mystuff" directory exists. Home directories are computer specific, so we will discuss these more in the actual course when you have the CMDB-provided laptop.

## Examining directory contents

Navigating around the filesystem is only useful if we can also see what is in each directory. To do this, we use the command `ls` which stands for "list". Make sure you are in the "terminal-basics" directory, then type "ls" and press enter. What is the command output (i.e. the text printed in the terminal)?

***
<details><summary> ANSWER: </summary>

```
orders.tsv  ref.fa  ref.fa.bak
```
</details>
***

You should see three files in this directory. If there were any directories here, they would also be listed but there would be no way to tell the difference from the file names. To do that, we need more detail, which is provided by using the option "-l", which stands for "long". Let's see what extra detail is provided.


```bash
ls -l
```

```
total 14
-rw-rw-rw- 1 0 0 105054 Aug  3 10:53 orders.tsv
-rw-rw-rw- 1 0 0     45 Aug  3 10:53 ref.fa
-rw-rw-rw- 1 0 0     45 Aug  3 10:53 ref.fa.bak
```

The `ls -l` command tells us about file permissions and several other attributes (don't worry about these for now), the file size in bytes, the latest modification date, and the name. If you want easier to read file sizes, add the option "-h", which will print a "human readable" size format.

We can also use `ls` with a specific target, for example another directory. If we run the command on our parent directory, we can see what a directory looks like.


```bash
ls -l ..
```
```
total 1
drwxrwxrwx 1 0 0 4096 Aug  3 10:53 terminal-basics
```

The "d" at the left-hand side indicates that this is a directory, not a file.

## Moving and copying

What if we need to make a copy of a file or directory because we want to change something but keep a backup? To do this, we can use the `cp` command, short for copy. The command takes a target, the file you want to copy, and a destination. The destination can either be a directory (in which case the copied file will have the same name, but be located in a new additional location), or a new name (with or without a path). Unfortunately, the online terminal does not allow copying files, so do not type the following command, but if we wanted to copy the "ref.fa" file to "ref.fa.backup", we would do the following within the "terminal-basics" directory.


```bash
cp ref.fa ref.fa.backup
```

Then, if we were able to copy the file we could use the `ls` command to see the additional file in the directory.

Copying a directory is similar but because directories can contain other things that need to be copied as well, you need to include the option "-R" for recursive. Unfortunately, the online terminal also does not allow copying directories, so do not type any of the following commands. If the online terminal did allow copying directories, it would look something like this:


```bash
ls -l
```
```
total 1
drwxrwxrwx 1 0 0 4096 Aug  3 12:30 terminal-basics
```

```bash
cp -R terminal-basics new-basics
ls -l
```
```
total 2
drwxrwxrwx 1 0 0 4096 Aug  3 12:30 terminal-basics
drwxrwxrwx 1 0 0 4096 Aug  3 12:31 new-basics
```

We can also move and rename files using the `mv` command. Like copy, you give it a target file or directory and a destination. If the destination is an existing directory, the target is moved into that destination directory. If the destination is a file name (with or without a path), then the target is renamed (and moved if there is a path to a different directory than the target is in).

Unfortunately, the online terminal also does not allow moving but it does allow renaming. So, if we are in "terminal-basics" and want to rename our "ref.fa.bak" file to "my_ref.fa", what command would we use? What about moving it into the parent directory? And if we wanted to move it and give it the new name "my_ref.fa"?

***
<details><summary> ANSWER for renaming ref.fa.bak to my_ref.fa: </summary>
```
mv ref.fa.bak my_ref.fa
```  
</details>
***
  
***
<details><summary> ANSWER for moving ref.fa.bak to the parent directory: </summary>
```
mv ref.fa.bak ..
```  
</details>
***
  
***
<details><summary> ANSWER for moving it to the parent directory with a new name my_ref.fa: </summary>
```  
mv ref.fa.bak ../my_ref.fa
```
</details>
***

## Head and tail

There are many bash commands besides those we've seen: `pwd`, `cd`, `ls`, `cp`, and `mv`. Right now we will focus on two more, `head` and `tail`. The `head` command reads through a text file, printing out the first *n* lines, where *n* is an arbitrary number passed as an option with `-n`. If *n* is not specified, `head` defaults to 10 lines. `tail` is similar but instead of printing out the first *n* lines, it prints out the **last** *n* lines. Try both of these out on the file "orders.tsv".


```bash
head orders.tsv
```

What do you get for output from `head`? 

***
<details><summary> ANSWER: </summary>

```
id      num     item_name
1       1       Chips and Fresh Tomato Salsa
1       1       Izze
1       1       Nantucket Nectar
1       1       Chips and Tomatillo-Green Chili Salsa
2       2       Chicken Bowl
3       1       Chicken Bowl
3       1       Side of Chips
4       1       Steak Burrito
4       1       Steak Soft Tacos
```
</details>
***


```bash
tail orders.tsv
```

What do you get for output from `tail`?

***
<details><summary> ANSWER: </summary>
```
1831    1       Carnitas Bowl
1831    1       Chips
1831    1       Bottled Water
1832    1       Chicken Soft Tacos
1832    1       Chips and Guacamole
1833    1       Steak Burrito
1833    1       Steak Burrito
1834    1       Chicken Salad Bowl
1834    1       Chicken Salad Bowl
1834    1       Chicken Salad Bowl  
```  
</details>
***

If you were to forget the default number of lines or need more information about `head`, you can get more information from the *command help*, a detailed list of options and arguments and the usage statement. To see the command help for `head`, use the option "--help".


```bash
head --help
```
```
Usage: head [OPTION]... [FILE]...
Print the first 10 lines of each FILE to standard output.
With more than one FILE, precede each with a header giving the file name.

With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -c, --bytes=[-]NUM       print the first NUM bytes of each file;
                             with the leading '-', print all but the last
                             NUM bytes of each file
  -n, --lines=[-]NUM       print the first NUM lines instead of the first 10;
                             with the leading '-', print all but the last
                             NUM lines of each file
  -q, --quiet, --silent    never print headers giving file names
  -v, --verbose            always print headers giving file names
  -z, --zero-terminated    line delimiter is NUL, not newline
      --help     display this help and exit
      --version  output version information and exit

NUM may have a multiplier suffix:
b 512, kB 1000, K 1024, MB 1000*1000, M 1024*1024,
GB 1000*1000*1000, G 1024*1024*1024, and so on for T, P, E, Z, Y.
Binary prefixes can be used, too: KiB=K, MiB=M, and so on.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/head>
or available locally via: info '(coreutils) head invocation'
```

The first line shows the usage statement, a description of how to run the command. Options (information based with a preceeding identifier like `-n`) and arguments (information passed without a preceeding identifier like `-n`) are denoted as optional when enclosed by **[]** and required when enclosed by **<>** or nothing at all. The usage statement also provides the order of options and arguments required by the command.

Most commands and tools have a help statement and usage statement, but not all. In addition, we can get even more information by looking at the manual, or **man** page for a command. To do this, we would type `man head`. Unfortunately this is one more feature missing in this online terminal. A man page is a text manual with a general description of the tool, an explanation of all of the possible arguments, and more. You can navigate with the up and down arrows. To move more quickly, hold down *fn*. To exit, push *q*.

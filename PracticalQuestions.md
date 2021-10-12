m# Practical 1: Shell

## Goals
* Practice how to create, copy, move, navigate directories and files with `cd, ls, cp, mkdir`
* Learn how to run files (difference between `sh filename.sh` vs. `./filename.sh`)
* Learn how to use help for commands, for example for `ls` command to see different listing options
* Learn how to change permissions with `chmod` command
* Play with redirecting of input/output using angle brackets `>` and the pipe operator `|`

## Guide

## Working directories using `ls` `pwd` `cd`

### Listing contents with `ls`
- `ls` is a command that will list all the files in your *present working directory*. For example, if you type `ls` in your shell and press enter, it will return to you a list of all the files and folders that you can see in the Files tab of your window:
```
~/COMP100-2021F-Lab1$ ls
greeting.sh  PracticalQuestions.md     Quiz.md
main.py      StudyQuestions.md
main.sh      profiles2020
```

### Present Working Directory with `pwd`
- Now let's talk about the *present working directory*. You can check what your *present working directory* is by typing `pwd` in the shell and pressing Enter. You will see something like this:
```
~/COMP100-2021F-Lab1$ pwd
/home/runner/COMP100-2021F-Lab1
```
- This tells you *where* your shell is running ie: which folder(a folder can sometimes be referred to as a directory) you are currently in. As you saw in the previous part, typing `ls` will list you all the files in your *present working directory*. 

### Navigation with `cd`
- Now let's talk about navigation. Navigation is like double-clicking a folder. You can navigate into a folder, you can go back etc. For example, let's navigate into the `profiles2020` directory(a directory is like a folder). We can do this by typing `cd profiles2020` in the shell and pressing Enter. Now, if we type `pwd` and press Enter, we will see that our *present working directory has changed*:
```
~/COMP100-2021F-Lab1$ cd profiles2020
~/COMP100-2021F-Lab1/profiles2020$ pwd
/home/runner/COMP100-2021F-Lab1/profiles2020
```
- If we type `ls` and press Enter, you will now see the files in the `profiles2020` directory:
```
~/COMP100-2021F-Lab1/profiles2020$ ls
alara.txt  burak.txt  can.txt  dilan.txt
```

- Now let's navigate back. We do this by typing `cd ..` This should take you back to the `~/COMP100-2021F-Lab1` directory

### Relative and Absolute Paths
- In order to see what's inside the `profiles2020` directory, we navigated into it using `cd`( which changed the *present working directory*) then we used the `ls` command. 

- A faster way to do this is to directly use the command `ls profiles2020`. This tells the `ls` command to list contents of the `profiles2020` directory instead of the *present working directory*.
```
~/COMP100-2021F-Lab1$ ls profiles2020
alara.txt  burak.txt  can.txt  dilan.txt
```
- Any path you specify in this way is always with respect to your *present working directory*. This is called a *relative path*, because it specifies a directory relative to your *present working directory*. This means that if the `profiles2020` folder does not exist in your *present working directory*, then `ls profiles2020` will give you an error. 

- In order to specify the path in an *absolute*  way, you can give the *absolute path*. For example, `ls /home/runner/COMP100-2021F-Lab1/profiles2020`.The first '/' represents your *root* directory, which is the highest point of your file system: everything exists inside the *root directory*.

- You can specify an absolute or relative *path* to a *file* or a *directory(folder)* 

Let's investigate some more examples:
```
ls .
ls ./profiles2020
ls ..
ls /
ls /home
ls /home/runner
ls ..
ls -R
ls -r
ls -l
ls -t
ls --help

cd -
cd ~
cd .
cd ./profiles2020
cd /
cd /home
cd /home/runner

```

## Copying files from one directory to another
Note: make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

You can use the `cp` command to copy files from one place to another. To do this, you should specify which file you want to copy, and where you want to paste it. For example, the command `cp ./profiles2020/alara.txt ./` will copy the file `alara.txt` and paste it in your *present working directory* 

## Printing to shell using `echo` and `cat`
### echo
Note: make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

In python, we use `print` to print to the console. In the shell however, we use `echo`.
Type `echo 'Hello world'` in the shell and press Enter. You will see the message *Hello world* printed on the shell:
```
~/COMP100-2021F-Lab1$ echo 'Hello world'
Hello world
```
### cat
What if we want to print the contents of the `greeting.sh` file? For this, we can use the `cat` command. To use it, we have to specify which file we want to see the contents of. Type `cat greeting.sh` in the shell and press Enter. You will see the following:
```
~/COMP100-2021F-Lab1$ cat greeting.sh
#!/bin/sh
echo "Welcome to the club, user!"
```

### Q1
Note: Make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

- There is a file `alara.txt` in the `profiles2020` directory. Write a command in the shell that will directly print the contents of this file without using `cd`.
- How can we print the contents of all the files?

## Making your own files and directories using `touch` and `mkdir`
Note: make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

### Using `touch` to make your own file
The `touch` command can be used to make your own files. To do this, you need to specify a filename. For example, type `touch ids.txt` in the shell and press Enter. You will see that the file has been created.

### Using `mkdir` to make your own directories
The `mkdir` command can be used to make your own directory. To do this, you can specify the directory you want to create. for example, type `mkdir profiles2021` in the shell and press Enter. You will see that a folder called `profiles2021` has been created. 

### Q2
Note: Make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

Create a file `<your-first-name>.txt` directly in the `profiles2021` directory without using `cd`

## Redirecting input/output using `>` `>>`
The shell's terminal is like a chat between you and the computer. You say something, and the computer replies. So far you've been giving commands to the computer and with each command, you have been specifying some kind of input. For example, when you type the command `echo Hello`, `echo` is the command and `Hello` is an input. The computer then replies by printing *Hello* to the terminal. You can change where and how the computer responds. Instead of printing to the terminal, you can tell the computer where to print. For example, `echo Hello > test.txt` will take the *output* of the *echo* command and place it in the *test.txt* file.

### Q3
Note: Make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

- Look at the format of the file `alara.txt`.
- Use the `>` operator to insert your details into the file `<your-first-name>.txt` you created in the previous 
- If this doesn't work, use the *append* operator `>>` instead of `>`.
- Did you notice how the `>>` operator appends output in a new line while `>` replaces everything in the file?


## Filtering with `grep` command
We can use the `grep` command to filter a specific text from a text file. To use it, you need to specify the file you want to process and the expression you are looking for. For example, if you want to extract the KUID of alara, you can type `grep 'KUID' profiles2020/alara.txt`. This command will search for *KUID* in the file *alara.txt* and print the line that matches:
```
~/COMP100-2021F-Lab1$ grep 'KUID' profiles2020/alara.txt
KUID: A111
```

### Q4
Note: Make sure you are in the `~/COMP100-2021F-Lab1` directory before proceeding.

Write a command to print out the KUIDs for all the students in the `profiles2020` directory


## Combining commands with the pipe `|` operator

Sometimes, we want to use two or more commands together. For example, I want to extract the KUIDs of all the students and put them into a text file `ids.txt`. We can do so with the command `cat profiles2020/* | grep 'KUID' >> ids.txt`. The *output* of the command on the left of the `|` is used as input to the command on the right. The output of this is then appended to the `ids.txt` file.

## Running BASH files and changing permissions
- Sometimes, we want to automate certain processes. We can do that by writing BASH scripts with commands that you have been using so far. Lets look at the `greeting.sh` file. What does it do? 

- How can we execute it? There are 2 ways: `sh greeting.sh` and `./greeting.sh`

- Why did `./greeting.sh` not work? Let's look at the permissions using `ls -l`
- *r* means read permission, *w* means write permission, *x* means execute permission. There are specifications for permissions for the user(u), group(g) and owner(o) of the file. If you do not have *execute* permission, you cannot run the file.
- to change the permission of this file, we can use `chmod a+x greeting.sh`. Now we can execute it with `./greeting.sh`

Let's try a few more examples and investigate their effect:
```
chmod a-x greeting.sh
chmod -rwxrwxrwx greeting.sh
chmod 750 greeting.sh
chmod ---------- greeting.sh
chmod u+rwx greeting.sh
chmod --help

```

## END




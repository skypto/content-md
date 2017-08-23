Command Line Basics
===

The Command Line isn't as Scary as you Think
-----

Raise your hand if you're scared of the command line. Yes, we have this image of developers staring at a black screen with white or green text flashing across while they wildly enter incomprehensible commands and hack into the corporate mainframe (spilling soda and wiping cheetos off their keyboard no doubt as well).

That black screen (or window) is the command line, where you're able to enter commands that your computer will run for you. And while that image of a programmer is a bit overdone, the command line really is sort of like our base of operations, from which we'll launch other programs to do our "real developing" in. It has a syntax of its own which is different but not all that difficult to pick up. You'll be entering the same commands dozens of times anyway, so you'll get pretty good at it in a short period of time.

In this introductory lesson to the command line, you will learn how to navigate around your computer and how to manipulate files and directories(also known as folders) all from the comfort of the command line. As you will soon see this is not as difficult as you may think. The commands you will learn in this lesson are very intuitive so don't let the the prospect of using the command line for the first time intimidate you.

To be able to navigate your terminal, you'll need to know some basic commands:

> Not all commands are similar in Mac and Windows. If there's a 'M', it's only for Mac; 'W': it's only for Windows.

* pwd (Print Working Directory) (M): this will print the directory you're currently in.
* ls (List) (M) : This will list all directories and files of the current directory
  + ls -a : To see hidden directories and files use -a option with the ls command.
  + ls -l : In order to see the size of directories and files you can use -l option with the ls command. It will also tell the permissions of the files and directories, their owners and the time/date of modification.
  + ls -lh: If you want to get the file size in human readable format then use ls -lh command.
* dir (W): does the same as ls but then for Windows.
* cd _Directory Name_ (Change Directory): Navigate to the specified directory
  + cd .. : the command cd followed by two dots will take you **back** one directory
* mkdir _directory name_ (Make Directory): will create a directory
* touch _file name_ (M): will create an empty file
> There's no similar command in Windows, but you can use `echo`.
> For example: `echo Hello World! > test.txt` will create a test.txt file with "Hello World!" as content.
* rmdir (Remove Directory): Will remove the directory
> Be careful while using this command. The terminal does **not** ask for confirmation, nor   does it place it in the Recycle Bin. Once deleted it's gone forever.
> You'll get an error if the directory is not empty. In that case use: `rmdir -rf`
* rm (remove): remove files
> The same warning applies here as for rmdir. To be safe, always use rm with the -i flag. This will prompt you for confirmation before deleting the file.


That's it, there are plenty more but those are all you need to know to get started. If something is not clear, don't forget: Google is your friend!

cli apps - living api's

Command line Resources:
----
* Learn enough command line to be dangerous: https://www.learnenough.com/command-line-tutorial
* Conquering the command line: http://conqueringthecommandline.com/book/ack_ag
* Lauch school command line book: https://launchschool.com/books/command_line/read/introduction
* http://leveluptuts.com/tutorials/command-line-basics
* Shell i/o redirection: http://linuxcommand.org/lc3_lts0070.php
* This tutorial site: https://linuxjourney.com/
* type this in your terminal:  telnet towel.blinkenlights.nl
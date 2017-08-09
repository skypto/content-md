Command Line
====

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
> Be careful while using this command. The terminal does **not** ask for confirmation, nor does it place it in the Recycle Bin. Once deleted it's gone forever.
> You'll get an error if the directory is not empty. In that case use: `rmdir -rf`
* rm (remove): remove files
> The same warning applies here as for rmdir. To be safe, always use rm with the -i flag. This will prompt you for confimation before deleting the file.


That's it, there are plenty more but those are all you need to know to get started. If something is not clear, don't forget: Google is your friend!


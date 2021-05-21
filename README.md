# Command Line Bootcamp Notes

`cal` - Shows calender

`date` - Displays date

`clear` - Clears terminal window

`sort` - Sorting function

`man` - Manual page for a certain command - Hit `h` for help on naviating a manual page

`man -k dog` - Search the man pages of 'dog' and prints the related man pages

`man 5 passwd` - Retrieves the 5th chapter in the 'passwd' man page

`echo` - Prints out the argument

`passwd` - Command for changing password

`which` - Writes out the path to the program you reference in argument

`pwd` - Writes out the current working directory

`type` - Writes out the type of a program / command

`whoami` - Returns your username

`who` - Returns system information, for example, which users are logged in.

`ls` - Lists the contents of a directory

`ls -a` - Lists all contents.

`ls -l` - Lists contents of a directory, extended information

`cd` - Change directory

`touch` - Creates a new file

`file` - Determines the file type

`rm` - Removes files and directories

`mv` - Moves/renames files and directories

`cp` - Copy files and directories

`CTRL-l` - Clears the screen (Same as `clear`)

`CTRL-a` - Move cursor to the beginning of line

`CTRL-e` - Move cursor to the end of line

`CTRL-f` - Move cursor to the right - Same as right arrow key

`CTRL-b` - Move cursor backward - Same as left arrow key

`Alt-f` - Move cursor forward one word

`Alt-b` - Move cursor back one word

`CTRL-t` - Swaps character under cursor with left character

`Alt-t` - Swaps word under cursor with word to the left

`CTRL-k` - Delete everything on the right to the cursor

`CTRL-u` - Delete everything on the left to the cursor

`alt-d` - Delete the text from the cursor though the end of the word

`CTRL-w` - Delete the text from the cursor though the beginning of the word

`CTRL-y` - Yank (paste) after deletion/kill

`history` - See command history

`history | less ` - Scroll command history

`!X` - Run command number X in history

`CTRL-r` - Search shell history of commands

`cat` - Prints the contents of a file

`cat file1 file2` - Concatenates file1 and file2 and prints it out

`less filename` - Scroll though filename

`tac` - Same as cat but prints file in reverse order (starts at end)

`rev` - Prints contents of a file, reversing order of each line

`head filename` - Prints the head of filename, usually the 10 first lines

`tail filename` - Prints out the end of the filename, usually the 10 last lines

`/var/syslog` - System log

`wc file` - Prints out number of lines, number of words, number of bytes and filename

`wc -l file` - Prints only the number of lines

`wc -w file` - Prints only the number of words

`sort filename` - Sorts the content of a file and prints it out

`date > file` - Redirects datastream from standard output to file

`ls -l /usr/bin > list.txt` - Redirects output from ls command to file

`sort -k5n list.txt > sorted_list.txt` - Sorts a list and outputs it to a file sorted_list.txt

Please note that with the redirection command `>`, you will basically always 
replace the file. If you instead want to append, use `>>` instead.

`cat < file` - Redirects the contents of file to the cat command

`cat < original.txt > output.txt` - Write contents of original.txt to cat and
then write cat output to output.txt

`cat nonexistentfile 2> errorlog.txt` - Redirects output from standard error to file errorlog.txt

`cat nonexistentfile 2>> errorlog.txt` - Redirects output from standard error to append file errorlog.txt

`1>` - Redirection of standard output - Can also use only `>`.

`2>` - Redirection of standard error

`cat bees.txt ants.txt > insects.txt 2> error.txt` - Redirect to insects.txt and if error, to error.txt

`ls docs > output.txt 2> output.txt` - Datastream to both output.txt and if error, also output.txt

`ls docs > output.txt 2>&1` - Same as above (shortcut)

`ls docs &> output.txt` - Same as above

`command1 | command2` - Piping, take the output from command1 to input it to the second command

`ls -l /usr/bin/ | less` - Scroll though the `ls -l /usr/bin/` command.

`ls /usr/bin/ -1 | wc -l` - Counts the number of programs in `/usr/bin/`

`ls /usr/bin/ -1a | wc -l` - Same as above, except it does not account for the `.` and `..` commands 

`>` - Connects a command to some file

`|` - Connects a command to another command

`ls /usr/bin/ -1a | wc -l > somefile.txt` - Redirects the output from the pipe to `somefile.txt`

`cat msg.txt | tr s S` - Replaces s with S and writes it to standard output

`cat msg.txt | tr s a` - Replaces s with a in the file `msg.txt` and writes it to standard output

`cat msg.txt | tr a-z A-Z` - Converts the text in `cat.txt` to upper case letters.

`cat data.txt | tr -d [:alpha:]` Deletes any alphabetic characters in data.txt and write it to standard output.

`cat data.txt | tr -d [:alpha:] | tr -d : | tr -d [:blank:]` - Removes alphabetic characters, colons and blanks from data.txt and writes it to standard output

`cat file | head -7 | tail -5` - Writes out the lines 3-7 to standard output

`cat countries.txt` gives following:

`cat -n countries.txt | head -7 | tail -5` - Same as before but with numbering of lines

`ls -lh | sort -rhk 5 | head -3` - Displays the three largest files in the current directory

`du -ha /usr/bin/ | sort -h | tail -4 | head -3` - Same as above, excludes the directory itself

`du -ha /usr/bin/ | sort -h | tee sizes.txt | tail -4 | head -3` - Saves the output from the command `du -ha /usr/bin/ | sort -h` into a file named sizes.txt and then prints the 3 largest file to standard output from the same command.




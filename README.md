# Command Line Bootcamp Notes

`cal` - Shows calender

`date` - Displays date

`clear` - Clears terminal window

`sort` - Sorting function

`man` - Manual page for a certain command - Hit `h` for help on naviating a
manual page

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

`history | less` - Scroll command history

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

`wc file` - Prints out number of lines, number of words, number of bytes and
filename

`wc -l file` - Prints only the number of lines

`wc -w file` - Prints only the number of words

`sort filename` - Sorts the content of a file and prints it out

`date > file` - Redirects datastream from standard output to file

`ls -l /usr/bin > list.txt` - Redirects output from ls command to file

`sort -k5n list.txt > sorted_list.txt` - Sorts a list and outputs it to a file
sorted_list.txt

Please note that with the redirection command `>`, you will basically always
replace the file. If you instead want to append, use `>>` instead.

`cat < file` - Redirects the contents of file to the cat command

`cat < original.txt > output.txt` - Write contents of original.txt to cat and
then write cat output to output.txt

`cat nonexistentfile 2> errorlog.txt` - Redirects output from standard error to
file errorlog.txt

`cat nonexistentfile 2>> errorlog.txt` - Redirects output from standard error
to append file errorlog.txt

`1>` - Redirection of standard output - Can also use only `>`.

`2>` - Redirection of standard error

`cat bees.txt ants.txt > insects.txt 2> error.txt` - Redirect to insects.txt
and if error, to error.txt

`ls docs > output.txt 2> output.txt` - Datastream to both output.txt and if
error, also output.txt

`ls docs > output.txt 2>&1` - Same as above (shortcut)

`ls docs &> output.txt` - Same as above

`command1 | command2` - Piping, take the output from command1 to input it to
the second command

`ls -l /usr/bin/ | less` - Scroll though the `ls -l /usr/bin/` command.

`ls /usr/bin/ -1 | wc -l` - Counts the number of programs in `/usr/bin/`

`ls /usr/bin/ -1a | wc -l` - Same as above, except it does not account for the
`.` and `..` commands

`>` - Connects a command to some file

`|` - Connects a command to another command

`ls /usr/bin/ -1a | wc -l > somefile.txt` - Redirects the output from the pipe
to `somefile.txt`

`cat msg.txt | tr s S` - Replaces s with S and writes it to standard output

`cat msg.txt | tr s a` - Replaces s with a in the file `msg.txt` and writes it
to standard output

`cat msg.txt | tr a-z A-Z` - Converts the text in `cat.txt` to upper case
letters.

`cat data.txt | tr -d [:alpha:]` Deletes any alphabetic characters in data.txt
and write it to standard output.

`cat data.txt | tr -d [:alpha:] | tr -d : | tr -d [:blank:]` - Removes
alphabetic characters, colons and blanks from data.txt and writes it to
standard outpujt

`cat file | head -7 | tail -5` - Writes out the lines 3-7 to standard output

`cat countries.txt` gives following:

`cat -n countries.txt | head -7 | tail -5` - Same as before but with numbering
of lines

`ls -lh | sort -rhk 5 | head -3` - Displays the three largest files in the
current directory

`du -ha /usr/bin/ | sort -h | tail -4 | head -3` - Same as above, excludes the directory itself

`du -ha /usr/bin/ | sort -h | tee sizes.txt | tail -4 | head -3` - Saves the output from the command `du -ha /usr/bin/ | sort -h` into a file named sizes.txt and then prints the 3 largest file to standard output from the same command.

`echo This folder containts the files *` - Writes "This folder contains the files file1 file2 file3 ...", to standard output.

`echo *.txt` - Writes all filenames in folder, with prefix .txt, to standard output.

`echo p*` - Writes out all filenames in the current directory that starts with the character p.

`ls -l *at*` - Selects the output from the `ls -l` command that has the characters ´at´ in its filename and writes it to standard output.

`*` - Matches all characters

`?` - Matches only one character

`ls picture?.png` - Prints out all files e.g. picture1.png picture2.png ...

`echo app[1-3].css` - prints out app1.css, app2.cs app3.css if they exist in the working folder

`echo [A-Z]*` - echos all the filenames that starts with a character between A-Z

`[]` - Ranges

`^` - Negating ranges

`ls [^a]*` - Will match any files that do not start with an "a".

`ls [^0-9]*` - Will match any files that do not start with a numeric digit (0-9)

`echo [^Cc]` - Echo all files in working directory that doesnt start with "c" or "C"

`cd ~` - Changes working directory to home directory

`{}` - Brace expansion

`touch pages{1,2,3}.txt` - Will generate three files, pages1.txt, pages2.txt, pages3.txt

`echo {Mon, Tue, Wed, Thu, Fri}_Planner.txt` - Prints Mon_Planner.txt ... Fri_Planner.txt to standard_output.

`touch {Mon, Tue, Wed, Thu, Fri}_Planner.txt` - Creates following files.

`echo {2..10..2}` - Prints 2,4,6,8,10

`mdkir journal_day{1..365}` - Creates 365 directories called journal_day1 ... journal_day365

`mkdir -p {Mon, Tue, Wed, Thu, Fri, Sat, Sun}/{Breakfast, Lunch, Dinner}` - Creates folder structure Mon ... Sun with Breakfast ... Dinner as subfolders 

`echo {x,y{1..5},z}` - prints x,y1,y2,y3,y4,y5,z to standard output

`echo {Mon,Tue{1..10},Wed}` - Prints Mon Tue1 Tue2 Tue3 Tue4 Tue5 Tue6 Tue7 Tue8 Tue9 Tue10 Wed

`echo $((10 + 3))` - Gives output of 13

`echo $((10 / 3))` - Gives 3

`echo $((10 ** 3))` - Gives 10 to the power of 3

`echo "Today is....       $(date)"` - Today is...     fre 21 maj 2021 21:02:01 CEST

`echo 'Today is....       $(date)'` - Today is...     $(date) 

`echo Hello There $(whoami)` - Hello There Mikael

`echo Today is `date` ` - Today is Friday..... 

## Search on a linux system

`locate filename` - Search for the file `filename` on your linux machine

`find -type f` - Will limit the search for files

`find -type d` - Will limit the search to files

`find ~/Desktop -name "*.txt"` - Find files on the desktop with the filetype .txt

`find ~ -iname "*chick*"` - find files that contains chick in the filename.

`find ~/Desktop -iname "*[0-9]*"` - Find files with numbers in the filename in the home Desktop folder.

`find -size +1G` - Find files that are larger than 1 GB

`find -size -50M` - Find files that has a size less than 50MB

`find -user mikael` - Find all files that belongs to the user mikael

`find -empty -type f` - Find empty files on the system

## Timestamps

`mtime` - Modification time, the time when the file content last changed

`ctime` - The time when a file was last changed. Same as `mtime` but also  accounts for changes in the name of the file, the moving of files and altering of permissions

`atime` - Access time, updated when a file is read by an application or command like `cat`.

`ls -lc` - Show ls command with `ctime`

`ls -l` - Show ls command with `mtime`

`ls -lu` - Show ls command with `atime`

`touch last_week.txt -d "1 week ago"` - Creates a file with the mtime for 1 week ago

`touch last_month.txt -d "1 month ago"` - Creates a file with the mtime for 1 month ago

`find -mmin 30` - Find files that were modified exactly 30 munutes ago

`find -mmin +30` - Find files that were modified mote than 30 minutes ago

`find -mmin -30` - Find files that were modified less than 30 minutes ago

`find -amin +100` - Find all that were accessed more than 100 minutes ago

`find -mtime -5` - Find all files that were created less 5 days ago

`find -name "*chick*" -or -name "*kitty*"` - Find files that has chick or kitty in the filename 

`find -type -f -not -name "*.html"` - Find files but ignore html files

`find ~ -iname "tue*" -or -iname "mon*"` - Find files in homedirectory that starts with tue or mon (case insensitive).

`find ~ -type f -empty -exec ls -l '{}' ';'` - Find all files in home directory that are empty and show the information that the command `ls -l` provides

`find -name "*broken*" -exec rm '{}' ';'` - Find all files that contains broken in the filename (case sensitive) and remove them

`find -name "*broken*" -ok rm '{}' ';'` - Find all files that contains broken in the filename (case sensitive) and promt removal of each file (asks for permission)

`find -empty -ok rm '{}' ';'` - Finds empty files in the current working directory and promt for permission about approval

`find -type f -name "*.html" - exec cp '{}' '{}_COPY' ';'` - Find html files in the current working directory and copy each file to a file with the same filename with the extension _COPY






# [BASH cell usual commands](http://swcarpentry.github.io/shell-novice/)

### [Navigating Files and Directories](http://swcarpentry.github.io/shell-novice/02-filedir/index.html)

$ **pwd** = print working directory


$ **ls** = listing, prints the names of the files and directories in the current directory

$ **ls -r** = lists the contents of a directory in reverse order

$ **ls -t** = lists items by time of last change instead of alphabetically

$ **ls -rt** = The most recently changed file is listed last

$ **ls -l** = displays file size and the time of its last modification

$ **ls -l -h** = displays file size ‘human readable’, with measure unit, like megabyte

$ **ls -s** = displays the size of files and directories alongside the names

$ **ls -S** = sorts the files and directories by size

$ **ls -F** = classify the output of 'listing' by adding a marker to file and directory names to indicate what they are:

		a trailing / indicates that this is a directory

		@ indicates a link

		* indicates an executable

$ **ls -F /** = listing of files and directories in the root directory /.

$ **ls -F .** = listing of files and directories in the working directory

$ **ls -F ..** = listing of files and directories in the directory above

$ **ls -a** = shows ALL, including hidden files or directories

$ **ls --help** =  displays more information on how to use the command or program


$ **cd** = without an argument will return you to your home directory

$ **cd ..** = change to above directory

$ **cd -** = the previous directory I was in


### [Working with Files and Directories](http://swcarpentry.github.io/shell-novice/03-create/index.html)

#### Creating directories and files

$ **mkdir <name>** = make directory indicated in '<>'

$ **nano <name.txt>** = creates a text file within an editor 

	Ctrl + O = writes text to disk

	Crtl + X = quits the editor and returns to shell

$ **touch <name.file type>** = generate a blank file to be used by programs which do not generate output files themselves, but require empty files already generated

$ **cat <file.file type>** = prints the content of the file

#### Moving files and directories

$ **mv <local/name> <local/new name>** = renames files and overwrites any existing file with the same name
	$ **mv - i** = makes **mv** ask for confirmation before overwriting

$ **mv** = also moves files and directories

#### Copying files and directories

$ **cp** = copies a file instead of moving it (the destination directory must be the last argument)

$ **cd -r** = copies a directory and all its contents

#### Removing files and directories

$ **rm** = delete _forever_!! just for files, not directories

	$ **rm -i** = asks for confirmation before deleting a file

	$ **rm -r** = delete a directory

$ **cd ..** =

$ **cd ..** = 

#### Using wildcards for accessing multiple files at once

When the shell sees a wildcard, it expands the wildcard to create a list of matching filenames before running the command that was asked for.

$ command + "*.<file type>" = matches every file type indicated

	p*.csv = matches only csv files which names begin with 'p'

$ command + ? = matches any single character in a filename

### [Pipes and filters](http://swcarpentry.github.io/shell-novice/04-pipefilter/index.html)

````

* Redirect a command’s output to a file.

* Process a file instead of keyboard input using redirection.

* Construct command pipelines with two or more stages.

* Explain what usually happens if a program or pipeline isn’t given any input to process.

* Explain Unix’s ‘small pieces, loosely joined’ philosophy.

````

**Ctrl+C** = escape out of the state in which nothing happens after including command without arguments enough (eg. missing file name)

! [Pipes outputs](pipes_outputs.png)

The vertical bar, |, between the two commands is called a pipe. It tells the shell that we want to use the output of the command on the left as the input to the command on the right.

**command > file** redirects a command’s output to a file (overwriting any existing content).

**command >> file** appends a command’s output to a file.

> In the first example with >, the string ‘hello’ is written to testfile01.txt, but the file gets overwritten each time we run the command.

> We see from the second example that the >> operator also writes ‘hello’ to a file (in this casetestfile02.txt), but appends the string to the file if it already exists (i.e. when we run it for the second time).

$ **wc <file name>** = counts the number of lines, words, and characters in files (from left to right, in that order)

	$ **wc *.<file format>** =  also shows the total number of all lines in the last line of the output

$ **cat** = displays the contents of its inputs.

$ **sort** = sorts its inputs.

	$ **sort -n** = specifies a numerical rather than an alphanumerical sort.

$ ... head =  displays the first 10 lines of its input.

$ ... tail =  displays the last 10 lines of its input.

$ **echo <text>** =  The echo command prints text

#### Pipe construction

$ **cut -d , -f 2 animals.txt** = ‘cut out’ certain sections of each line in the file, and cut expects the lines to be separated into columns by a Tab character. A character used in this way is a called a delimiter. In the example above we use the -d option to specify the comma as our delimiter character. We have also used the -f option to specify that we want to extract the second field (column).

**uniq command** = filters out adjacent matching lines in a file


### [Loops](http://swcarpentry.github.io/shell-novice/05-loop/index.html)

If the shell prints > or $ then it expects you to type something, and the symbol is a prompt.

If you type > or $ yourself, it is an instruction from you that the shell should redirect output or get the value of a variable.

$ for filename in *.dat; do head -n 2 $filename | tail -n 1; done
CLASSIFICATION: basiliscus vulgaris
CLASSIFICATION: basiliscus vulgaris
CLASSIFICATION: equus monoceros
CLASSIFICATION: equus monoceros

$ for filename in *.csv; do cp $filename original-$filename; done

* Nelle’s Pipeline: Processing Files

### [Shell scripts](http://swcarpentry.github.io/shell-novice/06-script/index.html)

(Ctrl-O in nano) save the file 

(Ctrl-X in nano) exit the text editor 

$ bash middle.sh = runs the commands printed in middle.sh file

$1 = ‘the first filename (or other argument) on the command line’

$@ =‘All of the command-line arguments to the shell script’

### [Finding things](http://swcarpentry.github.io/shell-novice/07-find/index.html)

$ **grep** (pattern) + (file) = finds and prints lines in files that match a pattern

$ **grep -w** (pattern) + (file) = limit matches to word boundaries

$ **grep -n** (pattern) + (file) = numbers the lines that match

$ **grep -n -w "the"** (file) = finds the lines that contain the word ‘the’ and -n to number the lines that match

$ **grep -i** (pattern) + (file) = make our search case-insensitive (i.e. returns Aa, Bb, ...)

$ **grep -n -w -v "the"** = outputs the lines that do not contain the word ‘the’

* [regular expressions](https://v4.software-carpentry.org/regexp/index.html)

$ **find** = lists the names of every file and directory under the current working directory

$ **find . -type d** = lists all directories under current directory, including itself

$ **find . -type f** = lists all files under current directory

$ find . -name "*.txt" = put *.txt in quotes to prevent the shell from expanding the * wildcard. This way, find actually gets the pattern *.txt, not the expanded filename

##### Listing X finding
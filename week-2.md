# Simple Commands 2.0
The root folder ` / ` is the parent of it's own.
```terminal
/$ cd ..
/$
```
### More on ` ls `

* Interpretation of directory as an argument
	- ` ls -l level1 ` will long list all the files of directory ` level1 `.
```
~$ ls -l level1
total 2
-rw-rw-r-- 1 sanr sanr 0 Dec 18 17:06 f1
-rw-rw-r-- 1 sanr sanr 0 Dec 18 17:06 f2
```

# Utilities for Knowing Files Better

### [` less `]
### ` cat `
* ` cat <filename> ` : Dumps the file output on screen for reading.
* Abbr. for concatenate.
* Navigation is difficult.
* To see the ` profile ` file content
```terminal
/etc$ cat profile
```

### ` more `
* ` more <filename> ` : Open file filename for reading page by page.
* It beautifully combines the features of [` less `](#less) and [` cat `](#cat).
* Can not scroll ` down ` to see content.
* Shows percentage of file read.
* To view the ` profile ` file content
```terminal
/etc$ more profile
```

### ` head `
* ` head <filename> ` : Print the first 10 lines of the file.
* Can also specify number of lines using ` -n ` option.
* To print first 5 lines.
```terminal
/etc$ head -n 5 profile
```

### ` tail `
* ` tail <filename> ` : Print the last 10 lines of the file.
* Can also specify number of lines using ` -n ` option.
* To print last 5 lines.
```terminal
/etc$ tail -n 5 profile
```

### ` wc `
* ` wc <filename> ` - Print number of newline, word and byte for each file
* To print newline (` -l `), word (` w `) an byte (` -c `) count of ` profile `
```terminal
/etc$ wc profile
 27  97 582 profile
```
* To print newline (` -l `) count of ` profile `
```terminal
/etc$ wc -l profile
 27 profile
```
---------------

# Knowing More Commands

### [` man `](/Week-1/Lecture2-3.md#man)

### ` which `
* ` which  <command> ` - Print the path of ` command ` or check if a package exists or not.
* To print path of commands ` less ` and ` more ` 
```terminal
/etc$ which less
/usr/bin/less
/etc$ which more
/usr/bin/more
```
* Actually the size of ` less ` is ` more `
```terminal
/etc$ ls -l /usr/bin/less
-rwxr-xr-x 1 root root 199048 Mar 24  2022 /usr/bin/less
/etc$ ls -l /usr/bin/more
-rwxr-xr-x 1 root root 43392 Feb 21  2022 /usr/bin/more
```

* To print the path of command ` which `!
```terminal
/etc$ which which
/usr/bin/which
```
* ` which ` is kind of reflexive!

### ` whatis `
* ` whatis <command> ` - Print brief description of ` command ` as the first line in ` man ` page
* To print the description of ` which `
```terminal
/etc$ whatis which
which (1)            - locate a command
```

### ` help `
* Print the help for currently running shell. [More on shell](#Shells)
* It includes keywords, syntax for commands, loops and symbolic expressions.  

### ` info `
* ` info ` - Prints documentation for commands.
* ` info <command> ` - Documentation of specific command ` command `.
* It is highly navigatable, just like a webpage.
* Links are marked in * and underline and can be navigated using arrow keys.

| ` keys ` | Description |
| :---:    | ---         |
| ` enter ` | Open a link |
| ` < ` ` shift + , ` | Go back or previous |
| ` > ` | Go forward or next | 
| ` M ` ` m ` | Search menu, similar to seach box |
| ` S ` ` s ` | Regex search |
| ` Q ` `q`| Quit |

### ` type `
* ` type <command> ` - Prints the type of the command.
* Is it
	- offered by shell?
	- offered by operating system?
	- alias?
* To print the type of commands ` type ` and ` ls `
```terminal
~$ type type
type is a shell builtin
~$ type ls
ls is aliased to `ls --color=auto'
```
* Note : commands displayed by ` help ` are all shell builtins.


### ` rmdir `
* ` rmdir <dirname> ` - Remove an empty directory.
* To remove empty directory ` level2 `
```terminal
~$ rmdir level2
```

## Multiple Arguments
* Let's create some files using ` touch ` and multiple arguments and a directory using ` mkdir `.
```terminal
~$ touch file1 file2 file3
~$ mkdir mydir
```
### Second argument
* First argument is a file and second argument is directory.
* ` file1 ` is copied to ` mydir ` 
```terminal
~$ cp file1 mydir
```
* Both arguments are files.
* ` file2 ` is overridden by contents of ` file2 `
```terminal
~$ cp file1 file2
```
* Note
	- Here the alias is not set for ` cp `, hence the command is not interactive.
	- See the [` man `](/Week-1/Lecture2-3.md#man "Explore man") command to figure out interactive option for ` cp `. 

* ` rmdir ` is not meant to handle non empty directories.
```
~$ rmdir mydir
rmdir: failed to remove 'mydir': Directory not empty
```
* We can use ` rm ` and ` rmdir ` and delete directory by explicitly navigating into them.
* But, can we do something better? as this process might be cumbersome.
* To force the deletion ` rm ` has one option ` -r `
```terminal
~$ rm -r mydir
```
* As you can see the file deletion happens without any noise.
* Note 
	- Interactive mode is not set here.
	- Now you know what to do to enable it.


### Interpretation of last argument

### Recursion assumed for ` mv ` and not ` cp `
* Some commands assume recursion while some don't.
* Let's setup our directory structure.
```terminal 
~$ mkdir mydir
~$ cp file1 mydir
```
* Let's check for ` cp `
```terminal 
~$ cp mydir mydir2
cp: -r not specified; omitting directory 'mydir'
~$ cp -r mydir mydir2
```
* Note that most commands tell you what to do.
* To take home, recursion is not assumed for ` cp `.

* Let's check for ` mv `
```terminal
~$ mv mydir mydir3
```
* As you can see no error is generated.
* That means ` mydir ` is successfully renamed as ` mydir3 `


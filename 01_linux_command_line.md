```python
!echo $SHELL
```

    /bin/bash
    


# Workshop: Linux Command Line for Scientists

The Linux command line has a bit of a learning curve, but it can be incredibly powerful for managing files, processing data, and automating tasks. Each section will focus on a set of related commands, provide a reference table, and include exercises to practice and reinforce your understanding.



## Section 1: Basic Commands

In this section, we will cover the basic commands that are essential for navigating and managing files and direcmtories in the Linux command line. These commands form the foundation of your command line skills.


| Command | Description |
|---------|-------------|
| `pwd`   | Print working directory |
| `ls`    | List directory contents |
| `cd`    | Change directory |
| `mkdir` | Make directories |
| `rmdir` | Remove empty directories |
| `touch` | Create an empty file |
| `rm`    | Remove files or directories |
| `cp`    | Copy files or directories |
| `mv`    | Move/rename files or directories |
| `cat`   | Concatenate and display file content |


#### **Exercises**

1. Print the current working directory.

2. List the contents of the current directory.
 


3. Change to the home directory.

4. Create a new directory named `testdir`.

4. Change to the `testdir` directory.

5. Create an empty file named `testfile.txt`.

6. List the contents of the `testdir` directory.

7. Copy `testfile.txt` to `testfile_copy.txt`.


8. Rename `testfile_copy.txt` to `testfile_renamed.txt`.


9. Remove `testfile_renamed.txt`.


10.  Create a nested directory structure `dir1/dir2/dir3`.

11. List the contents of `dir1` with detailed information.


12. Move `testfile.txt` to `dir1/dir2`.


13. Remove the `dir1/dir2/dir3` directory.


14. Display the contents of `testfile.txt`.


## Section 2: The 'nano' Text Editing TUI and Calling Optional Arguments

Terminals can have programs with user interfaces, just like graphical environments; instead of being called **"GUIs"** ("Graphical User Interfaces"), terminals have **"TUIs"** ("Terminal User Interfaces").  In this section, we'll work with the `nano` text editor, a ubiquitous program that's very helpful for doing basic file editing when working in a terminal environment.  `nano` is easy to learn, and has the main keyboard shortcuts shown on screen, which is handy if you don't use it often.  More keyboard shortcuts for power use can be found here: https://www.nano-editor.org/dist/v2.6/nano.html#Feature-Toggles

How do you open a text file in nano?  Just type `nano my_file.txt`!

Like many programs, `nano` also has optional arguments that change how it works; these can be really helpful, and make a program much more versatile.  They can usually either be entered in two ways:
  - as an **Option Flag** (e.g. `-h`)
  - as an **Option** (e.g. `--help`)
  
Flags are shorter to type, but harder to remember. Multiple options can be used, with flags being the simplest to combine (e.g. `-abc` combines the flags `-a`, `-b`, and `-c`). Documentation for these options is often found by calling the program with the `--help` option.

In the exercises below, we'll make some files practices launching `nano` with various options.  Below is a reference with some , taken from its online documentation: https://www.nano-editor.org/dist/v2.6/nano.html#Command_002dline-Options.  

| Option Flag | Option | Description |
| :--  | :-- | :-- |
| **`nano`** |  | Launch `nano` with default behaviors. |
| **`nano -h`** | **`nano --help`** | View the help text for `nano`. |
| **`nano filename`** |  | Open the referenced file in `nano`  |
| **`nano -V`** | **`nano --version`** | Show the version number of the installed `nano` program. |
| **`nano -T 2`** | **`nano --tabsize=2`** | Launch `nano`,  with tabs only taking up two columns |
|  **`nano -E`** |  **`nano --tabstospaces`** | Launch `nano`, with tabs converted automatically to spaces  |
|  **`nano -E`** |  **`nano --tabstospaces`** | Launch `nano`, with tabs converted automatically to spaces  |
|  **`nano -B`** |  **`nano --backup`** | Launch `nano`, with a the previous saved automatically in a backup file whenever a new save is made.  |
|  **`nano -P`** |  **`nano --positionlog`** | Launch `nano`, recording and going back to the last place you edited the file. |



**Exercises**: Use the `nano` text editor to create the following files.

1. Make a file called `name.txt`, containing your name.  Save the file, exit nano, and reopen the file to verify that it was saved!

2. Make a file called `shopping_list.txt` with three food items, one on each line.

3. Make a python script file called `hello.py` with the following code: `print("Hello, World!")`. 

**Exercises** Launch the `nano` text editor with the following options:

1. Check which version of `nano` is installed.

2. Make `nano` use spaces instead of tabs when hitting the Tab key.

3. Make it so preseing the Tab key only moves the cursor 3 columns.

4. Make it so the tab key is converted to 2 columns, **and** it uses spaces instead of tabs.

5. Make `nano` record what position in a file you were working in, for next time you open the same file.

6. Make `nano` automatically create a backup file.


## Section 3: Text Processing

Text processing is a common task in scientific computing. This section covers commands that allow you to manipulate and analyze text files efficiently.

| Command | Description |
|---------|-------------|
| `cat`   | Concatenate and display file content |
| `grep`  | Print lines matching a pattern |
| `sort`  | Sort lines of text files |
| `uniq`  | Report or omit repeated lines |
| `wc`    | Print newline, word, and byte counts for each file |
| `head`  | Output the first part of files |
| `tail`  | Output the last part of files |
| `cut`   | Remove sections from each line of files |
| `sed`   | Stream editor for filtering and transforming text |


#### **Exercises**

The exercises below do analysis and transformation of a file called `testfile.txt`, which needs to be made before starting.  Before starting, please use the `nano` text editor to put the following text into `textfile.txt`:

```
Bananas 1.52
Dragonfruit 6.23
Apples 0.89
Cherries 0.12
Apples 0.89
Bananas 1.52
```

1. Display the contents of `testfile.txt`.

2. Find all lines containing the word "test" in `testfile.txt`.

3. Sort the contents of `testfile.txt`.

4. Remove duplicate lines from `testfile.txt`.

5. Count the number of lines, words, and characters in `testfile.txt`.

6. Display the first 3 lines of `testfile.txt`.

7. Display the last 3 lines of `testfile.txt`.

8. Extract the first column from `testfile.txt` (assuming columns are separated by spaces).

9. Extract the second column from `testfile.txt` (assuming columns are separated by spaces).

10. Count the number of occurrences of the word "Apples" in `testfile.txt`.

11. Display lines 3 to 7 of `testfile.txt`.

12. Sort `testfile.txt` in reverse order.

13. Display the unique lines in `testfile.txt`.

14. Use `cut` to extract the first 4 characters of each line in `testfile.txt`.

## Section 4: Piping Commands and Text

Piping is a powerful feature in the Linux terminal that allows you to pass the output of one command as input to another. This enables you to build complex workflows by chaining simple commands together. In this section, we will explore different types of piping: `>`, `>>`, `|`, and `<`. These techniques are essential for data processing and analysis, making them invaluable for scientists working with large datasets.

| Symbol | Description | Example |
|--------|-------------|---------|
| `>`    | Redirects output to a file, overwriting the file if it exists. | `echo "Hello, World!" > output.txt` |
| `>>`   | Appends output to a file. | `echo "Hello again!" >> output.txt` |
| `\|`    | Passes the output of one command as input to another. | `echo "Hello, World!" \| grep "World"` |
| `<`    | Takes input from a file. | `sort < input.txt` |



#### **Exercises**

1. Basic Redirection: Use `echo` to create a file named `data.txt` with the content "apple banana cherry".

2. Appending Data: Append the text "date elderberry fig" to `data.txt`.

3. Using Pipes: Use `cat` and `grep` to find the word "banana" in `data.txt`.

4. Sorting Data: Sort the contents of `data.txt` and display the result.

5. Counting Words: Count the number of words in `data.txt` using `wc`.

6. Unique Words: Find unique words in `data.txt` using `sort` and `uniq`.

7. Cutting Fields: Use `cut` to extract the first word from each line in `data.txt`.

8. Combining Commands: Combine `echo`, `sort`, and `uniq` to create a sorted list of unique words from a new string.

9. Redirecting and Appending: Redirect the sorted unique words from the previous exercise to a file named `unique.txt`.

10. Appending to a File: Append the word "kiwi" to `unique.txt`.

11. Piping with `wc`: Use `wc` to count the number of lines in `unique.txt`.

12. Grep and Count: Use `grep` and `wc` to count the number of lines containing the word "apple" in `data.txt`.

13. Extracting Columns: Use `cut` to extract the second word from each line in `data.txt`.

14. Combining Multiple Commands: Combine `echo`, `grep`, `sort`, and `uniq` to filter and sort unique words containing the letter "e".

15. Advanced Piping: Create a file `numbers.txt` with numbers 1 to 10, one per line, and then use `sort` and `wc` to count the number of lines.



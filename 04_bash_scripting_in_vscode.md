# Writing and Executing Bash Scripts in VSCode

In this unit, we’ll cover the basics of writing and running Bash scripts, focusing on essential commands and structure. By working within Visual Studio Code (VSCode), you’ll also get hands-on experience with file navigation, editing tools, and terminal operations. Along the way, we’ll highlight useful VSCode extensions and shortcuts that streamline the workflow.


---


### Section 1: Setting Up VSCode for Bash Scripting and Script Basics

VSCode is a versatile code editor that integrates well with Bash scripting. You’ll use the file explorer to organize your scripts, the built-in terminal to execute them, and the text editor to write your code. In this section, we’ll set up VSCode with useful extensions and cover the basic structure of a Bash script, including shebang, comments, and permissions.

### Suggested Extensions for Bash Scripting

1. **Bash IDE**: Syntax highlighting, autocompletion, and linting.
2. **ShellCheck**: A linter for syntax errors and best practices.

| Component             | Description                                                  |
|-----------------------|--------------------------------------------------------------|
| `#!/bin/bash`         | Shebang; specifies the interpreter to execute the script     |
| `# Comment`           | Adds comments for readability                                |
| `echo`                | Prints text to the terminal                                  |
| `chmod +x script.sh`  | Makes the script executable                                  |

**Exercises**

1. Install the **Bash IDE** and **ShellCheck** extensions.

2. Open the VSCode file explorer, create a new folder for scripts, and add a file called `hello.sh`. Write a simple script:
   ```bash
   #!/bin/bash
   echo "Hello, World!"
   ```

3. Use `chmod +x hello.sh` to make the script executable, then run it with `./hello.sh`.

4. **Repetition Practice**: Create another script `goodbye.sh` that prints "Goodbye, World!" Run it to ensure it works.

---

### Section 2: Using Variables and Positional Arguments

Variables and positional arguments make scripts dynamic and customizable. Variables store values, while positional arguments (`$1`, `$2`, etc.) allow you to pass information to a script when running it, making your code flexible and interactive.

| Syntax                           | Description                                      |
|----------------------------------|--------------------------------------------------|
| `variable_name=value`            | Assigns a value to a variable                    |
| `$variable_name`                 | Retrieves the value of a variable                |
| `$1`, `$2`, …                    | Positional arguments passed to the script        |
| `"$@"`                           | All arguments passed to the script               |

**Exercises**

1. In a new script `greet.sh`, define a variable `name` and use `echo` to print "Hello, [name]!".

2. Modify `greet.sh` to accept a positional argument so you can run `bash greet.sh Alice` and get "Hello, Alice!".

3. **Repetition Practice**: Expand `greet.sh` to:
   - Print a greeting for two positional arguments (e.g., "Hello, Alice and Bob!").
   - Print a goodbye message using `$@` to include all arguments.

4. Create a new script `calculate.sh` that:
   - Accepts two numbers as positional arguments.
   - Prints their sum using a variable.

---

## Section 3: Conditional Statements and Functions

**Introduction:** Conditional statements allow scripts to make decisions based on conditions, adding intelligence to your code. Functions make scripts modular by grouping code into reusable blocks. Together, they add flexibility, structure, and efficiency to your Bash scripts.

| Syntax                        | Description                                      |
|-------------------------------|--------------------------------------------------|
| `if [ condition ]; then ... fi` | Basic conditional syntax                      |
| `[ -f filename ]`             | Checks if a file exists                          |
| `function_name() { ... }`     | Defines a function                               |
| `function_name`               | Calls the function                               |

**Exercises**

1. Create a script `check_file.sh` that takes a filename as an argument and checks if it exists. If it does, print "File exists"; otherwise, print "File does not exist."

2. **Repetition Practice**: Extend `check_file.sh` to also check if it’s a directory and if it’s readable.

3. In a new script `math_operations.sh`, write a function `add` that takes two arguments and prints their sum.

4. **Repetition Practice**: Add functions for subtraction, multiplication, and division (with a check to prevent division by zero). Test each function.

---

## Section 4: Debugging and Exporting Scripts

Debugging is essential for identifying and fixing errors in scripts. Bash offers tools like `set -x` to trace commands and `set -e` to exit on errors. Exporting your script to share or re-use is also a valuable practice. In this section, you’ll learn debugging techniques and how to document and organize scripts for export.

| Command                  | Description                                         |
|--------------------------|-----------------------------------------------------|
| `set -x`                 | Prints each command and its output as it runs       |
| `set -e`                 | Exits the script if any command returns an error    |
| `echo $variable`         | Print variable values for debugging                 |



**Exercises**



1. Add `set -x` at the beginning of `greet.sh` and run it to observe how commands execute.


2. **Repetition Practice**: Add `set -e` to `check_file.sh`, introduce an error (like referencing a non-existent variable), and see how the script exits.


3. Use `echo` statements to check the values of variables at different points in `math_operations.sh` for debugging.


4. Organize a script by adding comments and a section at the top describing its purpose, inputs, and outputs.


[[MOC - IBM Data Engineering]] #Shell #IBMDataEngineering 

## Module 3

- A script is a list of commands that can be interpreted.
- Commands can be entered interactively
- Scripting leanguages are interpreted at runtime
- Slower to run but faster to develop

Uses
- Used to automate processes
	- ETL jobs
	- File backup and archiving
	- System administration tasks 

Shell script - executable text file with an interpreter directive: a.k.a 'shebang' directive:
 
```
 #!interpreter [optional-arg]
```

shell script directives: 

```
#!/bin/sh
#!/bin/bash
python script directive
#!/usr/bin/env pyuthon3
```

![[Pasted image 20260918010925.png]]

![[Pasted image 20260918011029.png]]

run your bash script: 

```
./hello_world.sh
```


## Shell Variables

A **shell variable** stores a value, such as text or a number, so you can access or modify it later by name.

### Creating and Modifying a Variable

Assign a value using `name=value`, with **no spaces around `=`**:

```
firstname="Jeff"
```

To modify the variable, assign a new value:

```
firstname="Rodrigo"
```

### Accessing Its Value

Place `$` before the variable name to retrieve its value. Use `echo` to display it:

```
echo "$firstname"
# Output: Rodrigo
```

> **Key distinction:** `firstname` is the variable name; `$firstname` retrieves its value.

### Reading User Input

The `read` command waits for user input and stores it in a variable:

```
read lastname
# The user types Grossman and presses Enter

echo "$lastname"
# Output: Grossman
```

Within a script, you can display a prompt before reading the input:

```
echo "Enter your last name:"
read lastname
```

### Displaying Multiple Variables

```
echo "$firstname $lastname"
# Output: Rodrigo Grossman
```

### Summary

- `name=value`: creates or modifies a variable.
- `$name`: retrieves its value.
- `echo "$name"`: displays its value.
- `read name`: stores user input in a variable.
- **Command-line arguments** also allow values to be passed to a script; these will be covered later.

Pipes and Filters 

Filters are shell commands, which:
- Take input from standard input
- Send output to standard output
- Transform input data into output data
- Filter can be chained together

Pipes

```
|-pipe command
for chaining filter commandas
command1 | command2
ex: ls | sort -r
```

Shell variables
- Scopes limited to shell
- set - list all shell variables
```
var_name=value
No spaces around "="
GREETINS="Hello
echo $GREETINGS

AUDIENCE="World"
echo $GREETINGS $AUDIENCE

Deletes var_name
unset var_name
```

Environmental variables
- Extended scope
```
export var_name
ex:
export GREETINGS
evn | grep "GREE"
GREETINS=Hello
```

## Pipes and Filters

A **pipe** (`|`) sends the **standard output** of one command to the **standard input** of another.

```
command1 | command2 | command3
```

This allows commands to work together in a **pipeline** to process data.

### Combining `sort` and `uniq`

- `sort`: sorts lines of text.
- `uniq`: removes **consecutive duplicate lines**.

To display unique lines from a file:

```
sort pets.txt | uniq
```

**Why does the order matter?** `sort` places identical lines next to each other, allowing `uniq` to remove the duplicates.

> Using `uniq` alone does not remove duplicates that are separated by other lines.

### Replacing Characters with `tr`

The `tr` command translates or replaces characters received through **standard input**.

```
tr [OPTIONS] 'target_characters' 'replacement_characters'
```

Use `echo` to pass a string to `tr`:

```
echo 'Linux and shell scripting are awesome!' | tr 'aeiou' '_'
# Output: L_n_x _nd sh_ll scr_pt_ng _r_ _w_s_m_!
```

#### Complement: `tr -c`

The `-c` option targets characters **not included** in the specified set:

```
echo 'Linux and shell scripting are awesome!' | tr -c 'aeiou' '_'
```

> This replaces all characters other than lowercase vowels—including consonants, spaces, punctuation, and the newline—with underscores.

### Converting File Contents to Uppercase

Use `cat` to pass file contents to `tr`:

```
cat pets.txt | tr '[:lower:]' '[:upper:]'
```

To convert the text to uppercase and display only unique lines:

```
cat pets.txt | tr '[:lower:]' '[:upper:]' | sort | uniq
```

### Extracting a Field from JSON Text with `grep`

For a simple numeric `"price"` field:

```
cat Bitcoinprice.txt | grep -oE '"price"[[:space:]]*:[[:space:]]*[0-9]+(\.[0-9]+)?'
```

|Pattern or option|Meaning|
|---|---|
|`-o`|Displays only the matching portion|
|`-E`|Enables extended regular expressions|
|`"price"`|Matches the literal field name|
|`[[:space:]]*`|Matches zero or more whitespace characters|
|`:`|Matches the colon|
|`[0-9]+`|Matches one or more digits|
|`(\.[0-9]+)?`|Matches an optional decimal portion|

Example match:

```
"price": 65000.25
```

> `grep` searches text patterns; it does not understand JSON structure. This example can match multiple `"price"` fields and does not establish which one belongs to BTC.

### Summary

- `|` connects one command’s output to another command’s input.
- `sort | uniq` displays unique lines.
- `tr` replaces characters or changes letter case.
- `tr -c` processes characters outside the specified set.
- `grep -oE` extracts matching text using extended regular expressions.
- Output from commands such as `cat`, `echo`, or `curl` can be passed through a pipeline.

#### Extracting Information from URLs

In this exercise, you retrieve JSON data from the CoinStats API and use `grep` to extract the information you need.

##### 1. Create an Account

Open your web browser and navigate to the **CoinStats API website** linked in the lab.

Enter your email address and password to register, then verify your email. After verification, you will be redirected to the dashboard.

##### 2. Generate an API Key

On the dashboard, click **Generate API Key**.

Save the generated key, as you will need it to authenticate your API requests.

> **API key:** a credential that identifies and authenticates your requests. Keep it private.

##### 3. Open the API Documentation

Click **API Docs** in the dashboard’s left sidebar.

In the documentation, select the **`/coins` endpoint**, which retrieves cryptocurrency information.

##### 4. Test the Request

Locate the example **`curl` command** on the endpoint’s documentation page. This command requests data from the API and returns the response in **JSON format**.

Enter your generated API key in the authentication header field specified by the documentation, then click **Try it**.

After authentication, the API response will appear as JSON.

##### 5. Retrieve the Data Using `curl`

Copy the `curl` command provided by the documentation and run it in your terminal with the required API key.

The command retrieves the API response, which can then be processed using other shell commands.

##### 6. Extract Information Using `grep`

To extract numeric `"price"` fields, use the following command from the earlier exercise:

```
grep -oE '"price"\s*:\s*[0-9]*\.?[0-9]*'
```

You can append it to the copied `curl` command using a pipe:

```
# Template: replace <curl command> with the command from the API docs.
<curl command> | grep -oE '"price"\s*:\s*[0-9]*\.?[0-9]*'
```

The pipeline sends the output of `curl` directly to `grep`:

- **`curl`** retrieves the JSON data from the API.
- **`|`** passes that output to the next command.
- **`grep -oE`** displays only the portions matching the price pattern.

Example matching text:

```
"price": 65000.25
```

> If the response contains several `"price"` fields, the command returns all matching fields, rather than identifying only Bitcoin’s price.

##### Summary

- Generate an **API key** to authenticate your requests.
- Use the **API documentation** to select and test an endpoint.
- Run the provided **`curl` command** to retrieve JSON data.
- Pipe the response to **`grep`** to extract the required information.

### Useful features of the bash shell

**Metacharacters**

```
# - precedes a comment
; - Command separator
* - filename expansion wildcard
? - single character wildcard in filename expansion

```

Quoting
```
\ - escape unique character interpretation:
echo "\$1 each"
" " - interpret literally, but evaluate metacharacters
' ' - interpret literally
```

![[Pasted image 20260918020954.png]]

I/O redirection

![[Pasted image 20260918021036.png]]
![[Pasted image 20260918021117.png]]

Command substitution 
- Replace the command with its output
 ```
 $ (command) or `command`
 ```
 
Store output of pwd command in here: 
```
here=(pwd)
echo $here
/home/jgrom
```

![[Pasted image 20260918021406.png]]

![[Pasted image 20260918021440.png]]


### Reading

## Metacharacters

**Metacharacters** are characters with special meanings that the shell interprets as instructions.

|Character|Meaning|
|---|---|
|`#`|Begins a comment|
|`;`|Separates commands|
|`*`|Matches any sequence of characters in filename expansion|
|`?`|Matches one character in filename expansion|

### Pound Sign `#`

The `#` character introduces a **comment**. When it begins a comment, the shell ignores the remaining text on that line.

```
# Display a greeting
echo "Hello!"

firstname="Jeff" # Store the first name
```

Comments help document code, explain its purpose, and make scripts easier to maintain.

> **Note:** A quoted `#`, as in `echo "#"`, is treated as literal text.

### Semicolon `;`

The semicolon separates multiple commands on a single line. Commands run **sequentially**, in the order written.

```
echo "First"; echo "Second"; echo "Third"
```

Output:

```
First
Second
Third
```

> Commands separated by `;` run even if an earlier command fails.

### Asterisk `*`

The asterisk is a **wildcard** that matches any sequence of characters, including no characters.

```
ls *.txt
```

This lists matching names in the current directory that end in `.txt`.

Example matches:

```
notes.txt
data.txt
file123.txt
```

### Question Mark `?`

The question mark is a wildcard that matches **exactly one character**.

```
ls file?.txt
```

Example matches:

```
file1.txt
fileA.txt
```

It does **not** match `file.txt` or `file12.txt`, because the wildcard requires exactly one character.

## Quoting

**Quoting** controls how the shell interprets spaces and special characters. It allows text to be treated literally and keeps strings containing spaces together as one argument.

|Symbol|Meaning|
|---|---|
|`\`|Escapes the next character|
|`"..."`|Preserves literal text while allowing variable expansion and command substitution|
|`'...'`|Preserves all enclosed characters literally|

### Backslash `\`

A backslash removes the special meaning of the next character.

For example, escape spaces to create a file whose name contains spaces:

```
touch file\ with\ space.txt
```

The resulting filename is:

```
file with space.txt
```

You can also escape `$` to prevent variable expansion:

```
echo \$USER
# Output: $USER
```

### Double Quotes `"..."`

Double quotes preserve spaces and most characters literally, while still allowing **variable expansion** and **command substitution**.

```
echo "Hello $USER"
```

Example output:

```
Hello rodrigo
```

> **Note:** Double quotes do not activate every metacharacter. For example, `*` and `?` inside double quotes remain literal rather than expanding to filenames.

### Single Quotes `'...'`

Single quotes preserve all enclosed characters **literally**, preventing variable expansion and command substitution.

```
echo 'Hello $USER'
```

Output:

```
Hello $USER
```

The shell prints `$USER` as text instead of retrieving its value.

## Input/Output Redirection

**Input/output (I/O) redirection** changes where a command receives input or sends output.

In an interactive terminal, commands normally receive input from the keyboard and display output or errors in the terminal.

|Stream|File descriptor|Purpose|
|---|---|---|
|Standard input (`stdin`)|`0`|Input received by a command|
|Standard output (`stdout`)|`1`|Normal command output|
|Standard error (`stderr`)|`2`|Error messages|

### Redirection Operators

|Operator|Meaning|
|---|---|
|`>`|Redirect standard output to a file; overwrite existing contents|
|`>>`|Redirect standard output to a file; append|
|`2>`|Redirect standard error to a file; overwrite existing contents|
|`2>>`|Redirect standard error to a file; append|
|`<`|Read standard input from a file|

### Redirect Standard Output `>`

Use `>` to write a command’s standard output to a file:

```
ls > files.txt
```

The shell creates `files.txt` if it does not exist and writes the output of `ls` to it.

> [!warning]  
> If the file already exists, `>` overwrites its contents.

### Append Standard Output `>>`

Use `>>` to add output to the end of a file:

```
ls >> files.txt
```

Existing contents are preserved. The file is created if it does not exist.

### Redirect Standard Error `2>`

Use `2>` to write error messages to a file:

```
ls non-existent-directory 2> error.txt
```

The error from `ls` is written to `error.txt`.

> [!warning]  
> If the file already exists, `2>` overwrites its contents.

### Append Standard Error `2>>`

Use `2>>` to append error messages without removing existing contents:

```
ls non-existent-directory 2>> error.txt
```

### Redirect Standard Input `<`

Use `<` to supply a file’s contents as the command’s standard input:

```
sort < data.txt
```

The command reads from `data.txt` and displays the sorted lines in the terminal.

> **Remember:** `<` supplies input; it does not modify the source file.

## Command Substitution

**Command substitution** runs a command and uses its output within another command or a variable assignment.

There are two forms:

```
$(command)
```

```
`command`
```

The `$()` form is generally preferred because it is easier to read and nest.

### Example: Save and Return to the Current Directory

```
# Store the current directory's path
original_directory=$(pwd)

# Move to another directory
cd /tmp

# Return to the saved directory
cd "$original_directory"
```

Here, `$(pwd)` is replaced with the output of `pwd`, which is stored in `original_directory`.

### Example: Use Command Output in a Message

```
echo "The current directory is $(pwd)"
```

> **Key distinction:** `$variable` retrieves a variable’s value; `$(command)` runs a command and retrieves its output.

## Command-Line Arguments

**Command-line arguments** are values passed to a program or script when it is launched. They appear after the program or script name.

Arguments can provide input data, change behavior, or specify output locations.

```
./MyBashScript.sh arg1 arg2
```

Inside a Bash script, **positional parameters** provide access to these arguments:

|Parameter|Meaning|
|---|---|
|`$0`|Name or path used to invoke the script|
|`$1`|First argument|
|`$2`|Second argument|
|`$#`|Number of arguments|
|`"$@"`|All arguments, preserving each as a separate argument|

Example script:

```
#!/bin/bash

echo "Script: $0"
echo "First argument: $1"
echo "Second argument: $2"
```

Run it with:

```
./MyBashScript.sh Jeff Grossman
```

Output:

```
Script: ./MyBashScript.sh
First argument: Jeff
Second argument: Grossman
```

## Summary

- **Metacharacters** such as `#`, `;`, `*`, and `?` have special meanings.
- **Quoting** controls whether characters are interpreted literally or expanded.
- **Redirection** changes where commands read input or write output and errors.
- **Command substitution** uses a command’s output within another command or assignment.
- **Command-line arguments** pass information to scripts through positional parameters such as `$1` and `$2`.

# Introduction to Advanced Bash Scripting

Advanced Bash scripting combines **conditionals, logical operators, arithmetic, arrays, and loops** to automate more complex tasks.

## Objectives

After completing this reading, you should be able to:

- Run commands only when a specified condition is **true**.
- Combine conditions using **logical operators**.
- Perform basic **integer arithmetic**.
- Create **arrays** and access their elements.
- Use **`for` loops** to repeat operations.

## Conditionals

**Conditionals** allow a script to execute different commands depending on whether a condition is true or false.

### `if-then-else` Syntax

```
if [ condition ]; then
    # Commands executed when the condition is true
    statement_block_1
else
    # Commands executed when the condition is false
    statement_block_2
fi
```

- **True:** Bash executes the commands under `then`.
- **False:** Bash executes the commands under `else`.
- After `fi`, the script continues with the remaining commands.

> [!important]
> 
> - Spaces are required immediately inside `[ ]`.
> - Every `if` block must end with `fi`.
> - The `else` block is optional. Without it, a false condition simply skips the `then` block.

### Example: Check the Number of Arguments

The special parameter `$#` contains the number of command-line arguments passed to the script.

```
#!/bin/bash

if [ "$#" -eq 2 ]; then
    echo "Two arguments provided."
else
    echo "Please provide exactly two arguments."
fi
```

### Comparing Strings

Use `=` or `==` to compare strings in Bash:

```
string_var="Yes"

if [ "$string_var" = "Yes" ]; then
    echo "The answer is Yes."
else
    echo "The answer is not Yes."
fi
```

Bash also supports string comparisons inside double brackets:

```
if [[ "$string_var" == "Yes" ]]; then
    echo "The answer is Yes."
fi
```

> [!tip]  
> Quote variable expansions inside `[ ]` to handle empty values and strings containing spaces correctly.

## Comparison and Logical Operators

Comparison operators test values. Logical operators combine or negate conditions.

### Integer Comparisons

Use these operators inside `[ ]` or `[[ ]]`:

|Operator|Meaning|
|---|---|
|`-eq`|Equal to|
|`-ne`|Not equal to|
|`-lt`|Less than|
|`-le`|Less than or equal to|
|`-gt`|Greater than|
|`-ge`|Greater than or equal to|

```
a=2

if [ "$a" -le 3 ]; then
    echo "a is less than or equal to 3."
fi
```

For arithmetic conditions, use `(( ))` with familiar comparison symbols:

|Operator|Meaning|
|---|---|
|`==`|Equal to|
|`!=`|Not equal to|
|`<`|Less than|
|`<=`|Less than or equal to|
|`>`|Greater than|
|`>=`|Greater than or equal to|

```
if (( a <= 3 )); then
    echo "a is less than or equal to 3."
fi
```

> [!important]  
> Comparison syntax depends on context:
> 
> - `[ "$a" -le 3 ]` performs an integer comparison.
> - `(( a <= 3 ))` performs an arithmetic comparison.
> - `[ "$a" = "2" ]` compares text.

### Combining Conditions

|Operator|Meaning|
|---|---|
|`&&`|AND: both conditions must be true|
|`||
|`!`|NOT: reverses true and false|

#### AND `&&`

```
age=25

if [ "$age" -ge 18 ] && [ "$age" -le 65 ]; then
    echo "Age is between 18 and 65."
fi
```

#### OR `||`

```
answer="Yes"

if [[ "$answer" == "Yes" || "$answer" == "yes" ]]; then
    echo "Confirmed."
fi
```

#### NOT `!`

```
if [ ! "$answer" = "Yes" ]; then
    echo "The answer is not Yes."
fi
```

## Arithmetic Calculations

Use **arithmetic expansion** `$((expression))` to perform integer calculations.

```
echo $((3 + 2))
# Output: 5
```

You can also calculate using variables:

```
a=3
b=2
c=$((a + b))

echo "$c"
# Output: 5
```

Inside an arithmetic expression, variable names generally do not require `$`.

### Arithmetic Operators

|Symbol|Operation|
|---|---|
|`+`|Addition|
|`-`|Subtraction|
|`*`|Multiplication|
|`/`|Division|

```
echo $((3 - 2))  # Output: 1
echo $((3 * 2))  # Output: 6
echo $((3 / 2))  # Output: 1
```

> [!warning]  
> Bash’s native arithmetic uses integers. Integer division truncates the fractional part: `3 / 2` produces `1`, not `1.5`.

## Arrays

An **indexed array** stores multiple values under one name. Its elements are separated by spaces and enclosed in parentheses.

### Creating an Array

```
my_array=(1 2 "three" "four" 5)
```

This creates five elements: `1`, `2`, `three`, `four`, and `5`.

To declare an array without adding elements:

```
declare -a empty_array
```

### Appending Elements

Use `+=` with parentheses:

```
my_array+=("six")
my_array+=(7)
```

The array now contains:

```
1 2 three four 5 six 7
```

### Accessing Array Elements

|Expression|Meaning|
|---|---|
|`${my_array[0]}`|Element at index `0`|
|`${my_array[2]}`|Element at index `2`|
|`"${my_array[@]}"`|All elements, preserving each separately|
|`${#my_array[@]}`|Number of elements|
|`"${!my_array[@]}"`|All assigned indices|

```
echo "${my_array[0]}"
# Output: 1

echo "${my_array[2]}"
# Output: three

printf '%s\n' "${my_array[@]}"
# Prints each element on a separate line

echo "${#my_array[@]}"
# Output: 7
```

> [!important]  
> Array indexing starts at **0**, not 1. Use `"${my_array[@]}"` with double quotes to preserve elements containing spaces.

## `for` Loops

A **`for` loop** repeats commands for each item in a list or according to a numeric index.

### Iterating Over Array Values

```
for item in "${my_array[@]}"; do
    echo "$item"
done
```

Each iteration assigns the next array element to `item`.

### Iterating Over Array Indices

```
for i in "${!my_array[@]}"; do
    echo "${my_array[$i]}"
done
```

Each iteration assigns an array index to `i`, then retrieves the corresponding element.

### Loop Structure

```
for item in list; do
    # Commands to repeat
done
```

- `do` begins the loop body.
- `done` ends the loop.
- Use `;` before `do` when it appears on the same line.

Alternatively, place `do` on the next line:

```
for item in "${my_array[@]}"
do
    echo "$item"
done
```

### Numeric `for` Loops

When the number of iterations is known, use an arithmetic loop:

```
N=6

for ((i=0; i<=N; i++)); do
    echo "$i"
done
```

Output:

```
0
1
2
3
4
5
6
```

|Component|Purpose|
|---|---|
|`i=0`|Initializes the index|
|`i<=N`|Continues while the condition is true|
|`i++`|Increments the index after each iteration|

### Example: Count and Sum Array Elements

```
#!/bin/bash

numbers=(3 5 7 9)
count=0
sum=0

for number in "${numbers[@]}"; do
    count=$((count + 1))
    sum=$((sum + number))
done

echo "Number of elements: $count"
echo "Sum: $sum"
```

Output:

```
Number of elements: 4
Sum: 24
```

## Summary

- **Conditionals:** execute commands based on whether a condition is true.
- **Comparison operators:** compare strings or integers.
- **Logical operators:** combine or negate conditions using `&&`, `||`, and `!`.
- **Arithmetic expansion:** performs integer calculations using `$((...))`.
- **Arrays:** store multiple values accessible by index.
- **`for` loops:** repeat operations over values or indices.

> [!tip] Syntax Quick Reference
> 
> - `$variable` → retrieve a variable’s value.
> - `$(command)` → retrieve a command’s output.
> - `$((expression))` → retrieve an arithmetic result.
> - `${array[index]}` → retrieve an array element.

---
## Scheduling with Cron Jobs #cron

- Schedule jobs to run automatically at certain times
	- Load script at midnight every night
	- Backup script to run every Sunday at 2 AM
- Con allows you to automate task
-
Wat are Cron, Crond, and Contrab?
- Cron is a service that runs jobs
- Crond interprets "contab files"
- Crontab contains jobs and schedules data 
- Crontab enables to edit a Crontab file

```
crontab -e )opens editor)
job sytanx: 
	m h dom mon dow command
	30 15 * *  0 date >> sundays.txt
```

![[Pasted image 20260919012944.png]]

![[Pasted image 20260919013029.png]]

to delete cron job
```
crontab -e # add/remove cron hob with editor
```


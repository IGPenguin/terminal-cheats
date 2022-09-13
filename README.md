#Summary 

  - [What is it?](#section-id-2)
  - [Basic bash syntax](#section-id-9)
    - [Command chaining](#section-id-10)
    - [Variable comparsion](#section-id-17)
      - [Integer comparison operators](#section-id-22)
      - [String comparison operators](#section-id-31)
  - [Useful terminal commands](#section-id-43)
    - [man](#section-id-44)
    - [curl](#section-id-46)
    - [grep](#section-id-48)
    - [sort](#section-id-56)
    - [tr](#section-id-58)
    - [awk](#section-id-60)
    - [file](#section-id-62)
  - [Oneliners](#section-id-65)
    - [Run remote script](#section-id-66)
    - [Command result if](#section-id-68)
    - [Var is number](#section-id-70)
    - [Remove suff/pre-fix](#section-id-72)
    - [Format output into columns](#section-id-75)
    - [Schedule command](#section-id-77)
    - [Remove trailing carriage return](#section-id-79)
    - [Colorized output](#section-id-81)
  - [Code snippets](#section-id-85)
  - [Git](#section-id-88)
  - [Terminal shortcuts](#section-id-96)
  



<div id='section-id-2'/>

## What is it?
📃 **Terminal & bash cheat sheet**<br>
🙈 Sourced by Google search<br>
⚠️ Use at your own risk<br>
😍 **Contribute via [pull request](https://github.com/IGPenguin/terminal-cheat-sheet/pulls)**<br>
⭐️ Hit the star button, make me happy

<div id='section-id-9'/>

## Basic bash syntax
<div id='section-id-10'/>

### Command chaining
`command1; command2; command3;` - execute command regardless of success of the previous command<br>
`command1 && command2` - execute command2 if command1 executed successfully (exit code 0)<br>
`command1 || command2` - execute command2 if command1 execution failed (exit code != 0)<br>
`command1 &` - execute command as a background task<br>
`wait` - wait until triggered background tasks are done

<div id='section-id-17'/>

### Variable comparsion
`if [ "$var" -eq 1 ]`<br>
Always use **spaces between brackets and the condition** <br>
Always **quote a tested variable**<br>

<div id='section-id-22'/>

#### Integer comparison operators
**-eq** - equal to `if [ "$a" -eq "$b" ]`<br>
**-ne** - not equal to `if [ "$a" -ne "$b" ]`<br>
**-gt** - greater than if `[ "$a" -gt "$b" ]`<br>
**-ge** - greater than or equal to if `[ "$a" -ge "$b" ]`<br>
**-lt** - less than `if [ "$a" -lt "$b" ]`<br>
**-le** - less than or equal to `if [ "$a" -le "$b" ]`<br>
**\<, \<=, >, >=**  - within double parentheses `(("$a" < "$b"))`<br>

<div id='section-id-31'/>

#### String comparison operators
**-n** - string is not null `if [ -n "$string" ]`<br>
**-z** - string is null, that is, has zero length `if [ -z "$string" ]`<br>
**= or ==** - equal to, `if [ "$a" = "$b" ]`<br>
**!=** - not equal to, if [ "$a" != "$b" ]<br>
The == comparison operator behaves differently within a double-brackets test than within single brackets<br>
`[[ $a == z* ]]`   - true if $a starts with an "z" (pattern matching)<br>
`[[ $a == "z*" ]]` or `[ "$a" == "z*" ]` - true if $a is equal to z* (literal matching)<br>
`[ $a == z* ]` - file globbing and word splitting take place<br>
\< - less than, in ASCII alphabetical order, if [[ "$a" < "$b" ]], if [ "$a" \< "$b" ]<br>
\> - greater than, in ASCII alphabetical order, if [[ "$a" > "$b" ]], if [ "$a" \> "$b" ]<br>

<div id='section-id-43'/>

## Useful terminal commands
<div id='section-id-44'/>

### man
`man <command>` - show command manual, exit with q
<div id='section-id-46'/>

### curl
`curl -o <filename> -k <url>` - download file from url
<div id='section-id-48'/>

### grep
`grep <text>` - find lines containing \<text><br>
`grep ^<text>` - find \<text> at the start of a line<br>
`grep <text>$` - find \<text> at the end of a line<br>
`grep <text>.` - find line with \<text> and exactly one character immediately after it<br>
`grep <text>.?` - find line with \<text> and one optional character immediately after it<br>
`grep <text>Z+` - find line with \<text> and one or more Z characters immediately after it<br>
`grep <text>*` - find line with \<text> and any number of characters immediately after it<br>
<div id='section-id-56'/>

### sort
`sort -u` - strip duplicate lines
<div id='section-id-58'/>

### tr
`echo "some.string.with.dots" | tr . _` - replace dots with underscores
<div id='section-id-60'/>

### awk
`cat <some-file> | awk '{print $2}'` - get second word from each line
<div id='section-id-62'/>

### file
`file image_file.jpg` - file information including image resolution etc

<div id='section-id-65'/>

## Oneliners
<div id='section-id-66'/>

### Run remote script
`curl -L https://raw.githubusercontent.com/dummyuser/great-repo/master/install.sh | bash`
<div id='section-id-68'/>

### Command result if
`[ $(id -u) -eq 0 ] && return $TRUE || return $FALSE`
<div id='section-id-70'/>

### Var is number
`[ "$VAR" =~ ^[0-9]+$ ]`
<div id='section-id-72'/>

### Remove suff/pre-fix
`foo=${string#"$prefix"}`<br>
`foo=${foo%"$suffix"}`<br>
<div id='section-id-75'/>

### Format output into columns
`echo <tbd> | column` 
<div id='section-id-77'/>

### Schedule command
`<cmd> | at <time>` - run command at scheduled time
<div id='section-id-79'/>

### Remove trailing carriage return
`echo "<some-text-with-newline>" | tr -d '\r'`
<div id='section-id-81'/>

### Colorized output
`tput setaf 1; echo WARNING; tput sgr0;`<br>
[Output color codes](https://unix.stackexchange.com/questions/269077/tput-setaf-color-table-how-to-determine-color-codes)<br>

<div id='section-id-85'/>

## Code snippets
[Argument handling](https://github.com/IntergalacticPenguin/mobile-toolkit/blob/master/android/aoptions)

<div id='section-id-88'/>

## Git
`git reset --soft` - cancel commits, keep changes<br>
`git branch -m new-name` - rename local branch<br>
`git branch -d <branch_name> - delete local branch`<br>
`git commit --amend` - add to previous commit<br>
`git remote prune origin` - remove merged branches<br>
[Code conflict resolution command line manual](https://help.github.com/en/articles/resolving-a-merge-conflict-using-the-command-line)<br>

<div id='section-id-96'/>

## Terminal shortcuts
ctrl+u - stash command<br>
ctrl+y - pop stash<br>
ctrl+l - clear<br>

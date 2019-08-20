Bash Knowledge

Remove suff/pre-fix
foo=${string#"$prefix"}
foo=${foo%"$suffix"}

file videothumb.jpg - info o obrazku atd

https://unix.stackexchange.com/questions/269077/tput-setaf-color-table-how-to-determine-color-codes
tput setaf 1;echo WARNING;tput sgr0 - colorized output


tr -d '\r' - remove trailing carriage return

column - sloupce
<cmd> | at - at some time

ctrl+u - stash command
ctrl+y - pop stash
ctrl+l - clear

integer comparison
-eq is equal to, if [ "$a" -eq "$b" ]
-ne is not equal to, if [ "$a" -ne "$b" ]
-gt is greater than, if [ "$a" -gt "$b" ]
-ge is greater than or equal to, if [ "$a" -ge "$b" ]
-lt is less than, if [ "$a" -lt "$b" ]
-le is less than or equal to, if [ "$a" -le "$b" ]
<, <=, >, >= within double parentheses(("$a" < "$b"))

string comparison
= or == is equal to, if [ "$a" = "$b" ]
The == comparison operator behaves differently within a double-brackets test than within single brackets.
[[ $a == z* ]]   # True if $a starts with an "z" (pattern matching).
[[ $a == "z*" ]] # True if $a is equal to z* (literal matching).
[ $a == z* ]     # File globbing and word splitting take place.
[ "$a" == "z*" ] # True if $a is equal to z* (literal matching).
!= is not equal to, if [ "$a" != "$b" ]
< is less than, in ASCII alphabetical order, if [[ "$a" < "$b" ]], if [ "$a" \< "$b" ]
> is greater than, in ASCII alphabetical order, if [[ "$a" > "$b" ]], if [ "$a" \> "$b" ]
-z string is null, that is, has zero length, if [ -z "$String" ]
-n string is not null.

Caution
Always quote "$STRING" a tested string.

is_root(){
   [ $(id -u) -eq 0 ] && return $TRUE || return $FALSE
}

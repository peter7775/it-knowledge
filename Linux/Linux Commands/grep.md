# How To Use grep Command In Linux / UNIX
How do I use grep command on Linux or Apple macOS/OS X? How can I use grep command on Unix operating systems? Can you give me a simple examples of the grep command?

The grep command is used to search text. It searches the given file for lines containing a match to the given strings or words. It is one of the most useful commands on Linux and Unix-like system. Let us see how to use grep on a Linux or Unix like system.
### Did you know?
The name, “grep”, derives from the command used to perform a similar operation, using the Unix/Linux text editor ed:
`g/re/p` 
### grep command examples
Common grep command explained with examples in Linux:
    1. `grep 'word' filename` – Search any line that contains the word in filename on Linux
    2. `grep -i 'bar' file1` – A case-insensitive search for the word ‘bar’ in Linux and Unix
    3. `grep -R 'foo' .` – Search all files in the current directory and in all of its subdirectories in Linux for the word ‘foo’
    4. `grep -c 'nixcraft' frontpage.md` – Search and display the total number of times that the string ‘nixcraft’ appears in a file named frontpage.md
### The grep command syntax in Linux / Unix
The syntax is as follows:
`grep 'word' filename`
`grep 'word' file1 file2 file3`
`grep 'string1 string2'  filename`
`cat otherfile | grep 'something'`
`command | grep 'something'`
`command option1 | grep 'data'`
`grep --color 'data' fileName`
### How do I use grep to search a file on Linux?
Search /etc/passwd file for boo user, enter:
`$ grep boo /etc/passwd`
Sample outputs:
foo:x:1000:1000:boo,,,:/home/boo:/bin/ksh
You can force grep to ignore word case i.e match boo, Boo, BOO and all other combination with the -i option:
`$ grep -i "boo" /etc/passwd`

The last grep -i "boo" /etc/passwd can run as follows using the cat command too:
`cat /etc/passwd | grep -i "boo"`
### How to use grep recursively
You can search recursively i.e. read all files under each directory for a string “192.168.1.5”
`$ grep -r "192.168.1.5" /etc/`
OR
`$ grep -R "192.168.1.5" /etc/`
Sample outputs:
/etc/ppp/options:# ms-wins 192.168.1.50
/etc/ppp/options:# ms-wins 192.168.1.51
/etc/NetworkManager/system-connections/Wired connection 1:addresses1=192.168.1.5;24;192.168.1.2;
You will see result for 192.168.1.5 on a separate line preceded by the name of the file (such as /etc/ppp/options) in which it was found. The inclusion of the file names in the output data can be suppressed by using the -h option as follows:
`$ grep -h -R "192.168.1.5" /etc/`
OR
`$ grep -hR "192.168.1.5" /etc/`
Sample outputs:
ms-wins 192.168.1.50
ms-wins 192.168.1.51
addresses1=192.168.1.5;24;192.168.1.2;
### How to use grep to search words only
When you search for boo, grep will match fooboo, boo123, barfoo35 and more. You can force the grep command to select only those lines containing matches that form whole words i.e. match only boo word:
`$ grep -w "boo" file`
### How to use grep to search 2 different words
Use the egrep command as follows:
`$ egrep -w 'word1|word2' /path/to/file`
### How can I count line when words has been matched
The grep can report the number of times that the pattern has been matched for each file using -c (count) option:
`$ grep -c 'word' /path/to/file`
Pass the -n option to precede each line of output with the number of the line in the text file from which it was obtained:
`$ grep -n 'root' /etc/passwd`
Sample outputs:
1:root:x:0:0:root:/root:/bin/bash
1042:rootdoor:x:0:0:rootdoor:/home/rootdoor:/bin/csh
3319:initrootapp:x:0:0:initrootapp:/home/initroot:/bin/ksh
### Force grep invert match
You can use -v option to print inverts the match; that is, it matches only those lines that do not contain the given word. For example print all line that do not contain the word bar:
`$ grep -v bar /path/to/file`
### UNIX / Linux pipes and grep command
grep command often used with shell pipes. In this example, show the name of the hard disk devices:
`dmesg | egrep '(s|h)d[a-z]'`
Display cpu model name:
`cat /proc/cpuinfo | grep -i 'Model'`
However, above command can be also used as follows without shell pipe:
`grep -i 'Model' /proc/cpuinfo`
Sample outputs:
model           : 30
model name      : Intel(R) Core(TM) i7 CPU       Q 820  @ 1.73GHz
model           : 30
model name      : Intel(R) Core(TM) i7 CPU       Q 820  @ 1.73GHz
One of my favorite usage of grep or egrep command to filter the output of the yum command/dpkg command/apt command/apt-get command:
`dpkg --list | grep linux-image`
`yum search php | grep gd`
`apt search maria | egrep 'server|client'`

### How do I list just the names of matching files?
Use the -l option to list file name whose contents mention main():
`$ grep -l 'main' *.c`
Finally, you can force grep to display output in colors, enter:
`$ grep --color vivek /etc/passwd`


### Conclusion
The grep command in Unix/Linux summary is as follows:
Linux grep command options
`-i`
Ignore case distinctions on Linux and Unix
`-w`
Force PATTERN to match only whole words
`-v`
Select non-matching lines
`-n`
Print line number with output lines
`-h`
Suppress the Unix file name prefix on output
`-r`
Search directories recursivly on Linux
`-R`
Just like -r but follow all symlinks
`-l`
Print only names of FILEs with selected lines
`-c`
Print only a count of selected lines per FILE
`--color`
Display matched pattern in colors
If you enjoyed the grep tutorial, then you might like to read our “Regular Expressions in Grep” tutorial. You can view gnu grep man page here.

## Regular Expressions In grep examples


How do I use the grep command with regular expressions on a Linux and Unix-like operating systems? How do I use grep and regular expressions to search for text/ words in Linux?

Linux comes with GNU grep, which supports extended regular expressions. GNU grep is the default on all Linux systems. The grep command is used to locate information stored anywhere on your server or workstation.
Advertisements
### Regular Expressions in grep
[donotprint][/donotprint]
Regular Expressions is nothing but a pattern to match for each input line. A pattern is a sequence of characters. Following all are examples of pattern:
^w1
w1|w2
[^ ]
foo
bar
[0-9]
### grep Regular Expressions Examples
Search for ‘vivek’ in /etc/passswd
`grep 'vivek' /etc/passwd`
Sample outputs:
vivek:x:1000:1000:Vivek Gite,,,:/home/vivek:/bin/bash
vivekgite:x:1001:1001::/home/vivekgite:/bin/sh
gitevivek:x:1002:1002::/home/gitevivek:/bin/sh

Search vivek in any case (i.e. case insensitive search)
`grep -i -w 'vivek' /etc/passwd`

Search vivek or raj in any case
`grep -E -i -w 'vivek|raj' /etc/passwd`
The PATTERN in last example, used as an extended regular expression.

The following will match word Linux or UNIX in any case:
`egrep -i '^(linux|unix)' filename`

### How to match single characters
The . character (period, or dot) matches any one character. Consider the following demo.txt file:
$ cat demo.txt
Sample outputs:
foo.txt
bar.txt
foo1.txt
bar1.doc
foobar.txt
foo.doc
bar.doc
dataset.txt
purchase.db
purchase1.db
purchase2.db
purchase3.db
purchase.idx
foo2.txt
bar.txt
Let us find all filenames starting with purchase:
`grep 'purchase' demo.txt`
Next I need to find all filenames starting with purchase and followed by another character:
`grep 'purchase.db' demo.txt`
Our final example find all filenames starting with purchase but ending with db:
`grep 'purchase..db' demo.txt` 

### How to match only dot (.)
A dot (.) has a special meaning in regex, i.e. match any character. But, what if you need to match dot (.) only? I want to tell my grep command that I want actual dot (.) character and not the regex special meaning of the . (dot) character. You can escape the dot (.) by preceding it with a \ (backslash):
`grep 'purchase..' demo.txt`
`grep 'purchase.\.' demo.txt`

### Anchors
You can use ^ and $ to force a regex to match only at the start or end of a line, respectively. The following example displays lines starting with the vivek only:
`grep ^vivek /etc/passwd`
Sample outputs:
vivek:x:1000:1000:Vivek Gite,,,:/home/vivek:/bin/bash
vivekgite:x:1001:1001::/home/vivekgite:/bin/sh
You can display only lines starting with the word vivek only i.e. do not display vivekgite, vivekg etc:
`grep -w ^vivek /etc/passwd`
Find lines ending with word foo:
`grep 'foo$' filename`
Match line only containing foo:
`grep '^foo$' filename`
You can search for blank lines with the following examples:
`grep '^$' filename`
Matching Sets of Characters
### How to match sets of character using grep
The dot (.) matches any single character. You can match specific characters and character ranges using [..] syntax. Say you want to Match both ‘Vivek’ or ‘vivek’:
`grep '[vV]ivek' filename`
OR
`grep '[vV][iI][Vv][Ee][kK]' filename`
You can also match digits (i.e match vivek1 or Vivek2 etc):
`grep -w '[vV]ivek[0-9]' filename`
You can match two numeric digits (i.e. match foo11, foo12 etc):
`grep 'foo[0-9][0-9]' filename`
You are not limited to digits, you can match at least one letter:
`grep '[A-Za-z]' filename`
Display all the lines containing either a “w” or “n” character:
`grep [wn] filename`
Within a bracket expression, the name of a character class enclosed in “[:” and “:]” stands for the list of all characters belonging to that class. Standard character class names are:
    • [[:alnum:]] – Alphanumeric characters.
    • [[:alpha:]] – Alphabetic characters
    • [[:blank:]] – Blank characters: space and tab.
    • [[:digit:]] – Digits: ‘0 1 2 3 4 5 6 7 8 9’.
    • [[:lower:]] – Lower-case letters: ‘a b c d e f g h i j k l m n o p q r s t u v w x y z’.
    • [[:space:]] – Space characters: tab, newline, vertical tab, form feed, carriage return, and space.
    • [[:upper:]] – Upper-case letters: ‘A B C D E F G H I J K L M N O P Q R S T U V W X Y Z’.
In this example match all upper case letters:
`grep '[:upper:]' filename`
How negates matching in sets
The ^ negates all ranges in a set:
`grep '[vV]ivek[^0-9]' test`

### Wildcards
You can use the “.” for a single character match. In this example match all 3 character word starting with “b” and ending in “t”:
`grep '\<b.t\>' filename`
Where,
    • \< Match the empty string at the beginning of word
    • \> Match the empty string at the end of word.
Print all lines with exactly two characters:
`grep '^..$' filename`
Display any lines starting with a dot and digit:
`grep '^\.[0-9]' filename`
### Escaping the dot
Say you just want to match an IP address 192.168.2.254 and nothing else. The following regex to find an IP address 192.168.1.254 will not work (remember the dot matches any single character?):
`grep '192.168.1.254' hosts`
Sample outputs:
192.168.2.18        centos7
192x168y2z18        centos7
All three dots need to be escaped:
192.168.2.18        centos7
`grep '192\.168\.1\.254' hosts`
The following example will only match an IP address:
`egrep '[[:digit:]]{1,3}\.[[:digit:]]{1,3}\.[[:digit:]]{1,3}\.[[:digit:]]{1,3}' filename`
### How Do I Search a Pattern Which Has a Leading – Symbol?
Searches for all lines matching ‘–test–‘ using -e option Without -e, grep would attempt to parse ‘–test–‘ as a list of options:
`grep -e '--test--' filename`
### How Do I do OR with grep?
Use the following syntax:
`grep -E 'word1|word2' filename`
OR
`egrep 'word1|word2' filename`

OR
`grep 'word1\|word2' filename`
### How do I AND with grep?
Use the following syntax to display all lines that contain both ‘word1’ and ‘word2’
`grep 'word1' filename | grep 'word2'`
OR
`grep 'foo.*bar\|word3.*word4' filename`
### How Do I Test Sequence?
You can test how often a character must be repeated in sequence using the following syntax:
{N}
{N,}
{min,max}
Match a character “v” two times:
`egrep "v{2}" filename`
The following will match both “col” and “cool”:
`egrep 'co{1,2}l' filename`
The following will match any row of at least three letters ‘c’.
`egrep 'c{3,}' filename`
The following example will match mobile number which is in the following format 91-1234567890 (i.e twodigit-tendigit)
`grep "[[:digit:]]\{2\}[ -]\?[[:digit:]]\{10\}" filename`
### How Do I Hightlight with grep?
Use the following syntax:
`grep --color regex filename`
### How Do I Show Only The Matches, Not The Lines?
Use the following syntax:
`grep -o regex filename`
### grep Regular Expression Operator
I hope following table will help you quickly understand regular expressions in grep when using under Linux or Unix-like systems:
`grep regex operator`
Meaning
Example
.
Matches any single character.
`grep '.' file`
`grep 'foo.' input`
`?`
The preceding item is optional and will be matched, at most, once.
`grep 'vivek?' /etc/passwd`
`*`
The preceding item will be matched zero or more times.
`grep 'vivek*' /etc/passwd`
`+`
The preceding item will be matched one or more times.
```
ls /var/log/ | grep -E "^[a-z]+\.log."
{N}
```
The preceding item is matched exactly N times.
```
egrep '[0-9]{2} input
{N,}
```
The preceding item is matched N or more times.
```
egrep '[0-9]{2,} input
{N,M}
```
The preceding item is matched at least N times, but not more than M times.
```
egrep '[0-9]{2,4} input
–
```
Represents the range if it’s not first or last in a list or the ending point of a range in a list.
```
grep ':/bin/[a-z]*' /etc/passwd
^
```
Matches the empty string at the beginning of a line; also represents the characters not in the range of a list.
```
grep '^vivek' /etc/passwd
grep '[^0-9]*' /etc/passwd
$
```
Matches the empty string at the end of a line.
```
grep '^$' /etc/passwd
\b
```
Matches the empty string at the edge of a word.
```
vivek '\bvivek' /etc/passwd
\B
```
Matches the empty string provided it’s not at the edge of a word.
```
grep '\B/bin/bash /etc/passwd
\<
```
Match the empty string at the beginning of word.
```
grep '\
\>
```
Match the empty string at the end of word.
```
grep 'bash\>' /etc/passwd
grep '\
```
### grep vs egrep
egrep is the same as grep -E. It interpret PATTERN as an extended regular expression. From the grep man page:
In basic regular expressions the meta-characters ?, +, {, |, (, and ) lose their special meaning; instead use the backslashed versions \?, \+, \{,\|, \(, and \).

Traditional egrep did not support the { meta-character, and some egrep implementations support \{ instead, so portable scripts should avoid  {  in
       grep -E patterns and should use [{] to match a literal {.
	   GNU grep -E attempts to support traditional usage by assuming that { is not special if it would be the start of an invalid interval specification.
       For example, the command grep -E '{1' searches for the two-character string {1 instead of reporting a syntax  error  in  the  regular  expression.
       POSIX.2 allows this behavior as an extension, but portable scripts should avoid it.
### References:
• man page grep and regex(7)
    • info page grep
	
* * *
https://www.howtogeek.com/496056/how-to-use-the-grep-command-on-linux/
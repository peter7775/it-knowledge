## cat
Basic viewer. Write FILE(s) to standard output. With no FILE, or when FILE is -, read standard input.
## less
Less  is a program similar to more (1), but which allows backward movement in the file as well as forward movement.  Also, less does not have to read the entire input file before starting, so
with large input files it starts up faster than text editors like vi (1). 
## head
Print the first 10 lines of each FILE to standard output.  With more than one FILE, precede each with a header giving the file name.
## tail
Print the last 10 lines of each FILE to standard output.  With more than one FILE, precede each with a header giving the file name.
##  nl
Write each FILE to standard output, with line numbers added.
Good to combine with some view command like:
`nl text.txt | less`
## od
Write an unambiguous representation, octal bytes by default, of FILE to standard output.  With more than one FILE argument, concatenate them in the listed order to form the input.
## xxd
xxd  creates  a  hex  dump of a given file or standard input.  It can also convert a hex dump back to its original binary form.
## gv
## pv
## xvdi

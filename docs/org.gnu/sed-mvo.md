## NAME
 sed, minimum Viable operating instruction for package org/gnu/sed using *Substitute* command

## SYNOPSIS

```lang-sh
# Generic invoke
sed [OPTIONS] [SCRIPT] [STREAM]
```

```lang-sh
# Substitute command invotation
sed [OPTIONS] [address]s/[regexp]/[substitute]/[flags] [STREAM]
```

## DESCRIPTION
A working example of the minimum syntax values necessary for successful execution of gnu `sed` package. `sed` includes a fully featured scripting language [sed, gnu.org, 2023][4].

## INSTALLATION
- na, installed with various Linux kernels 

### Substitute invoke
This example will demonstrate the sed(1) substitute command, which replaces characters read from a file. 

- *[OPTIONS]* will include `-E` forcing the pattern syntax used to [POSIX regexp, gnu.org, 2023][2], not [Glob Wildcard, gnu.org, 2023][5]
- *[SCRIPT]* the command to be executed on each line of the Stream (line separators are `\r\n` or `\n), the substitution text command syntax:
  - *[address]* sed executes on lines that match the pattern `/[0-9]{1,5}$/`, the $ symbol matches a number at the end of the line [sed-addresses, gnu.org, 2023][1]
  - *s/* flag telling sed to use *substitute* command
  - *[regexp]* text to be removed. `/^#[ ]*/` will replace lines beginning with hash (^ means beginning of line) [POSIX regexp, gnu.org, 2023][2]
  - *[substitute]* replacement text, in this case it is empty
  - *[flags]* sed flags. 'g' will replace all matches for the current line
- *[STREAM]*, we will use a local file `/tmp/test.conf`

```lang-sh
~$ echo -e "# one two 12\n# three four\n# five six 56\n#seven eight 12\n# nine 999999\nhello=two\nthree\nblah # happy" >> /tmp/test.conf
cat /tmp/test.conf
# one two 12
# three four
# five six 56
#seven eight 12
# nine 999999
hello=two
three
blah # happy

~$ # Replace the first match in each line
~$ sed -E '/[0-9]{1,5}$/s/^#[ ]*//' /tmp/test.conf
one two 12
one two 12
# three four
five six 56
seven eight 12
hello=two
three
blah # happy

~$ # Replace all matches 
~$ echo "hello;world;two" | sed -E 's/\;/\n/g'
hello
world
two

```

## EXPLANATORY NOTES

1. *[SCRIPT]*, can also be retrieved: 
   - (from file) `sed ./my_script.sed [STREAM]`
1. *[STREAM]*, can also be:
   - (a piped string) `echo "# hello world" | sed [SCRIPT]`
   - (a piped command output) `cat ./input.txt | sed [SCRIPT]`
  - (piped Network location) `wget -O - http://stackoverflow.com | sed [SCRIPT]`, FYI: [Wget, gnu.org, 2023][3]
1. alternatives for the *[ADDRESS]*:
   - `/\b\(two|three|[0-9]{1,5}\)/`, will execute the command on lines containing numbers or **word** 'two' or 'three'.

## DEPENDENCIES

org.gnu.sed == 4.8

  [1]: https://www.gnu.org/software/sed/manual/sed.html#sed-addresses
  [2]: https://www.gnu.org/software/gnulib/manual/html_node/Regular-expressions.html
  [3]: https://www.gnu.org/software/wget/manual
  [4]: https://www.gnu.org/software/sed/manual/sed.html
  [5]: https://www.gnu.org/software/libc/manual/html_node/Wildcard-Matching.html

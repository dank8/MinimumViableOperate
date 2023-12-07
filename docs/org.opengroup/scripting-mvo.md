## NAME
 utilitiy, minimum viable operating instruction for POSIX *standard utilities*, guidelines for writing maintainable code.

## SYNOPSIS

```lang-sh
 # Generic Utility convention
UTILITY_NAME [OPTIONS...] [OPERANDS...]
```
```lang-sh
 # valid USAGE definition
UTILITY_NAME [ -abcd argument][ -e][ -f][ -g argument][ -h| -i] [--] [OPERAND...]
```

## DESCRIPTION
A working examples of the minimum syntax values necessary for successful execution of utilities and scripts from the command line.

> "argument syntax of the standard utilities and introduces terminology used throughout POSIX.1-2017 for describing the arguments processed by the utilities." [opengroup.org, 2023](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap12.html#tag_12)

1. Utility Conventions [opengroup.org, 2023](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap12.html#tag_12_01)
   - regexp pattern for validation (TBC)
   - use <blank> to separate each item (Guideline 6)
   - *UTILITY_NAME* alphanumeric string, validating regexp pattern `/[a-z0-9]{2,9}/` (Guideline 1, 2)
   - *OPTIONS* must either be `-OPTION` or a pair `-OPTIONS ARGUMENT` (Guideline 3, 4, 6, 7, 14)
     - <hyphen> mandatory, indicates the next character is *OPTION* 
     - *OPTION* {1,...}, single char `-a` (historically known as "flags"), validating regexp pattern `/\b\-[A-Za-vx-z0-9]+\b/`  
       - scripts often use 'long' options `--item-is-long`, validating regexp pattern `/\b\-\-[-A-Za-vx-z0-9]+\b/`
       - can be declared together `-abcd ARGUMENT`, the *ARGUMENT* relates to last *OPTION* for instance `[a,b,c,d=ARGUMENT]` (Guideline 5)
     - *ARGUMENT* {0,1}, a string immediately preceeding *OPTION* 
       - `-a one -bc two` is interpreted to `[a=one, b, c=two]`
       - <blank> inside of *ARGUMENT*s must be enclosed with single or double quotes
       - <comma> or <blank> delimit if muliple arguments are used for an *OPTION* (Guideline 8)
   - order is not enfoced for *OPTIONS* 
   - *OPERAND* {0,1}, string without a preceding *OPTION*
     - the following are signal the end of *OPTIONS* `--` and string without *OPTION* (Guideline 9, 10)
     - order is enforced for *OPERAND* (Guideline 12)
     - `-` indicates file for standard input and output, or a file named `-` (Guideline 13)
1. Examples demonstrating how Utility Syntax sees command line arguments:
```
./getopts_test "hello"-ab how-to-geek,"dave dee" -c dozy beaky -d -mick - tich
./getopts_test -ab how-to-geek,"dave dee" -c dozy beaky -d -mick - tich
./getopts_test -ab how-to-geek,"dave dee" -- -c dozy beaky -mick - tich
```
   - using script
```lang-sh
#!/bin/bash
# File name ./getopts_test
# examples
# ./getopts_test "hello"-ab how-to-geek,"dave dee" -c dozy beaky -d -mick - tich
# ./getopts_test -ab how-to-geek,"dave dee" -c dozy beaky -d -mick - tich
# ./getopts_test -ab how-to-geek,"dave dee" -- -c dozy beaky -mick - tich

# INPUT VALIDATION
usage() { echo "Usage: $0 -o OPTSTRING OPTIONS [OPERANDS]"; echo "OPTSTRING must conform to getopts() reference: pubs.opengroup.org" 1>&2; exit 1; }
if [[  $# -lt 1 ]]; then usage; fi

# Pattern detect
optstring=""
for (( itm=1; itm<=$#; itm++ ))
do
	result=${!itm}
	case ${result} in
		--?* ) echo "WARNING: getopts() does not recognise --long-form OPTIONS." 1>&2 ;;
		--   ) break ;;
		-?*  ) optstring+=${result:1} ;;
		*    ) if [[ ${#optstring} -lt 1 || ${optstring: -1} == ":" ]]; then  break; else optstring+=":"; fi ;;
	esac
done

# OPTIONS
echo "> arg count: $#, USAGE: getopts '$optstring' optname"
echo "TYPE  	FLAG	VALUE"
curItem=1
while getopts $optstring optname
do
	if [[ $optname != '?' ]]
	then
		echo "[OPT]	$optname	$OPTARG"
	fi
	curItem=$OPTIND
done

# OPERANDS
for (( itm=$curItem; itm<=$#; itm++ ))
do
	if [[ ${!itm} == '--' ]]
	then echo "[FLAG]	${!itm}"; 
	else echo "[OPER]	${!itm}"; fi
done
```

> QUOTE FROM DEVELOPER

### INSTALLATION

na, installed with various linux kernels 

### invoke
This example will demonstrate getopts command. 

- *VAR* variable name for writing each option argument to. 
- *[SCRIPT]* is the command to be executed against each line of the Stream 
  - *[supressError]* colon as the first character will suppress errors   - *[address]* sed executes on lines that match the pattern `/[0-9]{1,5}$/`, the $ symbol will match numbers at the end of the line [sed-addresses, gnu.org, 2023][1]
  - Repeating options:
    - *[ARG]* single alpha-character flag
    - *[hasValue]* colon only after option requiring a value. 
  - *s/* flag telling sed to use *substitute* command
  - *[regexp]* text to be removed. `/^#[ ]*/` will replace lines beginning with hash (^ means beginning fo line) [POSIX regexp, gnu.org, 2023][2]
  - *[substitute]* replacement text, in this case its empty
  - *[flags]* sed flags. 'g' will replace all matches for the current line
- *[STREAM]*, we will use a local file `/tmp/test.conf`


```lang-sh
$ COMMAND
OUTPUT
```

### EXPLANATORY NOTES

1. 

> "The first -- argument that is not an option-argument should be accepted as a delimiter indicating the end of options" [opengroup.org, 2023](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap12.html#tag_12_02), Guideline 10.


## Dependencies

PACKAGE == VERSION

### References

  [1]: # ️TODO


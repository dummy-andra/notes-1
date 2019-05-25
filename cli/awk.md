# awk

## Summary
"The basic function of awk is to search files for lines that contain certain pattersn." (GEAP:17)
pattern-scanning utility and processing languages, one of the two primary commands which accept regular expressions in Unix systems.

## Command line
awk programs can be defined _inline_ or in a _program-file_ (PGL:528)
  - inline: `awk options 'program' input-files`
  - program-file, also "source-file" (GEAP:18): `awk options -f program-file input-files` 

awk programs can be run without defining _input-files_, in which case awk will accept input from stdin

### Options
`-Fx` | `-F="x"` : sets field separator `FS` to {x}
`-f program-file` | `--file program-file` : specify awk program-file {program-file}
`-v var=value` | `--assign var=value` : sets variable {var} to {value} before script is executed (even before `BEGIN` pattern)
`--` : POSIX-standard flag which marks end of command-line options (allowing specification of a datafile with a "-" at the beginning of its filename)

## Scripts
`#!/bin/awk -f` : shebang
`#` : comments begin with octothorpe

## Programs
awk programs are the equivalent of sed "instructions", and similarly combine _patterns_ and _actions_ (PGL:530, GEAP:17)

### Patterns
Patterns can be:
  - regular expressions or fixed strings
  - line numbers using builtin variable `NR`
  - predefined patterns `BEGIN` or `END`, whose actions are executed before and after processing any lines of the data file, respectively

## Predefined variables
`$0` : current record
`$n` : field number {n}
`ARGC` : awk builtin variable that contains the number of arguments in command line
`ARGV` : awk builtin variable that contains the list of arguments
`FILENAME` : awk builtin variable that contains the current input filename
`FNR` : awk builtin variable that contains the number of the current record relative to the current input file
`FS` : awk builtin variable that contains the field separator (' ' by default)
`NF` : awk builtin variable that contains the number of fields for the current input record
`NR` : awk builtin variable that contains the number of the current input record
`OFS` : awk builtin variable that contains the output field separator (' ' by default)
`ORS` : awk builtin variable that contains the output record separator
`RS` : awk builtin variable that contains the record separator (newline)

## Functions
`gsub(regex,substitution[,string])` : replace all instances of {regex} with {substitution} in {string} (defaults to $0 if not provided)
`sub(regex,substitution[,string])` : replace first instance of {regex} with {substitution} in {string} (defaults to $0 if not provided)
`index(substring,string)` : return (1-indexed) position of {substring} within {string}, or 1 if not found
`length(string)` : return length of {string} (defaults to $0 if not provided)
`match(string,regex)` : return position in {string} where {regex} begins, or 0 if not found
`printf("control-string",*args)` : formatted strings (see below)
`split(string,array,delim)` : break up {string} by delimiter {delim} and store the fields in {array} (YUG: 481)
`substr(string,start,chars)` : extract a substring from {string}, where {start} represents the starting position and {chars} indicates the number of characters to extracted from that point
`tolower(string)` : convert {string} to lowercase
`toupper(string)` : convert {string} to uppercase

### Formatted strings
Formatted strings use the `printf` command, with the syntax `printf "control-string", *args`. The {control-string} is interpolated with expressions called _conversion specifications_, with the syntax `%[-][x[.y]]conv` where {x} represents minimum field width, {y} number of places to the right of a decimal point in a number, and _conv_ can be one of the following values (PGL:534):
  - `d` integer
  - `e` exponential notation
  - `f` floating point number
  - `g` use `f` or `e`, whichever is shorter
  - `o` unsigned octal
  - `s` string
  - `x` unsigned hexadecimal

#### Examples
`%6d` : integer taking up six characters
`%-10s` : left-aligned string taking up 10 characters (a positive number means the string is right-aligned)
`%6.1f` : floating point taking up six characters, including one digit after a decimal point

## Examples
`echo $PATH | awk 'BEGIN {RS=":"} {print}'` : change ":" to newlines in PATH variable; equivalent to `echo $PATH | tr ":" "\n"` 
`awk 'BEGIN {FS=";"} /enable/ {print FILENAME ":" FNR,$1}' *` : print the first field of all files in the current directory, taking semicolon `;` as the field separator, outputting filename, line number, and first field of matches, with colon `:` between the filename and line number
`awk '/MA/ {OFS=" " print FILENAME OFS FNR OFS $0} *` : search for string `MA` in all files, outputting filename, line, and line number for matches
`awk -F: -f awkscr /etc/passwd` : change field separator (`FS`) to a colon (`:`) and run `awkscr`
`awk -f script files` `-f` : flag also works for awk
`awk '{ print $1 }' list` : print the first field of each line in the input file
`awk '/MA/' * | awk '/MA/ {print}' *` : equivalent to `grep MA *` (`{print}` is implied)
`awk -F, '/MA/ { print $1 }' list` : `-F` flag is followed by field separator
`free -h | awk '/^Mem:/ {print $3 "/" $2}` : pipe output of `free` to `awk` to get free memory and total memory
`sensors | awk '/^temp1/ {print $2}` : pipe output of `sensors` to `awk` to get CPU temperature
`awk 'sub(^fake.,"real;")' fake_isbn` : replace initial "fake." with "real;" in file `fake_isbn`

### One-line syntax demonstrations
```
CREDITS,EXPDATE,USER,GROUPS
99,01 jun 2018,sylvain,team:::admin
52,01    dec   2018,sonia,team
52,01    dec   2018,sonia,team
25,01    jan   2019,sonia,team
10,01 jan 2019,sylvain,team:::admin
8,12    jun   2018,öle,team:support



17,05 apr 2019,abhishek,guest
```

`awk '1 { print }' file` : print all lines
`awk 'NR>1' file` : remove file header
`awk 'NR>1 { print } file` : remove file header
`awk 'NR>1 && NR < 4' file` : print lines in a range
`awk 'NF' file` : remove whitespace-only lines
`awk '1' RS='' file` : remove all blank lines
`awk '{ print $1, $3}' FS=, OFS=, file` : extract fields
`awk '{ SUM=SUM+$1 } END { print SUM }' FS=, OFS=, file` : perform column-wise calculations
`awk '/./ { COUNT+=1 } END { print COUNT }' file` : count the number of nonempty lines
`awk 'NF { COUNT+=1 } END { print COUNT }' file` : count the number of nonempty lines
`awk '+$1 { COUNT+=1 } END { print COUNT }' file` : count the number of nonempty lines
`awk '+$1 { CREDITS[$3]+=$1 } END { for (NAME in CREDITS) print NAME, CREDITS[NAME] }' FS=, file` : awk arrays
`awk 'a[$0]++' file` : identify duplicate lines
`awk '!a[$0]++' file` : remove duplicate lines
`awk '$1=$1' file` : remove multiple spaces
`awk '{ print $3 }' FS=, ORS=' ' file; echo`
: join lines

#### Dealing with floating point numbers
`awk '+$1 { SUM+=$1; NUM+=1 } END { printf("AVG=%f",SUM/NUM); }' FS=, file` : format 
`awk '+$1 { SUM+=$1; NUM+=1 } END { printf("AVG=%6.1f",SUM/NUM); }' FS=, file` 
`awk '$3 { print toupper($0); }' file` : convert to uppercase 
`awk '{ $3 = toupper(substr($3,1,1)) substr($3,2) } $3' FS=, OFS=, file` : change part of a string

#### Splitting fields in sub-fields
`awk '+$1 { split($2, DATE, " "); print $1,$3, DATE[2], DATE[3] }' FS=, OFS=, file` : split the second field ("EXPDATE") by spaces, storing the result into the array DATE; then print credits ($1) and username ($3) as well as the month (DATE[2]) and year (DATE[3]) 
`awk '+$1 { split($4, GRP, ":"); print $3, GRP[1], GRP[2] }' FS=, file` 
`awk '+$1 { split($4, GRP, /:+/); print $3, GRP[1], GRP[2] }' FS=, file` 
`awk '+$1 { gsub(/ +/, "-", $2); print }' FS=, file` : search and replace with comma 
`awk 'BEGIN { printf("UPDATED: "); system("date") } /^UPDATED:/ { next } 1' file` : adding date 
`awk '+$1 { CMD | getline $5; close(CMD); print }' CMD="uuid -v4" FS=, OFS=, file` : modify a field externally 
`awk '+$1 { cmd = sprintf(FMT, $2); cmd | getline $2; close(cmd); print }' FMT='date -I -d "%s"'  FS=, file` : invoke dynamically generated command
`awk '+$1 { CMD | getline $5; print }' CMD='od -vAn -w4 -t x /dev/urandom' FS=, file` : join data

### Arithmetic
`awk '{sum += $1} END {print sum}' file` : add up all first records to {sum}, then print that number out at the end

## Output redirection (HPR 2816)
`> "file"` redirect output to {file} (note quotes; filenames are treated as strings); if a file is already open from a previous write, the new data is appended
`>> "file"` {file} is expected to already exist, can be one of the special file names as well ("/dev/stderr", etc)
`| "program"` piping to a command
`close(cmd)` closing a file or command uses the exact same syntax, down to spaces, thus it is preferable to define the command as a string variable
`sprintf` takes a string template and interpolated values as argument, it is useful to dynamically build a string which is then treated within the script as a command
`|&` redirect to a coprocess, that is allows output to be read back with `getline`

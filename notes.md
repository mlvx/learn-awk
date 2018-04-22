# "AWK is a programming language designed for processing plain text data."

From the resource at [write.flossmanuals.net/command-line/awk/](http://write.flossmanuals.net/command-line/awk/)

- Small;
- Easy to learn;
- Ideal for quick, easy text processing;
- Prime use: Extract data from table-like input.

The file   `example.data`   has a small sample of data in tabular format
(Donkey Kong high scores), with which to practice using AWK.



## Example 1

Parse `example.data` and return scores greater than 1x10^6 with first name:

```awk '$1 > 1000000 { print $2, $1 }' example.data```

This returns:
Billy 1050200
Steve 1049100

From experimenting, it seems like the whitespace after `{` and before `}` is
cosmetic.  Also, using the `^` character for exponentiation (using '10^6' 
instead of '1000000') seems to work.

This is the structure of an Awk statement:
`pattern { action }`

The *pattern* defines a condition that must be met for the *action* to occur.
AWK scripts consist of an arbitrary quantity of such statements.  Basically,
an AWK program reads its input (a file or stdin) line by line, and for each
line executes the statements wherein the condition / pattern is matched.



## Example 2

Parse `example.data` and match the 4th column with year 2007; for lines that
match, return rank and 3rd column (surname), and make it look legible:

```awk '$4 == 2007 { print "Rank", NR, "-", $3 }' example.data```

This returns:
Rank 1 - Mitchell
Rank 2 - Wiebe
Rank 5 - Boyer

The strings in the print statement look similar to Python, so that should be
OK.
How does AWK know the ranks?  The table is sorted; therefore the rank is the 
row number, accessed via the AWK built-in variable **NR** <for **N**umber of **R**ow>.
AWK has several useful inbuilt variables.


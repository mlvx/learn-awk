# "Awk is a programming language designed for processing plain text data."

From the resource at http://write.flossmanuals.net/command-line/awk/

- Small;
- Easy to learn;
- Ideal for quick, easy text processing;
- Prime use: Extract data from table-like input.

The file   `example.data`   has a small sample of data in tabular format
(Donkey Kong high scores), with which to practice using Awk.



## Example 1

Parse `example.data` and return scores greater than 1x10^6 with first name:

```awk '$1 > 1000000 { print $2, $1 }' example.data```

This returns:
Billy 1050200
Steve 1049100

From experimenting, it seems like the whitespace after `{` and before `}` is
cosmetic.  Also, using the `^` character for exponentiation (using '10^6' 
instead of '1000000') seems to work.


# commandline10

十種人人都覺得會用 Unix Command Line 的人都知的概念，而你知或者不知。

## I/O Redirection

Output redirection

## Pipe

The concept that make the "do one thing and do it well" works. You can pipe the output from one command to another, example:

```{bash}
man grep | tr '[:upper:]' '[:lower:]' | tr ' ' '\n' | sort | uniq -c | sort -nr | head -50
```

The above chain of commands does the following

1. Get the man page of grep, and then
2. replace all uppercase letters to lowercase, and then
3. replace all spaces into newlines there fore each word is now a line, and then
4. sort the lines (i.e. words) according to alphabetical order, and then
5. count the unique words, and then
6. sort the order with the most frequent words on top, and then
7. return only the top 50

Good Unix commands work as filter (a program to process a stream and generate another stream) and such design makes piping possible.

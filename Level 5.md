# Level 5


My instinct is to find out a way to display the file size next to the file itself.

Looking at the man page for find - there is a printf command to print the files in the directory

with arguments including:

/n that gives newline for easier readibility
%s for file size in bytes
-size for matching file size, with + and - being used for greater than and less than
  -c for bytes
-executable matches files that are executable and directories that are searchable

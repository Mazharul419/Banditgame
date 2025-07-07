# Level 4

For this Level the following brief is provided:

![image](https://github.com/user-attachments/assets/a59419fb-6e5f-481e-bf95-29d0b3021033)

Firstly, I use ls to see what is in the current directory bandit4:
![image](https://github.com/user-attachments/assets/8943b72c-d429-4b78-a744-78aedd39407b)

cd into "inhere" and ls once more
![image](https://github.com/user-attachments/assets/113f68e9-1e71-4c5a-9553-562c8e09f50e)

A number of files pop up - and I have to see what file fits the criteria.

My instinct is to find out a way to display the file size next to the file itself.

Looking at the man page for find - there is a printf command to print the files in the directory

with arguments including:

/n that gives newline for easier readibility
%s for file size in bytes
-size for matching file size, with + and - being used for greater than and less than
  -c for bytes
-executable matches files that are executable and directories that are searchable


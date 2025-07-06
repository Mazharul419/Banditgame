# Level 1

For this level the ls command shows me the following files:

![image](https://github.com/user-attachments/assets/ae675fcb-ded5-49cc-8652-ecde253fbfa9)


Using the cat to attempt to open this file:

![image](https://github.com/user-attachments/assets/923d2d48-0378-4d06-b5e7-bb37d403f180)


The "-" symbol is a special character that indicates standard input - i.e., typing something into the terminal

The cat command is therefore waiting for the user to type an input - same as is the case when just using cat by itself.

### This does not open the file

### A different approach is needed

I tried different options:

1) Using different variations of the ls command to find out what type of file this is - to no avail, there are 3 hidden files however they do not provide insight
2) Treating the file as a folder and attempting to cd into it - no success
3) Using "" and / symbols so the shell interprets the - as a name as opposed to a signal

### A fourth solution then broke the cycle

I searched "- file linux" into google and the first link that popped up was a stack overflow from 8 years ago...

![image](https://github.com/user-attachments/assets/c9630a5a-4f22-43de-aa6c-05d7e9c69493)

The solution was gold:

![image](https://github.com/user-attachments/assets/1ae7eefa-7596-481d-9163-41508d5dbad4)

So I tried this in the terminal:

![image](https://github.com/user-attachments/assets/2495e91e-b14b-45e3-825c-70948410aa18)


## SUCCESS!

Lo and behold - it worked, and the password to the next level revealed itself


There was an alternative solution too proposed using redirection:

![image](https://github.com/user-attachments/assets/ac521847-6f44-4f0e-b45e-cd901a15797c)

Tried this and it worked too!


![image](https://github.com/user-attachments/assets/da09ab4f-7c4c-4012-8c7f-cfed278bddc7)



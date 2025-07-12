# Level 5

The Brief:
![image](https://github.com/user-attachments/assets/22d32655-9df6-4689-a58b-d0466550d723)



Using cd I went into the directory the folders are located:

![image](https://github.com/user-attachments/assets/eb3639aa-cc10-48ca-92cf-036c5bc7b70e)

Located the file will be very tricky since there are many folders - manual searching is unfeasible.

For this level I looked at the man page for the find command:

I then ran the command find command followed by the arguments for each requirement:

Type: I am looking for a file, so I use -type f
Size: The file needs to be 1033b in size, so I use the -size 1033c command, where c is the file size in b
Not Executable: The file is not executable so using the -executable argument, combined with ! as NOT

The final command is:

![image](https://github.com/user-attachments/assets/d26d3c20-10a4-4691-a867-5d6e6fcb9f0f)

I then used the cat command to obtain the password:

![image](https://github.com/user-attachments/assets/526ba08b-e7fa-49a5-9352-3a1b1596795e)

## SUCCESS!!

ssh onto the level 6 with password HWasnPhtq9AVKe0dmk45nxy20cvUa6EG !

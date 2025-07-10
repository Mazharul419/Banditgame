# Level 5

The Brief:
![image](https://github.com/user-attachments/assets/22d32655-9df6-4689-a58b-d0466550d723)



Using cd I went into the directory the folders are located:

![image](https://github.com/user-attachments/assets/eb3639aa-cc10-48ca-92cf-036c5bc7b70e)

Located the file will be very tricky since there are many folders - manual searching is unfeasible.

For this level I looked at the man page for the find command:

The find command can be followed with a -size argument and specifying c, for kb for file size.

I then ran the command find ./* -size 1033c to search the inhere folder for the file containing exactly 1033kb of size:

![image](https://github.com/user-attachments/assets/663fabc3-9689-4373-80bf-8b7e31123fe4)

I then used the cat command to obtain the password:

![image](https://github.com/user-attachments/assets/526ba08b-e7fa-49a5-9352-3a1b1596795e)

## SUCCESS!!

ssh onto the level 6 with password HWasnPhtq9AVKe0dmk45nxy20cvUa6EG !

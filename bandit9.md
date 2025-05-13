Alright, let's quickly tackle Bandit Level 9:

Connect: SSH into bandit9@your_ip_address -p 2220 using the password from Level 8.

The Clue: The level description will likely mention a file that is not in the usual place and might have unusual access control. It might also hint at files that have a specific size.

Searching by Size: A useful tool here is find again, but this time we'll use the -size option to look for files of a specific size. The level description might give you a hint about the size, or you might need to do some educated guessing based on common password lengths (often around 30-40 bytes). Let's try searching for files that are exactly 33 bytes (a common password length):

Bash

find / -size 33c
The -size 33c tells find to look for files that are exactly 33 bytes in size. You might need to adjust 33 based on clues or by trying a few common password lengths. Be patient, as searching the entire filesystem can take a little time.

Examining the Found File: Once find returns a file path, use ls -l to examine its permissions and ownership:

Bash

ls -l [file_path]
Pay attention to who owns the file and what permissions are set. You might find a file that's not readable by bandit9 directly.

Using the -exec Option with find: If you find a file that you can't directly read with cat due to permissions, you can use the -exec option with find to execute a command on the found file as a different user. The level description often hints that the password might be readable by the group owner. Let's say the file is owned by bandit9 but the group is bandit8, and the group has read permissions. You can try to read the file using the bandit8 group's privileges (though you are still logged in as bandit9):

Bash

find / -size [approximate_size] -exec cat {} \;
The {} is a placeholder for the found file, and \; marks the end of the command to execute. However, this won't directly change your user.

More likely, the hint points to a file that another user can read. You'll need to figure out how to access that content. Sometimes, the level description subtly points to a location where other users might place readable files.

Alternative Search Locations: If the size search doesn't immediately yield a readable file, reconsider the level's hints. Sometimes, the file might be in a less obvious location. Think about temporary directories (/tmp), or user home directories (/home). You might need to combine find with other criteria like -user or -group if you have a suspicion about the owner or group.

Reading the Password: Once you locate the file and figure out how to read it (either directly or by understanding the permissions), use cat [file_path] to display its contents. The password for Bandit Level 10 should be there.

Connect to Level 10: Disconnect with exit and SSH into bandit10@your_ip_address -p 2220 using the password you found.

![1431](https://github.com/user-attachments/assets/d9a84759-f6b9-4812-9207-c0a2f2c7cf33)

Connect: SSH into bandit10@your_ip_address -p 2220 using the password from Level 9.
The Clue: The level description usually mentions multiple files in a specific directory that are human-readable and contain the password for the next level.
Finding the Directory: The description will likely give you the name of this directory. It might be something like data.txt, files, or a hidden directory (starting with a .). Use the ls command to look for this directory:
Bash

ls
If it's a hidden directory, you'll need to use ls -a to see it.
Navigating to the Directory: Once you find the directory, use the cd command to enter it:
Bash

cd [directory_name]
Listing Files: Inside this directory, use ls to see the list of files. There will likely be several files.
Identifying Human-Readable Files: The hint specifies human-readable files. This usually means they are plain text files. You can often identify them by their extensions (like .txt) or by trying to read a few of them using head or less.
Reading the Files: You'll need to go through the files in this directory and examine their contents. Since there are multiple files, you don't want to cat them all at once (it could be overwhelming). Use commands like:
head [filename] to see the first few lines of a file.
less [filename] to view the file page by page (press q to exit).
grep "password" or grep "Bandit11" if you have a hint about what the password might look like.
Finding the Password: One of these human-readable files will contain the password for Bandit Level 11. It might be directly in the file or part of a larger block of text.
Connect to Level 11: Once you find the password, disconnect with exit and SSH into bandit11@your_ip_address -p 2220 using the password you found.
![1697 (1)](https://github.com/user-attachments/assets/1a5b8cd2-9584-43dd-86c2-22438e335d96)


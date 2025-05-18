![Bandit14](https://github.com/user-attachments/assets/ff8fbaec-ac13-4efa-9d6e-bda358efe93a)
The Solution:

Navigate to the bandit14 directory:

Bash

cd bandit14
List the files: You'll see a file named -. Standard ls might not handle this well. Try this:

Bash

ls -i
This will show you the inode number of the file.

Use find to locate the file (if ls -i didn't help):

Bash

find . -name "-"
Read the contents of the file: There are a few ways to do this because of the hyphen in the filename:

Using cat with --: This tells cat that everything after -- is a filename, even if it starts with a hyphen.
Bash

cat -- -
Using the inode number with find -inum -exec cat {} \;: Replace [inode_number] with the actual inode number you found earlier.
Bash

find . -inum [inode_number] -exec cat {} \;
Using a relative path:
Bash

cat ./-
The output will contain the password for Bandit Level 15.

In short: The tricky part is dealing with the filename -. Use cat -- - or find with the inode number to read its contents.

Level Goal:
The goal is to use a SetUID binary in the home directory to get the password for the next level. The password is in /etc/bandit_pass/bandit20.

Understanding SetUID:

A SetUID (Set User ID) bit is a special permission that can be set on executable files.
When a program with the SetUID bit is executed, it runs with the permissions of the owner of the file, not the user who executed it.
In this level, you'll find a binary owned by bandit20 with the SetUID bit set. This means when you run it as bandit19, the binary will execute with bandit20's privileges.
Steps to Solve:

Log in to Bandit 19:

Bash

ssh bandit19@bandit.labs.overthewire.org -p 2220
(Use the password from Level 18)

Examine the home directory:
List the files in your home directory:

Bash

ls -l
You should see a binary with permissions like -rwsr-x---. The s in the owner's permission (rws) indicates the SetUID bit is set. It will likely be named bandit20-do or similar. Notice that bandit20 is the owner of this binary.

Execute the binary to understand its usage:
Run the binary without any arguments:

Bash

./bandit20-do
This will usually print a usage message, telling you how to use it. It will likely indicate that you can run a command as another user (in this case, bandit20).

Use the binary to read the password file:
Since the binary runs as bandit20, and bandit20 has read access to /etc/bandit_pass/bandit20, you can use the binary to cat that file.

Bash

./bandit20-do cat /etc/bandit_pass/bandit20
This command will execute cat /etc/bandit_pass/bandit20 with the permissions of bandit20, revealing the password for the next level.

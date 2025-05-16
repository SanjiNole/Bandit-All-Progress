![Bandit13](https://github.com/user-attachments/assets/f98a06e2-22fe-455e-869b-2e3bb4a21b09)
I will SSH into bandit12@bandit.labs.overthewire.org -p 2220 using the level 12 password.
I will use the find command to look for setuid executables owned by bandit13: find / -user bandit13 -perm -4000 2>/dev/null.
I will execute any promising setuid executables I find to try and read /etc/bandit_pass/bandit13.
The output from the successful execution will be the password for Bandit level 13.

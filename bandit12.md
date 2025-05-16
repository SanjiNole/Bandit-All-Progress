![Bandit12](https://github.com/user-attachments/assets/0a677c14-328c-4ace-8582-f5ab3647f5d2)
I will use the password obtained for level 11.

Once I am logged in, the task for level 12 states: "The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions."

This indicates that the content of data.txt is encoded using ROT13. There isn't a direct rot13 command in standard Linux. However, I can use the tr command to perform the character substitution.

To decode the password, I will use the following command:

Bash

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
This command reads the content of data.txt and uses tr to translate uppercase letters 'A' through 'Z' to 'N' through 'Z' followed by 'A' through 'M', and similarly for lowercase letters 'a' through 'z' to 'n' through 'z' followed by 'a' through 'm'. This effectively performs the ROT13 decryption.

The output of this command will be the password for Bandit level 12.

In summary:

I will SSH into bandit11@bandit.labs.overthewire.org -p 2220 using the level 11 password.
I will read and decode the data.txt file using the tr command: cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'.
The output will be the password for Bandit level 12.

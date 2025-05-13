Connect: Use SSH with username bandit6 and the previous password to connect to the server.
Search: Use find / -name "bandit7*" to locate a file related to Bandit 7.
Inspect: Once you find a file, use ls -l [file_path] to see its permissions and owner. Look for a file owned by bandit7 that has read permission for the owner.
Read: Use cat [file_path] to read the contents of that file. The password for Bandit 7 will likely be there.
Connect to Level 7: Disconnect with exit and SSH into bandit7@your_ip_address -p 2220 using the password you found.
Key commands: ssh, find, ls -l, cat, exit. Focus on finding a file owned by bandit7 that you can read. Good luck!

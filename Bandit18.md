![Bandit18](https://github.com/user-attachments/assets/567fb1e0-f397-42f0-b6ce-e8605407bef4)
The Situation: I'm on Bandit Level 18, and the password for the next level is in a file called readme. The problem is, as soon as I try to log in, the server's .bashrc file disconnects me! I can't even get a shell to type cat readme.

My Goal: I need to find a way to read that readme file without letting the server's .bashrc log me out.

1. Understanding the "Logout Trap"
First, I always like to confirm the problem. So, I try to log in to bandit18 like I normally would:

Bash

ssh bandit18@bandit.labs.overthewire.org -p 2220
When it asks for a password, I provide the one I got from Bandit Level 17.

Sure enough, as soon as I enter it, I see:
Byebye!
And then, I'm disconnected. This confirms my suspicion: the .bashrc file on bandit18 is definitely kicking me out.

2. My Go-To SSH Trick: Remote Command Execution
I know that SSH isn't just for opening interactive shells. It also has a really handy feature: remote command execution. This means I can tell SSH to run a specific command on the server before it tries to give me a full interactive session.

The basic idea is to just add the command I want to run at the end of my SSH login line:

Bash

ssh <username>@<hostname> -p <port> <command_to_execute_remotely>
This is perfect for my current situation. Because I'm executing the command directly, it happens so fast that the .bashrc script doesn't have a chance to log me out of a shell that was never fully established anyway! The output of my command just gets sent right back to my terminal.

3. Executing cat readme Remotely
So, now I use this trick to read the readme file. I'll tell SSH to connect to bandit18 and immediately run cat readme:

Bash

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
When it asks for the password, I make sure to use the Bandit Level 17 password.

4. Retrieving the Password for the Next Level
Bingo! After I enter the password, I see a long string of characters printed directly to my screen, followed by the familiar "Byebye!" message. That string of characters is exactly what I'm looking for – it's the password for Bandit Level 19.

5. Moving On to Bandit Level 19
With that password in hand, I can now confidently log in to the next level:

Bash

ssh bandit19@bandit.labs.overthewire.org -p 2220

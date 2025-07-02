# BANDIT LEVEL 26 -> 27


## GOAL:

- Good job getting a shell! Now hurry and grab the password for bandit27!
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit27

## SOLUTION:

After listing all the files we found a suid binary that was running as user bandit27. 

When we ran the file it showed that we can run any command through it and since , it was running as bandit27 we just used the cat command to read the password of bandit27 from the file **/etc/bandit_pass/bandit27**.

![bandit27.1](./images/bandit27.1.png "Bandit27.1")


Here we got the password, this password will be used further when we login to bandit27

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit27@bandit.labs.overthewire.org`

![bandit27.2](./images/bandit27.2.png "Bandit27.2")

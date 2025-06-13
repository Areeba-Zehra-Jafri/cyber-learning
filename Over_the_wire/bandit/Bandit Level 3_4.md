# BANDIT LEVEL 3 -> 4


## GOAL:

- The password for the next level is stored in a hidden file in the inhere directory.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit4

## SOLUTION:

Use the following command to list all the files and directories .

`ls`

Then to go to the directory inhere using the following command:

`cd <directory_name>`

`cd inhere` 

![bandit4.1](./images/bandit4.1.png "Bandit4.1")

Here we can't see the file as it is hidden (There are some files that start with a . and are called hidden as they won't be displayed using a simple ls command), we opened the manual page and found a relevant flag:

![bandit4.2](./images/bandit4.2.png "Bandit4.2")

Here is the updated command that we used.

`ls -a`

`cat ...Hiding-From-You `

![bandit4.3](./images/bandit4.3.png "Bandit4.3")

Here we got the password, this password will be used further when we login to bandit4.

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit4@bandit.labs.overthewire.org`

![bandit4.4](./images/bandit4.4.png "Bandit4.4")

# BANDIT LEVEL 28-> 29


## GOAL:

- There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.
- Clone the repository and find the password for the next level.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit29

## SOLUTION:

First according to the task we cloned the repo  using the folllowing command on our local PC . Following is the final command we used.We are using **bandit.labs.overthewire.org:2220** in place of localhost as we are not logged in as bandit user.

`git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo`

When asked for password just give the password of bandit28.

![bandit29.1](./images/bandit29.1.png "Bandit29.1")

Here we can see that we are logged in.

Then we went into the folder, listed all the files. Here we found a README file. In the readme we saw some credentials but the password was encrypted.

![bandit29.2](./images/bandit29.2.png "Bandit29.2")

We know that git is a version control system and all the changes made in it are recorded and we can even view previously committed changes. Here we have following command:

`git log`

This command will list the history of commits in our git repository.

![bandit29.4](./images/bandit29.4.png "Bandit29.4")

Here we can see three commits were done the first one that is also tha latest shows a comment that info leak is fixed to search more we will try to go back to the previous versions .
Here we have a command:

`git show <commit-hash>`

![bandit29.5](./images/bandit29.5.png "Bandit29.5")


Here we got the password hardcoded in the very first commit on this repo , this password will be used further when we login to bandit28

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit29@bandit.labs.overthewire.org`

![bandit29.6](./images/bandit29.6.png "Bandit29.6")

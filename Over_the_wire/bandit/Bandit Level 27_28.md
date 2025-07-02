# BANDIT LEVEL 27-> 28


## GOAL:

- There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.
- Clone the repository and find the password for the next level.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit28

## SOLUTION:

First according to the task we tried cloning the repo logged in as bandit27 using the folllowing command. But we didn't have the permission.

`git clone <repo-link>`

`git clone ssh://bandit27-git@localhost/home/bandit27-git/repo`

![bandit28.1](./images/bandit28.1.png "Bandit28.1")

So we modified the url , changed the local host part to **bandit.labs.overthewire.org:2220** and cloned the repo on our local PC . Following is the final command we used.

`git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo`

When asked for password just give the password of bandit27.

![bandit28.2](./images/bandit28.2.png "Bandit28.2")

Here we can see that we are logged in.

Then we went into the folder, listed all the files. Here we found a README file and viewing it's content gave us the flag.

![bandit28.3](./images/bandit28.3.png "Bandit28.3")

Here we got the password, this password will be used further when we login to bandit28

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit28@bandit.labs.overthewire.org`

![bandit28.4](./images/bandit28.4.png "Bandit28.4")

# BANDIT LEVEL 31-> 32


## GOAL:

- There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.
- Clone the repository and find the password for the next level.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit32

## SOLUTION:

First according to the task we cloned the repo  using the folllowing command on our local PC . Following is the final command we used.We are using **bandit.labs.overthewire.org:2220** in place of localhost as we are not logged in as bandit user.

`git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo`

When asked for password just give the password of bandit30.

![bandit31.4](./images/bandit31.4.png "Bandit31.4")

After logging in we went into the folder, listed all the files. Here we found a README file. In the readme file we had some instructions that we have to make a file with certain content in it and push it to the remote repo on master branch.

We will use the follwoing command to list the branches and to check if we are in master branch.

`git branch -a`


![bandit32.1](./images/bandit32.1.png "Bandit32.1")

We saw that we are in master branch.

Now we will use the follwoing command to create the file:

`exho "May I come in?" > key.txt`

The above command will echo the content and redirect it to the file . Then we will use the command:

`git add key.txt` 

**git add** Stages changes (new or modified files) so they’re ready to be committed.

**git commit** Saves the staged changes to the repository with a message.It has following syntax.

`git commit -m <message>`

![bandit32.2](./images/bandit32.2.png "Bandit32.2")

After committing we will push these changes to the master branch for that we will use the following syntax:

`git push origin master`

![bandit32.3](./images/bandit32.3.png "Bandit32.3")

Here we got the password ,this password will be used further when we login to bandit32

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit32@bandit.labs.overthewire.org`

![bandit32.4](./images/bandit32.4.png "Bandit32.4")
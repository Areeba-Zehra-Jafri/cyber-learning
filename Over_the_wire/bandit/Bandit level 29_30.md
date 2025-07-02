# BANDIT LEVEL 29-> 30


## GOAL:

- There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.
- Clone the repository and find the password for the next level.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit30

## SOLUTION:

First according to the task we cloned the repo  using the folllowing command on our local PC . Following is the final command we used.We are using **bandit.labs.overthewire.org:2220** in place of localhost as we are not logged in as bandit user.

`git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo`

When asked for password just give the password of bandit29.

![bandit30.4](./images/bandit30.4.png "Bandit30.4")

After logging in we went into the folder, listed all the files. Here we found a README file. In the readme we saw some credentials but the password was not given.

We know that git is a version control system and all the changes made in it are recorded and we can even view previously committed changes. Here we have following command:

`git log`

This command will list the history of commits in our git repository.


Here we can see two commits were done to search more we will try to go back to the previous versions .
Here we have a command:

`git show <commit-hash>`

![bandit30.1](./images/bandit30.1.png "Bandit30.1")

We can see both commits showed no special information.So, now we will dig deeper.

In github there is a thing called **branches**.

**Branches** in GitHub are separate versions of the code used to develop features, fix bugs, or test changes without affecting the main project. They let multiple people work on different things at the same time.

We will use the follwoing command to list the branches in this repo.

`git branch -a`

Now, we will use the following command to select one branch and view what's inside.

`git checkout <branch_name>`

`git checkout dev`

![bandit30.2](./images/bandit30.2.png "Bandit30.2")

Here we found a readme file in it and after viewing it's content we got the password.

![bandit30.3](./images/bandit30.3.png "Bandit30.3")

this password will be used further when we login to bandit30

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit30@bandit.labs.overthewire.org`

![bandit30.5](./images/bandit30.5.png "Bandit30.5")
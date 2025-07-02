# BANDIT LEVEL 30-> 31


## GOAL:

- There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.
- Clone the repository and find the password for the next level.
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit31

## SOLUTION:

First according to the task we cloned the repo  using the folllowing command on our local PC . Following is the final command we used.We are using **bandit.labs.overthewire.org:2220** in place of localhost as we are not logged in as bandit user.

`git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo`

When asked for password just give the password of bandit30.

![bandit31.5](./images/bandit31.5.png "Bandit31.5")

After logging in we went into the folder, listed all the files. Here we found a README file. In the readme we found nothing.

We know that git is a version control system and all the changes made in it are recorded and we can even view previously committed changes. Here we have following command:

`git log`

This command will list the history of commits in our git repository.

Here we can see only one commit so can't do anything with it.

Now we will dig deeper. In github there is a thing called **branches**.

**Branches** in GitHub are separate versions of the code used to develop features, fix bugs, or test changes without affecting the main project. They let multiple people work on different things at the same time.

We will use the follwoing command to list the branches in this repo.

`git branch -a`

But we saw that there was no extra branch

![bandit31.1](./images/bandit31.1.png "Bandit31.1")

No we have a following command that we will use :

`git show-ref`

The git show-ref command lists all references (like branches and tags) in our Git repository, along with their corresponding commit hashes.

We know what branches are but what are tags?

**Tags** in Git are used to mark specific commits, usually for important points like releases (e.g., v1.0, v2.1.3).
They act like labels or bookmarks on a commit, so you can easily refer back to that version later.

![bandit31.2](./images/bandit31.2.png "Bandit31.2")

Here we found a tag named secret now we will use the following command to view it's content.

`git show <tag_name>`

`git show secret`

![bandit31.3](./images/bandit31.3.png "Bandit31.3")

Here we got the password ,this password will be used further when we login to bandit31

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit31@bandit.labs.overthewire.org`

![bandit31.6](./images/bandit31.6.png "Bandit31.6")
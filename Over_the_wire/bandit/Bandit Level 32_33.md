# BANDIT LEVEL 30-> 31


## GOAL:

- After all this git stuff, it’s time for another escape. Good luck!
- host => bandit.labs.overthewire.org
- port => 2220
- username => bandit32

## SOLUTION:

After logging in we found out that whatever we were writing was appearing and running in uppercase. But linux commands are case sensitive and only runs in lowercase. So we need to find a way to break out of this restricted shell.

![bandit33.1](./images/bandit33.1.png "Bandit33.1")

In Linux there is one things that is in uppercase and it's variables.

To read more about them visit the following links.

- [What do $0, $1, $2 mean in a shell script? – Stack Overflow](https://stackoverflow.com/questions/29258603/what-do-0-1-2-mean-in-a-shell-script?utm_source=chatgpt.com)
- [Understanding Positional Parameters – LinuxCommand.org](https://linuxcommand.org/lc3_wss0120.php?utm_source=chatgpt.com)

Here we will use a positional parameter `$0` because it re-invokes the current shell (i.e., the script itself), letting us escape the restricted uppercase-only environment by calling the shell directly.

![bandit33.2](./images/bandit33.2.png "Bandit33.2")

Here we can see we suceeded in getting the shell . After listing all the files we found that this shell was running as user bandit33 and when we ran `whoami` we found out that we were bandit33. 

Since, we are previliged we will directly cat the **/etc/bandit_pass/bandit33** file.

![bandit33.3](./images/bandit33.3.png "Bandit33.3")

Here we got the password ,this password will be used further when we login to bandit33.

To login we have to use SSH . Following is a basic syntax of the command which we will use.

`ssh -p <port_number> <username>@<host>`

`ssh -p 2220 bandit33@bandit.labs.overthewire.org`

![bandit33.4](./images/bandit33.4.png "Bandit33.4")
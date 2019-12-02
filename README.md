# GitHub Tutorial
by Kevin Wang

## Git vs. GitHub
Git | Github
----|----
Is local which doesn't need internet. |Is remote and stores code in cloud.
Doesn't require Github |Requires Git
Has version control- meaning that it help organize and keep track of changes |Allows collaboration


*Extra Info: Cloud is a server thats connected to the internet.*


---
## Initial Setup

##### **Github Account**:
1. To make a Github account, you have to [github.com](https://github.com/).
2. Click Sign up on the top right.
![Github](https://miro.medium.com/max/4320/1*9cs3WV8cx6EMADwzoVmmug.png)
3. Fill in your personal info and then follow the instructions.

##### **IDE** (Integrated Development Environment):

1. To set up your IDE you first have to make a Github account.
2. After doing that, go to [ide.cs50.io](https://ide.cs50.io) and sign in.
3. After that, you can go to [https://github.com/hstatsep/ide50](https://github.com/hstatsep/ide50) and follow the instructions.

##### **SSH vs. HTTPS**:
SSH |HTTPS
----|----
Know as Secure Shell| Known has Hypertext Transfer Protocol Secure
Require one time authentication unless you switch devices| Requires authentication everytime you try to `git clone`, `git pull`, `git push`.

SSH would be easier to use since you don't need to type in your username and password everytime you do the commands listed above.

You can switch to SSH from HTTPS or vice versa before cloning/downloading by click **Use SSH** or **Use HTTPS**  
      ![Cloning/Downloading](https://help.github.com/assets/images/help/repository/https-url-clone.png)


---
## Repository (Repo) Setup
##### **Creating in Github**
1. In [Github](https://github.com/), click the **+** icon next to your profile and click "New Repository"
![make repository](https://github-images.s3.amazonaws.com/enterprise/2.14/assets/images/help/repository/repo-create.png)
2. Fill in the name of your choice in lowercase letters and **-** for spaces.
![reponame](https://help.github.com/assets/images/help/repository/create-repository-name.png)
3. If you already have repository with a README.md file in your local, then you don't need to check the "**Initialize this repository with a README**" option.
4. Then click "**Create repository**"

##### **Creating in Git**
1. In your [IDE](https://ide.cs50.io), go into the folder you want to make a new repo in.
2. Use `mkdir <file-name>` to make a new directory or you can edit another existing repo by forking and then pulling or by cloning.  
    1. Forking and cloning makes a copy of the repository. However, forking also make a new repository while cloning doesn't. This means that you won't be able to `git commit -m ""` and `git push` if you use `git clone`. Forking allows you to make changes to the original by requesting a merge.
3. Do `git init` as it will initialize git and make the directory into a repository.  


*Extra Info: Repository is the same thing as a Directory but it has Git initialized. Merge can only be done in the remote.*

---
## Workflow & Commands
* When working in your IDE, it never hurts to do `git status` every now and then to check if you have the files you want to commit on stage.
* After you edit you codes, you add them to the stage using `git add <file>` (for one specific file) or `git add .` (to add all the files within your repository).
* After that, you can save it by using the command `git commit -m ""` with your message of what you did inside the quotation marks.
* You can push it to the remote (which is github.com) using the command `git push -u origin master`. You can also just use `git push`after the first command since `-u` in the command tells git to remember the repo.




---
## Rolling Back Changes
* If you accidentally initialize git in the wrong directory, you can remove it by using the command: `rm -rf .git`.  
    *Note: You can only remove a file/folder in the parent folder*
* If you don't want a file on the stage after doing `git add .`, you can remove it by using `git reset HEAD <file>`.
* If you want to revert a change after commiting, you can go back to any previous commits by using `git revert <commit id>` (you can find the commit id by using `git log`) or using `git revert HEAD` for the last commit.
* You can undo a commit using `git reset HEAD~` and then `git checkout -- <file name>`.
* 
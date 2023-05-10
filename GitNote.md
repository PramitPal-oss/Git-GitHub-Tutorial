<!-- @format -->

# Terminal command :

1. **cd** : Used for naviagte through the command line

2. **ls** : How many directries are in the current address.

3. **start .** : Open the a folder in that directry

4. **pwd** : Print the current directry

5. **cd ..** : For one level back from current directry.

6. **touch <dirname>** : example : `touch pp.txt index.html index.js style.css` It will create pp.text index.html index.js style.css in that directry that you are currently in.

7. **rm** : To delete the file . Example : `rm index.html` It will delete the index.html file

8. **rm -rf** : Tod delte folder. Example :

   creating a folder : `mkdir learn` It will create a learn folder in the present directry
   Delete the folder : `rm -rf learn` Delete the learn folder.

9. **mkdir** : making a folder in the current directry

# Git Commands :

1. _git init_ : It will initialize the empty git repository. And it will
   create an empty git folder. You can see that using `ls -a`
   It will show the hidden folder `(named .git)` inside that repo or that folder.

**Points To be Noted**
Once you are in git repo which is initialize it will work that initialization on a nested level. Such as : lets make some folder

`mkdir MyfirstNaval` (Inside the folder)=> `mkdir guts` (Inside guts folder) => `mkdir puplets`

If we come to parent directry that is `MyfirstNaval` and write `git int` It will initialize all the folder and files inside the `MyfirstNaval` folder and doesn't matter how nested the folders are. _SO BECAREFULL THAT DON"T REINITIALIZE THAT `git init` COMMAND AGAIN. ONCE YOU INITIALIZE IT WILL STAY ALWAYS WITH ALL HIS HISTORY_. And for Surety You can always check that using `git status`. Which will tell you the repo is initialize or not or how many file tracked in it. Or if you want to delete the initialization just delete the `.git` hidden folder.

2. _git status_ : To know the status of current repo. If it is initialize or not or how mant untracked files/folder there and many
   more...

3. _git add_ : Syntax: `git add <fileName1> <fileName 2>` We can add files using `git add index.html style.css` git add command. If we want to add all
   the files then we can write `git add .` this will add all the untracted files.

4. _git commit_ : Syntax : `git commit -m "you message"` git commit is work as a check point for project. We can create as many check point as we want.
   But becareful that this commit and commit message must me meaning full. Example : `git commit -m "add a nav bar"` or `git commit -m "fixing a bug"`
   _What about this -m??_ basically we use -m just for oneline message. Otherwise we can do `git commit` and this open our default editor.
   _BECAREFUL WHEN INSTALLING GIT THAT YOU HAVE CHOOSE YOUR DEFAULT EDITOR AS VSCODE OR WHATEVER YOU ARE COMFORTABLE WITH, OTHERWISE GIT WILL OPEN HIS DEFAULT EDITOR THAT IS **VIM**_

5. _git commit --amend_ : Syntax : `git commit --amend` This command is
   basically used for revert the changes of your previous commit. Suppose We create
   3 files and we forgot to add one file in that commit. In that case we can do this. And we can edit our commit message as well.

   > `touch index.html index.css index.js` => `git add index.html index.css` => `git commit -m "create a nav menu"`

   Now we forgot to add `index.js` file. So at the first stage `git status` that will so us the untracked file. And then `git add index.js`. So now we can do `git commit --amend`. This will now open our default editor that set in the time of installing git. And we can edit ou commit message and add that file in the same commit. This will not create a new commit.
   _REMEMBER WE CAN USE THAT AMEND COMMAND ONLY FOR JUST PREVIOUS COMMIT_.

6. _git log_ : It will show all the commit done by that brunch.
   _git log --oneline_ : It will show all commits in online
   _git log --pretty=oneline_ : It will show all the log in oneline more prettier way

7. _.gitignore_ : gitignore is a file that helps us to ignore a certain
   files and folder that we want to ignore such as Node modules or .env files. So we need to add gitignore file in the root directry. `touch gitignore`. Then suppose we are working on react project so for that in the gitignore file.

> node_modules/
> config.env

for folder we need to use `/` because it will indicates the folder. And for files just write the file name. Node modules is a folder which nexted witch buch of folders so we use `node_modules/`. and for file we use `config.env`.

Now we need to add gitignore file in the git. so `git add gitignore`.

# How To Do An Git Commit for the first for a Project Where git is not even Initialize:

1. `git init` (_initialize the git_) => `git add <file names>` or `git add .` (_add the files_) => `git commit -m <your commit message>`

# Git Branch :

`git branch` , `git branch <branch name>` , `git switch <branch name>`, `git switch -c <branch name>`(switch and create in one line)

`git checkout <branch name>` , `git checkout -b <branch name>`(switch and create in one line) , `git branch -D <branch name>`(delete branch from any other branch. It will forcefully delete the branch. Doesn't matter it merge the branch or not.), `git branch -d <branch name>` (you can do this if you already merge the branch)

`git branch -M <new branch rename>`(rename a branch from that branch)

# Git DIFF :

Git diff is used for see the difference between the changes.

**Concept**

_What is stagged area??_ staged area means after the adding any chnages, Or all the files or folder that are tracked by git.
If we want to staged something we need use `git add <file name>` or `git add .` . So as we all know this stage is just before the commiting phase and in this phase git will tracked the changes of these files.

_What is unstaged ??_ Unstaged means before the `git add .` . So just before staged or adding the files.

1. _git diff_ : Only shows the changes that are **NOT STAGED FOR NEXT COMMIT**

2. _git diff HEAD_ : It will show both staged and Unstaged changes.

3. _git diff --staged_ : Only show the stage changes.

4. _git diff <branch1> <branch2>_ : Show diffrence between the changes in two branch . It will only show the commited Changes.
   syntax : `git diff master pwt`

5. _git diff <branch1> <branch2> <filename>_ : Syntax : `git diff master pwt queenn.txt` show difference b/w changes that only happen
   in a perticular file of two branches. It will only show the commited Changes.

6. _git diff <commit hash> <commit hash>_ : Syntax : `git diff 2fff4112 dfjd4441` show difference b/w changes that only happen
   in those two commits. It will only show the commited Changes.

# Git Stash :

Git provides an easy way of stashing these uncommitted changes so that we can return to them later, without having to make unnecessary commits. Suppose I am working a branch and myy coworker needs help from me right that moment. But I am in a midlde of work and I can't commit that changes at that moment. SO that time git stash wil temporarely save the chnages and allow me to switch branches.

1. _git stash_ : git stash is super useful command that helps you save changes that you are not yet ready to commit. You can stash
   changes and then come back to them later. Basically it is used to change branch without add and commit and save the changes. Running git stash will take all uncommitted changes (staged and unstaged) and stash them, reverting the changes in your working copy.

2. _git stash pop_ : Use git stash pop to remove the most recently stashed changes in your stash and re-apply them to your working
   copy. When You back to the branches after using git stash, This `git stash pop` Helps to retrive all the uncommited and unstaged chnages that were left off.

3. _git stash apply_ : You can use git stash apply to apply whatever is stashed away, without removing it from the stash. This can be
   useful if you want to apply stashed changes to multiple branches.

**Working With Mulptiple Stash** :

5. _git stash list_ : If we stash multiple changes then we can use git stash list to see all the stashed.

6. _git stash apply <stashNo>_ : Syntax: `git stash apply stash@{1}` : This will apply a perticular stash.

7. _git stash clear_ : clear the full list of stash

8. _git stash drop <stashNo>_ : Syntax: `git stash drop stash@{1}` : this will delete perticular stash.

# Undoing Changes and Time Travelling :

1. _git checkout <commit-hash>_ : Example : `git checkout d8194d6` We can use git checkout commit <commit-hash>
   to view a previous commit. Remember, you can use the `git log --oneline` command to view commit hashes. We just need the first 7 digits of a commit hash. It will create a detached head.Usually, HEAD points to a specific branch reference rather than a particular commit.

   **How It Works**
   \*HEAD is a pointer to the current branch reference.

   \*The branch reference is a pointer to the last commit made on a particular branch.

When we make a new commit, the branch reference is updated to reflect the new commit. The HEAD remains the same, because it's pointing at the branch reference.When we make a new commit, the branch pointer is updated to reflect the new commit. The HEAD remains the same, because it's pointing at the branch reference.

_Get back to previous phase_ : Command : `git switch <branch-name>` : If we switch to the bugfix branch, HEAD is now pointing at the bugfix reference.

2. _git checkout HEAD <file>_ : Example : `git checkout HEAD lyrics.txt` : Suppose you've made some changes to a file but don't want
   to keep them. To revert the file back to whatever it looked like when you last committed, you can use: git checkout HEAD <filename> to discard any changes in that file, reverting back to the HEAD. Remeber If you commit the changes Then It will not work. It will always refer to just previous commit You have made.

3. _git checkout -- <fileName>_ : SAME AS `git checkout HEAD <file>`

4. _git restore <file-name>_ : Example : `git restore lyrics.txt` : Suppose you've made some changes to a file since your last
   commit. You've saved the file(only `ctrl +s` Not commiting or adding) but then realize you definitely do NOT want those changes anymore! Basically It will get back to You in previous commit but becareful It will This command is not "undoable" If you have uncommited changes in the file, they will be lost!.

5. _git restore --source HEAD~1 <fileName>_ : Get back to the commit that refers.

6. _git restore --staged <file-name>_ : If you have accidentally added a file to your staging area with `git add` and you don't wish
   to include it in the next commit, you can use git restore to remove it from staging.

7. _git reset <commit-hash>_ : Suppose you've just made a couple of commits on the master branch, but you actually meant to make
   them on a separate branch instead. To undo those commits, you can use git reset. Make sure that commit You want to get back. Suppose You made 3 commits.

8. _git reset --hard <commit>_ : If you want to undo both the commits AND the actual changes in your files, you can use the `--hard`
   option. for example, `git reset --hard HEAD~1` will delete the last commit and associated changes.

# GitHUB

Github is a hosting platform for git repositories. You can put your own Git repos on Github and access them from anywhere and share them with people around the world. Beyond hosting repos, Github also provides additional collaboration features that are not native to Git (but are super useful). Basically, Github helps people share and collaborate on repos.

`git clone <url>` : Clone a github repo.

`git remote -v` (checking if the remote exits)

`git remote add origin <url>` :(You can give any name other than `origin` But it is a convention so please follow along )

`git push <remote> <branch Name>` => `git push origin <branch Name>` (origin is remote name. In this case when first time running this for `push` github will make a new repo name master and push my code to there. Remember : the master brach is available in our local machine not in github so github has to make this branch before pushing my code. that's why after finish pushing it says
`master -> master` )

`git push origin try:main` (pushing in a diffrent git branch. In this case the point willbe `try -> main`. Basically `try` branch is our local machine and it will create `main` branch in github)

`git push -u <remote> <branch name>` : The -u option allows us to set the upstream of the branch we're pushing You can think of this as a link connecting our local branch to a branch on Github. Running git push -u origin master sets the upstream of the local master branch so that it tracks the master branch on the origin repo. Once we've set the upstream for a branch, we can use the only `git push` shorthand which will push our current branch to the upstream.

_Another way of using git_ :

1. When You start working on a project just make a repo on GitHub.

2. Clone that empty repo. `git clone <url>`

3. after cloning a repo We can see the remote of that branch using `git remote -v`

4. start working the project.

5. `git add .` => `git commit -m "<commit message>"` => `git push` . Because the remote and upstream already set to the branch so `git push` command will works here. or You can use `git push origin <branch name>`.

`git branch -r`(Run git branch -r to view the remote branches our local repository knows about.) Expected O/p : origin/master
`git fetch origin`(fetch all the chnages but doesn't messed up our working directry)  
`git fetch origin <branchName>` (fetch all the chnages in a perticular but doesn't messed up our working directry)
`git checkout <branch Name from git branch -r>`: Example :`git checkout origin/fantasy` (for check chnages on that branch)  
`git switch <branchname>`(switch to that branch)
`git pull origin <branch name>` (fetch and merge all the changes in our working directry and working branch. So becareful about that this will merge changes in current branch. If don't want that just change the branch to anyother using `git switch <branch name>` )

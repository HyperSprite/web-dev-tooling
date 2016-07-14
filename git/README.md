## Git-notes

You can have this on your local machine as easy as ```git clone https://github.com/HyperSprite/git-notes.git```

###Git learning resources
[Codecademy](https://www.codecademy.com/learn/learn-git) - Interactive, nothing to install, basic if you don't get the **Pro** plan (I don't have a Pro plan, can't say how good that is).
[FreeCodeCamp](https://www.freecodecamp.com/challenges/save-your-code-revisions-forever-with-git) - The real deal, you will work with a real github repo and get your name on the contributors list.

###Tools
I love the [bash-git-prompt](https://github.com/magicmonty/bash-git-prompt) tool. It makes git on the command line just that much better.

Windows users maybe [GitHub Desktop](https://desktop.github.com/) is for you. I can't say for sure, I'm on linux.

>Note: Even if you never plan to put something out on Github or share it with anyone else. **Never** put **anything** in a git repo that you don't want public without first adding it to the .gitignore file and testing that it is working properly. See **Ignoring Files** below for more information. 

####Document convention
Items inside of (parenthesis) are placeholders for file names, branch names etc. So (filename_1) could be *README.MD* or *index.html*.

-----
###Basics
Create a directory for your repo
```bash
mkdir cool-new-project
cd cool-new-project
```
You could also type all of that on one line:
```bash
mkdir cool-new-project && cd cool-new-project
```

```git init``` - Initializes a git repo and creates a hidden ```.git``` directory where it will store all of the history.

####Trems
**Working Directory** - Where you make changes to files.
**Staging Area** - Where you list all the changes you have made.
**Repository** - Where git stores the changes as versions.
**HEAD** - The commit you working on.
**Merge conflict** - Git will show you where the conflicts are, resolve them and remove any git added text. Save the file and ```git commit ...```.

**commit === save in git**

```git status``` - Shows the current status of the repo.

```git add (filename)``` - Use this for a specific file name.

```git add (filename_1) (filename_2)``` - Add multiple files.

```git add .``` - Use this to add all of the untracked files.

```git diff``` - Shows the diff for the unstaged files.

```git diff (filename)``` - Shows the diff for specific file.

```git diff (SHA)``` - Shows the diff for that commit.

```git diff --staged``` - Shows the diff for what is staged.

```git diff .``` - Shows the diff for all tracked files.

```git commit -m "(say something about your commit)"``` - Adding a commit with a short description. You can leave off the -m and comment and then git will open your default text editor and expect you to type it in there.

```git log``` - Shows list of commits.

```git show (SHA) - shows old versions of files.```

-----
###Undo

```git show HEAD``` - Shows the last commit changes.

```git checkout HEAD (filename)``` - Restores only the specified file since the last commit.

```git reset HEAD (filename)``` - Unstages a file but does not make changes to the file. "M" is short for modified.

```git rm (filename)``` - Use this to remove a file from the staging area.

```git reset (SHA)``` - Resets to a previous commit based on the first 7 letters of the SHA. Remember the SHA from the ```git log``` command?

-----
###Branching

```git branch``` - Lists branch you are on.

```git branch -a``` - Lists all branches.

```git branch (new_branch)``` - Creates a new branch (no white space allowed).

```git checkout (branch_name)``` - Switches you to a specific branch.

```git checkout -b (branch_name)``` - Creates and switches to the new branch.

```git branch -m (old_name) (new_name)``` - Renames a branch.

```git branch -d (branch_name)``` - Deletes a branch.

```git merge (branch_name)``` - Merges changes from current branch to branch_name. So if you are on ```master```, ```git merge some_other_branch``` will bring those changes into master.

-----
###Remotes
```git remote add origin (url)``` - Set the remote origin. 

```git clone remote (clone_name)``` - Before this will even work, you need to set the ```remote```. ```clone_name``` will mkdir with that name as a sub-directory of wherever directory you are in.

```git remote -v``` - Shows the remote path.

```git fetch``` - Gets any changes from the remote master.

```git fetch --dry-run``` - Shows you what will happen if you run the command.

```git merge origin/master``` - From your master branch, you are merging in the origin/master changes.

```git pull origin master``` - Pulls from the remote.

```git push origin (branch_name)``` - Adds local changes to the remote origin.

```git push remote --delete (branch_name)``` - Deletes a remote branch name 

-----
###Ignoring Files

There are things you really don't want to keep in version control. These are things like API keys, log files, npm modules etc. Git has a great way to exclude them from being added and committed. Create a text file called ```.gitignore``` file (note the ".", dots in the first position of a file name make them hidden on *nix OSs. Here is an example:
```bash
# Credentials and API keys
credentials.js

# Logs
logs
*.log
npm-debug.log*

# Grunt intermediate storage (http://gruntjs.com/creating-plugins#storing-task-files)
.grunt

# Dependency directory
node_modules

# Optional npm cache directory
.npm

# Optional REPL history
.node_repl_history
```
>If a file like credentials.js in the above example is critical but different for every user, you can create an example file called credentials-example.js other users can simply rename and edit with their information.

##Using this repo from Github
How I added this github repo to my local computer and updated the readme file.

```git clone git@github.com:HyperSprite/git-notes.git``` - Clones this repo to your computer.

```cd git-notes``` - cd into the repo directory.

```nano README.md``` - Opens the README file in Nano (small command line editor).

```git add README.md``` - Adds the README.md file to the staging area.

```git commit -m "First commit, Updated README.md"``` - Commit with meaaningful message.

```git push origin master``` - Pushes change back to the master on the remote.


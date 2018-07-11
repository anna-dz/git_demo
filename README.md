# git_demo

A quick reference for git and Github.  

## Why?

A version control system for managing changes to your code or files.  

- Create commits (checkpoints) to go back to previous versions of your programs.  
- Synchronise edits made by different people, and manage conflicts.  
- Share code with team members.

## When not to use it?

- git works best for text files containing code. It's not meaningful for binary files, for example .doc, .ppt
- sensitive information persists in commit history even if it's deleted from the most recent version of the file.

## Workflow

#### Working on your own.   
1. Do some work and save changes to files, as normal.
2. Use `git add` command to place these files in a staging area, so that git can track them.
3. Use `git commit` to create a checkpoint.

#### Collaborating with others.
In addition, you can use `git pull` (download) and `git push` (upload)
to sync your local repository with the version stored on Github, which is a good way of collaborating with others.  


## git commands

### Checking the state of your repository  
`git status`  see what's going on in your repository, e.g. which files have been modified since the last commit.  
`git diff`, `git diff <filename>`, `git diff <first commit hash>..<second commit hash>` show changes made to files.
`git log` see commit history for the repository (`git log <path>` to see history for a specific file). Shows commit hashes. Press space bar to go to next page, or q to quit.  

### Commiting changes  
`git add` stage files for commit: add one (`git add <filename`) or multiple (`git add -A`) files to the staging area.  
`git commit` commit everything in the staging area. This will open a text editor allowing to insert a commit message. After writing your message, follow the keyboard shortcuts to exit the text editor and save the message.  

### Undoing changes
`git checkout -- <filename or directory>` discard changes to file(s) that are yet unstaged.  
`git reset HEAD <filename or directory>` unstage staged files (undo `git add`). Then use `git checkout` to discard uncommitted changes.  
`git checkout <commit hash> <optional: filename or directory>` restore to a previous commit, and preserve the commit history. This can be saved as another commit, and undone.  
`git checkout -b <branch name> <commit hash>` restore the  previous commit as a new branch.  
`git reset --hard <commit hash>` restore to a previous commit, and delete any subsequent commit history - this cannot be undone.  

### Branches
`git branch` list branches  
`git checkout <branch name>` switch to a different branch.  
`git checkout -b <branch name>` create and switch to a new branch.  
`git merge <from> <to>` merge branches.  

### Working with Github
`git clone <repository>` initial download of a repository from Github. Done only once per project.  
`git pull` download new commits from Github, to update your local files with changes made by others.  
`git push` upload your commits to Github.

## Glossary
repository - the codebase for your project.  
HEAD - the most recent commit  
HEAD~1, HEAD~2, HEAD~3 - previous commit, 2nd last, 3rd last commit etc.  


## Structure of a git repository
`.git` hidden directory where git stores it's files.
`.gitignore` a text document containing a list of files (can include wildcard patterns) which should not be tracked.

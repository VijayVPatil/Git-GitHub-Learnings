# Git-GitHub-Learnings
Maintaining history of our project . Sharing code on github and sharing our project around the world.
Git: Git help us to know a what particular point of time and where the code changes are made.
Github: Github is an online platform that help us to host our git repository.
Repository: Folder where all the changes are saved.

# Let’s begin with the understanding Git:

## Download Git
Resource:   https://git-scm.com/downloads

### Write git on CLI and we will get git.  
  
  Now you are good to go  
1)Imagine we want to make a project and we make a folder for that.  

2)Now we make few changes in files, delete files.So where these history is stored.  
  All this history is stored in folder that git provides us called as git repository and it is named (.git).This folder is hidden 
    
3)Now how to get this folder where all the history is saved . Just write the following command(initialize empty git repository in the project folder).:

  ~project git init  
    
  ls -a command will show the .git folder
  Now any change made is this folder git will pick it up and save it.
   
4)Now we will be able to maintain the history of this project.

5) Now if we make a change in project. For ex: created a file names.txt
  Now this changes are not maintained how do we know what changes are made that are not currently saved in the history of the project.
  A command for this is :
  ➜  project git:(master) ✗ git status
  On branch master
  No commits yet
  Untracked files:
    (use "git add <file>..." to include in what will be committed)
        names.txt
  nothing added to commit but untracked files present (use "git add" to track)  
  
Here names.txt file is added but it is not tracked . If we share this project on github at this instance of time we will not be able to see names.txt in that file.
Because it is not tracked.So basically git status is the command that this are all the changes that are not in the history.

6) Now we want to maintain this changes, to be tracked and want it to be in history.
Git add  puts all files in the staging area which doesn’t have history or is untracked.
The git add command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit. However, git add doesn't really affect the repository in any significant way—changes are not actually recorded until you run git commit .
This can be done by the command git add <file name/directory>
This command stage the changes for commit
For ex: git add .
             git add <file_name>

➜ project git:(master) ✗ git add .
➜  project git:(master) ✗ git status
On branch master
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   names.txt 

#### Imagine If we want to unstage the changes 
 Now if we want to unstage the changes we can do following command:
  project git:(master) ✗ git restore --staged names.txt 
➜  project git:(master) ✗ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." t o update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   names.txt


7)Now if we want to add this changes in git repository .
The git commit command captures a snapshot of the project's currently staged changes by staged by the command git add. Committed snapshots can be thought of as “safe” versions of a project—Git will never change them unless you explicitly ask it to.
➜  project git:(master) ✗ git commit -m "Names.txt file added"
[master (root-commit) 13fdcee] Names.txt file added
 1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 names.txt

8) Lets see you want to delete the commits . Every commit has a hash value . Run the command:
-> git log
This will shoq the history of commits and lets say you want to delete a commit copy the hash value of commit below it.  Now to delete the commit write .
	Git reset <hash_value>
So what happened to the files that where changed /modified in the previous commits.They are now in the unstaged area.

Extras:   Now we  want a clean code we deleted a few commits and now they are in the unstaged area . We don’t want to save this progress with making a separate commit. We want to put all the work separately without making a history or commit and bring back these changes later.
First we need to put those file on staging area.
	 Git add <file_name>
Send this file back stage and bring back when they are ready to commit
	Git stash
To bring those file back to unstage area.
	Git stash pop
To clear the changes in stash.

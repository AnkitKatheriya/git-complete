# git-complete

##What is Git?
1) Distributed source control system
2) Massively scales
3) Open Source
4) Developed for Linuz project requiremients
5) Most operations are local
6) Very fast
7) Active community
8) Most popular DVCS, VCS

##Key Concepts:
1) Repository contains files, history, config managed by Git. 
2) Three States of Git
	i) Working directory
	ii) Staging area - pre-commit holding area.
	iii) Commit - Git repository (history)
3)	Remote repository (GitHub)
4)	Master branch

##Git Installation:
1) Windows
	Git for Windows(git-scm.com)
	Google Chrome (install in Bonus section, very optional)
2) Mac OS X
	Yosemite or later, easy path: "git version"
	See Bonus section for:
		Xcode Command Line Tools (Mavericks and below)
		Git for Mac (git-scm.com)
		Google Chrome install (very optional)
3) Install Git for windows
	https://github.com/git-for-windows/git/releases
	

##Quick Start Part1 : Starting with Github and Project Setup
1) Create an account using https://github.com
2) Create a project
3) Create a repository

##Quick Start Part2 : Configuration, Clone, and Git Basic Workflow
check version using command -> git version
$ git config --global user.name "Ankit Katheriya"
$ git config --global user.password "Archive@18"
$ git config --global user.email "ankitkatheriya@gmail.com"
$ git config --global --list

git clone '<git project url'
git status - TO see if there is any change between the working directory and remote directory.
git add <name of the files>
git commit -m 'Adding the new file'
git push origin master(branch name to push)

##Text editor Installation overview:
1) Windows
	Notepad++
	Bash alias
	Git configuration
2) Mac OS X
	TextMate 2
	GIt configuration
3) Resources
	Commands
	Git Config Files

##Windows Text Editor: Notepad++ Installation:
1) Download and install notepad++ from its official website.
2) Update the path environment variables for notepad++ utility.
3) open cmd and type notepad++ to check if it is working

##Configure Notepad++ with Git(Windows only):
1) using cmd type -> notepad++ .bash_profile
2) add below text in .bash_profile file
	alias npp='notepad++.exe -multiInst -nosession'
3) save these changes and exit the git-bash and notepad++ utility
4) open cmd and press -> npp (Notepad++ would be open)
5) To check the coniguration type -> cat ~/.gitconfig
6) $ git config --global core.editor "notepad++.exe -multiInst -nosession"
7) $ git config --global -e

##Git Basic Overview:
1) Starting a Project
	Fresh (no source yet)
	Existing source locally
	GitHub project (Fork and clone)
2) Basic Workflow (add, commit, push & pull)
3) Working with Files(rename, move & delete)
4) History and Aliases
5) Ignoring Unwanted Files

##Starting with a Fresh Project (git init)
1) Copy dummy text from http://hipsum.co website
2) create a directory <projects>
3) git init fresh-project
4) ls
5) ls -al (includes hidden files as well)
6) create new file using -> mate hipster.txt
7) git status
8) git add hipster.txt
9) git status
10) git commit (notepad++ would be open, now enter the comment)
11) rm -rf <folder_name> to remove the folder

##Adding Git to an Existing Project (git init)
1) http://initializr.com
2) Navigate to the project folder
3) unzip ~/Downloads/initializr-verekia-4.0.zip
4) mv initializr web-project
5) cd web-project
6) git init
7) git add .
8) git commit -m "My first commit inline"
9) git status
10) if we want to do that the project should not be managed by the git anymore, perform the below command.
	rm -rf .git

##Starting on GitHub by joining an Existing Project(git clone)
1) Login on Github using ur account credentials
2) Navigate to any of the URL :- 
	http://bitly.com/git-start-web
	https://github.com/scm-ninja/starter-web
3) Click on "Fork" Button aapearing at the top right corner of the account screen.
4) Copy the Git URL of this forked project and then run below mentioned command.
   git clone "<Git project URL>"
   
##Basic Git Workflow (add, commit, pull and push)
1) Useful websites
	http://bitly.com/git-start-web
	https://meettheipsums.com/
	https://hipsum.co/
2) Navigate to the project folder path using cmd
3) notepad++ hipster.txt
4) git status
5) git add hipster.txt
6) git commit -m "My first commit"
7) git pull origin master
8) git push origin master

##Tracked files:
1) notepad++ ~/.gitconfig
2) naviaget to the git-complete project directory using cmd on local
3) Now update the existing hipster.txt file using below command
	notepad++ hipster.txt
4) git status
5) git commit -am "Adding mote hipsum text"
6) Add a new file using ( notepad++ newfile.txt)
7) git status 
8) git ls-files (newfile.txt would not be visible there)
9) git add newfile.txt
10) git ls-files (Now newfile.txt would be visible here)

##Editing files:

##Recursive Add:
1) Navigate to the current git project using cmd
2) mkdir -p level1/level2/level3
3) cd level1
4) notepad++ level1file.txt
5) cd level2
6) notepad++ level1file.txt
7) cd level3
8) notepad++ level1file.txt
9) cd ../../..
10) git status (it will only show the level1 directory, but not the recursive files)
11) git add . (will add all recursive files, but if we want to add recursive files related to only a folder than use below command)
	git add <foldername>/\*
12) git status
13) git commit -m "Adding several files recursivly"

##Backing Out Changes:
1) Navigate to the level1file.txt and do some changes into it
2) git add level1file.txt
3) git status
4) Now suppose we are not happy with the changes did in the second step.
5) So will perform a head reset command to unstage the changes
6) git reset HEAD level1file.txt
7) git checkout -- level1file.txt (To remove working directory changes)
	(Working directory changes will also removed)

##Renaming and moving files:
1) Navigate to the file which you want to rename
2) git mv <currentFileName> <newFileName>
3) git status
4) Changes would be staged again
5) git commit -m "Renaming the level3file.txt file"
6) cd ..
7) mv level2file.txt level2.txt
8) git will take it as you performed two operation here
9) git add -A
10) git commit -m "Renamed the level2 file".
11) git mv <oldFileName> <newFileName> (git mv level2.txt 2.txt)
12) git mv <newFileName> <OldFileName> (git mv 2.txt level2.txt)

	Move the file to another directory
1) git mv <filenameToMove> <FolderNameInWhichMoving> (git mv level2.txt level3)
2) Now command to move file without using git command (or using bash command)
3) mv level2.txt ..
4) git status
5) git add -A
6) git commit -m "Moving back level2 file to level2 directory"
7) now update the file name using window, by directly reaching to that file and updating the name to (from level1file.txt to level1.txt)
8) git add level1.txt (updated file name)
9) git add -u (Now it will correctly say renamed the level1file.txt to level1.txt)

##Deleting files:
1) create the file -> notepad++ doomed.txt
2) remove the file using OS command -> rm doomed.txt
3) git rm newfile.txt
4) git status
5) Git will show the file nefile.txt has been deleted
6) git commit -m "Deleting the new file"
7) git status
	How to backout staged deletion:
1) git rm hipster.txt
2) git reset HEAD hipster.txt
3) git status
5) ls (hipster.txt file will not available at local directory)
4) git checkout -- hipster.txt
5) ls (Now file would be available)

##History:
1) git help log
2) git log
	Tips: press q to exit from the log screen
3) git log --oneline --graph --decorate
4) git log 0269de0...59d6266
5) git log --since="3 days ago"
6) git log -- hipster.txt
7) git log --follow -- level1/level2/level2.txt (To check the rename history of the file)
8) git show <commitId> (like git show 33af11b2185d8ff833492f99d0b8141c76a69406)
9) git log --all --graph --decorate --oneline

##Git Alias:
1) It is used to search the short the search command
2) like -> git config --global alias.hist "log --all --oneline --graph --decorate"
3) We have setup search command with hist keyword
4) now perform -> git hist
5) If we want to update these commands later -> then first open .gitconfig file and upadte it accordingly
6) notepad++ ~/.gitconfig

##Ignoring unwanted Files and Folders:
1) ls -al (Command to show all hidden files)
2) Git Ignore Patter Examples:
	Specific file: MyFile.txt
	File Pattern: *.ext
	Folder: my-folder/
3) check if .gitignore file already exists using ls -al command, and if not created then create it using below command 
4) notepad++ .gitignore
	add few lines 
	*.log
	log/
5) Add a new file with extension .log (like access.log)
6) Now perform -> git status (Due to gitignore file it will not show .log file in git status command)
7) mkdir log
8) mv access.log log
9) cd log
10) ll
11) cp access.log access.2014-11-04
12) git status ( will not show any log folder inside git status command)
13) git commit -am "Excluding log file directory"

##Cleanup and Back to Origin (GitHub)
1) git pull origin master
2) git push origin master

##Visual Merge/Diff tool Installation overview
1) Windows:
		P4Merge for Windows
		Git configuraton
	MAC OS X
		P4Merge for Mac OS X
		Git configuration
	Resources
		Commands
		Git COnfig Files
2) Download and installP4Merger from below link
	https://www.perforce.com/downloads/visual-merge-tool

3)	P4merge configure on windows 
Update path variable to open p4merge using cmd (C:\Program Files\Perforce)

4) P4Merge for WIndows Git Configuration:
open git bash and perform below command
git config --global merge.tool p4merge
git config --global mergetool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"
git config --global mergetool.prompt false
git config --global diff.tool p4merge
git config --global difftool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"
git config --global difftool.prompt false
git config --global --list
git config --global -e


Git Repository Setup (for comparing examples)

##Comparing Working Directory and the Staging Area
git diff
git difftool - (to see visual changes)

##Comparing Working directory and git Repository
git diff HEAD
git difftool HEAD

##Comparing between the Staging Area and teh Git Repository (Last commit)
git diff --staged HEAD
git difftool --staged HEAD

##Limiting Comparsons to one File (or path)
git diff -- README.md
git difftool -- README.md

##Comparing between commits
git log --oneline (to know the commit id)
git diff 839e896 HEAD
git diff HEAD HEAD^
git difftool 839e896 HEAD
git difftool HEAD HEAD^ 

##Comparing between Local and Remote Master Branches
<<<<<<< HEAD
git checkout -b <newbranchname> (Here name is title-change)
(update or add any file and commit it to the new branch, in this example new branch is title-change)
git diff master title-change 
git difftool master title-change
=======
git diff master origin/master
git difftool master origin/master

##Comparison Section Cleanup and Push back to GitHub

#Branching and Merging
##Branching Basics
git branch -a
git branch <newBranchName>
git checkout mynewbranch (to move to a new branch)
git log --oneline --decorate
git checkout master
git branch -m mynewbranch newbranch (To move a branch to another branch)
git branch -d newbranch (to delete a branch)

##Happy path / Fast Forward Merges
1) git checkout -b title-change
2) change any file or add new file and push it to new branch
3) git checkout master
4) git diff master title-change (new branch name is title-change)
   git difftool master title-change
5) git merge title-change
6) git branch -d title-change
		or
	git branch -D title-change

##Happy path / Disable Fast Forward Merges
git merge <branch-name> --no-ff

##Automatic merges
git checkout -b simple-changes
git merge simple-changes -m "Merging changes from simple-changes branch"

Conflicting Merges and Resolution
git checkout -b realwork
do some changes in this branch and push the data to this branch
git diff master realwork
git merge realwork
source control tool
git mergetool
git commit -m "Done resolving merge conflicts"
notepad++ <filename>.orig ( Git always saves an original copy to revert the changes)


inside .gitignore file add an entry ( *.orig )
git commit -m "Updating gitignore file to exclude merge tmp changes"


Section cleanup and push back to GitHub
git push origin master

##Rebasing - (Rebase is a kind of merge + squash)
===============
Simple Rebase example			(git commit -am "commit message is known as express commit")
switch to the branch you want to rebase
git checkout -b rebsebranch
git rebase <source branch name> ( git rebase master )

Setup for rebasing conflicts

Abort a rebase:
git rebase --abort

Rebase Conflict and Resolution
resolve the conflict using merge tool
git mergetool
git rebase --continue

Pull with Rebase (GitHub)
git fetch origin master
git pull --rebase origin master

Section cleanup and push to GitHub
Tip:- git rebase -i origin/master

##Stashing - (To save the current changes - work with the HEAD version)
===============
Simple stash example
git stash
git stash apply ( to apply the stash change on our working directory)
git stash list ( to see list of all stash)
git stash drop

Stashing Untracked Files and Using Pop
git ls-files
do the change into a file and add a new file
Run the git stash command (git stash command will only stash the updated file, but exclude the newly added file or untracked file)
git stash -u ( to include any untracked file as well)
git stash pop ( to drop last stash in a stash list)

Managing Multiple Stashs
git stash save "type stash message here"
do multiple changes and perform this command each time
git stash list
git stash show stash@{1} (To show list of all files in the specific list)
git stash apply stash@{1} (It will implement the second stash in stash list)
git stash drop stash@{1}
git stash clear ( To remove all stash in the stash list)

Stashing into a branch
git stash -u
git stash branch <branchname> (new branch would be created -> switched to that branch -> stash would be apply on this branch -> and at the end same stash would be dropped)

Section cleanup and push to GitHub
git pull origin master
git push origin master


##Tagging: (Tagging is nothing more than labeling)
===============
Simple tag Example/Lightweight Tags
git tag <myTag>
git tag --list
git show <myTag>
git tag --delete <myTag>

Annotated Tags
git tag -a v-1.0 
git show v-1.0

Comparing Tags:
git commit --amend
git tag v-1.2 -m "Release 1.2"
git diff v-1.2 v1.1
git difftool v-1.2 v1.1

Tagging a specific commit:
using git log --oneline --graph --decorate --all (find the commit id, which ever you want to tag)
git tag -a v-0.9-beta <commit_id>

Updating Tags:
1) One approach is to delete the current tag and create a new tag
2) git tag -a v-0.8-alpha -f <correct_commit_id>

Using tags with GitHub
git push origin v-0.9-beta
GitHub releases are tracked by tags

git tag --list
git push origin :v-0.8-alpha ( command to delete the tag name which is accidently commit on GitHub)


##Reset and Reflog:
git reset HEAD^1
git reset HEAD^^
git reflog ( Its a log of what we ever did on git repository)
git reset <commit_id>
git reset HEAD@{2}

##Comparing Branches via GitHub 

##Comparing Branches via command Line
git fetch origin test-branch
git diff master <otherBranchName>


##Stash vs Branch


##Git Help
git help
git help stash

##Cherry Pick
git cherry pick <commit_id>


	


# git-complete

What is Git?
1) Distributed source control system
2) Massively scales
3) Open Source
4) Developed for Linuz project requiremients
5) Most operations are local
6) Very fast
7) Active community
8) Most popular DVCS, VCS

Key Concepts:
1) Repository contains files, history, config managed by Git. 
2) Three States of Git
	i) Working directory
	ii) Staging area - pre-commit holding area.
	iii) Commit - Git repository (history)
3)	Remote repository (GitHub)
4)	Master branch

Git Installation:
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
	

Quick Start Part1 : Starting with Github and Project Setup
1) Create an account using https://github.com
2) Create a project
3) Create a repository

Quick Start Part2 : Configuration, Clone, and Git Basic Workflow
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

Text editor Installation overview:
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

Windows Text Editor: Notepad++ Installation:
1) Download and install notepad++ from its official website.
2) Update the path environment variables for notepad++ utility.
3) open cmd and type notepad++ to check if it is working

Configure Notepad++ with Git(Windows only):
1) using cmd type -> notepad++ .bash_profile
2) add below text in .bash_profile file
	alias npp='notepad++.exe -multiInst -nosession'
3) save these changes and exit the git-bash and notepad++ utility
4) open cmd and press -> npp (Notepad++ would be open)
5) To check the coniguration type -> cat ~/.gitconfig
6) $ git config --global core.editor "notepad++.exe -multiInst -nosession"
7) $ git config --global -e

Git Basic Overview:
1) Starting a Project
	Fresh (no source yet)
	Existing source locally
	GitHub project (Fork and clone)
2) Basic Workflow (add, commit, push & pull)
3) Working with Files(rename, move & delete)
4) History and Aliases
5) Ignoring Unwanted Files

Starting with a Fresh Project (git init)
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

Adding Git to an Existing Project (git init)
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

Starting on GitHub by joining an Existing Project(git clone)
1) Login on Github using ur account credentials
2) Navigate to any of the URL :- 
	http://bitly.com/git-start-web
	https://github.com/scm-ninja/starter-web
3) Click on "Fork" Button aapearing at the top right corner of the account screen.
4) Copy the Git URL of this forked project and then run below mentioned command.
   git clone "<Git project URL>"
   
Basic Git Workflow (add, commit, pull and push)
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

Tracked files:
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

Editing files:

Recursive Add:
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

Backing Out Changes:
1) Navigate to the level1file.txt and do some changes into it
2) git add level1file.txt
3) git status
4) Now suppose we are not happy with the changes did in the second step.
5) So will perform a head reset command to unstage the changes
6) git reset HEAD level1file.txt
7) git checkout -- level1file.txt (To remove working directory changes)
	(Working directory changes will also removed)

Renaming and moving files:
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



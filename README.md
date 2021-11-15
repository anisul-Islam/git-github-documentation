# Git & GitHub Documentation

### Lesson 1. Introduction to git and GitHub

1. git?
   - git is a version control software
   - It keep track of code changes
   - It helps to collaborate in a project
   - It is installed and maintained locally
   - It provides Command Line Interface (CLI)
   - Released in April 7, 2005
   - Developed by Linus Torvalds & Junio C Hamano
2. github?
   - GitHub is a hosting service where we can keep our git repositiory/folders
   - It is maintained on cloud/web
   - It provides Graphical User Interface (GUI)
   - Founded in 2008

<img src="./images/git and github.png" width="90%">
     
<br/>

### Lesson 2. Environment setup

- Download and install git on your pc: https://git-scm.com/
- check git version: open terminal or cmd then use the command `git --version` to find out whether git is installed or not. if git is installed it will return a version number of git.

<br/>

### Lesson 3. git configuration

1.  check all configuartion options: `git config`
2.  set global user name and user email for all repository/git folders (if you want to set different username and email for different git repository then remove --global)
    - set global user name: `git config --global user.name "anisul-islam"`
    - set global user email: `git config --global user.email "anisul2010s@yahoo.co.uk"`
3.  list all git configuration:
    - list all the configuration: `git config --list`
    - list user name: `git config user.name`
    - list user email: `git config user.email`
4.  change global username & email
    - change global user name: `git config --global user.name "PUT_NEW_USER_NAME_HERE"`
    - change global user email: `git config --global user.email "PUT_NEW_USER_EMAIL_HERE"`

<br/>

### Lesson 4. creating git repo and adding new files

1.  creating a git folder

- ls -a : list all files inside of a directory

  ```
  mkdir DIRECTORY_NAME_HERE
  cd DIRECTORY_NAME_HERE
  git init

  Example:
  mkdir notes
  cd notes
  git init
  ls -a
  ```

2.  adding new files in git folder

- git status : displays the state of the working directory and staging area

  ```
  ls -a
  touch fileName.extension
  open fileName.extension
  git status

  Example:
  touch day1.txt
  open day1.txt
  write something inside the file
  ```

- Git is aware of the file but not added to our git repo
- Files in git repo can have 2 states – tracked (git knows and added to git repo), untracked (file in the working directory, but not added to the local repository)
- To make the file trackable stagging or adding is required

# Git & GitHub Documentation

## Table of Contents

1. [Beginner Part](#beginner-part)

    [1.1 Introduction to git and GitHub](#11-introduction-to-git-and-github)
      - [Why do we need Git?](#why-do-we-need-git)
      - [What is git?](#what-is-git)
      - [What is github?](#what-is-github)

    [1.2 Git environment setup and configuration](#12-git-environment-setup-and-configuration)
      - [Create a GitHub Account](#why-do-we-need-git)
      - [Download and install git](#download-git)
      - [git configuration](#git-configuration)
      - [What is SSH? How to setup SSH?](#what-is-ssh-how-to-setup-ssh)
  
    [1.3 Basic Git Concepts](#13-basic-git-concepts)

      - [Git repo and adding files](#git-repo-and-adding-files)
      - [Git staging area](#git-staging-area)
      - [Git commit & uncommit](#git-commit--uncommit)
      - [Basic Commands & workflow](#basic-commands--workflow)
      - [Git ignore](#git-ignore)

    [1.4 GitHub Basics & Collaborating with Git](#14-github-basics--collaborating-with-git)

      - [Create github repository and commits](#create-github-repository-and-commits)
      - [Connecting local repo to remote repo](#connecting-local-repo-to-remote-repo)
      - [Push and Pull](#push-and-pull)
      - [README.md](#readmemd)
      - [GitHub Issues: not completed](#github-issues-not-done)

2. [Intermediate Part](#intermediate-part)

    [2.1 Branching and merging](#21-branching-and-merging)
      - [What is Branching & Merging](#what-is-branching--merging)
      - [Basic commands for branching & merging](#basic-commands-for-branching--merging)
      - [Types of Merges: 2-way and 3-way merges](#types-of-merges-2-way-and-3-way-merges)
      - [Resolve Merge Conflicts](#resolve-merge-conflicts)
3. [Advanced Part](#advanced-part)
4. [Learning Resources](#learning-resource)

### Beginner Part

#### [1.1 Introduction to git and GitHub](https://youtu.be/ulTs4vqOzyo)

##### Why do we need Git?

- Change Control (add/restore)
- Version Control (Commits)
- Collaboration (parallel development)

##### What is git?

- git is a version control software
- It keep track of code changes
- It helps to collaborate in a project
- It is installed and maintained locally
- It provides Command Line Interface (CLI)
- Released in April 7, 2005
- Developed by Linus Torvalds & Junio C Hamano

##### What is github?

- GitHub is a hosting service where we can keep our git repositiory/folders
- It is maintained on cloud/web
- It provides Graphical User Interface (GUI)
- Founded in 2008

![github](./images/git%20and%20github.png)

#### [1.2 Git environment setup and configuration](<https://youtu.be/vj5-nkhTRbo>)

##### Create a GitHub Account

- go to this [site](https://github.com/) and register with a valid email address.

##### Download git

- Download and install git on your pc: <https://git-scm.com/>
- check git version: open terminal or cmd then use the command `git --version` to find out whether git is installed or not. if git is installed it will return a version number of git.

##### git help

- git commandName --help

##### git configuration

- check all configuartion options: `git config`
- set global user name and user email for all repository/git folders (if you want to set different username and email for different git repository then remove --global)
  - set global user name: `git config --global user.name "anisul-islam"`
  - set global user email: `git config --global user.email "anisul2010s@yahoo.co.uk"`
- list all git configuration:
  - list all the configuration: `git config --list`
  - list user name: `git config user.name`
  - list user email: `git config user.email`
- change global username & email
  - change global user name: `git config --global user.name "PUT_NEW_USER_NAME_HERE"`
  - change global user email: `git config --global user.email "PUT_NEW_USER_EMAIL_HERE"`

##### What is SSH? How to setup SSH?

- SSH, or Secure Shell, is a cryptographic network protocol used for secure communication between devices over an unsecured network. It provides a secure way to access remote systems, execute commands, transfer files, and manage network infrastructure.
- SSH allows users to securely log into remote systems and execute commands as if they were sitting in front of the machine.

- go to your github account
- [setup ssh](https://youtu.be/ykLd4YQMzCo?si=hS4bShi16XfD4n5y) :
  - type in terminal `for generating SSH Key: ssh-keygen -t ed25519 -C "your email goes here"`
  - type in terminal `cat ~/.ssh/id_ed255519.pub`
  - copy the ssh and add to github

The command `ssh-keygen -t ed25519 -C "your email goes here"` is used to generate a new SSH key pair (a public and private key) for secure authentication. Here’s a detailed breakdown of the command:

###### Breakdown of the Command

1. **`ssh-keygen`**:
   - This is the command-line tool used to generate, manage, and convert authentication keys for SSH.

2. **`-t ed25519`**:
   - The `-t` option specifies the type of key to create.
   - `ed25519` refers to the Ed25519 algorithm, which is a modern and secure elliptic-curve algorithm for SSH keys. It is known for its high security, performance, and small key size compared to older algorithms like RSA.

3. **`-C "your email goes here"`**:
   - The `-C` option adds a comment to the key. This comment is typically used to identify the key.
   - `"your email goes here"` is the comment that will be added to the key. It's common to use your email address here, so you can easily identify the key later.

###### What Happens When You Run the Command

1. **Prompt for a File Location**:
   - After running the command, you will be prompted to specify a file to save the key. By default, it will suggest a location such as `~/.ssh/id_ed25519`.
   - If you press Enter without specifying a location, it will use the default path.

2. **Prompt for a Passphrase**:
   - You will be asked to enter a passphrase. This is an optional step, but adding a passphrase provides an additional layer of security. If you choose to set a passphrase, you’ll need to enter it whenever you use the private key.
   - If you do not want to set a passphrase, you can press Enter without typing anything.

3. **Key Generation**:
   - The tool generates a new Ed25519 key pair and saves it to the specified file. The private key is stored in the file you specified (e.g., `~/.ssh/id_ed25519`), and the public key is stored in a file with the same name but with a `.pub` extension (e.g., `~/.ssh/id_ed25519.pub`).

###### Example Output

When you run the command, the interaction might look like this:

```sh
$ ssh-keygen -t ed25519 -C "your_email@example.com"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/yourusername/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/yourusername/.ssh/id_ed25519.
Your public key has been saved in /home/yourusername/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:examplefingerprint your_email@example.com
The key's randomart image is:
+--[ED25519 256]--+
|       ..o.      |
|      .+ +       |
|     . o* .      |
|      o.O        |
|      .=S o      |
|    . + . = .    |
|     + o + . o   |
|      + o + .    |
|       o o..     |
+----[SHA256]-----+
```

###### Using the Generated SSH Key

1. **Add the Public Key to the Remote Server**:
   - Copy the contents of the public key file (e.g., `~/.ssh/id_ed25519.pub`) to the `~/.ssh/authorized_keys` file on the remote server you want to access.
   - You can use the `ssh-copy-id` command for this:

     ```sh
     ssh-copy-id -i ~/.ssh/id_ed25519.pub user@remote_host
     ```

2. **Connect Using SSH**:
   - Use the SSH command to connect to the remote server. SSH will use your private key for authentication.

     ```sh
     ssh user@remote_host
     ```

#### [1.3 Basic Git Concepts](https://youtu.be/IDhgZX4esQQ)

- Repositories
- Staging Area
- Working Directory
- Local Repositories
- Remote Repositories
- Commits
- Branches
- Merging

##### [Git repo and adding files](https://youtu.be/oa6viOCTEeM)

- creating a git folder

  - ls -a : list all files inside of a directory

    ```t
    mkdir DIRECTORY_NAME_HERE
    cd DIRECTORY_NAME_HERE
    git init

    Example:
    mkdir notes
    cd notes
    git init
    ls -a
    ```

- adding new files in git folder

  - git status : displays the state of the working directory and staging area

    ```t
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

##### [Git staging area](https://youtu.be/IDhgZX4esQQ)

- Adding files to stagging area:

  - `git add fileName` add a file in staging area / index
  - `git add .` add all files of directory to stagging area not subdirectory
  - `git add -A` add all files of directory and subdirectory to stagging area
  - `git rm --cached fileName` unstage a file from staging area
  - `git diff` - checking the differences of a staged file
  - `git restore fileName` - restore the file

##### [practice-1](https://youtu.be/jSj-GF-utls)

##### [Git commit & uncommit](https://youtu.be/gmBKbxKGcn8)

- `git commit -m "message"` move the file to local repository from stagging area
- `git log` check the commit history
- `git reset --soft HEAD^` uncommit the commit in HEAD and move to staging area
- `git reset HEAD^` uncommit the commit in HEAD and move to unstaging / working area
- `git reset --hard HEAD^` uncommit the commit in HEAD and delete the commit completely with all the changes

##### [Basic Commands & workflow]

- git init: Initialize a new Git repository.
- git clone: Clone an existing repository.
- git status: Check the status of your repository.
- git add: Add files to the staging area.
- git commit: Commit changes to the repository.
- git log: View commit history.

![git-workflow](./images/git-level.png)

##### [Git ignore](https://youtu.be/CKla6oWTezM)

- create a .gitignore file and add the things you do not want to add in the stagging area
- Inside .gitignore we can keep secret files, hidden files, temporary files, log files
- `secret.txt` secret.txt will be ignored
- `*.txt` ignore all files with .txt extension
- `!main.txt` ignore all files with .txt extension without .main.txt
- `test?.txt` ignore all files like test1.txt test2.txt
- `temp/` all the files in temp folders will be ignored

#### [1.4 GitHub Basics & Collaborating with Git]

- Creating a GitHub account
- Creating a new repository
- creating a readme.md
- Forking a repository
- Cloning a repository from GitHub
- Basic GitHub web interface overview
- Connecting local and remote repo
- Push and pull
- Pull Requests
- Issues
- Basic repository settings

##### [Create github repository and commits](https://youtu.be/HRVNOjl9e5U)

- sign in to your github account
- create a git repo

##### [Connecting local repo to remote repo](https://youtu.be/sLX2YWYpkAc)

- check remote connection: `git remote` or `git remote -v`
- `git remote add name <REMOTE_URL>` example: git remote add origin http://...
- to clone a remote repository: `git clone <REMOTE_URL>`

##### [Push and Pull](https://youtu.be/UXEoCfYwI1Q)

- push a branch `git push -u origin branch_name`
- push all branches `git push --all`
- pull from a repo: `git pull` which is equivalent to git fetch + git merge

##### [README.md](https://youtu.be/bl0-DTgh-mw)

[README video is here](https://youtu.be/bl0-DTgh-mw)

- Everything you need to know about README.md is discussed in the video.
- 6 heading levels: number of hashes define heading levels. check the following examples:
  - `# heading 1 level text is here`
  - `## heading 2 level text is here`
- bold syntax: `**text goes here**`
- italic syntax: `_text goes here_`
- bold and italic syntax: `**_text goes here_**`
- strikethrouh syntax: `~~this is~~`
- single line code syntax: `` place code inside backticks
- multiple line code syntax: ``` place code inside three open and closing backticks
- multiple line code syntax language specific: ```html for specific lanaguage use language name when starting; not closing
- Ordered List syntax

```txt
      1. HTML
      2. CSS

          1. Fundamental
          2. CSS Architecture - BEM
          3. CSS Preprocessor - SASS

      3. JS
```

- Unordered List syntax ->
  
  ```txt
   - html
   - css
     - Fundamental
     - CSS Architecture - BEM
     - CSS Preprocessor - SASS
   - js
  ```

- Task List
  
  ```txt
     - [x] Task1
     - [x] Task2
     - [x] Task3
  ```

- adding link
  
  ```txt
     <!-- automatic link -->

     http://www.studywithanis.com

     <!-- markdown link syntax -->
     [title](link)
     [studywithanis](http://www.studywithanis.com)
     [studywithanis][websitelink]

     <!-- all link is here  -->

     [websitelink]: http://www.studywithanis.com

  ```

- adding image syntax -> `![alt text](imageURL)`
  `![1800 milestone](https://i.postimg.cc/qvZpmxKF/1-800-Uploads-Milestone.png)`

- adding emoji  
   [emoji src](https://getemoji.com/) ### Smileys
  😀 😃 😄 😁 😆 😅 😂 🤣 🥲 ☺️ 😊 😇 🙂 🙃 😉 😌 😍 🥰 😘 😗 😙 😚 😋 😛 😝 😜 🤪 🤨 🧐 🤓 😎 🥸 🤩 🥳 😏 😒 😞 😔 😟 😕 🙁 ☹️ 😣 😖 😫 😩 🥺 😢 😭 😤 😠 😡 🤬 🤯 😳 🥵 🥶 😱 😨 😰 😥 😓 🤗 🤔 🤭 🤫 🤥 😶 😐 😑 😬 🙄 😯 😦 😧 😮 😲 🥱 😴 🤤 😪 😵 🤐 🥴 🤢 🤮 🤧 😷 🤒 🤕 🤑 🤠 😈 👿 👹 👺 🤡 💩 👻 💀 ☠️ 👽 👾 🤖 🎃 😺 😸 😹 😻 😼 😽 🙀 😿 😾

  - Gestures and Body Parts
      👋 🤚 🖐 ✋ 🖖 👌 🤌 🤏 ✌️ 🤞 🤟 🤘 🤙 👈 👉 👆 🖕 👇 ☝️ 👍 👎 ✊ 👊 🤛 🤜 👏 🙌 👐 🤲 🤝 🙏 ✍️ 💅 🤳 💪 🦾 🦵 🦿 🦶      👣 👂 🦻 👃 🫀 🫁 🧠 🦷 🦴 👀 👁 👅 👄 💋 🩸

- adding table

 ```txt
     table syntax
     | heading1 | heading2 |
     | ----- | ----- |
     | data1 | data2 |
     | data3 | data4 |
     | data5 | data6 |
```

##### [GitHub Issues: Not Done](https://youtu.be/E5HFlpx7QP4)

GitHub Issues is a feature within GitHub that allows users to track and manage work on a project. It's a powerful tool for managing bugs, tasks, feature requests, and other project-related activities. Here's a detailed explanation of GitHub Issues:

###### Overview

GitHub Issues provides a way to:

- Report bugs
- Suggest enhancements
- Ask questions
- Manage tasks
- Track project milestones

Each issue serves as a discussion thread where collaborators can comment, provide feedback, and attach files or code snippets.

###### Key Features

1. **Creating Issues**
   - Users can create an issue by clicking on the "Issues" tab in a repository and then selecting "New issue."
   - Each issue requires a title and description. The description can include text, markdown, images, and code snippets.

2. **Labels**
   - Labels are used to categorize issues. For example, labels can indicate the type of issue (bug, enhancement, question) or its priority.
   - Custom labels can be created to suit the project's needs.

3. **Assignees**
   - Issues can be assigned to one or more collaborators who are responsible for resolving the issue.

4. **Milestones**
   - Milestones group issues into larger goals or releases. This helps in tracking progress toward significant project objectives.

5. **Projects**
   - GitHub Projects is a feature that allows users to organize issues into boards, similar to Kanban boards, for better project management.

6. **Comments and Mentions**
   - Collaborators can comment on issues to provide updates, feedback, or solutions.
   - Users can mention others using `@username` to draw their attention to specific comments or issues.

7. **References and Links**
   - Issues can be cross-referenced with other issues, pull requests, and commits using their respective IDs (e.g., `#123` for issue 123).

8. **Closing Issues**
   - Issues can be closed manually by maintainers or automatically when a related pull request is merged using keywords like "fixes #123" in commit messages.

9. **Templates**
   - Repository maintainers can create issue templates to guide users in providing necessary information when opening new issues.

###### Workflow

1. **Opening an Issue**
   - A user opens an issue describing a bug, feature request, or task.
   - Labels and milestones can be assigned at this stage.

2. **Discussion**
   - Collaborators discuss the issue in the comments, providing insights, feedback, and potential solutions.
   - The issue can be updated based on the discussion.

3. **Assigning and Prioritizing**
   - The issue is assigned to one or more developers.
   - The priority is set using labels or by placing the issue within a milestone.

4. **Working on the Issue**
   - Developers work on the issue, often linking commits and pull requests to the issue for tracking progress.

5. **Closing the Issue**
   - Once the issue is resolved, it is closed manually or automatically via a merged pull request.

6. **Reviewing Closed Issues**
   - Closed issues can be reviewed for historical reference and to ensure that similar issues do not arise again.

###### Benefits

- **Centralized Tracking:** All issues related to a project are tracked in one place.
- **Collaborative Problem-Solving:** Issues facilitate discussion and collaboration among team members.
- **Transparency:** The status and progress of issues are visible to all project collaborators.
- **Efficient Workflow:** Issues integrate seamlessly with other GitHub features like pull requests and project boards, making it easier to manage the development lifecycle.

###### Best Practices

- **Use Descriptive Titles and Descriptions:** Ensure issues are clear and concise.
- **Label Appropriately:** Use labels to categorize and prioritize issues.
- **Stay Organized:** Regularly review and update issues, milestones, and projects.
- **Encourage Participation:** Invite team members to comment, contribute, and collaborate on issues.
- **Close Issues Promptly:** Close resolved issues to keep the repository clean and up-to-date.

GitHub Issues is a versatile tool that enhances project management and collaboration, making it easier to track, discuss, and resolve tasks and bugs in software development projects.

### Intermediate Part

#### [2.1 Branching and Merging](https://youtu.be/3k8Bq_usPsk)

##### What is Branching & Merging?

- Branch is a new and separate branch of the master/main repository, which allows you parallel development.
- Branching allows you to diverge from the main line of development and continue working on a separate line of code without affecting the main codebase. When you create a branch, you essentially create a copy of the code at a certain point in time, and you can make changes to this copy independently of other branches. Branches are often used for developing new features, fixing bugs, or experimenting with changes.

- Merging is the process of combining the changes from one branch (the source branch) into another (the target branch). This allows you to incorporate the changes made in one branch back into the main codebase or another branch. When you merge branches, Git automatically integrates the changes, resolving any conflicts that may arise if the same part of the code was modified in both branches.

##### Basic commands for branching & merging

- create a branch `git branch branch_name`
- List branches `git branch`
- List all remote branches `git branch -r`
- List all local & remote branches `git branch -a`
- move to a branch `git checkout branch_name`
- create and move to a branch `git checkout -b branch_name`
- delete a branch: `git branch -d branch_name`
- merge branches:

  ```txt
    git checkout branchName
    git merge branchName
  ```

- `git log --oneline --all --graph`

##### [Types of Merges: 2-way and 3-way merges]

- Reeference:
  - https://www.tutorialspoint.com/what-is-a-fast-forward-merge-in-git
  - https://www.tutorialspoint.com/what-is-3-way-merge-or-merge-commit-in-git
  - https://medium.com/@koteswar.meesala/git-fast-forward-merge-vs-three-way-merge-8591434dd350

##### [Resolve Merge Conflicts]

- https://www.tutorialspoint.com/what-is-merge-conflict-in-git-how-to-handle-merge-conflicts

###### resolve merge conflict on Git

###### resolve merge conflict on Github

##### git merge vs git rebase

#### [1.8 Git HEAD and undo theory](https://youtu.be/xUNsecljvog)

- `git log --oneline`
- `git show`
- `git show HEAD^`
- `git show commit-id`
- `git checkout commit-id`
- `git checkout master`

#### [1.10 Git revert]()

#### Tags

In GitHub, "tags" typically refer to Git tags. Git tags are a way to mark specific points in a Git repository's history as being important or significant. They are often used to label specific commits, such as releases or version numbers, to make it easier to reference those commits in the future.

Here's how Git tags work:

1. **Creating a Tag:** You can create a Git tag by running a command like `git tag <tag-name>`, where `<tag-name>` is the name you want to give to the tag. For example, you might create a tag for a release like this: `git tag v1.0.0`.

2. **Tagging Commits:** Tags are typically associated with specific commits. When you create a tag, it's linked to the current commit, but you can also specify a different commit if needed.

3. **Listing Tags:** You can list all the tags in a Git repository using the `git tag` command.

4. **Annotated vs. Lightweight Tags:** Git supports two types of tags: annotated and lightweight. Annotated tags are recommended for most use cases because they store extra metadata like the tagger's name, email, date, and a tagging message. Lightweight tags are just a name for a specific commit and don't include extra information.

5. **Pushing Tags:** By default, when you push changes to a remote Git repository, tags are not automatically pushed. You need to use `git push --tags` to push tags to a remote repository. This is important when you want to share tags, especially when creating releases on GitHub.

6. **Using Tags on GitHub:** On GitHub, you'll often see tags associated with releases. When you create a release on GitHub, it typically creates a Git tag behind the scenes to mark the specific commit associated with that release. Users can then download or reference that release by its tag name.

GitHub also has its own concept of "releases" that are closely related to Git tags. A release on GitHub is a way to package and distribute software versions, and it often corresponds to a Git tag. When you create a GitHub release, you can upload release assets (e.g., binaries, documentation) and provide release notes.

In summary, GitHub tags are essentially Git tags, and they are used to mark important points in a repository's history, often associated with releases or significant commits. They help users easily reference and work with specific versions of a project.

#### git revert

In Git, git revert is a command used to create a new commit that undoes the changes made by a previous commit. This command is helpful when you want to revert specific changes without altering the commit history.

#### Advanced Part

#### Learning Resource

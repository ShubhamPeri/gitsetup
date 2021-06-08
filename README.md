## A quick introduction to Git with an hands on example starting with GitHub, making local changes and back to GitHub again. ##
This covers:<br /> 
         1. What is Git?<br />
         2. Git core concepts.<br />
         3. How to install Git on Windows.<br /> 
         4. Knowledge of Git Commands.<br />
         5. Demonstration.<br />
         6. Git branching, merging and merge conflicts.
## Topic 1) What is Git? ##
- Git is a decentralized and distributed version control system.
- Highly scabale.
- Open source and free.
- Most of the git operations are local.
- It is very fast and has active community to solve the issues.
## Topic 2) Git core concepts ##
- Repository contains files, history, configuartion manged by git.
- Three states of git:<br />
         1. Working directory (on local machine).<br />
         2. Staging area (when the code is committed but not pushed).<br />
         3. Git repository (when the code is pushed).<br />
## Topic 3) How to install Git on Windows? ##
- Download the Git from this link [Windows Setup x32/x64 bit] (https://git-scm.com/download/win).
- Once downloaded, open the executable file.
- Accept the license agreement, click next.
- Let it create the git folder in [C:\Program Files\Git] location.
- Adjusting PATH environment, you can select either options: <br />
               `use git from windows command prompt` <br />
            **OR** `use git and unix tool from command prompt` depending on your need.
- HTTPS transport backend, select `use openSSL library`.
- Configuring line ending conversions, select `checkout as-is,commit unix-style line ending`.
- Terminal emulator, choose the default `use MinTTY`.
- Extra feature, choose `enable file system caching` & `enable git credential manager`.
- Final step, click on `install`. On the start menu, you can see git GUI, git bash, git cmd.
## Topic 4) Knowledge of Git Commands ##
#### 1. Setup the Project Folder ####
#####   Command Listing ######
 - pwd (Open git bash ---> type pwd) -----> `Points at (/c/Users/{user_name})`
 - mkdir {new_directory_name}
 - cd {new_directory_name}
 - pwd ----->  `(/c/Users/{user_name}/{new_directory_name})`
#### 2. Git Configuration ####
##### Command Listing #####
- git version
- git config --global user.name "{your_github_username}"
- git config --global user.email "{your_email_address}"
- git config --global --list
#### 3. Copy the Repository (clone) ####
##### Command Listing #####
- git clone {your_github_repository_path}
- ls -----> `{your_github_repository})`
- cd {your_github_repository}
- pwd -----> `(/c/Users/{user_name}/{new_directory_name}/{your_github_repository_path})`
- ls -----> `It will shows all the files you have in repository`
- git status
#### 4. The First Commit ####
##### Command Listing #####
- touch demo.txt -----> `It will create a new empty file touch.txt`
- echo "Hello, Good morning" >> demo.txt
- ls
- cat demo.txt
- git status -----> `It will show one untracked file, pointed in red colour`
- git add demo.txt -----> `It you want to add multiple files, use git add .`
- git status
- git commit -m "Adding start text file" -----> `commit moves from the file from local repo to staging area`
- git status
#### 5. Publishing Changes to GitHub (push) ####
##### Command Listing #####
- git push -u origin master/main -----> `pushes the file from staging area to github`<br />
- By default, GitHub uses the term **"master"** for the primary version of a source code repository. Since, Oct. 1, 2020, any new repositories you create will use **main** as     the default branch instead of master.<br />
- When you push the code for the first time it will ask you to enter the github username and password for authentication purpose.<br />
## Exception: ##
- If you have multi-factor authentication enabled on github, your github password won't bypass the authentication method. In this case, you will need `personal access token`.
  - go to settings on github.
  - select developer settings.
  - choose personal access token.
  - copy the token.
  - paste the token in the password field while pushing the code.
## Topic 5) Demonstration ##
![image](https://user-images.githubusercontent.com/58199878/121227791-d4e26100-c840-11eb-9663-06dd2ab34a7d.png)
Follow all the steps mentioned in previous topic.
![image](https://user-images.githubusercontent.com/58199878/121227890-f0e60280-c840-11eb-998b-ab3a1b4f0e0e.png)
You only need to authentcate once for pushing the code into github repository.
## Topic 5) Git branching, merging and merge conflicts ##
- **Merge conflicts** occur when competing changes are made to the same line of a file, or when one person edits a file and another person deletes the same file.
- To resolve a merge conflict caused by competing line changes, you must choose which changes to incorporate from the different branches in a new commit.<br />
![image](https://user-images.githubusercontent.com/58199878/121238566-16790900-c84d-11eb-86c1-7e32186e332c.png)
- Firstly, edit the file `demo.txt` from github by appending some text to the existing line. 
- From the git bash, edit the same file by adding text to the line.
- In this case, github file version has `Hello, Good morning, Have a great day!`. While git bash file has `Hello, Good morning, Take care` text.
- If you try to perform git pull, an error will occur stating `merge conflict in demo.txt`
- open the file in text editor and decide when version to keep.
![image](https://user-images.githubusercontent.com/58199878/121237815-4e338100-c84c-11eb-800f-d47594bc24df.png)
- The text between `<<<<<<<` and `=======` is the git bash version whereas the text between  `=======` and `>>>>>>>>` is the github version.
- Remove the unwanted line and keep ony the required one. In this case it is `Hello, Good morning, Have a great day!`.
- **Branching** is a feature available in most modern version control systems. Instead of copying files from directory to directory, Git stores a branch as a reference to a commit. In this sense, a branch represents the tip of a series of commits—it's not a container for commits.
##### Command Listing ######
- git branch -----> `will show the default branch`
- git branch {branch_name} -----> `add a new branch`
- git checkout {branch_name} -----> `change the branch to new_branch
- edit the file demo.txt
- git add demo.txt
- git commit -m "New lines added to the file demo.txt"
- cat demo.txt -----> `display the content of the file with new changes`
- git checkout main/master
- cat demo.txt -----> `This file won't have the changes made to the file in new_branch`
![image](https://user-images.githubusercontent.com/58199878/121238606-21339e00-c84d-11eb-9e5c-028568d2c8a9.png)
- **Merging** is Git's way of putting a forked history back together again. The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.
##### Command Listing ######
- git checkout main/master
- cat demo.txt
- git merge {branch_name}
- cat demo.txt
- git push -u origin master/main -----> `changes will be pushed to main/master github repository`
- git checkout {branch_name}
- git push -----> `Error: No upstream branch`
- git push --set-upstream origin feature -----> `New branch created in github repository`
![image](https://user-images.githubusercontent.com/58199878/121238658-30b2e700-c84d-11eb-9bda-19c5158a5362.png)


## Try Configuring git and join git and github together. Enjoy learning!. ##




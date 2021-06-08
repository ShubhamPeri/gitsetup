## A quick introduction to Git with an hands on example starting with GitHub, making local changes and back to GitHub again.<br /> ##
This covers:<br /> 
         1. What is Git?<br />
         2. Git core concepts.<br />
         3. How to install Git on Windows.<br /> 
         4. Knowledge of Git Commands.<br />
         5. Collaborating Git and Github.<br />
         6. Git branching, merging and merge conflicts.
## Topic 1) What is Git?<br /> ##
- Git is a decentralized and distributed version control system.
- Highly scabale.
- Open source and free.
- Most of the git operations are local.
- It is very fast and has active community to solve the issues.
## Topic 2) Git core concepts<br /> ##
- Repository contains files, history, configuartion manged by git.
- Three states of git:<br />
         1. Working directory (on local machine).<br />
         2. Staging area (when the code is committed but not pushed).<br />
         3. Git repository (when the code is pushed).<br />
## Topic 3) How to install Git on Windows?<br /> ##
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
## Topic 4) Knowledge of Git Commands <br /> ##
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
- ls
- cd github-demo
- ls
- git status
#### 4. The First Commit ####
##### Command Listing #####
echo "Test Git Quick Start demo" >> start.txt
ls
cat start.txt
git status
git add start.txt
git status
git commit -m "Adding start text file"
git status
#### 5. Publishing Changes to GitHub (push) ####
##### Command Listing #####
git push origin master

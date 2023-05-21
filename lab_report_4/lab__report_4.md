# CSE-15L Lab Report 4
This is lab report 4 for CSE-15L course from Jiho Kim.
## 1) Log into ieng6
![1](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/c7e4f165-196d-401e-91b1-ff7631cdd4c0)    
Keys pressed: **\<ctrl-r>\<up>\<up>\<enter>**
* `ctrl-r`: to access your bash history, you don't have to type the `ssh cs15lsp23gc@ieng6.ucsd.edu`
* `up`:  to navigate through previously executed commands
* `enter`: Once you press "Enter," the command you entered is sent to the system or shell for processing and execution
---
## 2) Clone your fork of the repository from your Github account
![2](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/9b7f68e8-89b0-47f6-92ff-5a743ac56ed3)    
Keys pressd: **git\<space>clone\<spaec>\<ctrl-v>**
* `git clone`: It allows you to obtain a full copy of the repository, including all its files, commit history, and branches
* `space`: it inserts a space character into the text you are typing
* `ctrl-v`: to paste the contents of the clipboard. After copying or cutting text or other content using "Ctrl-C" 
---
## 3) Run the tests, demonstrating that they fail
![4](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/4095e435-0c6b-45fa-8427-74efa063900d)    
The error indicates a test failure in JUnit version 4.13.2. It seems that the test case testMerge2 from the ListExamplesTests class has failed due to a timeout    

Keys pressed: **cd\<space>lab7\<enter>chmod\<space>+x\<space>test.sh\<enter>./test.sh\<enter>**
* `cd`: is a command-line command used to change the current working directory in a command-line interface or terminal
* `lab7`: is a name of a directory
* `chmod +x<file>`: The command chmod +x is used to grant executable permissions to a file in a Unix-based operating system. It allows the file to be executed as a program or script
* `./`: The dot-slash notation is used to refer to the current directory
* `test.sh`: This is the name of the shell script file that you want to execute.
---
## 4) Edit the code file to fix the failing test, Run the tests, demonstrating that they now succeed
![5](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/9ddd39fa-5627-4d9e-a4bb-cb6d8bbec49f)    
After editing file in vim, and run the tests, it shows that they now succeed

Keys pressed: **vim\<space>ListExamples.java\<enter>/ind\<enter>jjjjjjjjjjjjjjjjjjlllxi2\<esc>:wq\<enter>\<up>\<up>\<enter>**
* `vim`: is a highly configurable and powerful text editor
* `ListExamples.java`: is a name of file in the vim text editor for editing
* `/ind`: '/' is a command for searching within the file, I wanted to find index1 in the file
* `j`: The j command moves the cursor down one line
* `l`: The l command moves the cursor one character to the right
* `x`: The x command is used to delete the character under the cursor or to the right of the cursor
* `i`: The i command is used to enter insert mode. Insert mode allows you to directly insert or edit text in the document
* `esc`: To exit insert mode and return to normal mode
* `:wq`: The wq command is used to save changes to the file and exit the editor    
---
## 5) Commit and push the resulting change to your Github account 
![6](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/9b1e0018-4f08-4e9b-a2f6-7b2de6ffb9ed)    
Key pressed: **git\<space>add\<space>ListExamples.java\<enter>git\<space>commit\<space>-m\<space>"Modified ListExamples.java"\<enter>git\<space>push\<space>origin\<space>master\<enter>git\<space>branch\<enter>git\<space>push\<space>origin\<space>main\<enter>**
* `git add`: In Git, the git add command is used to stage changes in your working directory for the next commit. It allows you to specify which files or directories you want to include in the next commit
* `git commit -m'`: It allows you to record the changes made to your files and create a checkpoint in the Git history
* `git push origin main`: In Git, the git push origin main command is used to push your local commits to a remote repository named "origin" on the branch "main". It updates the remote repository with the changes you have made locally.
---
## Reference
![chatgpt](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/74cd446e-6472-4d91-a3c9-1ea191dd4856)

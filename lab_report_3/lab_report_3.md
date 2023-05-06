# CSE-15L Lab Report 3
This is lab report 3 for CSE-15L course from Jiho Kim.
## 1) PART 1
### "Find" command
1. What is the "Find" command?    
* The find command in shell script is used to search for files and directories in a directory hierarchy based on different criteria such as name, type, size, ownership, and modification time     
2. How do we use it?
* The basic syntax for "Find" command is `find [path] [expression]`, where path is a directory, expression is a set of options and tests that you want to use to filter your search results    
## 2) PART 2
### Options of the `Find` Command
1. `-name`: The find -name command searches for files with a specific name in the specified directory or its subdirectories  
```console
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/stringsearch/stringsearch-data (main)
$ find . -name "*.txt"
./technical/plos/pmed.0020247.txt
./technical/plos/pmed.0020249.txt
./technical/plos/pmed.0020257.txt
./technical/plos/pmed.0020258.txt
./technical/plos/pmed.0020268.txt
./technical/plos/pmed.0020272.txt
./technical/plos/pmed.0020273.txt
./technical/plos/pmed.0020274.txt
./technical/plos/pmed.0020275.txt
./technical/plos/pmed.0020278.txt
./technical/plos/pmed.0020281.txt
```
* `find . -name "*.txt"`: This command will search for all files ending with the ".txt" extension in the current directory and all subdirectories, this method is useful when you want to see all files ends with ".txt"    
```console
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/stringsearch/stringsearch-data (main)
$ find technical/911report/ -name "*-*"
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-2.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-8.txt
technical/911report/chapter-9.txt
```
* `find technical/911report/ -name "*-*"`: This command searches for all files in the technical/911report/ directory (and its subdirectories) that have a hyphen in their filename, by using this command, you are able to find all the files that has hyphen in your 911report directory, which is quite useful for specifying files
* [Click here for more information](https://recipes4dev.tistory.com/156)
---
2. `-type`: The -type option in the find command is used to specify the type of the file that we want to search for
```console
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/stringsearch/stringsearch-data (main)
$ find . -type d
.
./.git
./.git/hooks
./.git/info
./.git/logs
./.git/logs/refs
./.git/logs/refs/heads
./.git/logs/refs/remotes
./.git/logs/refs/remotes/origin
./.git/objects
./.git/objects/info
./.git/objects/pack
./.git/refs
./.git/refs/heads
./.git/refs/remotes
./.git/refs/remotes/origin
./.git/refs/tags
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
* `find . -type d`: This command will search for all directories within the current directory, and if you are wondering how many directories within the curren directory, you can check it by using this command.    
```console
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/stringsearch/stringsearch-data (main)
$ find . -type f
./technical/plos/pmed.0020226.txt
./technical/plos/pmed.0020231.txt
./technical/plos/pmed.0020232.txt
./technical/plos/pmed.0020235.txt
./technical/plos/pmed.0020236.txt
./technical/plos/pmed.0020237.txt
./technical/plos/pmed.0020238.txt
./technical/plos/pmed.0020239.txt
./technical/plos/pmed.0020242.txt
./technical/plos/pmed.0020246.txt
./technical/plos/pmed.0020247.txt
./technical/plos/pmed.0020249.txt
./technical/plos/pmed.0020257.txt
./technical/plos/pmed.0020258.txt
./technical/plos/pmed.0020268.txt
./technical/plos/pmed.0020272.txt
./technical/plos/pmed.0020273.txt
./technical/plos/pmed.0020274.txt
./technical/plos/pmed.0020275.txt
./technical/plos/pmed.0020278.txt
./technical/plos/pmed.0020281.txt
```
* `find . -type f`: This command will find all files (not directories) in the current directory and its subdirectories recursively, if you want to see only the files in the current directory you can easily check it with this command    
* [Click here for more information](https://recipes4dev.tistory.com/156)
---
3. `-size`: The -size option in the find command is used to search for files based on their size. It allows you to search for files that are of a specific size or within a range of sizes.
* `find . -size +1024c`: This command will find all files in the current directory and its subdirectories that are larger than 1024 bytes    
![lab_report-3 7](https://user-images.githubusercontent.com/129816454/236585658-b8363628-cdf6-457f-8688-4cdf3ecaafad.png)
* `$  find . -size -1024c`: This command will find all files in the current directory and its subdirectories that are less than 1024 bytes    
![lab_report-3 8](https://user-images.githubusercontent.com/129816454/236585829-4eb4d87c-bc63-4d57-a66d-e48d844fbd1f.png)
---
4. `-newermt`: The -newermt option is used with the find command in Linux to locate files that were modified more recently than a particular time
* `$ find . -newermt "2023-04-02"`: This command will find all files and directories in the current directory that have been modified more recently than April 2nd, 2023.
* `$ find . -newermt "2023-05-05"`: This command will find all files and directories in the current directory that have been modified more recently than May 5th, 2023.







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
* `find . -name "*.txt"`: This command will search for all files ending with the ".txt" extension in the current directory and all subdirectories
![lab_report-3 1](https://user-images.githubusercontent.com/129816454/236583673-c8ae31ab-620e-4c21-9bfd-056d4b0cffa0.png)
![lab_report-3 2](https://user-images.githubusercontent.com/129816454/236583674-d46e3df5-e518-48c6-b354-fc3e0347664c.png)    
* `find technical/911report/ -name "*-*"`: This command searches for all files in the technical/911report/ directory (and its subdirectories) that have a hyphen in their filename    
![lab_report-3 3](https://user-images.githubusercontent.com/129816454/236584442-526decee-60af-419d-900a-e757f80a9d0c.png)
---
2. `-type`: The -type option in the find command is used to specify the type of the file that we want to search for
* `find . -type d`: This command will search for all directories within the current directory
![lab_report-3 4](https://user-images.githubusercontent.com/129816454/236584827-2b460d70-1434-4029-a687-46f6975fce1d.png)
* `find . -type f`: This command will find all files (not directories) in the current directory and its subdirectories recursively.
![lab_report-3 5](https://user-images.githubusercontent.com/129816454/236585054-d7ca65fe-c647-4881-9f8c-22a681e04347.png)
![lab_report-3 6](https://user-images.githubusercontent.com/129816454/236585055-f86e1875-1bdb-4d8d-8b1d-fbb0d3caa059.png)
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







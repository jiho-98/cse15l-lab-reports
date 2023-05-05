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
1. `-name`: The find -name command searches for files with a specific name in the specified directory or its subdirectories.
* `find . -name "*.txt"`: This command will search for all files ending with the ".txt" extension in the current directory and all subdirectories
![lab_report-3 1](https://user-images.githubusercontent.com/129816454/236583673-c8ae31ab-620e-4c21-9bfd-056d4b0cffa0.png)
![lab_report-3 2](https://user-images.githubusercontent.com/129816454/236583674-d46e3df5-e518-48c6-b354-fc3e0347664c.png)    
* `find technical/911report/ -name "*-*"`: This command searches for all files in the technical/911report/ directory (and its subdirectories) that have a hyphen in their filename    
![lab_report-3 3](https://user-images.githubusercontent.com/129816454/236584442-526decee-60af-419d-900a-e757f80a9d0c.png)


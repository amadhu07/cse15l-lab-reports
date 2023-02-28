# Researching Find String

1.```find . -type d -name "berlitz1"```  
Output:  
./written_2/travel_guides/berlitz1

This command allows you to search for folders with the name "berlitz1" in the subdirectory. This is useful if you're looking for a specific filename.

2.```find . -name '*.txt'```
Output:
![findtxt](findtxt.png)

This command will list all files with the txt extension in the current directory. Good for searching for a specific file type. 

3.```find . -name '*.txt' | wc -l```
Output:
224
This command lists the number of all files with .txt extenstion. Is useful if you want to know how many files of a specific filetype exist in the current directory. 





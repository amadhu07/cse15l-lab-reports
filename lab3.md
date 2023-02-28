# Researching Find String

1. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -name "V*.txt"```    
command [manual](https://man7.org/linux/man-pages/man1/find.1.html)      
Output:    
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2/Vallarta-History.txt
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt

This command allows you to search for .txt files containing "V". This is useful if you're looking for files starting with a particular letter.

2. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -name "ashutosh.txt"```  
Output:  


This find command searches for a file ashutosh.txt in the written_2 subfolders. Since it didn’t find ashutosh.txt there is nothing to display as the output. 


3. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -name "chz.txt"```    
Output:    
Nothing is outputted since ```ch.txt``` does not exist however if I use -iname which ignore case sensitivity,
```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -iname "chz.txt"```      
find [ignorecase] (https://alvinalexander.com/blog/post/linux-unix/case-insensitive-file-searching-unix-linux-mac-osx/)
Output:  
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Castro/chZ.txt

This command will list every file containing the supplied string. This useful for finding multiple files containing a particular string of the same word.

4. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -iname "CHZ.txt"```  
Output:  
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Castro/chZ.txt
Not case sensitive so will return the text file. Its good for searching txt files containing a word regardless of case. 

5. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -type d```  
find [depth](https://tecadmin.net/how-to-limit-directory-depth-with-find-command/)       
Output:   
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Berk
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Abernathy
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Rybczynski
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Kauffman
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Fletcher
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction/OUP/Castro
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2

This command lists sub directories but up to a directory depth of 1. This is useful because we can limit the search to a depth of one.

6. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2 -maxdepth 1 -type d```  
Output:    
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/non-fiction
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides  

This command lists sub directories but up to a directory depth of 1. This is useful because we can limit the search to a depth of one.

7. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2  -size +200k```  
find [filesize](https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size)   
Output:  
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/WhereToItaly.txt
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/WhereToFrance.txt
/Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
This command list files of size more than 200 kilobytes. This is useful for findin files of a certain size. 


8. ```find /Users/ashutoshmadhu/Documents/GitHub/docsearch/written_2  -size +1M```    
Output:  
Since there are no files with size more than 1 megabyte nothing is outputted. This is useful for finding a threshold for file size in the directory. 


 








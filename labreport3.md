# Lab Report 3 #
----

## Command 1 ##

````
find -name
````
This command searches for files of a specified pattern (the pattern is based on what proceeds -name). I learned about this command during the CSE 15L lectures. 

### Example 1 ###

````
$ find -name "berlitz2"
    ./skill-demo1-data/written_2/travel_guides/berlitz2
````

Essentially what this command does is find the file that has the name of berlitz2, and provides a direct path to it. This is useful, as often we don't know where are files are located, and with the find command, we can find the files, as a direct path, so we may be able to access the files again. 

### Example 2 ###

````
$ find . -name "*WhereToGo*"
    ./Algarve-WhereToGo.txt
    ./Amsterdam-WhereToGo.txt
    ./Athens-WhereToGo.txt
    ./Bahamas-WhereToGo.txt
    ./Bali-WhereToGo.txt
    ./Barcelona-WhereToGo.txt
    ./Beijing-WhereToGo.txt
    ./Berlin-WhereToGo.txt
    ./Bermuda-WhereToGo.txt
    ./Boston-WhereToGo.txt
    ./California-WhereToGo.txt
    ./Canada-WhereToGo.txt
    ./CanaryIslands-WhereToGo.txt
    ./Cancun-WhereToGo.txt
    ./China-WhereToGo.txt
    ./Costa-WhereToGo.txt
    ./Crete-WhereToGo.txt
    ./CstaBlanca-WhereToGo.txt
    ./Cuba-WhereToGo.txt
    ./Nepal-WhereToGo.txt
    ./Paris-WhereToGo.txt
    ./Portugal-WhereToGo.txt
    ./PuertoRico-WhereToGo.txt
    ./Vallarta-WhereToGo.txt
````
Essentially what this command does here is find files that has the name "WhereToGo" in the title, and provides a path to all of the files that include the exact phrase in the title. This is useful, as often times we do not know where we placed certain files, but only remember the names of the file (maybe not even the whole name but simply a phrase). 

-----
## Command 2 ##

````
$ find -type
````
This command searches for files, directories, symbolic links, character devices, etc. and returns results of all of the desired type the user wanted. I asked chatGPT for useful commands from the find function, and it provided me this. I investigated the command more thoroughly in [Stackoverflow](https://stackoverflow.com/).


### Example 1 ###
````
$ find . -type d
    .
    ./.git
    ./.git/info
    ./.git/hooks
    ./.git/branches
    ./.git/refs
    ./.git/refs/heads
    ./.git/refs/tags
    ./.git/refs/remotes
    ./.git/refs/remotes/origin
    ./.git/objects
    ./.git/objects/pack
    ./.git/objects/info
    ./.git/logs
    ./.git/logs/refs
    ./.git/logs/refs/remotes
    ./.git/logs/refs/remotes/origin
    ./.git/logs/refs/heads
    ./lib
    ./written_2
    ./written_2/non-fiction
    ./written_2/non-fiction/OUP
    ./written_2/non-fiction/OUP/Abernathy
    ./written_2/non-fiction/OUP/Berk
    ./written_2/non-fiction/OUP/Castro
    ./written_2/non-fiction/OUP/Fletcher
    ./written_2/non-fiction/OUP/Kauffman
    ./written_2/non-fiction/OUP/Rybczynski
    ./written_2/travel_guides
    ./written_2/travel_guides/berlitz1
    ./written_2/travel_guides/berlitz2
````
This command searches for all the directories from the directory that the user is currently residing in. It cycles through each directory, going as far in as possible then prints all the directories for the user. This is useful, as now the user can effectively navigate all the directories without any issues. 

### Example 2 ###
````
$ find . -type c

    ./Algarve-History.txt
    ./Algarve-Intro.txt
    ./Algarve-WhatToDo.txt
    ./Algarve-WhereToGo.txt
    ./Amsterdam-History.txt
    ./Amsterdam-Intro.txt
    ./Amsterdam-WhatToDo.txt
    ./Amsterdam-WhereToGo.txt
    ./Athens-History.txt
    ./Athens-Intro.txt
    ./Athens-WhatToDo.txt
    ./Athens-WhereToGo.txt
    ./Bahamas-History.txt
    ./Bahamas-Intro.txt
    ./Bahamas-WhatToDo.txt
    ./Bahamas-WhereToGo.txt
    ./Bali-History.txt
    ./Bali-WhatToDo.txt
    ./Bali-WhereToGo.txt
    ./Barcelona-History.txt
    ./Barcelona-WhatToDo.txt
    ./Barcelona-WhereToGo.txt
    ./Beijing-History.txt
    ./Beijing-WhatToDo.txt
    ./Beijing-WhereToGo.txt
    ./Berlin-History.txt
    ./Berlin-WhatToDo.txt
    ./Berlin-WhereToGo.txt
    ./Bermuda-WhatToDo.txt
    ./Bermuda-WhereToGo.txt
    ./Bermuda-history.txt
    ./Boston-WhereToGo.txt
    ./Budapest-History.txt
    ./Budapest-WhatToDo.txt
    ./Budapest-WhereoGo.txt
    ./California-History.txt
    ./California-WhatToDo.txt
    ./California-WhereToGo.txt
    ./Canada-History.txt
    ./Canada-WhereToGo.txt
    ./CanaryIslands-History.txt
    ./CanaryIslands-WhatToDo.txt
    ./CanaryIslands-WhereToGo.txt
    ./Cancun-History.txt
    ./Cancun-WhatToDo.txt
    ./Cancun-WhereToGo.txt
    ./China-History.txt
    ./China-WhatToDo.txt
    ./China-WhereToGo.txt
    ./Costa-History.txt
    ./Costa-WhatToDo.txt
    ./Costa-WhereToGo.txt
    ./CostaBlanca-History.txt
    ./CostaBlanca-WhatToDo.txt
    ./Crete-History.txt
    ./Crete-WhatToDo.txt
    ./Crete-WhereToGo.txt
    ./CstaBlanca-WhereToGo.txt
    ./Cuba-History.txt
    ./Cuba-WhatToDo.txt
    ./Cuba-WhereToGo.txt
    ./Nepal-History.txt
    ./Nepal-WhatToDo.txt
    ./Nepal-WhereToGo.txt
    ./NewOrleans-History.txt
    ./Paris-WhatToDo.txt
    ./Paris-WhereToGo.txt
    ./Poland-History.txt
    ./Poland-WhatToDo.txt
    ./Portugal-History.txt
    ./Portugal-WhatToDo.txt
    ./Portugal-WhereToGo.txt
    ./PuertoRico-History.txt
    ./PuertoRico-WhatToDo.txt
    ./PuertoRico-WhereToGo.txt
    ./Vallarta-History.txt
    ./Vallarta-WhatToDo.txt
    ./Vallarta-WhereToGo.txt
````
This command searches for all the files that contain characters from the directory that the user is currently residing in. It cycles through each file in every proceeding directory (going further in from the directory that the user is in),. This is useful, as now the user would be able to know which files contain characters and are not empty. 



-----
## Command 3 ##

````
$ find -size
````

This command searches for files of a specific size. It can also find files greater or less than a certain size, when desired. I learned about this command asking chatGPT for some CLI commands. I further explored this command using stackoverflow, and learned of how to use certain letters to represent the bytes (c for bytes for example). 


### Example 1 ###
````
$ find . -size 17k
    ./Athens-WhatToDo.txt
    ./Bahamas-History.txt
    ./Bali-History.txt
    ./Budapest-WhatToDo.txt
    ./Crete-WhatToDo.txt
    ./Cuba-WhatToDo.txt
    ./Portugal-WhatToDo.txt
````
Essentially what this command does is find the files that have a size of 17 kilobytes.It then provides a path to all the files that have exactly 17 kilobytes size. This is useful, as often we don't know we are certain for files of a specific size to delete (if space is full) and this command makes it easier. 


### Example 2 ###
````
$ find . -type f -size +100k
    ./Canada-WhereToGo.txt
    ./China-WhereToGo.txt
    ./Portugal-WhereToGo.txt
````
Essentially what this command does is find the files that have a size over 100 kilobytes.It then provides a path to all the files that have over 100 kilobytes size. This is useful, as often we don't know we are certain for files of a specific size to delete (if space is full) and this command makes it easier to find the larger files, for us to delete. 

-----
## Command 4 ##

````
$ find -mtime
````
This command searches for files based on when its modified. It will search based on how much days months, or even hours since the file has been modified. I learned about this command asking chatGPT for some CLI commands. I further explored this command using [Stackoverflow](https://stackoverflow.com/questions/25599094/explaining-the-find-mtime-command), and learned of effective usecases where you would need to know the modification date. 


### Example 1 ###
````
$ find . -type f -mtime +2

    ./Algarve-History.txt
    ./Algarve-Intro.txt
    ./Algarve-WhatToDo.txt
    ./Algarve-WhereToGo.txt
    ./Amsterdam-History.txt
    ./Amsterdam-Intro.txt
    ./Amsterdam-WhatToDo.txt
    ./Amsterdam-WhereToGo.txt
    ./Athens-History.txt
    ./Athens-Intro.txt
    ./Athens-WhatToDo.txt
    ./Athens-WhereToGo.txt
    ./Bahamas-History.txt
    ./Bahamas-Intro.txt
    ./Bahamas-WhatToDo.txt
    ./Bahamas-WhereToGo.txt
    ./Bali-History.txt
    ./Bali-WhatToDo.txt
    ./Bali-WhereToGo.txt
    ./Barcelona-History.txt
    ./Barcelona-WhatToDo.txt
    ./Barcelona-WhereToGo.txt
    ./Beijing-History.txt
    ./Beijing-WhatToDo.txt
    ./Beijing-WhereToGo.txt
    ./Berlin-History.txt
    ./Berlin-WhatToDo.txt
    ./Berlin-WhereToGo.txt
    ./Bermuda-WhatToDo.txt
    ./Bermuda-WhereToGo.txt
    ./Bermuda-history.txt
    ./Boston-WhereToGo.txt
    ./Budapest-History.txt
    ./Budapest-WhatToDo.txt
    ./Budapest-WhereoGo.txt
    ./California-History.txt
    ./California-WhatToDo.txt
    ./California-WhereToGo.txt
    ./Canada-History.txt
    ./Canada-WhereToGo.txt
    ./CanaryIslands-History.txt
    ./CanaryIslands-WhatToDo.txt
    ./CanaryIslands-WhereToGo.txt
    ./Cancun-History.txt
    ./Cancun-WhatToDo.txt
    ./Cancun-WhereToGo.txt
    ./China-History.txt
    ./China-WhatToDo.txt
    ./China-WhereToGo.txt
    ./Costa-History.txt
    ./Costa-WhatToDo.txt
    ./Costa-WhereToGo.txt
    ./CostaBlanca-History.txt
    ./CostaBlanca-WhatToDo.txt
    ./Crete-History.txt
    ./Crete-WhatToDo.txt
    ./Crete-WhereToGo.txt
    ./CstaBlanca-WhereToGo.txt
    ./Cuba-History.txt
    ./Cuba-WhatToDo.txt
    ./Cuba-WhereToGo.txt
    ./Nepal-History.txt
    ./Nepal-WhatToDo.txt
    ./Nepal-WhereToGo.txt
    ./NewOrleans-History.txt
    ./Paris-WhatToDo.txt
    ./Paris-WhereToGo.txt
    ./Poland-History.txt
    ./Poland-WhatToDo.txt
    ./Portugal-History.txt
    ./Portugal-WhatToDo.txt
    ./Portugal-WhereToGo.txt
    ./PuertoRico-History.txt
    ./PuertoRico-WhatToDo.txt
    ./PuertoRico-WhereToGo.txt
    ./Vallarta-History.txt
    ./Vallarta-WhatToDo.txt
    ./Vallarta-WhereToGo.txt
````
This command essentially finds all the files that have been modified after 2 days, and prints them all out. This is useful, as we in certain cases would want to know how recently a file has been modified, to show how new it is, and it will also help find bugs and such if there is all of a sudden an influx of bugs, and with modification you can see when it was modified.


### Example 2 ###

````
$ find . -type f -mtime +7
    
````
This command finds all the files that have been modified in the after 7 days, and prints them out. Here we see that no files have been modified past then. This is useful, as if we see certain files not modified and sitting there, we can delete those files taking up space. 









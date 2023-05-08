# Terminal_HW_2

1. **Create a directory `dir_1`** 

    `$ mkdir dir_1`
    
            *the `mkdir` (make directory) command allows you to create a new directory. New directories created with this command grant the owner read,                  write, and execute permissions
   
2. **Go to the folder `dir_1`**

    `$ cd dir_1/`
    
         *the `cd` command (change directory) allows you to change the current folder to another one
  
 3. **Create a directory `inner_dir_1`**
 
    `$ mkdir inner_dir_1`
     
 4. **See where I am**
```
     $ pwd
    
    /d/QA/dir_1
   
```
 
         *the `pwd` command outputs the path to the current folder
    
 5. **Create an empty text file `tf_1.txt` in a directory `dir_1`**
 
    `$ touch tf_1.txt`
    
         *the `touch` command allows you to create one or more empty files
    
 6. **Create `tf_2.txt` in a directory `dir_1` using `cat` with strings the first 1, the second 2, the third 3** 
 
   ```
   
    $ cat > tf_2.txt
    
    the first 1
   
    the second 2
    
    the third 3
    
   ```
       
         *`cat` with the redirection operator `>` allows you to enter any characters that need to be written to the file*
        
7. **Go to the folder `inner_dir_1`**

   `$ cd inner_dir_1/`
  
8. **Create `tf_3.txt` using `cat` with any lines**
```
    $ cat > tf_3.txt
    
    novell
    
    story
    
    poem
    
    myph
    
    tale
    
```
   
9. **Add a line "the second 2" to the `tf_3.txt` using `cat`**

   ```
     $ cat >> tf_3.txt

     the second 2
   
   ```
        *`cat` with the redirection operator `>>` allows to add data to the end of the file
        
10. **Add a string "the sec 2" to the `tf_3.txt` using `cat`**


   ```
     $ cat >> tf_3.txt

     the sec 2
   
   ```
   
11. **Add a string "the sec 3" to the `tf_2.txt` using `cat`**

```
      $ cd ..
   
      $ cat >> tf_2.txt

      the sec 3
```
       *here we use `cd ..` to go to the parent directory. We can also use `cd -`
      
12. **Add a string "the SeCoNd 2" to the `tf_3.txt` using `cat`**

```
      $ cat >> inner_dir_1/tf_3.txt
      the SeCoNd 2
   
```

13. **Add a string "the seConD 2" to the `tf_2.txt` using `cat`**

```
     $ cd ..
   
     $ cat >> tf_2.txt

     the seConD 3
   
```

14. **Create `tf_4.txt` with 15 lines inside** 

```

     $ cd inner_dir_1/
     
     $ seq 1 15 | cat > tf_4.txt`
     
```

         *the seq command outputs a sequence of numbers (from 1 to 15). We also can create 15 lines in the file with help of editor Vim.
      
15. **Create `tf_5.txt` with 15 lines inside**

     `$ seq 1 13 | cat > tf_5.txt`
   
16. **List all files**

```

     $ ls
     tf_3.txt  tf_4.txt  tf_5.txt

```  

      *The `ls` (list) command is used in the Linux shell to output directory contents and file information.The command options indicate exactly how and in        what form information should be displayed on the screen. 
       We also can use the command `echo *` or `echo *.txt`
      
      
17. **Exit the folder `inner_dir_1`**

     $ cd ..`
        
18. **Output the contents of the file `tf_3.txt` to the terminal**

```
     $ cat inner_dir_1/tf_3.txt
     novell
     story
     poem
     tale
     myph
     the second 2
     the sec 2
     the SeCoNd 2
```
        
19. **Find the path to the file `tf_4.txt`**

```

     $ find -name tf_4.txt
     ./inner_dir_1/tf_4.txt

```  

        *the command `find` is used to search for files and directories based on special conditions. It can be used in various circumstances, for example,          to search for files by permissions, owners, groups, type, size, and other similar criteria.
         The find command has this syntax: find [folder] [parameters] criterion template [action]
         Folder - the directory in which we will search
         Parameters - additional parameters, for example, search depth, etc
         Criterion - by which criterion we will search: name, date of creation, rights, owner, etc.
         Template - directly the value by which we will select files.
         
         -name - search for files by name
        
20. **Clear the contents of the file `tf_4.txt` without deleting the file**

     `$ echo > inner_dir_1/tf_4.txt`
     
            *we can do it using the other commands, for example: `$ cat /dev/null > inner_dir_1/tf_4.txt`. The pseudo-device /dev/null is a kind of "black              hole" in the system. Everything that is written to this file "disappears" forever.
                                                                 `$ > inner_dir_1/tf_4.txt`;
                                                                 `$ cp /dev/null > inner_dir_1/tf_4.txt`;
                                                                 `$ : > inner_dir_1/tf_4.txt`
                                                                 
21. **Find the path to the files which have "`tf`" in their names**

```

    $ find -name "tf*"
    ./inner_dir_1/tf_3.txt
    ./inner_dir_1/tf_4.txt
    ./inner_dir_1/tf_5.txt
    ./tf_1.txt
    ./tf_2.txt
    
```

22. **Find the path to the files which have "`tf`" in their names in any register**

```

    $ find -iname "tf*"
    ./inner_dir_1/tf_3.txt
    ./inner_dir_1/tf_4.txt
    ./inner_dir_1/tf_5.txt
    ./tf_1.txt
    ./tf_2.txt
    
```

        *the option -i allows the command to ignore register in names.
        
23. **Find lines in files in the current folder where there is a combination of letters `sec`**

```

    $ grep -n sec *.*
    tf_2.txt:2:the second 2
    tf_2.txt:4:the sec 3

```

        *The name of the `grep` command stands for "global search for strings matching a regular expression and printing them". 
        `Grep` gives a lot of possibilities for text filtering. You can select the desired strings from text files, filter the output of commands, and even          search for files in the file system that contain certain strings.
         The syntax of the command is as follows: `$ grep [options] template [/path/to/file/or/folder...]`
         or `$ command | grep [options] template`
         Options are additional parameters that specify various search and output settings, such as the number of rows or the inversion mode.
         A template is any string or regular expression that will be searched for.
         The name of the file or folder is the place where the search will be performed. As you will see later, grep allows you to search in multiple files          and even in a directory using recursive mode.
        

24. **Find lines in files in the current folder where there is a combination of letters `sec` in any register**

```
    $ grep -in sec *.*
    tf_2.txt:2:the second 2
    tf_2.txt:4:the sec 3
    tf_2.txt:5:the seConD 2
    
```

25. **Find lines in files in the current folder where there is the only combination of letters `sec`**

``` 
    $ grep -w sec *.*
    tf_2.txt:the sec 3
    
```

26. **Find lines in files in the current folder where there is the only combination of letters `sec` in any register**

``` 
    $ grep -iw sec *.*
    tf_2.txt:the sec 3
    
```

27. **Find lines in files in the current folder where there is a combination of letters `second`**

```

    $ grep -n second *.*
    tf_2.txt:2:the second 2

```

28. **Find lines in files in the current folder where there is a combination of letters `second` in any register**

```

    $ grep -in second *.*
    tf_2.txt:2:the second 2

```

29. **Find lines in all files where there is a combination of letters `second`**

``` 

    $ grep -r second
    inner_dir_1/tf_3.txt:the second 2
    tf_2.txt:the second 2

```
        *`-r` (or --recursive) option is used to traverse also all sub-directories of /path
        
30. **Find only the path and the name of files where there is a combination of letters `second` in the current folder**

```

    $ grep -l second *.*
    tf_2.txt

```
        *`-l` (or --files-with-matches) option is used to only print filenames of matching files
        
31. **Find all lines in all files where there is no `second`**

```

    $ grep -rv second
    inner_dir_1/tf_3.txt:novell
    inner_dir_1/tf_3.txt:story
    inner_dir_1/tf_3.txt:poem
    inner_dir_1/tf_3.txt:tale
    inner_dir_1/tf_3.txt:myph
    inner_dir_1/tf_3.txt:the sec 2
    inner_dir_1/tf_3.txt:the SeCoNd 2
    inner_dir_1/tf_5.txt:1
    inner_dir_1/tf_5.txt:2
    inner_dir_1/tf_5.txt:3
    inner_dir_1/tf_5.txt:4
    inner_dir_1/tf_5.txt:5
    inner_dir_1/tf_5.txt:6
    inner_dir_1/tf_5.txt:7
    inner_dir_1/tf_5.txt:8
    inner_dir_1/tf_5.txt:9
    inner_dir_1/tf_5.txt:10
    inner_dir_1/tf_5.txt:11
    inner_dir_1/tf_5.txt:12
    inner_dir_1/tf_5.txt:13
    tf_2.txt:the first 1
    tf_2.txt:the third 3
    tf_2.txt:the sec 3
    tf_2.txt:the seConD 2
 

```
        *`-v` (--invert-match) option is used to output only those lines in which the search pattern is not found
               
32. **Find only the names and the path to the files where there is no `second`**

```
    $ grep -rL second
    inner_dir_1/tf_4.txt
    inner_dir_1/tf_5.txt
    tf_1.txt

```
        *`-L` (or -files-without-matches)
      
33. **Print the last 4 lines of any text file**

```

    $ tail -n 4 inner_dir_1/tf_3.txt
    myph
    the second 2
    the sec 2
    the SeCoNd 2
    
```
       
34. **Print the first 4 lines of any text file**

```

    $ head -n 4 tf_2.txt
    the first 1
    the second 2
    the third 3
    the sec 3

```

35. **Сreate a folder and a text file with the contents. Use an one-line command**

    `$ mkdir inner_dir_2 ; touch inner_dir_2/file.txt`
    
            *instead `;` we can use `&&`. This is an operator that is used to join more than one expression, and then outputs a result based on their                    combined result.
            
    
36. **Move to any folder files with the contents of the `sec`. Use an one-line command**

```

    $ grep -rlw sec | xargs mv -t inner_dir_2/
    $ ls inner_dir_2
    file.txt  tf_2.txt  tf_3.txt

```   
    
            *`xargs` reads arguments from input and executes the specified command using input as command arguments. 
            `-t` (--target-directory=DIRECTORY) move all SOURCE arguments into DIRECTORY             

37. **Copy files with the contents of "sec" to any folder. Use an one-line command**

```

    $ mkdir inner_dir_3 && grep -rlw sec | xargs mv -t inner_dir_3/
    $ cd inner_dir_3/
    $ ls
    tf_2.txt  tf_3.txt
    
```

38. **Find all lines with `sec` in all text files, copy and paste the lines into a new file. Use an one-line command**

```

    $ grep sec *.* >> new.txt
    $ cat new.txt
    tf_2.txt:the second 2
    tf_2.txt:the sec 3
    tf_3.txt:the second 2
    tf_3.txt:the sec 2
    
```

39. **Delete files that contain the word `sec`. Use an one-line command**

  `$ grep -rlw sec | xargs rm`
  
40. **Output the line "Good job!" to the terminal**

```
    $ echo Good job!
    Good job!
    
```

    












         




            
       
   

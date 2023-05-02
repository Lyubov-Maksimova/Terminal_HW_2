# Terminal_HW_2

1. **Create a directory `dir_1`** 

    `mkdir dir_1`
   
2. **Go to the folder `dir_1`**

    `cd dir_1`
    
         *the `cd` command (change directory) allows you to change the current folder to another one
  
 3. **Create a directory `inner_dir_1`**
 
    `mkdir inner_dir_1`
     
 4. **See where I am**
 
    `pwd`
    
         *the `pwd` command outputs the path to the current folder
    
 5. **Create an empty text file `tf_1.txt` in a directory `dir_1`**
 
    `touch tf_1.txt`
    
         *the `touch` command allows you to create one or more empty files
    
 6. **Create `tf_2.txt` in a directory `dir_1` using `cat` with strings the first 1, the second 2, the third 3** 
 
   ```
   
    cat > tf_2.txt
    
    the first 1
   
    the second 2
    
    the third 3
    
   ```
       
         *`cat` with the redirection operator `>` allows you to enter any characters that need to be written to the file*
        
7. **Go to the folder `inner_dir_1`**

   `cd inner_dir_1`
  
8. **Create `tf_3.txt` using `cat` with any strings**
```
    cat > tf_3.txt
    
    novell
    
    story
    
    poem
    
    myph
    
    tale
    
```
   
9. **Add a string "the second 2" to the `tf_3.txt` using `cat`**

   ```
   cat > tf_3.txt

   the second 2
   
   ```

10. **Add a string "the sec 2" to the `tf_3.txt` using `cat`**


   ```
   cat > tf_3.txt

   the sec 2
   
   ```
   
11. **Add a string "the sec 3" to the `tf_2.txt` using `cat`**

```
   cd ..
   
   cat > tf_2.txt

   the sec 3
```
       *here we use `cd ..` to go to the parent directory. We can also use `cd -`
      
12. **Add a string "the SeCoNd 2" to the `tf_3.txt` using `cat`**

```
   cd inner_dir_1 
   
   cat > tf_3.txt

   the SeCoNd 2
   
```

13. **Add a string "the seConD 2" to the `tf_2.txt` using `cat`**

```
   cd ..
   
   cat > tf_2.txt

   the seConD 3
   
```

14. **Create `tf_4.txt` with 15 strings inside** 

   `seq 1 15 | cat > tf_4.txt`
   
      * the seq command outputs a sequence of numbers (from 1 to 15)
      
15. **Create `tf_5.txt` with 15 strings inside**

   `seq 1 13 | cat > tf_5.txt`
   
16. **List all files**

   `ls` 
   
      * 
   

# Sed-Command-in-Linux
       
   SED command in UNIX stands for stream editor.

## What is the use of Sed Command?
          
- SED is a powerful text stream editor. Can do insertion, deletion, search and replace(substitution).
- SED command in unix supports regular expression which allows it perform complex pattern matching.
  
### Syntax:
         sed OPTIONS... [SCRIPT] [INPUTFILE...] 
   
#### Examples of Sed command:
- Replace:
    1. Replacing or substituting string  
   
       > sed 's/unix/linux/' file.txt 
 
    2. Replacing the nth occurrence of a pattern in a line :  
       > sed 's/unix/linux/2' file.txt
    3. Replacing the all occurrences of a pattern in a line :
       > sed 's/unix/linux/g' file.txt
    4. Replacing from nth occurrence to all occurrences in a line : 
       > sed 's/unix/linux/3g' file.txt
    5. Replacing string on a specific line number :  
       > sed '3 s/unix/linux/g' file.txt

    6. Replace string on a defined range of lines :    
       > sed '2,5 s/to/TWO/' a.txt
       > sed '2,$ s/to/TWO/' a.txt  
    7. Replace string of case insensitive :
       > sed 's/life/Love/i' a.txt
    8. Replace multiple spaces with a single space:
        > sed 's/  */ /g' filename
         
- Insertion-
          
    1. Insert one blank line after each line –  
        > sed G a.txt 
    2. To insert two blank lines –  
        > sed ‘G;G’ a.txt 
    3. Delete blank lines and insert one blank line after each line –  
        > sed '/^$/d;G' a.txt
    4. Insert a black line above every line which matches “love” –  
        > sed '/love/{x;p;x;}' a.txt

    5. Insert a blank line below every line which matches “love” –  
        > sed '/love/G' a.txt
    6. Insert 5 spaces to the left of every lines –  
        > sed 's/^/     /' a.txt

- printing-
   1. printing 1st line in file:
        > sed -n '1p' a.txt
   2. printing 1 to 5lines in file:
        > sed -n '1,5p' a.txt
   3. printing last line in a file:
        > sed -n '$p' a.txt
    4. printing 1st line and last line of file:
        > sed -n '1p ;$p' a.txt
    5. printing multiple range of lines of file:
        > sed -n '1,5p;10,11p;' a.txt
- Deleting lines-
    1. Delete a particular line 
       > sed '5d' a.txt
    2. Delete the last line 
       > sed ‘$d’ a.txt
    3. Delete line from range 2 to 5
       > sed '3,5d' a.txt
    4. Delete from 2nd to last line 
       > sed '2,$d' a.txt
    5.  Delete the pattern matching line 
        > sed '/life/a' a.txt
    6. Delete lines starting from 3rd line and every 2nd line from there 
        > sed '3~2d' a.txt
    7.  Delete the lines which matches the pattern and 2 lines after to that
        > sed '/every/,+2d' a.txt
    8. Delete blank Lines 
        >  sed '/^$/d' a.txt
    9. Delete empty lines or those begins with “#” 
        > sed '/^#/d ;/^$/d' a.txt
           
       
    












### References-
[sed Manual](https://www.gnu.org/software/sed/manual/sed.html#Invoking-sed)

[sed Tutorial with Examples](https://www.geeksforgeeks.org/sed-command-linux-set-2/)

[How To Use Sed Command ](https://youtu.be/xdUo5aM5UqE)
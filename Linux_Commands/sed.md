# **sed command**

sed stands for stream editor.
sed is used to edit/replace a string in a file.

Syntax:

#### $ **sed 's/<_old_string_>/<_new_string_>/' <_path/file_name_>**

Let's dissect the above command :)

**'s/<_old_string_>/<_new_string_>/'** ====> 5 parts in the command

1. s ==== stands for string
2. / ==== (Note : 3X times in the command) is delimiter, it lets the command know what to be replaced by what
3. <_old_string_> ==== Old string needed to be replaced
4. <_new_string_> ==== New string needed in the file
5. <_path/file_name_> ==== File needs to be updated


Example:
$ cat myFile.txt

Output ->

red, blue, green

green, yellow, black

**If we want to replace green with gold**

$ sed 's/green/gold/' myFile.txt

Output ->

red, blue, gold

gold, yellow, black

**But, wait why the myFile.txt is not updated???**

$ cat myFile.txt

Output ->

red, blue, green

green, yellow, black

**_Hmm, because sed doesn't update the file, it just shows the output after replacement._**

$ sed **-i** 's/green/gold/' myFile.txt

With -i in command updates the file.

### Pro tip :

**What if we want to replace the character / in a file??**

/ -> is not the only delimiter, we can have .(dot) , |(pipe), (space) as a dilimiter

So in case we need to replace / in a file then modify the command as below.

$ sed **'s./tmp./.'** myFile1.txt

--------------------------------------

$ sed 's/green/gold/g' myFile.txt

The g at the end of the command denotes it will replace the word green to gold in the entire file.


**_Happy Learning!!_**
# **find command**

find is used find things on linux.

Syntax:

**$ find <_path to be searched in_> -name <_some expression_>**

Example :

$ find /var/log -name *.log

//Output: all the file/directories in /var/log with name ending with .log

$ find /var/log -type f -name *.log

//Output: all the file in /var/log with name ending with .log

$ find /var/log -type d -name *.log

//Output: all the directories in /var/log with name ending with .log

$ find /var/log -type f -name *.log -exec truncate -s 0 {}+

//Output: all the files in /var/log with name ending with .log will be truncated or sized to 0

exec command is used to execute some command on the output of find command

{} acts as a loop; it makes sure the exec block is executed on each and every item from find

"+" denotes the end of exec command. We can use "\;" instead of "+"

$ find /var/log -type f -name *.log -exec cp --parent {} /backup \;

This command finds all the files with .log extension present in /var/log directory and -exec copies the files along with the directory structure to /backup directory.


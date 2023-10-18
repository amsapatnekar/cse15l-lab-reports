# Lab Report 1
## cd
1. **cd** without any argument provided no output as **cd** changes the current directory to the one specified with the argument. As no argument is provided, it takes you one step back to the previous directory, which is home in this case.    
![image](cdNoArg.png)   
  2. **cd** with a directory as an argument changes the directory the terminal is in, allowing you to use files within that directory.
  ![image](cdDirectory.png)   
  3. **cd** with a file as an argument provides an error message, as 'cd' only works with directories.
![image](cdFile.png)
## ls
1. **ls** without an argument provides a list of the files and the messages folder within the lecture1 directory.
![image](lsNoArg.png)   
2. **ls** with a directory as an argument creates an error message, as this command is not meant to use a directory in that way. 
![image](lsDirectory.png)   
3. **ls** using a file as an argument provides the file's name.
![image](lsFile.png)
## cat
1. **cat** without an argument runs while waiting for a keyboard input. Control + c is used to return to the terminal.
![image](catNoArg.png)    
2. **cat** with lecture1 as an argument provides an error message. This error message is caused as 'lecture1' is not a plain text readable file. 
![image](catDirectory.png) 
3. **cat** with a file name outputs the code within that file. 
![image](catFile.png)
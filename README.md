# linux-basic-commands

 To Elevate Permissions : `sudo -s` for root user - you will go to Home directory /home
                         
                        
                        `Sudo -i`                                              

To check the directory : `pwd` (present working directory)

To change the directory : `cd`

To exit the permissions : `exit`, `cmd d`

To view content of the file : `cat`     example - `cat /etc/os-release`


To list the files : `ls`


Displays files and directories with detailed information : `ls -al`

Shows all files and directories, including hidden : `ls -a`

Displays file sizes in a human-readable format : `ls -ah`

Displays files : `ls -lt`

Reverse sorting : `ls -ltr`

-l : Long format listing.
-a : Include hidden files hidden ones
-h : Human-readable file sizes.


To create a new directory : `mkdir`

To remove the directory : `rmdir` (to delete empty directory)

To remove directory forcefully : `rm -rf` (DO NOT USE UNTIL NECESSARY)


To create new file : `touch`

To go back one directory : `cd ..`


To copy the file : `cp`

To copy the files from one directory to another directory : `cp directory1/* directory2/`
                                                          : `cp -r directory1/ directory2/`


To rename the file/directory : `mv directory1 directory2`

To move the file : `mv index.html directory2/`

To edit the file : `vi filename`
    
    – To edit the content the file : `i` ()
    
    – To exit press `esc`
    
    – To save the content the file : `:wq`
    
    – To save the content of the file and exit forcefully : `:wq!`


To view the file : `cat filename`

To sort the file : `sort filename`

To display the first few lines of the file : `head filename` (it will display first 10 lines)
                       Last few lines      : `tail filename` (it will display last 10 lines)
 

To display specific number of lines : `head -n 5 filename`, `tail -n 5 filename` (5 represents 5 lines)

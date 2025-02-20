# linux-basic-commands

 To Elevate Permissions : `sudo -s` for root user - you will go to Home directory /home
                         
  `Sudo -i`  /root                                       

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

## Creating a directory or removing it

To create a new directory : `mkdir`

To remove the directory : `rmdir` (to delete empty directory)

To remove directory forcefully : `rm -rf` (DO NOT USE UNTIL NECESSARY)

## Creating a file or files


To create new file : `touch`

To go back one directory : `cd ..`


To copy the file : `cp`

To copy the files from one directory to another directory : `cp directory1/* directory2/`
                                                          
                                                          : `cp -r directory1/ directory2/`


To rename the file/directory : `mv directory1 directory2`

To move the file : `mv index.html directory2/`

To edit the file : `vi filename`
to edit with `cat` command : `cat > filename`

To create and edit the file at same time : `cat > filename` (it will overwrite)

To append the content of the file : `cat >> filename`
    
    – To edit the content the file : `i` ()
    
    – To exit press `esc`
    
    – To save the content the file : `:wq`
    
    – To save the content of the file and exit forcefully : `:wq!`


To view the file : `cat filename`

To sort the file : `sort filename`

To display the first few lines of the file : `head filename` (it will display first 10 lines)
                      
Last few lines     : `tail filename` (it will display last 10 lines)
 

To display specific number of lines : `head -n 5 filename`, `tail -n 5 filename` (5 represents 5 lines)

To compare the data between 2 files : `cmp file1 file2`

to see the difference between 2 files data : `diff file1 file2`

And to see the difference in detail : `diff -u file1 file2`

## Searching the files

To find the file : `find /path -name filename/*`

To show the number of lines in file : `cat -n filename`

To find a particular word in files : `grep word filename`

for case sensitive purpose : `grep -i word filename`

To record the session : `script`

## Zip and Unzip

To zip the file : `gzip -k filename` (zips the file and also keeps the original file)

To unzip the file : `gunzip filename`

To zip the directory : `tar -czf directory.tar.gz directory/`

to unzip the directory : `tar -xzf directory.tar.gz`







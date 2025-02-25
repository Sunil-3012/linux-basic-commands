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

============================
## Creating a directory or removing it

To create a new directory : `mkdir`

To remove the directory : `rmdir` (to delete empty directory)

To remove directory forcefully : `rm -rf` (DO NOT USE UNTIL NECESSARY)

============================
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

============================
## Searching the files

To find the file : `find /path -name filename/*`

To show the number of lines in file : `cat -n filename`

To find a particular word in files : `grep word filename`

for case sensitive purpose : `grep -i word filename`

To record the session : `script`

============================
## Zip and Unzip

To zip the file : `gzip -k filename` (zips the file and also keeps the original file)

To unzip the file : `gunzip filename`

To zip the directory : `tar -czf directory.tar.gz directory/`

to unzip the directory : `tar -xzf directory.tar.gz`

## To download the file : 
`wget link`

============================
## To edit the data within the file

To replace the data within the file : `sed -i 's/word1/word2/' filename` (S stands for string)  -- (sed stands for stream editor)

To replace multiple words at the same time : `sed -i 's/word1/word2/g; s/word3/word4/g' filename`

To replace a line : `sed -i '4c goodbye' filename `  

to add a line : `sed -i '4i goodbye' filename`  

To delete a line : `sed -i '4d' filename `    (in this case the 4th line)  

============================
## Installation

to install any package/service : `yum install -y packagename` example : `yum install -y nginx`

To Start, status, restart and stop : 
`systemctl status nginx
systemctl start nginx
systemctl status nginx
systemctl restart nginx`

To list all services in Linux : `systemctl list-units --type=service --all`

To find a package/service in linux : `systemctl list-units --type=service --all | grep word`

To Show all running processes with detailed information : `ps aux`

============================
## System Information commands

To Displays all system information. : `uname -a`        

To Show the current username : `whoami `            

Displays disk space usage in a human-readable format : `df -h`             

Provides the total size of the specified directory : `du -sh directory/`     

Displays memory usage in a human-readable format : `free -h`         

Shows the current system uptime : `uptime`             

Provides detailed CPU information : `lscpu`             

Show operating system information such as distribution name and version : `cat /etc/os-release`  

============================
## Networking Commands


Shows the details of all network interfaces : `ifconfig`         

If not getting executed run this command : `yum install net-tools`



Downloads “file.txt” from the specified URL : `wget http://example.com/file.txt` 

if you want to download and have with your desired name : `wget -o yourownnamefile.txt URL_of_file`  

Retrieves the content of a webpage from the specified URL : `curl http://example.com`        

Calling API's using CURL command : `curl http://numbersapi.com/random`


## To check if the port is open or not

`telnet IP port
netstat -putan | grep 80 -- see if port 80 is opened or not`

==============================
## Environment Variable Commands

Environment variables in Linux are dynamic values that can impact how programs and processes run on a computer

`printenv`

Sets the value of an environment variable : export VARIABLE_NAME=value             
Example: `export name=sunil`    here variable is 'name' and value is 'sunil'  

Displays the value of a specific environment variable : `echo $VARIABLE_NAME`            
Ex: `echo $name`

To Unset or removes an environment variable : `unset VARIABLE_NAME`           
Ex: `unset name`

================================
## To Add users/Groups or delete 

to add a user : `useradd`

set passwrod : `passwd username`

To list the users : `cat/etc/passwd`

To switch user : `su - username`

To add a user via another user go to `visudo` and then go to line number 100, :100 --> copy - yy, paste - p
`root    ALL=(ALL)       ALL
username    ALL=(ALL)       ALL
`
Now you can add user via another user `sudo useradd username2`

To delete user `userdel username`

To add/create the group : `groupadd username`

==================================

## Transferring files from one linux machine to another linux machine

To transfer files from one linux machine to another linux machine we use SCP(Secure Copy protocol)

`scp -i key-pair-name.pem /path/my-file.txt ec2-user@privateip:/path/`

Example : `scp -i MyKey.pem test.zip ec2-user@172.31.6.82:/home/ec2-user/`

for directory recursive : `scp -r -i MyKey.pem test/ ec2-user@172.31.6.82:/home/ec2-user/`

=====================================
## Example of reverse proxy using nginx and Apache(httpd)

Set up a linux machine with a web server ex:Apache

`sudo -s`

`yum install -y httpd`

`cd /var/www/html`

`vi index.html`

 Add a random html code

launch another ec2 instance with nginx server

`sudo -s`

`yum istall -y nginx`

`cd /etc/nginx/`

`vi nginx.conf`
 

add the following code

`location/{
    proxy_pass http:// Private Ip of the Apache server:/80;
    }`


`systemctl restart nginx`

Open the Public Ip of the nginx serevr

If you get error

`getsebool -a | grep httpd`

`setsebool httpd_can_network_connect on -P`

============================================













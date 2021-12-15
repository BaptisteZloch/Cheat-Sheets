# Linux cheat sheet

## Usefull commands
- Change directory : `cd <directory>` .. mean the parent directory
- List all files and directory in a folder : `ls` or `ls -a` to see everything in the folder
- Show the content of a file : `cat <filename>`
- Show the 100 first lines of a file : `head --lines=100 <filename>`
- Show the 100 lasy lines of a file : `tail --lines=100 <filename>`
- To create an empty file : `sudo touch <filename>`
- Rename file : `mv <oldfilename> <newfilename>`(it also works for folder)
- To write something in a file : `echo "something" > <filename>` if you want to make \n understandable `echo "something \nsomthing else" > <filename>`
- To edit a file : `sudo vi <filename>` or `sudo nano <filename>`
- How to restart apache : `/etc/init.d/apache2 restart`
- Copy file from VPS to local windows : `scp <user>@<ip_adress>:/home/<user>/<filename> /<folder>` **To run on a cmd terminal**

## Usefull folders
- Apache .conf files in `/etc/apache2/sites-enabled`
- Where project has to be stored : `/var/www/` after installing apache


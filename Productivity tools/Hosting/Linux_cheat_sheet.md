# Linux cheat sheet

## Navigation commands
- Change directory : `cd <directory>` .. mean the parent directory
- List all files and directory in a folder : `ls` or `ls -a` to see everything in the folder
- To get current location : `pwd`


## File commands
### Showing
- Show the content of a file : `cat <filename>`
- Show the 100 first lines of a file : `head --lines=100 <filename>`
- Show the 100 lasy lines of a file : `tail --lines=100 <filename>`
### Editing
- To create an empty file : `sudo touch <filename>`
- To rename file : `mv <oldfilename> <newfilename>`(it also works for folder)
- To copy a file into another : `cp <filename> <destination_filename>` or to copy into a folder `cp <filename> <destination_folder>`
- To write something in a file : `echo "something" > <filename>` if you want to make \n understandable `echo "something \nsomthing else" > <filename>`
- To edit a file : `sudo vi <filename>` or `sudo nano <filename>`
- To replace something in a file : `sed -i -e "s/something/something else/g" <filename>`

## Process, IO & Network commands
- To see ports and running : `netstat -an | grep LISTEN`
- To see current process : `ps -edf` to locate one process `ps -edf | grep <process_name>`
- To see other current process : `ps -aux` to locate one process `ps -aux | grep <process_name>`
- To see current process : `top` Q (to quit)
- `vmstat`
- To check partition and IO consumption : `iostats -p`
- To list top usage of IO : `iotop`
- To list current processus and branches : `pstree pach` in order to identify hierarchy
- To list deamonized jobs : `jobs`

## User commands
- To create a user : `sudo adduser <username>`
- To add user to sudo : `sudo adduser <username> sudo`


## Rights commands
- `chown`
- To give apache the rights to write files : `sudo chown -R www-data:www-data /var/www`
- `chmod`


## Apache commands
- How to restart apache : `/etc/init.d/apache2 restart`


## Usefull folders
- Apache .conf files in `/etc/apache2/sites-enabled`
- Where project has to be stored : `/var/www/` after installing apache


## Others
- Copy file from VPS to local windows : `scp <user>@<ip_adress>:/home/<user>/<filename> /<folder>` **To run on a cmd terminal**

## Help on commands
- `apropos <command_name>`
- `whatis <command_name>`
- `man <command_name>`
- To locate where a command come from : `where <command_name>`
- To see if a command is shell or alias : `type <command_name>`

## Links
- Hardlink = same data area : `ln <file_one> <file_two>`
- Softlink = like a pointer to the original data, like a shortcut : `ln -s <original_file> <shortcut_file>`

# Linux cheat sheet

## Usefull commands
- Change directory : `cd <directory>` .. mean the parent directory
- List all files and directory in a folder : `ls`
- Show the content of a file : `cat <filename>`
- Show the 100 first lines of a file : `head --lines=100 <filename>`
- Show the 100 lasy lines of a file : `tail --lines=100 <filename>`
- How to restart apache : `/etc/init.d/apache2 restart`
- Copy file from VPS to local windows : `scp <user>@<ip_adress>:/home/<user>/<filename> /<folder>` **To run on a cmd terminal**
- To create an empty file : `sudo touch <filename>`
- To edit a file : `sudo vi <filename>` or `sudo nano <filename>`


## Usefull folders
- Apache .conf files in `/etc/apache2/sites-enabled`
- Where project has to be stored : `/var/www/` after installing apache

## MySQL commands
- Launch mysql : `sudo mysql -p`
- Change password : `SET PASSWORD FOR 'root'@'localhost' = PASSWORD('password');`
- List all databases : `mysql> SHOW DATABASES;`
- Start working with one database : `mysql> USE <database>;`
- List all table from database : `mysql> SHOW TABLES;`
- Add an SQL query in a database : `mysql> nom_base_de_donnees < fichier.sql`
- Export an sql database : `sudo mysqldump -u root -p <database> > /home/<user>/<filename>.sql` or `sudo mysql -u root -p <database>  > /home/<user>/<filename>.sql` 
- Export an sql table : `sudo mysqldump -u root -p <database> <table> > <table>.sql`
- To disable key verification : `mysql> SET FOREIGN_KEY_CHECKS=0;` **Don't forget to reactivate it after importing data**
- To start/restart mysql service : `systemctl restart mysql.service` or `/etc/init.d/mysql restart`
- To stop mysql service : `systemctl stop mysql.service` or `/etc/init.d/mysql stop`
- To check mysql status : `systemctl status mysql.service`

# Linux cheat sheet

## Usefull commands
- Change directory : `cd <directory>` .. mean the parent directory
- List all files and directory in a folder : `ls`
- Show the content of a file : `cat <filename>`
- How to restart apache : `/etc/init.d/apache2 restart`


## Usefull folders
- Apache .conf files in `/etc/apache2/sites-enabled`
- Where project has to be stored : `/var/www/` after installing apache

## MySQL commands
- launch mysql : `sudo mysql -p`
- List all databases : `mysql> SHOW DATABASES;`
- Start working with one database : `mysql> USE <database>;`
- List all table from dtaabase : `mysql> SHOW TABLES;`
- Add an SQL query in a database : `mysql> nom_base_de_donnees < fichier.sql`
- Export an sql database : `sudo mysqldump -p <database> > /home/<user>/<filename>.sql`

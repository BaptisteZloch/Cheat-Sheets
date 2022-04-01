# MySQL CLI Cheat sheet 

## Terminal commands
- Launch mysql : `sudo mysql -u root -p`
- Export an sql database : `sudo mysqldump -u root -p <database> > /home/<user>/<filename>.sql` or `sudo mysql -u root -p <database>  > /home/<user>/<filename>.sql` 
- Export an sql table : `sudo mysqldump -u root -p <database> <table> > <table>.sql`
- Add an SQL query in a database : `mysql -u root -p nom_base_de_donnees < fichier.sql`
- To start/restart mysql service : `systemctl restart mysql.service` or `/etc/init.d/mysql restart`
- To stop mysql service : `systemctl stop mysql.service` or `/etc/init.d/mysql stop`
- To check mysql status : `systemctl status mysql.service`


## MySQL commands

- Change password : `mysql> SET PASSWORD FOR 'root'@'localhost' = PASSWORD('password');`
- List all databases : `mysql> SHOW DATABASES;`
- Start working with one database : `mysql> USE <database>;`
- List all table from database : `mysql> SHOW TABLES;`
- To disable key verification : `mysql> SET FOREIGN_KEY_CHECKS=0;` **Don't forget to reactivate it after importing data**

## Users
```sql
CREATE USER '<user_name>'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO '<user_name>'@'localhost';
FLUSH PRIVILEGES;
```



# Before starting
```sh
 sudo apt-get update && sudo apt-get upgrade
```
# Installing git
 ```sh
 sudo apt install git
 git --version
```
# Installing Apache2
 ```sh
 sudo apt install nginx
 sudo systemctl status nginx #to check status
```
# Installing mysql
```bash
 sudo apt install mariadb-server
 sudo mysql_secure_installation #to add root auth
```
Best practices are : When running the last command you sould select n for No on every choice except for reload privileges.
Then you should create another user that can connect from anywhere else using ssh and db auth. To do it :
```sh
 sudo mysql
```
Then you are using mysql so you can run SQL commands, then run 
```sql
GRANT ALL ON *.* TO 'sadmin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT; 
```
You can check the mysql deamon status running or not by using this command :
```sh
 sudo systemctl status mariadb
```

# Installing pip and venv
```sh
 # sudo apt-get install python3.7 # normaly python3.7 is already installed
 sudo apt install -y python3-pip python3-venv tree
```

Then you are ready to clone you git repository, activate the venv and deploy your site.

To deploy it you should should create a conf file in `/etc/nginx/sites-available` named with the same name as your project name. After it create a link with the file in  `/etc/nginx/sites-enabled` by running `sudo ln -s /etc/nginx/sites-available/<project_name> /etc/nginx/sites-enabled`.

The config file should look like this :
```cnf
server {
    listen 80;
    server_name www.domain.com;
      
    location /static {
        autoindex on;
        alias /home/admin/var/www/<project_name>/static/;
    }
    location /media {
        autoindex on;
        alias /home/admin/var/www/<project_name>/media/;
    }

    location / {
        include proxy_params;
        proxy_pass http://localhost:8000/;
    }
}
```
To finish run this command at the root of you project `sudo gunicorn <project_name>.wsgi --bind 0.0.0.0:8000 --workers 4 &
` to run the project with localhost:8000. The `&`at the end means we deamonize this process.



# Turning your site to HTTPS
```sh
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx # then select the conf file you want to turn into https.
```

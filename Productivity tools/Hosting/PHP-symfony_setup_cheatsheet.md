
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
 sudo apt install apache2
 sudo systemctl status apache2 #to check status
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
 # Installing PHP
 ```sh
 sudo apt install -y curl wget gnupg2 ca-certificates lsb-release apt-transport-https
 wget https://packages.sury.org/php/apt.gpg
 sudo wget https://packages.sury.org/php/apt.gpg
 sudo apt-key add apt.gpg
 echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php7.list
 sudo apt-get update
 sudo apt install -y php7.4 php7.4-cli php7.4-common php7.4-curl php7.4-xml php7.4-mbstring php7.4-mysql php7.4-gd
 php --version
```
# Installing composer
 ```sh
 sudo apt install unzip curl
 sudo apt-get update
 cd ~
 curl -sS https://getcomposer.org/installer -o composer-setup.php
 sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
 composer
 ```

# Installing Symfony
 ```sh
 wget https://get.symfony.com/cli/installer -O - | bash
 export PATH="$HOME/.symfony/bin:$PATH"

  ```
  
Then you are ready to clone your git repository and deploy your site.

**Here is an example of apache config with a DNS**
```xml
<VirtualHost *:80>
    ServerName domain.com
    ServerAlias www.domain.com

    DocumentRoot /var/www/<project>/public
    DirectoryIndex /index.php

    <Directory /var/www/<project>/public>
        AllowOverride None
        Order Allow,Deny
        Allow from All

        FallbackResource /index.php
    </Directory>

    <Directory /var/www/<project>/public/bundles>
        DirectoryIndex disabled
        FallbackResource disabled
    </Directory>
    ErrorLog /var/log/apache2/custom_error.log
    CustomLog /var/log/apache2/custom_access.log combined
RewriteEngine on
RewriteCond %{SERVER_NAME} =domain.com [OR]
RewriteCond %{SERVER_NAME} =www.domain.com
RewriteRule ^ https://%{SERVER_NAME}%{REQUEST_URI} [END,NE,R=permanent]
</VirtualHost>
```

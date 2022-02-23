```sh
 ls
 cd /
 ls
#Installing git
 sudo apt-get update
 sudo apt install git
 git --version
 sudo apt-get update
#Installing Apache2
 sudo apt install apache2
 sudo apt-get update
#Installing mysql
 sudo apt install mariadb-server
 sudo mysql_secure_installation #to add root auth
 sudo systemctl status mariadb #to check status
 sudo apt-get install libmariadbclient-dev -y #to use with python/django
 #GRANT ALL ON *.* TO 'sadmin'@'localhost' IDENTIFIED BY 'idj9273dKJDDHJI9339jd!!65HSdh' WITH GRANT OPTION;
 sudo apt-get update
 #Installing Python3 & pip & venv
 sudo apt-get install python3.7
 sudo apt install -y python3-pip python3-venv tree
 #Installing PHP
 sudo apt install -y curl wget gnupg2 ca-certificates lsb-release apt-transport-https
 wget https://packages.sury.org/php/apt.gpg
 sudo wget https://packages.sury.org/php/apt.gpg
 sudo apt-key add apt.gpg
 echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php7.list
 sudo apt-get update
 sudo apt install -y php7.4 php7.4-cli php7.4-common php7.4-curl php7.4-xml php7.4-mbstring php7.4-mysql php7.4-gd
 php --version
 sudo apt-get update
#Installing composer
 sudo apt install unzip curl
 sudo apt-get update
 cd ~
 curl -sS https://getcomposer.org/installer -o composer-setup.php
 sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
 composer
 sudo systemctl status mariadb
 sudo systemctl status apache2
 #Installing Symfony
 wget https://get.symfony.com/cli/installer -O - | bash
 
 #Installation terminated
 ls
 cd /
 ls
 cd var/www
 ls
 ls html
 git clone https://gitlab.com/EPFProjets-SI/intranet_refonte.git
 sudo git clone https://gitlab.com/EPFProjets-SI/intranet_refonte.git
 ls
 cd intranet_refonte
 ls
 sudo apt-get update
 sudo composer update
 sudo composer install
 
 
 #
 server {
    listen 80;
    listen [::]:80;
    server_name www.zlochteam.com;
      
    location /static {
        autoindex on;
        alias /home/admin/var/www/ZlochTeam/static/;
    }
    location /media {
        autoindex on;
        alias /home/admin/var/www/ZlochTeam/media/;
    }

    location / {
        include proxy_params;
        proxy_pass http://localhost:8000/;
    }
}
# sudo ln -s /etc/nginx/sites-available/ZlochTeam /etc/nginx/sites-enabled

 #Certbot install for HTTPS WITH
 sudo apt install snapd
 sudo snap install core
 sudo snap install core; sudo snap refresh core
 sudo snap install --classic certbot
 sudo ln -s /snap/bin/certbot /usr/bin/certbot
 #To add HTTPS to a website on Nginx
 sudo certbot --nginx
 #To add HTTPS to a website on apache
 sudo certbot --apache
```

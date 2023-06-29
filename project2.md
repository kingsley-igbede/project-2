## Kingsley Documentation Of Project 2

### Installing Nginx

`sudo apt update`

![update server](.\images\server-update.PNG)

`sudo apt install nginx`

`sudo systemctl status nginx`

![nginx install/status](.\images\install-nginx.PNG)

`curl http://localhost:80`

![access nginx local](.\images\access-nginx-local.PNG)

[accessing nginx](http://http://13.53.187.128/:80)

![accessing nginx2](.\images\access-nginx-browser.PNG)


### Installing MySql

`sudo apt install mysql-server`

`sudo mysql`

![mysql status](.\images\mysql-status.PNG)


### Securing MySql

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

`mysql> exit`

`sudo mysql_secure_installation`

`sudo mysql -p`

`mysql> exit`

![securing](.\images\securing-mysql.PNG)


### Installing PHP

`sudo apt install php-fpm php-mysql`

![installing PHP](.\images\installing-php.PNG)


### Configuring NGINX to use PHP Processor

`sudo mkdir /var/www/projectLEMP`

`sudo chown -R $USER:$USER /var/www/projectLEMP`

`sudo nano /etc/nginx/sites-available/projectLEMP`

`#/etc/nginx/sites-available/projectLEMP

server {
    listen 80;
    server_name projectLEMP www.projectLEMP;
    root /var/www/projectLEMP;

    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
     }

    location ~ /\.ht {
        deny all;
    }

}`

`sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`

`sudo nginx -t`

![nginx syntax errors](.\images\nginx-syntax-errors-test.PNG)

`sudo unlink /etc/nginx/sites-enabled/default`

`sudo systemctl reload nginx`

`sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`

	[nginx site using IP](http://13.48.44.19.com)

![nginx site using IP](.\images\nginx-site-ip.PNG)


### Testing PHP with NGINX

`sudo nano /var/www/projectLEMP/info.php`

`<?php
phpinfo();`

[test PHP with NGINX](http://http://13.48.44.19/info.php)

![test PHP with NGINX](.\images\php-nginx-test.PNG)














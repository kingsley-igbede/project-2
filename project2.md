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









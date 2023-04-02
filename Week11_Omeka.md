# Week 11 Install and Setup Omeka

## Instructions 

## General Steps
1. Update and Upgrade
2. Install Image Magick
3. Enable Apache Mod_Rewrite
4. Create New MySql Database and User
5. Install wget
6. Configure Login Creditentials
7. Run chown command
8. Restart Apache2 and MySql
9. Finish Install in Omeka Web Browser

## Update and Upgrade
```
sudo apt update
sudo apt upgrade -y
```

## Install and Image Magick
Change Directories
```
cd /var/www/html
```

Install ImageMagick
```
sudo apt install imagemagick
```

## Enable Apache mod_rewrite
```
sudo a2enmod rewrite
sudo systemctl restart apache2
```

## Create New MySql Database and User
Switch to root users
```
sudo su
mysql -u root
```
Create User, Password, and Database
```
create user 'omeka'@'localhost' identified by 'password';
create database omeka;
grant all privileges on omeka.* to 'omeka'@'localhost';
show databases;
\q
```

## Install weget
Change Directories
```
cd /var/www/html
```
Download wget file
```
sudo wget https://github.com/omeka/Omeka/releases/download/v3.1/omeka-3.1.zip
sudo apt install unzip
unzip omeka-3.1.zip
sudo mv omeka-3.1.zip omeka
```

## Configure Login Credentials
```
cd /var/www/html/omeka
ls
nano db.ini
```
Change - 
 - database
 - user 
 - password
 - host 

## Run Chown Command

```
sudo chown -R www-data:www-data *
```

## Restart Apache2 and Mysql
```
sudo systemctl restart apache2
sudo systemctl restart mysql
```

## Finish Omeka Install in Browser
Wrote down password information on paper


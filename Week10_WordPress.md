# Week 10 - Install WordPress

Log Into WordPress - http://34.71.188.17/blog/wp-admin/

## Update and Upgrade
```
sudo apt update
sudo apt upgrade - y
```

## Step 1: Requirements for WordPress
```
php -version
mysql --version
```
WordPress Requires php 7.4 and MySql 8.0 as of 03/2023

Install Additional PHP modults

```
sudo apt install php-curl php-xml php-imagick php-mbstring php-zip php-intl
```

Restart Apache2 and MySql 
```
sudo systemctl restart apache2
sudo systemctl restart mysql
```


## Step 2: Download
Change Directory
```
cd /var/www/html
```

Download the Latest Version of WordPress using the wget program. Wordpress is installed in a zipped like file which we extract using the tar command. 
```
sudo wget https://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
```

This installation created a new directory
/var/www/html/wordpress

Checked the location of this directory using the ls command

## Step 3: Create a Database and User

1. Switch to root Linux user
```
sudo su
```

2. Log In As MySQL Root User
```
mysql -u root
```

Now we are in the MySQL Command Prompt. 

1. Create a New User 'localuser'
2. Create a Password by replacing the Xs. Noted on paper
3. Create a New Database for WordPress. 'wordpress'
4. Grant all priviledges to the new user of the database
5. Examine the output
6. Exit MySql Prompt

```
create user 'wordpress'@'localuser' identified by 'XXXXXXXXX';
create database wordpress;
grant all privileges on wordpress.* to 'wordpress'@'localuser';
show databases;
\q
```

## Step 4: Set Up wp-config.php
Follow these general steps:

1. Change to the wordpress directory, if you haven't already.
2. Copy and rename the wp-config-sample.php file to wp-config.php.
3. Edit the file and add your WordPress database name, user name, and password in the fields for DB_NAME, DB_USER, and DB_PASSWORD.

```
cd /var/www/html/wordpress
sudo cp wp-config-sample.php wp-config.php
sudo nano wp-config.php
```

## Step 5
http://34.71.188.17/blog/


Home Directory has User Name, Password, Title and URL in wordpress.md

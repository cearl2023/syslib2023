#Week7 Install and Setup a Lamp Stack

## LAMP
LAMP stands for  Linux, Apache, MySQL, PHP stack. 

## Module is broken down into 5 parts 
1. Installing the Apache Web Server
2. Installing and Configuring PHP
3. Installing and Configuring MySql
4. Creating a Bare Bones OPAC
5. Creating a Bare Bones Cataloging Module

- Note: Parts 4 and 5 are week 8 and 9 modules.

## Installing the Apache Web Server
Apache is a HHTP Server. Read Apache's Getting Started page for further understanding. 

- Update System
  - sudo apt update
  - sudo apt -y upgrade

- Search 
  - sudo apt search apache2 | head

- Show apache
  - apt show apache2

- Install apache
  - sudo apt install apache2

- Show Apache2 is Running
  - systemctl list-unit-files apache2.service
  = systemctl status apache2

### Creating a Webpage

- Install w3m
  - sudo apt install w3m
  - w3m localhost (to show default site)

- Create a new webpage
  - cd /var/www/html/ 
  - sudo mv index.html index.html.original  (renamed and moved file to new name to save as backup)
  - sudo nano index.html (created the new page)

- Note: These pages can use HTML.

## Installing and Configuring PHP

PHP is a server side programming language. It has to be installed on server in order to be used. (Opposite is JavaScript). 

- Install PHP
  - sudo apt install php libapache2-mod-php
  - sudo systemctl restart apache2 (checks system and restarts)
  - systemctl status apache2 (checks for errors in system)

- Check Install of PHP
  - cd /var/www/html/
  - sudo nano info.php (created php page)
    - Add code to info. php
    - <?php
    - php.info();
    - ?>

- Check status of File by going to - http://000.00.0001/info.php (replace numbers with external IP address for VM)

- Configuring Directory (.html to .php URL)
  - Configure Directory
    - cd /etc/apache2/mods-enabled/ 
    - sudo cp dir.conf dir.conf.bak
    - sudo nano dir.conf

- Change Directory Line
  - DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm

- Check Configuration
  - apachectl configtest

- If Apache2 configuring is Syntax OK
  - sudo systemctl reload apache2
  - sudo systemctl restart apache2

## Create A index.php File
- cd /var/www/html/ 
- sudo nano index.php
- Save and exit nano

Check using external IP and /index.php






## Installing and Configuring MySql

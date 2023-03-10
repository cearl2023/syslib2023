# Week 9 - Create a Bare Bones Cataloging Module, Part 2

## This week's objectives are:
1. Create an index.html file in a new cataloging directory in /var/www/html
2. Create an insert.php file in the new cataloging directory
3. Secure your cataloging directory with the htpasswd command
4. Add some additional records using the new web form
5. Use your OPAC to retrieve the new records

## Create an index.html file

Change Directories and Make New Directory cataloging
- cd /var/www/html
- sudo mkdir cataloging 

Add to cataloging a index.html file
- cd cataloging
- sudo nano index.html

Index.html mirrored our OPACdb set up with Author, Book Title, Publisher and Copyright

## Creat an insert.php file
PHP script is needed to communicate between index.html file and our Opacdb MySql database books

Create insert.php
- sudo nano insert.php (copy code, edit two url links to my own external ip address)

## Secure catloging system
Use htpasswd in Apache2 server to secure Opacdb integrity (others can't add records without username and password). 

Change Directories
- cd /etc/apache2 (this is where Apache2 stores configuration files)

Create htpasswd
- sudo htpasswd -c /etc/apache2/.htpasswd libcat 
enter password once
reenter password 

Change Apache2 web server to know we will use htpasswd 
- sudo nano /etc/apache2/apache2.conf 
- change from none to all in specific code
  - <Directory /var/www/> 
  - Options Indexes FollowSymLinks 
  - AllowOverride None Require all granted
  - </Directory>

Change directory to cataloging to create .htaccess
- cd /var/html/cataloging
- sudo nano .htaccess
- add to .htaccess
  - AuthType Basic 
  - AuthName "Authorization Required" 
  - AuthUserFile /etc/apache2/.htpasswd 
  - Require valid-user

Check Configuration and restart Apache 2
- apachetl configtest
- sudo systemctl restart apache2
- systemctl status apache2



# Hosting Requirements

## Ubuntu
Install Ubuntu on AWS Console
### Typical EC2 setup
+ data mounts
+ application mounts

## Apache 2
refresh all default packages on Ubuntu
```
sudo apt-get update
```

installation of apache2. when asked for a prompt enter Y
```
sudo apt-get install apache2
```

Run the following command and observe that you dont get a warning.
```
sudo apache2ctl configtest
```

Check if Apache is running by executing the following commans
```
service apache2 status
```

You can also check via Web Browser that Apache is running. This assumes that you are running
on port 80 and the IP Address and Port are both available from the browser.
```
http://IP_ADDRESS/
```

### Apache Configurations

#### mod_rewrite ON
#### mod_Security (strict configurations) off


## PHP 5.5 and 5.6
### cURL on
### register_globals off
### safe_mode off
### suhoshin (strict configurations off)

### PHP
The following comman will install several PHP and some critical PHP libraries as part
of the LAMP stack.
```
sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql
```

Next we need to tell Apache to prioritize PHP files over HTML. this is achieved by making
a change to apache's configuration. Replace the contents of the file in following location
```
sudo nano /etc/apache2/mods-enabled/dir.conf
```
[sample dir.conf](supporting_files/info.php)

To test that PHP is configured on Apache, you need to create a PHP file as follows.
/var/www/html is the default docroot where all files will be deployed.
** this location when setting up AWS should be on a different mount **
```
sudo nano /var/www/html/info.php
```
[info.php](supporting_files/info.php)

#### PDO
#### DOM
#### mbstring
#### zip
#### ziplib
#### ftp
#### json


## MySQL 5.6
Run
The following command will start the downlaod and installation of MySQL (latest version).
When asked for a Root password, please provide one.
```
sudo apt-get install mysql-server
```

Check that MySQL has been installed and running
```
service mysql status
```

Secure the MySQL installation with following command. This will ask a series of questions,
the answers to which are judgemental and you should pick during installation.
```
sudo mysql_secure_installation
```

## GD Library 2 with FreeType support
## Mail Server (sendMail or Exim)
## Cron

## Other Utilities
These are utilities that you will need over the course of project to manage the server,
so better we install it now. Based on the AWS image, some of these may already be available.

CURL
```
sudo apt-get install curl
```

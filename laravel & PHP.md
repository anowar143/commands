# Install Laravel & PHP in Ubuntu
```
sudo apt update

sudo apt install apache2


systemctl status apache2
```
### Type in browser
```
http://localhost/ or localhost
```
## Install PHP
```
sudo apt install libapache2-mod-php php php-common php-xml php-gd php-opcache php-mbstring php-tokenizer php-json php-bcmath php-zip unzip


php --version

PHP 7.4.3 (cli) (built: Nov 25 2021 23:16:22) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.3, Copyright (c), by Zend Technologies
    
```
```
cd /etc/php

etc/php$ ls
7.4

etc/php$ cd 7.4/

etc/php/7.4$ ls
apache2  cli  mods-available

etc/php/7.4$ cd apache2/

etc/php/7.4/apache2$ ls
conf.d  php.ini

/etc/php/7.4/apache2$ sudo nano php.ini

ctl w
search word      cgi.fix_  (then enter)

change word  ;cgi.fix_pathinfo=1    to    cgi.fix_pathinfo=0

ctl x and y  to save and exit : then press enter to back

systemctl restart apache2
enter your password
```
## Install Composer

```

curl -sS https://getcomposer.org/installer | php

sudo mv composer.phar /usr/local/bin/composer

composer global require laravel/installer

sudo nano ~/.bashrc

end of file add

export PATH="$HOME/.config/composer/vendor/bin:$PATH"
```
# Create an App
```
laravel new myapp

sudo chgrp -R www-data /home/username/myapp

sudo chmod -R 775 /home/username/myapp/storage

cd /etc/apache2/sites-available/

/etc/apache2/sites-available$ ls
000-default.conf  default-ssl.conf

etc/apache2/sites-available$ sudo nano myapp.com.conf

paste the flowing code in myapp.com.conf

<VirtualHost *:80>
    ServerName myapp.com

    ServerAdmin admin@myapp.com
    DocumentRoot /home/ubuntu/myapp/public

    <Directory /home/ubuntu/myapp>
    Options Indexes MultiViews
    AllowOverride None
    Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

sudo a2enmod rewrite

systemctl restart apache2

sudo a2ensite myapp.com.conf

systemctl restart apache2

sudo nano /etc/hosts

paste the flowing code in hosts

127.0.0.1       myapp.com

then open your browser and search myapp.com

```

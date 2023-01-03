## Install PHP and Laravel on Ubuntu 20.04:

### Step 1: Install Apache2:
``` 
sudo apt update && sudo apt install apache2

```
##### For chcek apache2 status
###### press "q" for exit:
```
systemctl status apache2

```

##### type your browser
```
localhost

```
### Step 2: Install MysSQL Server:

```
sudo apt install mysql-server && sudo systemctl start mysql.service && sudo mysql
```
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
exit
```
```
sudo mysql_secure_installation
```
###### passwoard is "password"
##### Press Following command:

###### Change the password for root ? ((Press y|Y for Yes, any other key for No) : N
###### Remove anonymous users? (Press y|Y for Yes, any other key for No) : Y
###### Disallow root login remotely? (Press y|Y for Yes, any other key for No) : Y
###### Remove test database and access to it? (Press y|Y for Yes, any other key for No) : Y
###### Reload privilege tables now? (Press y|Y for Yes, any other key for No) : Y
###### All done!


###### Next time you can login "via mysql -u root -p" Instead of sudo mysql:
```
mysql -u root -p

```
### Step 3: Install PHP on Ubuntu 22.04:
###### Add reposotory
```
sudo apt install software-properties-common && sudo add-apt-repository ppa:ondrej/php && sudo apt update
```
```
php --version
```
###### php-extensions
```
sudo apt install php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-redis php8.1-intl -y
```
##### edit php8 library (Optional)
```
sudo nano /etc/php/8.1/apache2/php.ini
```
###### Hit F6 for search inside the editor and update the following values for better performance.
```
upload_max_filesize = 32M 
post_max_size = 48M 
memory_limit = 256M 
max_execution_time = 600 
max_input_vars = 3000 
max_input_time = 1000
```

###### Restart the apache2:
```
systemctl restart apache2

```


### Or Install PHP on Ubuntu 20.04:
```
sudo apt-get install -y php7.4 php7.4-cli php7.4-json php7.4-common php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php7.4-bcmath
```
```
php --version

```
###### Enable Php7 library
```
sudo nano /etc/php/7.4/apache2/php.ini


```
###### Press ctl+w for search word  >  cgi.fix_  (then enter)

###### change word  ;cgi.fix_pathinfo=1    to    cgi.fix_pathinfo=0

###### ctl+x and y  to save and exit : then press enter to back

##### Restart the apache2:
```
systemctl restart apache2

```


### Step 4: Install Composer:

```
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
composer global require laravel/installer
composer --version

```
###### Set Composer Path
```
sudo nano ~/.bashrc

```
###### Add this code End of file

```
export PATH="$HOME/.config/composer/vendor/bin:$PATH"
```
###### The type in the terminal
```
source ~/.bashrc
echo $PATH
```
### Step 5: Create New Laravel Project in your home diroctory
```
laravel new laravelapp
```
###### or

```
composer create-project --prefer-dist laravel/laravel laravelapp
```

##### Change the ownership permission of the Laravel directory: (Optional)

```
sudo chgrp -R www-data /home/username/laravelapp
```
```
sudo chmod -R 775 /home/username/laravelapp/storage
```

## Change to Domain name
```
cd /etc/apache2/sites-available
sudo nano laravelapp.com.conf
```
###### paste the flowing code in myapp.com.conf

```
<VirtualHost *:80>
    ServerName laravelapp.com

    ServerAdmin admin@laravelapp.com
    DocumentRoot /home/username/laravelapp/public

    <Directory /home/username/laravelapp>
    Options Indexes MultiViews
    AllowOverride None
    Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
###### Then Paste The following command:
```
sudo a2enmod rewrite
systemctl restart apache2

```
```
sudo a2ensite laravelapp.com.conf
```
```
systemctl restart apache2

```
###### paste the flowing code in hosts
```
sudo nano /etc/hosts

```
```
127.0.0.1       laravelapp.com
```
###### then open your browser and search myapp.com

#### You can change php version by following command (Optional)
```
sudo a2dismod php8.1
sudo a2enmod php7.4
```
```
sudo service apache2 restart
```
###### E n d

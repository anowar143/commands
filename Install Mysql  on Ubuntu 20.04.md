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

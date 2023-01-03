## Apache2 Uninstall

```
sudo service apache2 stop && sudo apt-get purge apache2 apache2-utils apache2.2-bin && sudo apt-get autoremove && whereis apache2 && sudo rm -rf /etc/apache2
```

## Mysql Uninstall

```
sudo systemctl stop mysql && sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-* && sudo rm -rf /etc/mysql /var/lib/mysql && sudo apt autoremove && sudo apt autoclean && sudo rm /etc/apparmor.d/abstractions/mysql
```


## PHP Uninstall

```
sudo apt-get purge php7.* && sudo apt-get autoclean && sudo apt-get autoremove
```

## Larave Uninstall

```
sudo apt-get purge --auto-remove composer && sudo rm -r ~/.cache/composer && sudo rm -r ~/.config/composer && sudo rm -r ~/.local/share/composer && sudo rm /usr/local/bin/composer
```

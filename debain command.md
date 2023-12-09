## Terminal Shortcut
```
Terminal
gnome-terminal
ctl+alt+t

```

## Permission root
```
su root
Password:

nano /etc/sudoers

# User privilege specification
root	ALL=(ALL:ALL) ALL
ttbangla  ALL=(ALL:ALL) ALL   # Addd this line

usermod -aG sudo ttbangla #ttbangla is username

exit

```

### Disable update Problem
```
apt-cdrom error

nano /etc/apt/sources.list

add #commented cdrom line

deb cdrom:[Debian GNU/Linux 12.2.0 _Bookworm_ - Official amd64 DVD Binary-1 wi>


```
###  Minimize window option show

```
$ gsettings set org.gnome.desktop.wm.preferences button-layout ":minimize,maximize,close"


```
### Show Bangla language

```
Found the problem that was causing this issue. I removed FreeSansand FreeSerif family fonts and the issue was fixed.

```
#### Solution:

####install required fonts

```
sudo apt-get install fonts-noto-core
sudo apt-get install fonts-noto-ui-core

```
#### remove the conflicting fonts

```
sudo rm -f /usr/share/fonts/truetype/freefont/FreeSans*
sudo rm -f /usr/share/fonts/truetype/freefont/FreeSerif*

```
#### update font cache

```
fc-cache -f -v

```



 ### Change System Language
 
```
su -
 
apt -y install task-bengali
 
localectl
 
nano /etc/locale.gen
 
```
 #### #comment out
 
```
 bn_Bn.UTF-8

save&exit
 
```

```
locale-gen
 
localectl list-locales
 
localectl set-locale LANG=bn_BD.UTF-8 LANGUAGE="bn_BD:bn"

```
 
 

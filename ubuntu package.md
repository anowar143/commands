## Install any downloaded package

```
sudo apt install ./package-name
```

## Upgrade stop specific package

```
sudo apt-mark hold firefox
sudo apt-mark unhold firefox
sudo apt-mark showhold
```

## Sound increes decrease
     
```
pactl -- set-sink-volume 0 -10%
pactl -- set-sink-volume 0 150%
```

## Table Plus
       

#### Add TablePlus gpg key
```
wget -O - -q http://deb.tableplus.com/apt.tableplus.com.gpg.key | sudo apt-key add - 
```
#### Add TablePlus repo

```
sudo add-apt-repository "deb [arch=amd64] https://deb.tableplus.com/debian tableplus main"
```
#### Install
```
sudo apt update
sudo apt install tableplus
```

## Postman

#### Once you download Postman in your system. Go to the Download folde

```
cd Downloads/
tar -xzf Postman-linux-x64-VERSION-NAME.tar.gz
sudo rm -rf /opt/Postman
sudo mv Postman /opt
sudo ln -s /opt/Postman/Postman /usr/local/bin/postman
postman
```

#### Create a desktop file for Postman App
```
sudo gedit /usr/share/applications/postman.desktop
```
#### Add following lines
```
[Desktop Entry]
Type=Application
Name=Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Exec="/opt/Postman/Postman"
Comment=Postman GUI
Categories=Development;Code;
BashCopy
```

#### After adding the above lines don’t forget to save it. Next, you can search the application from your app dash.

## Unijoy


```
sudo apt-get install ibus-m17n m17n-db ibus-gtk m17n-contrib

If you see an error above command, run following

sudo apt-get install ibus-m17n m17n-db ibus-gtk
sudo dpkg -L m17n-db | grep unijoy
ibus-daemon -xdr
```

### Next
```
Now open up Settings, and navigate to Region & Language

Click on the “+” Button in the Input Sources Section.

Click on the three dots. And scroll the list at the bottom.

Now Click on the “Other” button

Now Select “Bengla (unijoy (m17n))” And click “Add”.

Now open any text editor, and in the keyboard, type “super+space”
```
## Install MPV Player
```
sudo apt install mpv
```
## Install Appimagelancher
```
sudo add-apt-repository ppa:appimagelauncher-team/stable && sudo apt-get install appimagelauncher
```
#### Check
```
pycharm appimage
```
#### Permission to app
```
chmod +x ./PyCharm-Community.AppImage ./PyCharm-Community.AppImage
```
## Resulation size change
```
xrandr
cvt 1920 1080
xrandr --newmode "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
xrandr --addmode VGA-1 "1920x1080_60.00"
```

## To restart an audio driver:
```
pulseaudio -k && sudo alsa force-reload
pactl -- set-sink-volume 0 125%
```




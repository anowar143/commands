# Install Bijoy Ekushe 


#### sudo apt-get install ibus-m17n
#### sudo chmod 777 /usr/share/m17n/
#### sudo chmod 777 /usr/share/m17n/icons/
#### Download Bijoy Ekushe.zip and unzip file
#### cd ~/Download unzip folder/ 

#### mv bn-bijoyClassic.mim /usr/share/m17n/
#### mv bn-bijoyUnicode.mim /usr/share/m17n/
#### mv bn-bijoyClassic.png /usr/share/m17n/icons/
#### mv bn-bijoyUnicode.png /usr/share/m17n/icons/
#### sudo chmod 777 /var/lib/dpkg/info/m17n-db.list



#                        Next

#### gedit /var/lib/dpkg/info/m17n-db.list
#### and put the following code 

#### /usr/share/m17n/icons/bn-bijoyClassic.png
#### /usr/share/m17n/icons/bn-bijoyUniconde.png
#### /usr/share/m17n/bn-bijoyClassic.mim
#### /usr/share/m17n/bn-bijoyUniconde.mim



#                       Next

#### Ubuntu : go to Activitis, searching for the "Startup Applications" and open it.
#### In the pop box Click on "Add" and fill the empty according to the below.

#### Name: IBus Daemon
#### Command:/usr/bin/ibus-daemon -d
#### Comment: Start IBus daemon when Gnome starts
#### Restart your System


#                         Next

#### cd ~/Download unzip folder/
#### install SutonnyMJ-Bold.ttf, SutonnyMJ-Bolditalic.ttf, SutonnyMJ-Italic.ttf, SutonnyMJ-Regular.ttf


#                         Next

#### Your system   Setting > Region & Language > Input Sources
####  +  -  here click to '+'  search Bangla/bijoyUnicode(m17n)  to add
####  +  -  here click to '+'  search Bangla/bijoyClassic(m17n)  to add


### Complete Installations

#install any downloaded package

####sudo apt install ./package-name


#upgrade stop specific package

####sudo apt-mark hold firefox
####sudo apt-mark unhold firefox
####sudo apt-mark showhold


#sound increes decrease
     
####pactl -- set-sink-volume 0 -10%
####pactl -- set-sink-volume 0 150%


#table Plus
       
####Add TablePlus gpg key
####wget -O - -q http://deb.tableplus.com/apt.tableplus.com.gpg.key | sudo apt-key add - 

####Add TablePlus repo
####sudo add-apt-repository "deb [arch=amd64] https://deb.tableplus.com/debian tableplus main"

####Install
####sudo apt update
####sudo apt install tableplus


      postman

sudo snap install postman






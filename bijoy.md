# Two way Install bangla keyboard

### One Unijoy Second Bijoy They are same
##### Unijoy is best for linux, ok I,m going to show 2 method install Unijoy or Bijoy 


## Method 1 Install Unijoy
##### In Terminal ([Ctrl] + [Alt] + T) run following command:

```
sudo apt install ibus-m17n m17n-db ibus-gtk
```
##### Check if Unijoy is installed using the below command:

```
sudo dpkg -L m17n-db | grep unijoy
```
Now type and enter the following command:

```
ibus-daemon -xdr
```

#####
Update: Ubuntu 20.04 LTS

```
    Open “Settings“, then,
    Click “Region & Language“
    Click “+” sign
    Click “three dot“, then “Other” and then Click“ “ then Bangla“ “Bengali (unijoy (m17n))“
    Finally Click “Add“

Use [super] + [space] to change keyboard layout.
```

#### Restart the system

##### Go to Setting/Keyboard/Input/Bangla/Bangla(bn-unijoy(m17)) Add


##### এখন যেকোন প্রোগ্রাম থেকেই ctrl + space bar চাপ দিয়ে বাংলা লেখা শুরু করতে পারবেন। লেখার শুরুতেই টাস্কবারে কি-বোর্ড এর মত একটি আইকন দেখতে পাবেন যেখানে Bangla(bn-unijoy(m17)) কথাটি লেখা আছে। এটিতে ক্লিক করেও কি-বোর্ড পরিবর্তন করতে পারবেন।

```


```

## Method  2 Install Bijoy
### Step 1

```
sudo apt-get install ibus-m17n
sudo chmod 777 /usr/share/m17n/
sudo chmod 777 /usr/share/m17n/icons/
```
### Download & Unzip folder
##### https://drive.google.com/file/d/1mWaUlA1AH5LXsTxv553z8UK9hIS-UDTF/edit


### Step 2

#### Open Terminal in Unziped folder then type following command:

```
mv bn-bijoyClassic.mim /usr/share/m17n/
mv bn-bijoyUnicode.mim /usr/share/m17n/
mv bn-bijoyClassic.png /usr/share/m17n/icons/
mv bn-bijoyUnicode.png /usr/share/m17n/icons/
sudo chmod 777 /var/lib/dpkg/info/m17n-db.list
```


### Step 3

#### nano /var/lib/dpkg/info/m17n-db.list
##### and put the following code 

```
/usr/share/m17n/icons/bn-bijoyClassic.png
/usr/share/m17n/icons/bn-bijoyUniconde.png
/usr/share/m17n/bn-bijoyClassic.mim
/usr/share/m17n/bn-bijoyUniconde.mim
```


### Step 4

#### Ubuntu : go to "Startup Applications" and open it.
##### In the pop box Click on "Add" and fill the empty according to the below.

```
Name: IBus Daemon
Command:/usr/bin/ibus-daemon -d
Comment: Start IBus daemon when Gnome starts
Restart your System
```

### Step 5

```
cd ~/Download unzip folder/
install SutonnyMJ-Bold.ttf, SutonnyMJ-Bolditalic.ttf, SutonnyMJ-Italic.ttf, SutonnyMJ-Regular.ttf
```

### Step 6

```
Setting > Region & Language > Input Sources
+  -  here click to '+'  search Bangla/bijoyUnicode(m17n)  to add
+  -  here click to '+'  search Bangla/bijoyClassic(m17n)  to add
```

### Complete Installations

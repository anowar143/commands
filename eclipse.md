# Install Java with Eclipse

### Install Java

```
sudo apt update
sudo apt install openjdk-14-jre
java --version

```

### Install Eclipse
```
wget https://download.eclipse.org/oomph/epp/2020-06/R/eclipse-inst-linux64.tar.gz
sudo tar -xf eclipse-inst-linux64.tar.gz -C /opt
cd /opt/eclipse-installer
./eclipse-inst
```

```
1. choose "Eclipse IDE for Java Developers"
2. select java-14-openjdk
2. select installation folder "opt/
4. then click on install icon
```
### shortcut to launch your IDE. Using your favorite editor to create a file named 'eclipse.desktop' and enter the following lines to it:

```
[Desktop Entry]
Name=Eclipse
Type=Application
Exec=/opt/eclipse/eclipse
Terminal=false
Icon=/opt/eclipse/icon.xpm
Comment=Integrated Development Environment
NoDisplay=false
Categories=Development;IDE;
Name[en]=Eclipse
Name[en_US]=Eclipse
```
### open terminal in eclipse.desktop folder and run command

```
which eclipse

```
### Now, let's enable the launcher icon:

```
sudo chmod +x eclipse.desktop
sudo mv eclipse.desktop /usr/share/applications/eclipse.desktop
```

```
if need give permisson to user
sudo chmod -R 777 /root
```

##### then Eclipse packages window appears, let's choose your favorite package IDE.

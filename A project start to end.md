# Virtualenvwrapper Installing
```
sudo apt-get install python3-pip

sudo pip3 install virtualenv

sudo pip3 install virtualenvwrapper

mkdir ~/.virtualenv

export WORKON_HOME=~/.virtualenv
```

# Virtualenvwrapper settings:

#### Add the following lines to ~/.bashrc:
```
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME="/home/username/projects"
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
source /usr/local/bin/virtualenvwrapper.sh
```
# Create project and run virtualenvwrapper
```
mkproject my_project

workon my_project
```




#docker  

```
sudo apt update
sudo apt upgrade
sudo apt install docker.io
sudo systemctl enable --now docker
sudo groupadd docker
newgrp docker
sudo usermod -aG docker $USER
docker --version
docker run hello-world
Reboot if still got error
reboot
```

#docker-compose
      
```
sudo apt update
sudo apt upgrade
sudo apt install curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo chmod 755 -R .
docker–compose –version



#Start project

##Step 1

```
workon my_project
Install requirements txt
pip install -r requirements.txt

##Step 2

```
mkdir src
cd src
django-admin startproject name .
./manage.py runserver
```

##Step 3 project run with docker

####create nesesary files

```
.gitignore
.editorconfig
Dockerfile
docker-compose.yml
.env
requirements.txt



##Step 4

####Add/Change in settings.py

```
import os, SECRET_KET, DEBUG, DATABASES, ALLOWED HOST ['*'], 
```
##Installation
```
docker-compose up --build
```
##check project
```
http://localhost:8099/
```
##Run commands
```
docker-compose exec app bash
cd src
./manage.py makemigrations
./manage.py migrate
```


##Step 5 create custom user

```
django-admin startapp user
edit Model.py
Add in settings: AUTH_USER_MODEL = 'user.User'
python manage.py migrate admin zero
python manage.py migrate auth zero
python manage.py migrate contenttypes zero
python manage.py migrate sessions zero 
docker-compose down
docker-compose up --build
Afterwards, you can run makemigrations accounts and migrate accounts.
```












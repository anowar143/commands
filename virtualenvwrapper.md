# Virtualenvwrapper Installing


#### sudo apt-get install python3-pip

#### sudo pip3 install virtualenvwrapper

#### mkdir ~/.virtualenvs

#### export WORKON_HOME=~/.virtualenvs






# Virtualenvwrapper settings:


#### Add the following lines to ~/.bashrc:


#### export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
#### export WORKON_HOME=$HOME/.virtualenvs
#### export PROJECT_HOME="/home/ma/Projects"
#### source /usr/local/bin/virtualenvwrapper.sh




# Create project and run virtualenvwrapper

 
#### mkproject my_project

#### workon my_project

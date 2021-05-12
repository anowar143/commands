# Virtualenvwrapper Installing

#### sudo apt-get install python3-pip

#### sudo pip3 install virtualenv

#### sudo pip3 install virtualenvwrapper

#### mkdir ~/.virtualenv

#### export WORKON_HOME=~/.virtualenv

# Virtualenvwrapper settings:

#### Add the following lines to ~/.bashrc:

#### export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
#### export WORKON_HOME=$HOME/.virtualenvs
#### export PROJECT_HOME="/home/username/projects"
#### export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
#### source /usr/local/bin/virtualenvwrapper.sh

# Create project and run virtualenvwrapper

#### mkproject my_project

#### workon my_project


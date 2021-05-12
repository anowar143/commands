# Install using archves.

```
from download folder to /opt/ folder extra pycharm file

sudo tar xfz pycharm.tar.gz -C /opt/
```
### For run

```
cd /opt/pycharm/bin
sh pycharm.sh
```



# After run Pycharm

```
1 Starting PyCharm.
2 From the Tools menu, select "Create Desktop Entry..."
3 Tick the corresponding box if you want the launcher for all users.
4 If you selected "Create entry for all users", you will be asked for your password.
5 A green message bubble should appear informing you that it was successful.
6 You should then be able to find PyCharm in the Unity Dash or pin it to the launcher.
```



# Pycharm run from anywhere in terminal 

```
export PATH="/opt/pycharm/bin:$PATH"
pycharm.sh
```




# Pycharm  root privileges.

```
sudo chown -R $(whoami) .
```

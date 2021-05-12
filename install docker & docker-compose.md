# docker  

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

# docker-compose
      
```
sudo apt update
sudo apt upgrade
sudo apt install curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo chmod 755 -R .
docker–compose –version

```

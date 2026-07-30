

To Install sonarqube or jenkins go to doc

```bash
docker run -itd --name sonarqube-server -p 9000:9000 sonarqube:lts-community

# first delete 

docker rm -f sonarqube-server

# give access

sudo sysctl -w vm.max_map_count=262144

docker run -itd --name sonarqube-server \
  --restart unless-stopped \
  -p 9000:9000 \
  --ulimit nofile=131072:131072 \
  --ulimit nproc=8192:8192 \
  sonarqube:lts-community

  sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
echo '/swapfile swap swap defaults 0 0' | sudo tee -a /etc/fstab

free -h

sudo dmesg -T | grep -i "killed process"


docker restart sonarqube-server
docker logs -f sonarqube-server


```



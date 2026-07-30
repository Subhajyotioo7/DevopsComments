

To Install sonarqube or jenkins go to doc

```bash

sudo apt update
sudo apt install fontconfig openjdk-21-jre
java -version

sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins

sudo systemctl start jenkins

sudo systemctl status jenkins


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



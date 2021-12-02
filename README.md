# Jenkins-
Installation
Kiki, [12/10/2021 11:36 PM]
#!/bin/bash
# Run this as a script
# create an ubuntu-18.04 ec2 instance in aws
sudo hostname docker
sudo apt update -y
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu 

# Install java as jenkins dependency
sudo apt install openjdk-11-jdk -y
# install jenkis in ubuntu:
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins -y
sudo systemctl start jenkins 
sudo usermod -aG docker jenkins 
echo "jenkins  ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/jenkins 
docker --version
sudo su - jenkins

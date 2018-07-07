## Installing Docker

To install Docker CE on Raspbian Jessie/Stretch:

```bash
# Install some required packages first
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install -y \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     python3-pip \
     software-properties-common

# Get the Docker signing key for packages
curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID_LIKE")/gpg | sudo apt-key add -

# Add the Docker official repos
echo "deb [arch=armhf] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID_LIKE") $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list

# Install Docker
sudo apt-get update
sudo apt-get install -y docker-ce

# Instakk Docker Compose
sudo pip3 install setuptools wheel
sudo pip3 install docker-compose

# bash completition for docker-compose
sudo mkdir /etc/bash_completion.d
sudo curl -L https://raw.githubusercontent.com/docker/compose/1.21.2/contrib/completion/bash/docker-compose -o /etc/bash_completion.d/docker-compose

# Start docker service
sudo systemctl enable docker
sudo systemctl start docker

# optional: run a test image
sudo docker run --rm arm32v7/hello-world
```

[link to Original Instructions](https://withblue.ink/2017/12/31/yes-you-can-run-docker-on-raspbian.html), thanks to _Alessandro Segala_.
